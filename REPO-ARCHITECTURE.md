# Rejoin Media — Knowledge Repository Architecture
## Claude Code Setup Guide

**Purpose:** This document defines the folder structure, file naming conventions,
and Claude Code setup for running your entire business from a single repo.

---

## HOW THIS WORKS

When you run `claude` from this repo root, Claude Code sees every file.
Your knowledge library becomes Claude's permanent context.
No uploading. No copy-pasting. No Projects.

```bash
cd ~/rejoin-knowledge
claude
```

That's the entire workflow.

---

## FOLDER STRUCTURE

```
rejoin-knowledge/
│
├── CLAUDE.md                          ← Claude Code reads this first, always
├── README.md                          ← Human-readable repo overview
│
├── 00-foundation/                     ← Who you are, who you serve (LOCKED)
│   ├── company-thesis.md
│   ├── north-star.md
│   ├── founder-story.md               ← MISSING — needs to be built
│   ├── ideal-customer.md
│   ├── icp-exact-words.md             ← MISSING — Jay's language + others
│   ├── energy-focus-profile.md
│   └── proof-repository.md
│
├── 01-offer/                          ← What you sell
│   ├── 06-offer-one-pager.md          ← Internal reference
│   ├── 07-program-curriculum.md       ← 12-week map
│   ├── offer-stack.md                 ← All offers + economics
│   └── pricing-rationale.md          ← MISSING
│
├── 02-brand/                          ← How everything looks and sounds
│   ├── brand-standards.md             ← Colors, fonts, voice, tone
│   ├── language-rules.md             ← Canonical terms, replacements
│   └── visual-identity.md            ← MISSING — screenshots + guidelines
│
├── 03-frameworks/                     ← Your IP (LOCKED)
│   ├── framework-advantage-mapping.md
│   ├── framework-audience-identity.md
│   ├── framework-autocorrected-existence.md
│   ├── framework-category-design.md
│   ├── framework-full-stack-human.md
│   ├── framework-future-self-operating-system.md
│   ├── framework-minimum-effective-offer.md
│   ├── framework-time-sovereignty.md
│   └── framework-uncopyable-positioning.md
│
├── 04-content/                        ← Content system
│   ├── content-crosswalk.md
│   ├── hook-design-guide.md
│   ├── break-desire-maps.md
│   ├── become-desire-maps.md
│   ├── build-desire-maps.md
│   ├── linkedin-operating-rules.md
│   ├── substack-notes-rules.md
│   └── youtube-role-governance.md
│
├── 05-sales/                          ← How you close
│   ├── 18-sales-conversation-guide.md
│   ├── 19-application-form.md         ← MISSING
│   ├── 20-objection-guide.md          ← MISSING (populate after 5 calls)
│   ├── 21-follow-up-sequences.md      ← MISSING
│   └── 22-dm-outreach-scripts.md      ← MISSING
│
├── 06-delivery/                       ← What happens after they pay
│   ├── 24-onboarding-sequence.md      ← MISSING
│   ├── 25-intake-form.md              ← MISSING
│   ├── 26-week-by-week-guide.md       ← MISSING
│   ├── 27-session-templates.md        ← MISSING
│   ├── 28-client-workbook.md          ← MISSING
│   ├── 29-mastermind-structure.md     ← MISSING
│   └── 31-offboarding-process.md      ← MISSING
│
├── 07-ai/                             ← How Claude operates in this system
│   ├── ai-usage-instructions.md
│   ├── content-bot-instructions.md
│   ├── claude-universal-writer-prompt.md
│   ├── session-prep-agent.md          ← MISSING
│   ├── sales-call-agent.md            ← MISSING
│   └── weekly-review-agent.md         ← MISSING
│
├── 08-operations/                     ← How you run yourself
│   ├── operating-index.md
│   ├── founder-sync-template.md
│   └── decision-log.md                ← MISSING
│
└── 09-research/                       ← Raw inputs, transcripts, notes
    ├── jay-fontanini-transcript.md
    └── [future client conversations]
```

---

## THE MOST IMPORTANT FILE: CLAUDE.md

Claude Code automatically reads `CLAUDE.md` at the root of every repo.
This is your master instruction file — it tells Claude who you are,
what system you're operating in, and how to behave.

**This file is why everything works consistently.**

See `CLAUDE.md` in this repo for the full contents.

---

## BUILD PRIORITY

### Week 1 — Get selling
These files unlock your ability to close clients now:
- [ ] Set up repo structure (copy existing files into folders)
- [ ] Write `CLAUDE.md` (use template in this repo)
- [ ] Add `05-sales/19-application-form.md`
- [ ] Add `05-sales/22-dm-outreach-scripts.md`
- [ ] Add `00-foundation/founder-story.md`

### Week 2-3 — Get delivering
These files unlock your ability to onboard and run clients:
- [ ] `06-delivery/24-onboarding-sequence.md`
- [ ] `06-delivery/25-intake-form.md`
- [ ] `06-delivery/28-client-workbook.md`
- [ ] `06-delivery/29-mastermind-structure.md`

### Month 2 — Get scaling
- [ ] `07-ai/session-prep-agent.md`
- [ ] `07-ai/sales-call-agent.md`
- [ ] `05-sales/20-objection-guide.md` (after first 5 calls)

---

## CLAUDE CODE INSTALLATION

```bash
# Install Node.js if not already installed
# https://nodejs.org

# Install Claude Code globally
npm install -g @anthropic-ai/claude-code

# Authenticate (one time)
claude login

# Navigate to your repo
cd ~/rejoin-knowledge

# Start a session
claude
```

---

## DAILY WORKFLOW

```bash
# Start your day
cd ~/rejoin-knowledge
claude

# Example prompts once inside:
# "Build a DM outreach script for a consultant like Jay"
# "Write a LinkedIn post for Break stage using the content crosswalk"
# "Prep me for a sales call with [name] — here's their background: ..."
# "Build this week's mastermind agenda"
```

---

## GITHUB SYNC

Keep GitHub as source of truth. Update files there, pull locally.

```bash
# Pull latest before every session
git pull origin main

# After updating files
git add .
git commit -m "Update [filename] — [what changed]"
git push origin main
```

---

## RULES FOR THIS REPO

1. **CLAUDE.md is sacred** — never delete, always keep updated
2. **Frameworks folder is LOCKED** — never rename or restructure frameworks
3. **Foundation folder is LOCKED** — update only at review points
4. **Raw transcripts go in 09-research/** — never in other folders
5. **Missing files get a stub** — create the file with STATUS: MISSING
   rather than leaving the folder incomplete
6. **One truth** — if something changes, update the file. Never have
   two files saying different things about the same topic.
