# Setup: Your North Star & Revenue Tracker

## What This Skill Does

Walks you through a short conversation and writes two files:
- `context/ceo-north-star.md` — your strategic direction, your offers, and your filter for decisions
- `context/revenue-tracker.md` — your income target and current pipeline

Claude reads both of these at the start of every session. The north star keeps decisions aligned with what you're actually building. The revenue tracker means Claude flags when income looks off-track without you having to ask.

Run this once during setup. Both files can be updated at any time.

---

## Rules

- Ask one question at a time. Never list multiple questions in one message.
- Wait for the answer before moving to the next question.
- This is a strategic conversation — give it space. Don't rush through the questions.
- Some answers will be uncertain or incomplete. That's fine — write what they know and note what's still to be decided.
- After all questions are answered, write both files without asking for approval. Show them the finished files and confirm they're saved.

---

## Step 1 — Route them

Before asking any questions, ask:

"To set up your north star and revenue tracker I need to understand your business goals, your offers, and your income situation. We can do this two ways — I can ask you questions one at a time, or if you've already got something written down (a business plan, a strategy doc, an offer guide, even rough notes) you can paste it in and I'll pull what I need from that. Which works better for you?"

**If they choose questions:** go to the Questions path below.

**If they paste material:** go to the Extract path below.

---

## Path A — Questions (in order)

1. "Why does your business exist? Not the polished version — the real reason. What are you trying to get out of this?"

2. "What's your income target? You can give me an annual figure, a monthly figure, or both."

3. "What does your business look like in 3 years if everything goes the way you want? Not a fantasy — just what does a good outcome actually look like for you?"

4. "Who do you work with? Be as specific as you can — the type of person, where they are in their business or life, what they're dealing with."

5. "Who do you not work with? Any type of client or situation you've learned to avoid?"

6. "Walk me through your current offers — what you sell, roughly what it costs, and who it's for. Don't worry about getting it perfect, we can refine later."

7. "What are your biggest priorities for the next 90 days? The 2 or 3 things that actually matter right now."

8. "What won't you do? Hard limits — on your time, your clients, the type of work, how you want to live."

9. "What's your current monthly income from the business — roughly? And is there anything confirmed in the pipeline coming up?"

---

## Path B — Extract from existing material

Ask them to paste whatever they have. Accept anything — a business plan, strategy doc, offer guide, pricing page, pitch deck, rough notes.

Once they've pasted it, extract:
- Why the business exists / the real motivation
- Income target (annual or monthly)
- 3-year vision
- Who they work with and who they don't
- Current offers — name, price, who it's for
- 90-day priorities
- Hard limits / what they won't do
- Current income and pipeline

Ask only the questions that genuinely can't be answered from the material — income and pipeline figures in particular may not be in any document, so ask those directly if needed.

---

## After All Information Is Gathered (both paths)

Write both files. Do not leave any `[brackets]` unfilled — use what they said, make reasonable inferences for anything unclear, and add a comment where something is genuinely unknown.

### ceo-north-star.md

```markdown
# CEO North Star

*Last updated: [TODAY'S DATE]*

---

## Why this business exists

[Their answer to question 1 — in their words. Don't sanitise it.]

---

## What they're building toward (3 years)

[Their answer to question 3.]

---

## Who they work with

[Their answer to question 4. Include who they don't work with from question 5.]

---

## Their offers

[List each offer from question 6 — name, one-sentence description, price if given, who it's for.]

**Decision rule:** Before adding anything new to this list, be willing to drop something already on it.

---

## What they won't do

[Bullet list from question 8.]

---

## 90-day priorities (from [TODAY'S DATE])

[Numbered list from question 7 — 2 or 3 items with one sentence of context each.]

---

## The filter

Before starting anything new — a project, an offer, a content direction, a client conversation — ask:

**Does this move me toward [summarise their goal from question 1 and 2 in a short phrase]?**

If yes: proceed.
If no: be honest about why you're doing it anyway.
```

### revenue-tracker.md

```markdown
# Revenue Tracker

*Last updated: [TODAY'S DATE]*

---

## The number

**Annual target: [from question 2]**
**Monthly target: [calculated or given]**

---

## This month — [CURRENT MONTH YEAR]

| Client | Amount | Status |
|---|---|---|
[Fill from question 9 — current income and any confirmed pipeline]

**This month confirmed: [total]**
**vs target: [gap or surplus]**

---

## Pipeline

| Client / Source | Amount | Notes |
|---|---|---|
[Any pipeline items from question 9]

---

## Actions needed

- [ ] [Any obvious next steps that came up in the conversation]

---

*Updated by Claude at each session. Share when income changes — new client, lost client, invoice paid — and this file gets updated.*
```

After writing both files, confirm: "Both files are saved. Claude will read these at the start of every session. Update the revenue tracker whenever your income situation changes — just tell me and I'll update it."

Then suggest they move to Module 3: capturing their brand voice.
