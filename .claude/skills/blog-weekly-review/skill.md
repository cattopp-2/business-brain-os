---
name: blog-weekly-review
description: >
  Weekly blog strategy briefing. Runs on Monday mornings. Reads the Airtable pipeline,
  rank tracking CSV, and keyword queue to produce a one-page brief covering: what's in
  the pipeline and what needs attention, any significant rank movements, the next 3
  keyword candidates, and the top existing post to fix this week. On the first Monday
  of each month, runs an extended check and offers to route to seo-strategy-checker.
  Strategic only — no writing, no publishing.
---

# Blog Weekly Review

A 5-minute Monday morning brief that keeps Cathy in the strategic seat. Reads
data, surfaces what needs attention, suggests the next move. Does not write
posts or push anything to WordPress.

---

## Before starting

Read `learnings.md` in this skill's folder if it exists and apply any notes.

---

## Airtable reference

- Base: `appxFaTh8wdrUZREh`
- Table: Website Blogs (`tblln1TvIWF1pwPF7`)
- Status field: `fldbHRoeGBhby73vE`
- Title field: `fldf0HUCTavw4dfiZ`
- Primary Keyword field: `flditqxSIR9XQ56Xr`
- Notes field: `fldiS2IViMJDkafSe`
- URL field: `fld2b7yQNkD5ZbXUh`
- Link to Google Doc field: `fldvwAf8Y8gSYt5cV`

**Views:**
- `Blog Posts - to be fixed/updated`: `viwNzI2bBVzGawnIW`
- `Blog Posts - outdated/irrelevant (to do)`: `viwdtpuY0Tdks8NOo`
- `Everything`: `viwSagVmOwrwIFJIG`

---

## Monthly check trigger

Before running any steps, check today's date. If today is the first Monday of
the current month, set `IS_MONTHLY = true`. Otherwise `IS_MONTHLY = false`.

First Monday = the Monday on or before the 7th of the month.

---

## Step 1 — Pipeline snapshot

Query Airtable Website Blogs (`tblln1TvIWF1pwPF7`), view `Everything`. Read all
records. Group by Status and count:

| Status | Count | Titles |
|--------|-------|--------|
| AI draft - to be edited | n | [list titles] |
| Ready to publish | n | [list titles] |
| WP Draft | n | [list titles] |
| to be fixed/updated | n | [list titles] |

Show titles only for statuses where count > 0.

**Attention flags:**
- If "AI draft - to be edited" count ≥ 3: flag — "You have [n] drafts waiting for review. Consider editing one before writing new posts."
- If "Ready to publish" count ≥ 1: flag — "Run /blog-session to push [title] to WordPress."
- If "WP Draft" count ≥ 1: flag — "[title] is sitting as a WP Draft — ready to hit Publish?"

---

## Step 2 — Rank signal

Find the most recently modified file matching `SEO Strategy/Your Web Toolkit Rank Tracking*.csv`.

Read it. Columns: No, Position, Keyword, Change, SD, Search Volume, URL, Location.

Parse the `Change` column (may be stored as a number or string like "+5" or "-12").

Surface:
- **Drops** (Change ≤ -10): list keyword, current position, change value, URL
- **Quick wins** (Position between 11–20): list keyword, position, URL
- If nothing significant: "No major rank movements this week."

If the CSV cannot be read or has no Change column, note it and skip this step.

---

## Step 3 — Keyword queue

Read `SEO Strategy/Keyword Opportunities.csv`.
Columns: Keyword, Search Volume, Difficulty, Recommended Page Type, Priority, Added to the plan, Notes.

Filter: rows where `Added to the plan` is blank or not "yes" (case-insensitive).

Also query Airtable for records with Status in: `Idea`, `AI draft - to be edited`,
`Ready to publish`, `WP Draft`. Remove any CSV keywords that match a record's
Primary Keyword (case-insensitive) — these are already in progress.

Sort remaining rows:
1. Priority = "High" first
2. Then Search Volume descending
3. Then Difficulty ascending

Show the top 3 as candidates:

> **Next keyword candidates:**
> 1. [keyword] — Vol: [x], Difficulty: [x] [HIGH PRIORITY if applicable]
> 2. [keyword] — Vol: [x], Difficulty: [x]
> 3. [keyword] — Vol: [x], Difficulty: [x]
>
> Ready to write one? Run /blog-session and confirm the keyword there.

If fewer than 3 remain, show what's available and note the list is running low.

---

## Step 4 — Existing content queue

Read Airtable view `Blog Posts - to be fixed/updated` (`viwNzI2bBVzGawnIW`).

Show the first 2 records (title, URL, any Notes). If empty, check
`Blog Posts - outdated/irrelevant (to do)` (`viwdtpuY0Tdks8NOo`) and show the
first 2 from there instead.

If both views are empty, note: "No existing posts flagged for update."

Format:
> **Existing posts needing attention:**
> - [Title] ([URL]) — [Notes if any]

---

## Step 5 — GSC prompt

Always show this, no integration needed:

> **GSC check (manual):** Worth a quick look at Search Console for [current month]
> — anything surprising in queries or clicks this week?

---

## Step 6 — Monthly extended check (IS_MONTHLY = true only)

Skip this step if IS_MONTHLY = false.

Find the file matching `SEO Strategy/Your Web Toolkit Rank Tracking (30 days previous*.csv`
(the older snapshot). Read it.

Compare positions for published posts against the current rank tracking CSV:
- Match rows by Keyword
- Flag any where position has dropped ≥ 10 between the two snapshots

Show:
> **Monthly position comparison (vs 30 days ago):**
> - [keyword]: was [x], now [y] ([change])

Then ask:
> Want to run a full keyword strategy check this month? That'll audit the keyword
> CSV against your current offers and surface what to prioritise next. Just say yes
> and I'll route to seo-strategy-checker.

---

## Output format

Deliver the full brief as a single clean response. Use headers for each section.
No preamble. Start directly with the pipeline snapshot.

Example structure:

---

**Blog Brief — [date]**

**Pipeline**
[pipeline table + attention flags]

**Rank movements**
[drops and quick wins, or "nothing significant"]

**Keyword queue**
[top 3 candidates]

**Existing posts to fix**
[1–2 records, or "none flagged"]

**GSC**
[standing prompt]

[Monthly section if applicable]

---

End with: "That's your blog brief. Run /blog-session to action any of the above."
