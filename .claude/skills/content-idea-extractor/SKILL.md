---
name: content-idea-extractor
description: >
  Extract 10–15 content ideas from source material — transcripts, call recordings, client
  language docs, Google Docs — get approval, and save selected ideas to Airtable as Ready
  to draft briefs. Triggers on: "extract ideas", "pull ideas from this", "content ideas from
  transcript", "what can I write about from this call", "find angles in this doc", "content
  from this recording", "idea extraction". Does NOT write the content — it surfaces and saves
  ideas only. Use content-router to write from the saved ideas.
---

# Content Idea Extractor

Read source material → surface 10–15 content ideas → get approval → save to Airtable.

This is how raw material (client calls, transcripts, audience language docs) becomes a bank of ready-to-draft content briefs.

## Learnings
Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply any notes to this run.

## Outcome
A numbered table of 10–15 approved content ideas saved to Airtable as Ready to draft briefs — each with enough context for the daily content agent or content-router to write from without going back to the source. The user confirms which ideas to keep before anything is saved.

## Edge Cases

**Source material is very thin (under 500 words)** — extract whatever's there and flag that fewer ideas were possible. Don't pad with generic content angles.

**Google Doc URL or file path fails** — ask the user to paste the content directly instead. Don't block on a tool failure.

**User rejects all ideas** — ask: "What angles were you hoping to see?" Adjust the filter (more story angles, more tactical, more specific to one offer) and regenerate.

**Ideas cluster around one theme** — actively vary the types before presenting: at least one pain point, one outcome, one process, one belief/opinion, one story. Don't submit a table of ten variations of the same angle.

**User wants to save all ideas without reviewing each one** — still present the table first; batch-save once the full list is confirmed. Never save to Airtable without explicit approval.

**Source material is in a format that can't be read** — ask the user to paste the key sections as text. Note what couldn't be read and why.

---

## Feedback
After saving ideas to Airtable, ask:
> "Any feedback on these ideas or how they were extracted? A quick note helps improve next time."

If feedback is given, append to `.claude/skills/content-idea-extractor/learnings.md`:
```
### [DATE]
[feedback]
```
Create the file if it doesn't exist.

## Step 1 — Source

Ask:

> "Where's the source material? Choose one:
> 1. I'll paste the text now
> 2. It's a file on my computer (give me the path)
> 3. It's a Google Doc (give me the URL or file ID)"

Wait for the answer, then read the content:

- **Paste** → it's already in the conversation, proceed to Step 2
- **File path** → use the Read tool to load the file
- **Google Doc** → use `mcp__claude_ai_Google_Drive__read_file_content` with the file ID (extract from URL: the ID is between `/d/` and `/edit` or `/view`)

If the file is very long (over 3,000 words), note this to the user and explain you'll read the full content but will prioritise the richest sections for idea extraction.

---

## Step 2 — Analyse for Ideas

Read through the material. You are looking for:

**Pain points** — what problems, frustrations, or struggles does the content describe? (these become "I used to..." or "If you're struggling with..." angles)

**Outcomes** — what results, transformations, or wins are mentioned? (these become "How to..." or "What happened when I..." angles)

**Beliefs and mindset shifts** — opinions, takes, or things the speaker believes that others might not (these become "Unpopular opinion:" or "Here's what nobody tells you..." angles)

**Processes and how-tos** — step-by-step things explained or demonstrated (these become tactical posts or blog posts)

**Stories and moments** — specific scenes, client examples, turning points (these become narrative posts or email openers)

**Questions the audience is asking** — explicit questions, confusions, things they want to know (these become FAQ posts, myth-busting content, or direct answer blogs)

Extract 10–15 distinct ideas. Aim for variety — not 10 variations of the same angle.

---

## Step 3 — Present for Approval

Present ideas in a numbered table:

```
| # | Idea / Angle | Suggested format(s) | Brand / offer fit |
|---|---|---|---|
| 1 | [topic + angle in one sentence] | [Blog / Facebook post / Email / Instagram / Threads] | [Your Web Toolkit / AI Growth Lab / Copywriter in Your Pocket — or "general"] |
| 2 | ... | ... | ... |
...
```

After the table:

> "Which numbers do you want to keep? You can tell me to tweak any angle before saving, or add a note to any idea."

Wait for the response. The user may:
- Give a list of numbers (e.g. "1, 3, 5, 9")
- Ask to tweak an idea first, then confirm
- Add notes to specific ideas

Incorporate any tweaks before saving.

---

## Step 4 — Save to Airtable

For each approved idea, create one record using `mcp__claude_ai_Airtable__create_records_for_table`:

**Base ID:** `appcNLyoNspCp5AC2`
**Table ID:** `tbliPVBb8lRJGmvTS`

**Fields per record:**

- `fldCvYcmSFGxzM7S5` (Hook/Subject Line) — the idea angle written as a usable brief. Format:
  `[Topic]: [Angle]. [One sentence on what the content should do or say.]`
  Example: `"AI for business owners: The 3 tools I actually use daily. Give specific names and show how each saves time — not generic AI cheerleading."`

- `fldOuQQzhsU7g6VZm` (Content) — the fuller idea description including: source context, suggested format(s), and any notes from Cathy. This gives the daily content agent enough to work from.

- `fldQUrc34BUzz0xYz` (Status) — `selUjgf122gznExRG` (Ready to draft)

- `fldcIsU925uOoBuCm` (Promotion) — offer choice ID if a specific brand/offer was identified. To get the correct choice ID, call `mcp__claude_ai_Airtable__get_table_schema` first if needed.

Save all approved ideas in a single batch call (pass all records as an array).

---

## Step 5 — Confirm

After saving:

> "Done. Saved [n] ideas to Airtable as Ready to draft. Ready to write any of them now? Just tell me the number and which format — or call /content-router to pick from your Airtable queue."

---

## Notes

- **The goal is quantity and variety** — pull different angles, don't over-cluster around one theme
- **Don't invent** — every idea should be grounded in something actually in the source material
- **Brand fit is a guide, not a rule** — if an idea clearly serves one offer, note it; if it's general, mark it "general"
- **Source types matter:** Client language docs → rich in pain points and outcomes. Call transcripts → rich in stories and specific moments. Audience language files → rich in exact phrasing to mirror back
