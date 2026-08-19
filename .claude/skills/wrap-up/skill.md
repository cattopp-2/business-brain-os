---
name: wrap-up
description: >
  End-of-session wrap-up. Writes today's daily memory block, logs skill feedback to
  context/learnings.md, and proposes SOUL.md or USER.md updates if patterns were detected.
  Triggers on: "/wrap-up", "let's wrap up", "end of session", "wrap up this session".
---

# Wrap-Up Skill

## What This Skill Does

Closes the session cleanly by writing structured memory and capturing any feedback before it's forgotten. Takes 2–3 minutes. Run it at the end of every working session.

Writes to three places:
1. **`context/memory/YYYY-MM-DD.md`** — today's session block
2. **`context/learnings.md`** — any skill feedback, under the relevant skill's section
3. **`context/SOUL.md`** / **`context/USER.md`** — proposes updates if patterns or new information were detected

---

## Step 1 — Read today's file

Check if `context/memory/[today's date].md` exists.
- If yes, read it — there may already be session blocks from earlier today. Append a new block.
- If no, create the file.

Today's date format: YYYY-MM-DD

---

## Step 2 — Derive session information from the conversation

Do not ask questions. Read the conversation and extract:

- **Goal** — what was Cathy trying to accomplish?
- **Deliverables** — what was produced? Include file paths where known.
- **Decisions** — any choices made and the reasoning behind them.
- **Open threads** — anything unfinished, flagged, or deferred to next session.

---

## Step 3 — Derive skill feedback from the conversation

Do not ask questions. Scan the conversation for:
- Corrections to skill output ("don't use this phrasing", "I don't like this")
- Format changes requested ("no character counts", "remove the numbering")
- Anything already saved to a skill's learnings.md during the session

Compile the list. If nothing was flagged, skip to Step 4.

---

## Step 4 — Write the daily memory block

Write a new session block to `context/memory/[today's date].md` using this format:

```
## Session [N]

**Goal:** [what they set out to do]

**Deliverables:**
- [item with file path]
- [item with file path]

**Decisions:**
- [decision — reasoning]

**Open threads:**
- [anything unfinished]
```

If this is the first session today, N = 1. If a block already exists, increment N.

---

## Step 5 — Update learnings

For each piece of skill feedback gathered in Step 3:

1. Read `context/learnings.md`
2. Find the section for that skill
3. Append an entry in this format:
   > [YYYY-MM-DD] — [what the issue was and how the skill should handle it differently]
4. Replace "No learnings yet." if it was the first entry

Write the updated file.

---

## Step 5b — Direct skill fixes

For each piece of feedback, assess whether it points to a structural problem in the skill itself — not just an observation, but something that would cause the same mistake every time.

Signs it needs a direct fix:
- A step is missing (e.g. "it never asks for the CTA")
- The output format is wrong (e.g. "it shouldn't use bullet points here")
- A default assumption is broken (e.g. "it always assumes UK audience but this skill is for global")
- An instruction is ambiguous and caused confusion

If a direct fix is warranted:
1. Read the skill file at `.claude/skills/[skill-name]/skill.md`
2. Identify the exact section that needs changing
3. Show Cathy: the current text, the proposed replacement, and one sentence on why
4. Wait for approval
5. On approval: edit the skill file directly

If feedback is a general note or preference rather than a structural problem, log it to learnings only (Step 5) — do not propose a skill edit.

---

## Step 5c — Add rules for hard constraints

For each piece of feedback, assess whether it is a hard constraint — something that must always or never happen in that skill's output, regardless of context.

Signs it's a rule (not just a learning or direct fix):
- Absolute language: "never", "always", "every time", "not allowed"
- A constraint that applies to all runs of that skill, not just this one
- Something that would be wrong even if the methodology was followed correctly

Examples of rules:
- "Facebook posts must never end with a question"
- "Sales pages must always include the price before the CTA"
- "Email subjects must never use all-caps"

If a rule is warranted:
1. Read the skill file at `.claude/skills/[skill-name]/skill.md`
2. Check if a `## Rules` section already exists
3. If yes: append a new dated entry in this format:
   > [YYYY-MM-DD]: [the constraint, written as a clear instruction]
4. If no: add a `## Rules` section at the end of the file with the first entry
5. No approval needed for rule additions — these come directly from Cathy's feedback

If feedback is a general preference rather than a hard constraint, log it to learnings only (Step 5) — do not add a rule.

---

## Step 6 — Check for SOUL.md updates

Scan the session conversation for corrections made to Claude's behaviour. Look for: instructions given more than once, corrections to tone, structure, or approach, anything prefixed with "no," "don't," "stop," or "actually."

If the same type of correction appeared 2+ times, propose a specific update to SOUL.md. Show:
- The current rule (or confirm there isn't one)
- The proposed addition or change
- Why (based on what was corrected)

Wait for approval before editing SOUL.md.

If no patterns detected: skip this step.

---

## Step 7 — Check for USER.md updates

If anything new was learned about Cathy during this session — her role, preferences, a project she mentioned, a working style observation — propose a specific update to USER.md.

Wait for approval before editing USER.md.

If nothing new: skip this step.

---

## Step 8 — Write tomorrow's action list

Write (or overwrite) `context/tomorrow.md` with a consolidated action list for the next session.

To build it:
1. Read today's full memory file (`context/memory/[today's date].md`)
2. Collect every item listed under **Open threads** across all session blocks
3. Remove any that were clearly resolved in a later session (e.g., a thread says "blog not written" and a later session lists it as a deliverable)
4. Order the remaining items by priority — anything with a named file or Airtable record ready to go comes first
5. Note the single most important resource to read first, if there is one

Format:

```markdown
# Start Here — [tomorrow's date]

## Open threads

- [ ] [task — specific enough to act on immediately]
- [ ] [task — include file path or Airtable record ID where relevant]

## Read first
- `[file path]` — [one line on why]
```

If there are no open threads, write the file with a single line: "No open threads."

---

## Step 9 — Confirm

One line: what was written and where. Example:

> Session block written to `context/memory/2026-05-14.md`. `context/tomorrow.md` updated with 3 open threads. Learnings updated for `seo-blog-writer`. No SOUL.md changes proposed.
