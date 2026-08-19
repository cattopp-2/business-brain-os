# Setup: Your User Profile

## What This Skill Does

Walks you through a short set of questions and writes your `context/USER.md` file from your answers. This file tells Claude who you are so it can calibrate every session to you — your brand, your goals, your working style.

Run this once during setup. You can update USER.md at any time by opening the file directly.

---

## Rules

- Ask one question at a time. Never list multiple questions in one message.
- Wait for the answer before moving to the next question.
- Do not offer examples or suggestions unless the person is stuck after their first attempt to answer.
- Write conversationally — this is a setup conversation, not a form.
- After all questions are answered, write the file without asking for approval. Show them the finished file and confirm it's saved.

---

## Step 1 — Route them

Before asking any questions, ask:

"To set up your profile I need to understand who you are and how you work. We can do this two ways — I can ask you questions one at a time, or if you've already saved something into your brand-context/about-me/ folder I can read that and pull what I need from it. Which works better for you?"

**If they choose questions:** go to the Questions path below.

**If they have material in brand-context/about-me/:** List the files in that folder, read the most relevant one (or all of them if short), and go to the Extract path below.

**If they want to paste material directly:** also go to the Extract path below.

---

## Path A — Questions (in order)

Work through these one at a time. Use the answer to each question to inform how you ask the next one — keep it conversational, not clinical.

1. "What's your name?"

2. "What's your primary brand called, and what do you do — one sentence is fine."

3. "What's your website URL?"

4. "Are there any other brands or businesses you run that we might need to write content for sometimes?"

5. "What are you hoping this system will do for your business? Just tell me in your own words — what does it look like when this is working well for you?"

6. "How would you describe your comfort level with tech? Pick whichever fits: not very technical, reasonably comfortable, or pretty confident with tools."

7. "How do you like to work with me? For example — do you want me to explain what I'm doing before I do it, or just get on with it? Do you prefer short responses or more detail? Anything that would make this feel like a good working relationship."

---

## Path B — Extract from existing material

Ask them to paste whatever they have. Accept anything — an about page, a bio, a brand guide, a LinkedIn profile, notes they've written about themselves, a past proposal.

Once they've pasted it, read through and extract:
- Name
- Primary brand name and what they do
- Website URL (if present — if not, ask for it)
- Any other brands
- What they're trying to achieve with this system (infer from how they describe their business and goals)
- Technical level (infer from tone and language used)
- Working style preferences (infer where possible — flag anything you can't determine and ask just those questions)

Ask only the questions that genuinely can't be answered from the material. If you can infer it reasonably, do so and note it in the file.

---

## After All Information Is Gathered (both paths)

Write `context/USER.md` using this structure. Fill every field from the conversation — do not leave any `[brackets]` unfilled. If a question wasn't answered, make a reasonable inference from what was said and note it in the file with a comment so they can adjust.

```markdown
# USER.md — [Name]

Read this file at the start of every session. It tells you who you're working with and how to calibrate your approach.

---

## Who They Are

**Name:** [Name]
**Email:** [leave blank — they can add this]
**Primary brand:** [Brand name] — [what they do] | [website URL]

[Other brands if mentioned:]
- [Brand] — [description]

---

## What They're Building

[2–3 sentences from their answer to question 5 — in their words, not paraphrased into business-speak.]

---

## Technical Level

[One of: Not very technical / Reasonably comfortable / Pretty confident with tools]

**How to frame technical explanations:** [one sentence based on their tech level — e.g. "Practically. What does it do and what's the effect, not how it works under the hood."]

---

## Communication Style

[3–4 bullet points drawn from their answer to question 7.]

---

## Working Preferences

[3–4 bullet points drawn from their answer to question 7.]

---

## Evolution

Update this file during wrap-up if anything new was learned about [first name]'s role, preferences, or working style. Append changes with a datestamp.

**Change log:**
<!-- Updates appended below in format: [YYYY-MM-DD] — what changed -->
```

After writing the file, confirm: "USER.md is saved. Claude will read this at the start of every session from now on. You can open and edit the file any time if anything changes."

Then suggest they move to the next setup skill: `setup-north-star`.
