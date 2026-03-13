# Upstream Diagnostic — Go Live Guide

## What you're deploying

| Piece | Where | Time |
|---|---|---|
| API proxy | Vercel (free) | 15 min |
| Chatbot page | GHL funnel | 10 min |
| GHL workflow | GHL automation | 20 min |
| Test end to end | — | 10 min |

---

## Step 1 — Deploy the API Proxy to Vercel

The proxy hides your Claude API key from the browser.

**1a. Create a free Vercel account**
→ vercel.com — sign up with GitHub

**1b. Create a GitHub repo**
- New repo: `upstream-proxy` (private)
- Upload both files from the `vercel-proxy/` folder:
  - `api/claude.js`
  - `vercel.json`

**1c. Import to Vercel**
- vercel.com/new → Import Git Repository → select `upstream-proxy`
- Click Deploy (no config needed, Vercel auto-detects)

**1d. Add your API key as an environment variable**
- Vercel dashboard → your project → Settings → Environment Variables
- Add: `ANTHROPIC_API_KEY` = your key from console.anthropic.com
- Redeploy: Deployments tab → ⋯ → Redeploy

**1e. Copy your proxy URL**
- Looks like: `https://upstream-proxy-abc123.vercel.app`
- Your proxy endpoint is: `https://upstream-proxy-abc123.vercel.app/api/claude`

---

## Step 2 — Configure the Chatbot HTML

Open `upstream-diagnostic-final.html` in any text editor. At the top of the `<script>` block, update these two lines:

```javascript
const GHL_WEBHOOK = 'https://services.leadconnectorhq.com/hooks/YOUR_ID';
const CLAUDE_PROXY = 'https://upstream-proxy-abc123.vercel.app/api/claude';
```

Save the file.

**Lock down CORS (after testing):**
In `api/claude.js`, change:
```javascript
res.setHeader('Access-Control-Allow-Origin', '*');
```
to your GHL domain:
```javascript
res.setHeader('Access-Control-Allow-Origin', 'https://yoursite.com');
```
Then redeploy Vercel.

---

## Step 3 — Host the Chatbot on GHL

**Option A: Funnel page (recommended)**
- GHL → Funnels → New Funnel → Blank
- Add a step → Edit page
- Add element: Custom Code / HTML block
- Paste the entire contents of `upstream-diagnostic-final.html`
- Publish the funnel step

**Option B: Website page**
- GHL → Sites → Websites → your site → Add page
- Same process — Custom HTML element, paste file contents

**Test it:** Open the published URL, run through the full diagnostic, check browser console for errors.

---

## Step 4 — Set Up GHL Webhook + Workflow

**4a. Get your webhook URL**
- GHL → Automation → Workflows → New Workflow → Start from Scratch
- Trigger: Inbound Webhook
- Copy the webhook URL → paste into chatbot HTML as `GHL_WEBHOOK`

**4b. Build the workflow**

| Step | Action | Config |
|---|---|---|
| 1 | Trigger | Inbound Webhook |
| 2 | Create/Update Contact | Map: firstName, lastName, email, phone |
| 3 | Add Tag | Use `{{trigger.tags}}` or hardcode: `diagnostic-complete` |
| 4 | Wait | 1 minute (gives contact time to save) |
| 5 | Send Email | Template below |

**4c. Map custom fields**
In the Create/Update Contact step, map these webhook fields to custom fields you create in GHL (Settings → Custom Fields → Contact):

| Webhook field | GHL custom field |
|---|---|
| `customFields.priority_phase` | Priority Phase |
| `customFields.positioning_rating` | Positioning Rating |
| `customFields.package_rating` | Package Rating |
| `customFields.pipeline_rating` | Pipeline Rating |
| `customFields.infrastructure_rating` | Infrastructure Rating |
| `customFields.root_diagnosis` | Root Diagnosis |

---

## Step 5 — Email Template (Static PDF for now)

**Subject:** Your Upstream Business Diagnostic is here, {{contact.firstName}}

**Body:**
```
Hi {{contact.firstName}},

You just completed the Upstream Business Diagnostic.

Here's what we found at a glance:

• Positioning: {{contact.positioning_rating}}
• Package: {{contact.package_rating}}  
• Pipeline: {{contact.pipeline_rating}}
• Infrastructure: {{contact.infrastructure_rating}}

Your priority phase: {{contact.priority_phase}}

Your full report is attached — it breaks down each phase, what's missing, 
and what it's costing you. Read it before our next conversation.

[CTA BUTTON: Book a Call / Download the Guide]

— Michael
```

**Attach the PDF:**
- Upload `upstream_diagnostic_v3.pdf` to GHL (Media Library)
- Attach to this email template
- Note: this is a generic sample report for now — everyone gets the same PDF until automation is built

---

## Step 6 — End-to-End Test

1. Open your GHL funnel URL
2. Run through the full diagnostic with real answers
3. Confirm: contact created in GHL ✓
4. Confirm: tags applied ✓
5. Confirm: email received with PDF ✓
6. Confirm: no console errors ✓

**Common issues:**
- CORS error → check proxy URL is correct in chatbot
- Webhook not firing → check GHL webhook URL is saved in HTML
- Email not sending → check workflow is published (not draft)

---

## What's Live After This

- Prospects land on your GHL page
- Run a 5-minute diagnostic
- GHL captures contact + all scorecard data
- Email sent automatically with PDF
- You see every lead in GHL with phase ratings as tags

**When you're ready to automate the PDF:**
The `build_report.js` script generates a personalized PDF from the scorecard JSON.
Next step is a Vercel function that receives the JSON, runs the script, and returns a PDF URL for GHL to attach. Build that when you have 10+ leads and the report is validated.
