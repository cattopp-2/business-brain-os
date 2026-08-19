---
name: seo-service-page-writer
description: Write a fully optimised, conversion-focused SEO service page for any website. Use this skill whenever the user wants to write or rewrite a service page, create a new page for a specific service offering, or produce a page that needs to rank for a keyword AND convert visitors. Trigger even if they just say "write a page for [service]", "I need a service page for [topic]", or "create a page about [offering]" without mentioning the skill explicitly.
---

<objective>
Turn a target keyword and service into a fully optimised, publish-ready service page — structured to rank in search and convert visitors into leads or buyers. Written inside Claude in a format that can be copied directly into a CMS or page builder.

Service pages are not blog posts. They are shorter, conversion-focused, and structured around the buyer journey — not informational intent. This skill applies SEO best practices while keeping copy tight and action-oriented.
</objective>

<quick_start>
Invoke this skill with a keyword or service name. The skill will gather details, plan the page structure for approval, then write the full page ready to copy into a CMS.
</quick_start>

<workflow>

Follow these steps in order. Do not skip ahead.

**Step 0: Keyword (if not already provided)**

If the user has given a target keyword, skip to Step 1.

If they've given a service name or topic but no keyword, offer to find the best match:

> "I can check your keyword opportunities list to find the best keyword for this page. Want me to look? Or do you have a specific keyword in mind?"

If yes: Read `SEO Strategy/Keyword Opportunities.csv`. Find keywords matching the service — look at intent and topic, not just exact text. Present the top 2–3:

> "Best matches from your keyword list:
> 1. [keyword] — [volume]/month, difficulty [score]
> 2. [keyword] — [volume]/month, difficulty [score]
>
> Which fits best, or shall I use a different keyword?"

Wait for confirmation before continuing.

---

**Step 1: Intake**

Ask the user for:

**Required:**
1. The target keyword (confirmed in Step 0, or provided here)
2. The service name and what it includes (a brief description is enough)
3. Who the page is for — describe the target customer

**Optional:**
4. Any specific angle or hook they want the page to lead with
5. Any internal pages on their site that could be linked from this page
6. Price, packages, or process steps to include
7. Any testimonials or proof points to weave in

Wait for the required information before proceeding.

---

**Step 2: Plan the Page Structure**

Build the full page structure before writing. Present this for approval — the user can adjust before the full page is written.

**Meta Title** (max 60 characters — count them)
Include the target keyword. Lead with the benefit or outcome, not just the service name. Do not pad to fill the limit.

**Meta Description** (max 160 characters — count them)
Write as a compelling reason to click — what will they get, or what problem does this solve? Include the keyword naturally.

**H1: Hero Headline**
Benefit-led, not just a service label. Include the keyword. Write the kind of headline that makes the right person think "this is exactly what I need."

**Supporting tagline or subheader** (optional, 1 sentence)
Qualifies who this is for or reinforces the headline promise.

**H2 Structure**
Plan 4–6 H2s that guide a buyer through the page. Typical service page arc:

- What this service is / the problem it solves
- What's included or what they get (benefits-led)
- How it works (process — 3–5 steps)
- Who this is right for
- Frequently Asked Questions (3–5 objection-handling questions)

Adjust this arc based on the service and intake details. Each H2 should move the reader closer to taking action.

**CTA placement**
Note where calls-to-action appear: after the intro, after "what's included," and at the end minimum.

Present the full structure and wait for the user to confirm or request changes.

---

**Step 3: Write the Page**

Write the full page in this order. Use the formatting below so it can be copied cleanly into a CMS.

---

**META TITLE:** [title here — max 60 characters]
**META DESCRIPTION:** [description here — max 160 characters]

---

# [H1: Hero Headline]

[Supporting tagline if planned — 1 sentence]

