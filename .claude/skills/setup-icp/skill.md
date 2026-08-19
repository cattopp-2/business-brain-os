# Setup: Your Audience Profile

## What This Skill Does

Walks you through building your ICP file and your first audience language file from real customer language.

These files are what stop the system writing generic AI content. Every copy skill reads them before writing — the more specific and real the language in here, the more the output sounds like it was written for your actual clients.

Run this once during Module 4 setup. Update the files as you collect more customer language.

---

## Rules

- Ask one question at a time. Never list multiple questions in one message.
- Wait for the answer before moving to the next question.
- Push for specifics. If an answer is vague or paraphrased, ask: "Can you think of a time a client said something like that — what were the actual words they used?"
- Accept partial answers. Not everyone has testimonials or intake form data ready — work with what they have and note where the gaps are.
- Write both files after gathering information. Do not ask for approval before writing.

---

## Step 1 — Route them

Before asking any questions, say:

"To set up your audience profile I need to understand who your ideal client is and — most importantly — how they talk. We can do this two ways. I can ask you questions one at a time, or if you've already got something written down (client testimonials, intake form answers, discovery call notes, a past ICP doc) you can paste it in and I'll pull what I need from that. Which works better for you?"

**If they choose questions:** go to Path A.

**If they paste material:** go to Path B.

---

## Path A — Questions (in order)

### Part 1 — Who they are

1. "Who is your ideal client? Don't give me the polished version — describe the actual person who gets the best results from working with you. What do they do, where are they in their business or life, what's going on for them?"

2. "Are there any types of clients you've learned to avoid? People who aren't a good fit, or situations that don't tend to work out well?"

3. "How do your clients tend to feel about technology? Is that relevant to your offer?"

### Part 2 — What they want (in their words)

4. "What does your ideal client want more than anything? And I want their words if you can — not your interpretation of what they want, but something close to what you've actually heard them say."

5. "What are they trying to get away from? What's the situation or feeling they're stuck in when they come to you?"

6. "What stops them from saying yes? What objections or worries do you hear before someone buys?"

### Part 3 — Real language

7. "Give me 3 to 5 phrases your clients actually use — words, questions, or ways of describing their problem that you hear regularly. Exact wording if you can."

8. "Are there any words or phrases that feel wrong for your audience — things that would immediately put them off or sound unlike how they talk?"

### Part 4 — First offer area

9. "Which of your offers do you want to start with for your first audience language file? Pick your main one — the offer you talk about most and produce the most content around."

10. "For that offer specifically — what does your client want from it? What does success look like to them after working with you? Again, their words if you have them."

---

## Path B — Extract from existing material

Ask them to paste whatever they have. Accept anything: testimonials, intake form answers, discovery call notes, a past ICP document, client emails, DM screenshots.

Once they've pasted it, extract:
- Who the ideal client is — role, stage, situation
- Who they don't work with
- Their tech relationship (if relevant)
- What they want — in direct quotes where possible
- What they're running from — in direct quotes where possible
- Objections and worries
- Real language phrases — exact wording
- Language to avoid
- Which offer to build the first audience language file around

After extracting, ask only the questions that genuinely can't be answered from the material — particularly the offer focus for the language file, and any missing real-language quotes. Prompt: "Is there anything in there that doesn't sound quite right, or any language that feels too paraphrased? The more direct the quotes, the better the system performs."

---

## After All Information Is Gathered (both paths)

Write both files. Fill every section with what they said. Where quotes are direct, keep them in quotes. Where they gave a paraphrase, use it but note it.

### icp.md

```markdown
# Ideal Customer Profile — [Brand Name]

The single source of truth for who we're writing to. Read this before writing promotional copy, crafting hooks, or building messaging for any offer.

---

## Who They Are

**Role:** [Type of person — job title, business type, or life situation]

**Stage:** [Where they are in their journey]

**Business model:** [How they operate]

**Team:** [Solo / small team / etc.]

**Tech relationship:** [How they feel about technology, if relevant]

---

## Who They're Not

[Any client types or situations that don't work — from their answer to question 2]

---

## What They Want (In Their Own Words)

> "[Direct quote or close paraphrase]"
> "[Direct quote or close paraphrase]"
> "[Direct quote or close paraphrase]"

---

## What They're Running From

> "[Direct quote or close paraphrase]"
> "[Direct quote or close paraphrase]"

---

## Their Objections

- "[Objection in their words]"
- "[Objection]"
- "[Objection]"

---

## Real Language to Use

[Specific phrases your clients actually use]

- "[phrase]"
- "[phrase]"
- "[phrase]"

---

## Language to Avoid

- "[phrase to avoid]"
- "[phrase to avoid]"
```

### audience-language-[offer-slug].md

Name this file after their main offer area — e.g. `audience-language-coaching.md`, `audience-language-seo.md`, `audience-language-membership.md`. Keep it lowercase with hyphens.

```markdown
# Audience Language — [Offer Name]

Real language from clients and prospects about [offer topic]. Used by copy skills to ground content in how this audience actually speaks.

---

## What They Want From This

> "[Direct quote about desired outcome]"
> "[Direct quote]"

---

## How They Describe Their Problem

> "[Direct quote about the struggle or situation that leads them to this offer]"
> "[Direct quote]"

---

## Language Patterns

[Phrases, questions, or ways of describing the problem that come up regularly]

- "[phrase]"
- "[phrase]"
- "[phrase]"

---

## What Success Looks Like to Them

[What they're hoping for after working with you — in their words]

> "[Direct quote or close paraphrase]"

---

*Add more language here as you collect testimonials, DMs, and intake form answers. The more specific and direct the quotes, the better the system performs.*
```

After writing both files, say:

"Both files are saved. Your ICP is in brand-context/icp.md and your first audience language file is in brand-context/audience-language-[name].md.

These are the files that make the system sound like it was written for your actual clients. The most important thing you can do to improve them over time is add real quotes whenever you hear something good — after a discovery call, when a testimonial lands, when someone DMs you with a question. Even one strong quote makes a difference.

To test whether they're working: run /content-router with a topic related to your main offer. The output should reference your client's actual situation, not a generic version of it."

Then suggest they move to Module 5: loading their offers.
