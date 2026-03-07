# Rejoin Coaching — Knowledge Repository

**Owner:** Michael Gardon
**Primary Offer:** The Upstream Consultant
**Purpose:** Single source of truth for all business knowledge, brand standards, frameworks, and operating systems.

---

## What This Is

This repo is the brain of Rejoin Coaching. Every framework, offer, brand rule, sales guide, and delivery asset lives here.

When you run Claude Code from this folder, Claude has full context of your entire business — no uploading, no copy-pasting, no repeating yourself.

---

## How To Use It

```bash
# Pull latest
git pull origin main

# Start Claude with full context
cd rejoin-knowledge
claude
```

That's it. Claude reads `CLAUDE.md` automatically and knows what to do.

---

## Folder Structure

| Folder | What's In It |
|--------|-------------|
| `00-foundation/` | Who you are, who you serve — locked |
| `01-offer/` | The Upstream Consultant — offer, curriculum, pricing |
| `02-brand/` | Colors, fonts, voice, tone — locked |
| `03-frameworks/` | Canonical IP frameworks — locked |
| `04-content/` | Content system, platform rules, desire maps |
| `05-sales/` | Sales conversation, objections, outreach scripts |
| `06-delivery/` | Onboarding, sessions, workbooks, mastermind |
| `07-ai/` | Claude operating instructions and agent prompts |
| `08-operations/` | Founder operating system, weekly sync, decisions |
| `09-research/` | Client transcripts, raw inputs, ICP notes |

---

## Key Files

- **`CLAUDE.md`** — Claude Code reads this first on every session
- **`02-brand/brand-standards.md`** — governs every artifact
- **`07-ai/ai-usage-instructions.md`** — governs Claude's behavior
- **`REPO-ARCHITECTURE.md`** — full folder blueprint and build priority

---

## What's Missing

Files marked `STATUS: MISSING` are stubs — the folder slot is reserved but the content isn't built yet. See `REPO-ARCHITECTURE.md` for the full build priority list.

---

## Rules

1. `CLAUDE.md` is sacred — never delete it
2. `03-frameworks/` is locked — never rename frameworks
3. `00-foundation/` updates only at quarterly review
4. Raw transcripts go in `09-research/` only
5. One truth — if something changes, update the file
