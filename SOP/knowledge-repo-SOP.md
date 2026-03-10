# Knowledge Repo SOP
## Rejoin Coaching — Daily Operating Procedure
**Owner:** Michael Gardon
**Last Updated:** March 2026

---

## The Three-Layer System

| Layer | What It Is | Sync Required |
|-------|-----------|---------------|
| **GitHub** | Source of truth. All files backed up here. | Always push changes here |
| **Local Machine** | Where Claude Code runs. Live access to full repo. | Pull before each session |
| **Claude.ai Project** | Quick access on mobile/web. Governance files only. | Manual — update when locked files change |

---

## One-Time Setup (First Time Only)

```bash
# 1. Clone the repo to your machine
git clone https://github.com/your-repo/rejoin-knowledge

# 2. Navigate into it
cd rejoin-knowledge

# 3. Confirm Claude Code is installed
claude --version
```

Do this once. Never reclone unless starting on a new machine.

---

## Daily Workflow

### Starting a Session

```bash
cd rejoin-knowledge
git pull
claude
```

That's it. Claude Code now has full context of every file in the repo.

### Ending a Session (After Making Changes)

```bash
git add .
git commit -m "brief description of what changed"
git push
```

Always push before closing. GitHub is your backup.

---

## Editing Files

### Primary Rule
**Pick one editing location and stick to it.**

**Recommended: Edit locally** (in Cursor, VS Code, or any text editor), then push to GitHub.

Avoid editing directly in GitHub's web editor unless you're making a quick single-line fix — mixing both creates conflicts.

### If You Edit in GitHub Web Editor
Always pull before your next local session:
```bash
git pull
```

---

## Claude.ai Project — What Lives There

Only upload files that are **locked and rarely change:**

- `CLAUDE.md`
- `02-brand/brand-standards.md`
- `02-brand/voice-signature.md`
- `03-frameworks/` (all framework files)
- `00-foundation/company-thesis.md`
- `00-foundation/ideal-customer.md`

**Do not upload:** Sales scripts, content drafts, session notes, research files — these change too often.

### When to Re-upload to Claude.ai Project
Only when a locked file above gets updated. After updating:
1. Open Claude.ai Project
2. Delete the old file version
3. Upload the new one

---

## Adding New Files to the Repo

```bash
# 1. Create the file in the right folder
# (follow folder structure in REPO-ARCHITECTURE.md)

# 2. Add, commit, push
git add .
git commit -m "added [filename] to [folder]"
git push
```

---

## Troubleshooting

**Conflict error on pull:**
```bash
git status          # see what's conflicting
git stash           # temporarily shelve local changes
git pull            # get latest from GitHub
git stash pop       # reapply your local changes
```

**Forgot to pull before editing:**
Same as above — stash, pull, pop.

**Claude Code doesn't seem to know a file:**
Confirm the file is saved locally and you ran `git pull` before starting the session.

---

## Quick Reference Card

| Action | Command |
|--------|---------|
| Start session | `cd rejoin-knowledge && git pull && claude` |
| Save changes | `git add . && git commit -m "msg" && git push` |
| Check status | `git status` |
| See recent changes | `git log --oneline -10` |

---

## Rules

1. Always `git pull` before starting Claude Code
2. Always `git push` after making changes
3. Never edit the same file locally AND in GitHub web on the same day
4. `CLAUDE.md` and `03-frameworks/` are locked — changes require deliberate decision
5. Claude.ai Project files are manually synced — check quarterly
