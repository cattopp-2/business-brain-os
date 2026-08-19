---
name: ceo-check
description: >
  Check whether a task, project, idea, or list of work is aligned to Cathy's
  CEO north star — values, offers, 90-day priorities, and financial goals.
  Triggers on: "ceo check", "is this aligned", "should I be doing this",
  "check my priorities", "check my open threads", "am I on track",
  "does this make sense for my goals". Returns: Aligned / Off-track / Uncertain
  for each item, one sentence of reasoning, and a suggested action if off-track.
---

# CEO Check

Run any task, project, idea, or list of work through the north star filter. Get a clear verdict on each item — aligned, off-track, or uncertain — before spending time on it.

## Learnings
Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply any notes to this run.

## Step 1 — Load the North Star

Read `context/ceo-north-star.md` before doing anything else. This is the filter everything gets measured against. Do not skip this step.

## Step 2 — Get the Input

If the user hasn't specified what to check, ask:

> "What do you want me to check? You can give me a single task, a project idea, or paste your full open threads list."

Accept any of:
- A single task or idea (typed or described)
- A list of open threads (pasted or from `context/tomorrow.md`)
- A project or offer concept
- A named file or Airtable record

If the user says "check my open threads" or similar, read `context/tomorrow.md` and use the open threads list from there.

## Step 3 — Run the Check

For each item, evaluate it against the north star. Use these criteria:

**Aligned** — directly moves toward £70k, protects time/energy, fits the committed offers, attracts the right clients, or builds the system that makes things predictable

**Off-track** — drifts from the offers list, serves wrong-fit clients, trades time for low money, adds complexity without clear return, or pulls attention from the 90-day priorities

**Uncertain** — could be aligned but the connection isn't clear, or more information is needed to judge

## Step 4 — Output

Present results as a clean table:

| Item | Verdict | Reason | Suggested action |
|---|---|---|---|
| [item] | ✅ Aligned / ❌ Off-track / ⚠️ Uncertain | One sentence | Do it / Pause / Drop / Reframe / Needs decision |

Keep the reason column to one sentence. Keep suggested actions concrete — not "consider whether this is right" but "drop it", "move it to someday", "reframe as a retainer conversation", etc.

After the table, add one short paragraph summarising the pattern — what the list says about where time is actually going vs where it should be going.

## Step 5 — Offer to Go Deeper

Ask: "Want to go deeper on any of these, or shall I help you build the action list from here?"

If the user wants to act on the results, help them update `context/tomorrow.md` or create a plan — don't just leave them with a table.

## Rules

- Always read `context/ceo-north-star.md` first. Never run this check from memory.
- Never soften a verdict to avoid discomfort. Off-track means off-track.
- If an item is clearly a distraction, say so directly.
- The filter is the filter: does this move toward boring, predictable, £70k?
- Do not add nuance that lets the user keep everything on the list. The point is to cut.
