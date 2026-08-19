# Business Brain OS — Dry Run Checklist

Work through this as a fictitious client. The goal is to find every gap, blocker, and point of confusion before you put a real client through this.

Use a made-up business (e.g. a life coach called Sarah who sells a 1:1 programme and a group course). Don't use your own brand — you already know too much about how it works.

---

## Phase 1 — Pre-work (what the client does before the day)

This is everything that happens before they arrive. The goal is to know exactly what to send them, in what order, and how long it realistically takes.

### 1.1 Technical install
- [ ] Download and install Claude Code from scratch on a fresh machine (or a browser profile you've never used)
- [ ] Create an Anthropic account and get an API key — time how long this takes for a non-developer
- [ ] Add the API key to settings.json — is this instruction clear enough for a non-technical person?
- [ ] Open Claude Code and confirm it launches without errors

**Stress test:** What happens if they have Windows? Mac? What if they get an API key error? Write down every blocker you hit.

### 1.2 Completing the intake form
- [ ] Fill in ONBOARDING-INTAKE.md as the fictitious client — take it seriously, don't rush it
- [ ] Note any questions that are confusing or would cause a real client to stall
- [ ] Note any questions that are missing
- [ ] Time how long it realistically takes to complete

**Stress test:** What if they have no testimonials yet? What if they sell more than 3 offers? What if they don't have a WordPress site?

---

## Phase 2 — Pre-day check (what you do 2–3 days before)

- [ ] Review the completed intake as if you're seeing it for the first time
- [ ] Identify what's missing or thin
- [ ] Work out what questions you'd need to ask before the day
- [ ] Can you spot gaps that would break the setup if not caught now?

**Stress test:** What's the minimum viable intake — what can you work with vs what makes the day impossible?

---

## Phase 3 — Setup (done on the day, or by you before they arrive)

### 3.1 Copy and rename the folder
- [ ] Copy `Business Brain OS — Client Install` to a test location
- [ ] Rename it to `[Fictitious Client] AI Hub`
- [ ] Open Claude Code and point it at the new folder
- [ ] Confirm Claude reads CLAUDE.md correctly at session start

### 3.2 Populate context files
Work through each file. For each one, note: is the template clear? Is the placeholder text helpful or confusing? Does Claude use it correctly once filled in?

- [ ] `context/USER.md` — fill in from intake
- [ ] `context/ceo-north-star.md` — fill in from intake
- [ ] `context/revenue-tracker.md` — fill in from intake
- [ ] `context/rhythm.md` — customise for this client's situation
- [ ] `context/weekly-focus.md` — set 2–3 priorities for the fictitious client

**Stress test:** What if they don't know their monthly revenue target? What if they have no clear 90-day priorities yet? What if their rhythm looks nothing like yours?

### 3.3 Populate brand-context
- [ ] `brand-context/writing-examples.md` — paste the fictitious client's writing samples
- [ ] Run `mkt-brand-voice` to generate `voice-profile.md` — does it work? Is the output good?
- [ ] `brand-context/icp.md` — fill in from intake
- [ ] Create one `audience-language-[topic].md` file — is the template clear?

**Stress test:** What if their writing samples are short or thin? What if the voice profile output is generic? What if they have no customer quotes?

### 3.4 Create offer files
- [ ] Copy `offer-template.md` and create one offer file
- [ ] Fill it in for the fictitious client
- [ ] Is the template clear enough that a client could do this themselves?

### 3.5 Connect MCPs (optional)
- [ ] Test Airtable connection — does the content saving workflow work end to end?
- [ ] Test Google Drive connection if relevant
- [ ] Test WordPress publishing if relevant
- [ ] Update the base/table IDs in CLAUDE.md

**Stress test:** What if they don't use Airtable? What if they don't have WordPress? Does the system still work without MCPs?

---

## Phase 4 — First content run (the real test)

This is where you find out if the setup actually works.

- [ ] Start a fresh Claude Code session in the client folder
- [ ] Does Claude read all the context files at session start without being prompted?
- [ ] Run `/content-router` with a test idea from the fictitious client's business
- [ ] Pick Facebook post as the format
- [ ] Read the output — does it sound like the client? Does it reference their offer correctly? Is it in their voice?
- [ ] Run it again with a different format (email, LinkedIn post)
- [ ] Run `/content-ideas` with a fake transcript — does it extract usable ideas?

**Stress test:** What if the voice sounds generic? What if it gets the offer details wrong? What if it doesn't read the context files automatically?

---

## Phase 5 — Day-one client handover

Walk through what you'd show a real client at the end of the setup day.

- [ ] Can you explain how to start a session in under 2 minutes?
- [ ] Can they use `/content-router` without your help after one demo?
- [ ] Do they understand what `context/tomorrow.md` is for?
- [ ] Can they run `/end-of-day` themselves?
- [ ] Do they know where their files are saved?
- [ ] Do they know what to do if something goes wrong?

**Stress test:** What questions would a non-technical client ask that you haven't answered yet? Write them down — these become your FAQ.

---

## Phase 6 — After the day (what happens next)

- [ ] Is there a follow-up resource they can refer back to? (video walkthrough, reference guide)
- [ ] What's the support model? Email you? Community? Nothing?
- [ ] What's the natural next step — ongoing monthly, another session, self-sufficient?

---

## What to capture as you go

Keep a running notes doc alongside this checklist. For each phase, note:

**Blockers** — things that stopped or slowed you
**Gaps** — information or files that were missing
**Confusions** — anything unclear in the templates or instructions
**Time taken** — realistic time for each phase (not your time, fictitious-client time)
**Questions** — things a real client would ask that you couldn't answer

---

## Output of the dry run

By the end you should have:

1. A revised ONBOARDING-INTAKE.md with any missing questions added
2. A clear split: what's pre-work vs what's done on the day
3. A realistic time estimate for the setup day
4. A list of edge cases and how to handle them
5. A first draft FAQ for clients
6. Confidence the system works end to end for someone who isn't you
