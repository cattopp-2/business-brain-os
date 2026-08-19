# Business Brain OS — Build Day Setup Guide

Step-by-step walkthrough for installing and configuring the system for a new client. Do this on the build day with the client's onboarding intake already completed.

---

## Before you start

- [ ] ONBOARDING-INTAKE.md is complete (or as complete as possible)
- [ ] Client has Claude Code installed and signed in on their machine
- [ ] Client has a GitHub account (free at github.com)
- [ ] Client has GitHub Desktop installed (desktop.github.com)
- [ ] You have added the client as a collaborator on the private `business-brain-os` GitHub repo

---

## Step 1 — Clone the repo to the client's machine

On the client's machine, open GitHub Desktop.

File → Clone Repository → find `business-brain-os` → choose where to save it.

Rename the cloned folder:
```
[Client First Name] AI Hub/
```
or
```
[Brand Name] — AI Hub/
```

Open Claude Code and point it at this folder.

**Why GitHub and not just copying the folder:** When you improve a skill or fix something in the master template, the client gets the update by clicking "Pull origin" in GitHub Desktop. No manual file copying.

**What's excluded from the repo (.gitignore):** `.claude/settings.json` — this file contains their API key and is never uploaded to GitHub.

---

## Step 2 — Populate the context files

Work through the ONBOARDING-INTAKE.md responses and fill in:

**`context/USER.md`**
- Name, email, primary brand, website URL
- What they're building
- Technical level and communication style

**`context/ceo-north-star.md`**
- Why the business exists (their real reason)
- Their 3-year vision
- Who they work with (and who they don't)
- Their confirmed offers with prices
- Their 90-day priorities

**`context/revenue-tracker.md`**
- Annual and monthly income target
- Current confirmed income
- Active clients and pipeline

**`context/rhythm.md`**
- Customise the daily and weekly checks for their situation
- Remove anything that doesn't apply (e.g. if they don't have a blog, remove the blog pipeline section)

---

## Step 4 — Populate brand-context

**`brand-context/writing-examples.md`**
Paste their 5–10 writing examples from the intake doc.

**Then run `mkt-brand-voice` to generate `brand-context/voice-profile.md` automatically from those examples.**

**`brand-context/icp.md`**
Fill in from the intake doc — especially the real customer quotes. These are the most important part.

**`brand-context/audience-language-[topic].md`**
Create one file per offer area. Copy `audience-language-template.md` and rename it.
Add real customer quotes from DMs, testimonials, and intake forms.

---

## Step 5 — Create offer files

For each offer in their business:
1. Copy `offers/offer-template.md`
2. Rename it `offers/offer-[slug].md`
3. Fill it in from the intake doc

---

## Step 6 — Connect MCPs (optional but recommended)

**Airtable** (for content tracking):
- Set up their Airtable base using the standard content tracking template
- Update the base ID and table IDs in `CLAUDE.md` under "Saving Content to Airtable as a Draft"

**Google Drive** (for long-form content):
- Connect via MCP if they use Google Docs for blog drafts

**WordPress** (for publishing):
- Update WP URL and credentials in `.claude/settings.json` env section

---

## Step 7 — Test the system

Run a quick content piece to verify everything is connected:

1. Start a new Claude Code session in the client's folder
2. Claude should read the context files at session start
3. Run: `/content-router`
4. Type a test idea from their business
5. Pick a format (e.g. Facebook post)
6. Check the output — does it sound like them? Does it reference their offer correctly?

If the voice is off, the writing examples need more variety or the voice profile needs adjusting.

---

## Step 8 — Walk the client through day-one use

Show them:
- How to start a session (open Claude Code, point it at their folder)
- How to use `/content-router` to create any piece of content
- Where files get saved
- How to use `/end-of-day` to close a session properly
- What `context/tomorrow.md` is for

---

## Done

The system is live. Leave them with:
- This folder on their machine
- Access to Claude Code (their subscription)
- A recording of the walkthrough (optional but useful)