[Intro paragraph — 3–5 sentences. Include the keyword naturally in the first 1–2 sentences. Speak directly to the problem or situation the target customer is in. Make clear what this service does and who it's for. End with a reason to keep reading or a soft CTA.]

**[CTA — first placement]**
[e.g. "Book a free discovery call →" or "Get started today →"]

---

## [H2: What this is / the problem it solves]

[100–150 words. Ground the reader in the problem or situation this service addresses. Do not list features — focus on the gap between where they are now and where they want to be. Include the keyword and semantically related terms where they fit naturally.]

---

## [H2: What's included / What you get]

[100–200 words. Lead with outcomes and benefits, not a feature list. If there are specific deliverables, present them clearly — but frame each one around what it means for the client. Use a short bulleted list only if the deliverables are genuinely list-like.]

**[CTA — second placement]**

---

## [H2: How it works]

[Brief intro sentence, then the process as numbered steps — typically 3–5. Each step should be a short heading + 1–2 sentences of explanation. Keep it scannable. Avoid jargon.]

---

## [H2: Who this is right for]

[80–120 words. Qualify the ideal customer clearly. This builds trust by being specific — it tells the right people "yes, this is for you" and tells the wrong people "this probably isn't your fit." Write as a short paragraph or a brief bulleted list of descriptors.]

---

## Frequently Asked Questions

**Q: [Question — frame as a real buying concern or objection]**
A: [Answer in 2–4 sentences. Address the concern honestly. Natural language, not keyword-stuffed.]

*(3–5 FAQs total — focus on the questions that prevent someone from booking or buying)*

---

[Closing CTA section — 3–4 sentences. Summarise the core promise of the service. Make it easy to take the next step. End with a clear action.]

**[CTA — final placement]**

---

**INTERNAL LINKS TO ADD:**
[2–4 suggestions — related pages or posts that reinforce this service. Anchor text suggestion → page title or URL slug]

**SCHEMA TO ADD:**
[Recommend whether to add Service schema or LocalBusiness schema, and what the key fields should be: name, description, provider, areaServed if relevant]

---

**Step 4: Conversion + E-E-A-T Check**

Before presenting the page, run through this checklist internally. Fix anything that fails.

**Conversion**
- Does the H1 immediately communicate who this is for and what they get?
- Is there a CTA after the intro, after "what's included," and at the end?
- Are benefits leading — not a list of features?
- Does the FAQ section address real objections, not just generic questions?
- Is the next step clear and low-friction?

**E-E-A-T**
- Does the copy feel like it comes from someone who has done this work — with specific, credible detail?
- Is it accurate and thorough enough to be genuinely useful?
- Are any claims honest and defensible?
- Is the writing free from hype, hollow phrases, and vague generalisations?

If any check fails, rewrite the relevant section before presenting the output.

</workflow>

<writing_standards>

**SEO — Keyword Placement**
- Target keyword in: meta title, meta description, H1, first paragraph, at least one H2, and naturally throughout the body
- Semantic and related terms woven in naturally — do not list them, just use them
- Do not keyword-stuff. One natural mention is worth more than three forced ones
- FAQ questions structured around real buying intent — not keyword variations of the H2s

**Copy — what not to write**
- No hollow phrases: "game-changer", "transform", "elevate", "revolutionise", "bridge the gap", "dive in", "in today's fast-paced world", "unlock", "leverage"
- No filler openings that delay the point
- No rule-of-three staccato sentence structures
- No em-dashes
- Mix short and long sentences — avoid staccato throughout

**Structure**
- Service pages are shorter than blog posts: aim for 600–900 words of body copy
- Every section should earn its place — cut anything that doesn't move the reader toward action
- CTAs should feel natural, not bolted on

**Voice**
Warm, clear, and direct. Conversational without being casual. Write for the person who is one decision away from getting in touch.

</writing_standards>

<success_criteria>
The page is complete when:
- [ ] Meta title confirmed at 60 characters or under, keyword included
- [ ] Meta description confirmed at 160 characters or under, written as a reason to click
- [ ] H1 is benefit-led and includes the keyword
- [ ] Page follows the approved H2 structure
- [ ] Three CTA placements present (intro, mid-page, close)
- [ ] Benefits lead — features are in service of outcomes
- [ ] FAQ section addresses real objections (not generic questions)
- [ ] Internal link and schema suggestions provided
- [ ] E-E-A-T + conversion check passed before output
</success_criteria>
