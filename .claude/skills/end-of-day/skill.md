# End-of-Day Close Ritual

A 5-minute structured close that anchors tomorrow's focus email to strategic priorities, not tactical noise.

---

## Rules

- Ask questions ONE AT A TIME. Never list multiple questions together.
- Tone is calm and efficient — this is a wind-down, not an audit.
- Focus tasks for the JSON must come from `context/weekly-focus.md` first. Only pull from `tomorrow.md` if a tactical item is genuinely high-stakes (e.g. blocks a client deliverable due tomorrow).
- Never write more than 2 focus tasks to the JSON.
- Always write today's memory file even if Cathy says "nothing to add" — the minimum entry is what the weekly focus items are and that a close was run.
- Do not run `/wrap-up` — that is a separate skill. This ritual is faster and more focused.

---

## Steps

### Step 1 — Load context

Read these files silently before saying anything:

1. `context/weekly-focus.md` — the week's strategic priorities
2. `context/tomorrow.md` — current open threads
3. `context/ceo-north-star.md` — the filter

### Step 2 — Check content schedule

Run `scripts/fetch_content_schedule.py` to get today's content status (posted/scheduled/gap). Use the output to populate the `content` section of the JSON. If the script fails, set all platforms to `null`.

```
python scripts/fetch_content_schedule.py
```

### Step 3 — Ask what got done

Say:

> "Quick close — what did you get done today? Even bullet points are fine."

Wait for response. Note anything that should be marked complete in `tomorrow.md`.

### Step 4 — Check weekly focus

Say:

> "Anything that needs to shift on the weekly focus before tomorrow?"

Wait for response. If Cathy says no or nothing, proceed. If she names a change, update `context/weekly-focus.md` accordingly.

### Step 5 — Pick tomorrow's 2 focus tasks

From `context/weekly-focus.md`, identify which of the 2–3 priorities is most active right now. Write 2 focus tasks in this format:
- `task`: the specific next action (concrete, not vague)
- `reason`: why it matters strategically — one sentence referencing the CEO north star or week priority

Example of GOOD focus task:
```json
{
  "task": "Quiz live test — run it with a fresh email address",
  "reason": "The quiz is the only active lead gen mechanism. It cannot launch until this is confirmed working."
}
```

Example of BAD focus task (too tactical/admin):
```json
{
  "task": "Pick a subject line for the broadcast email",
  "reason": "This is on the to-do list."
}
```

### Step 6 — Update tomorrow.md

Mark any items Cathy confirmed as done. Add any new threads that emerged today. Do not reformat or restructure the file — append and update only.

Today's date heading should read: `# Start Here — [tomorrow's date]`

Update it to tomorrow's date if it still shows today's.

### Step 7 — Write project_nudge_data.json

Write `scripts/project_nudge_data.json` with:
- `date`: tomorrow's date, formatted as "Weekday DD Month YYYY"
- `focus_tasks`: the 2 tasks from Step 5
- `content`: from Step 2 (fetch_content_schedule output, or nulls if failed)
- `email_gap`: leave as `null` (the marketing nudge script handles cadence checking)

### Step 8 — Write today's memory file

Write `context/memory/[today's date].md`. Minimum content:

```markdown
## End-of-Day Close — [date]

**Weekly focus this week:**
1. [item 1]
2. [item 2]
3. [item 3 if exists]

**Got done today:**
[bullet list from Cathy's response, or "Not recorded"]

**Focus tasks set for tomorrow:**
1. [task 1]
2. [task 2]

**Weekly focus changes:** [any changes made, or "None"]
```

If a memory file for today already exists (from an earlier session), append a `## End-of-Day Close` section rather than overwriting.

### Step 9 — Confirm

Say:

> "Done. Tomorrow's nudge email will focus on: [task 1 title] and [task 2 title]. See you tomorrow."

Nothing else. No summary of everything completed. No list of what's in the files.
