---
name: tool-ai-formatter
description: >
  Reformat finished long-form content (blog posts, articles, emails) into
  "Answer-Ready" structure optimised for extraction by AI search engines
  (ChatGPT, Perplexity, Claude, Google AI Overviews). Transforms essay-style
  writing into scannable, answer-first content with clear H2 headings, bullet
  lists, numbered steps, short paragraphs, and an expanded FAQ — while keeping
  the original voice, ideas, and inline links intact.
  Triggers: "make this answer-ready", "optimise for AI search", "format for
  Perplexity", "reformat for AI", "answer engine format", "GEO format",
  "make this extractable", "AI formatter".
---

# AI Answer Formatter

Take finished long-form content and reformat it so AI search engines can extract and cite it accurately. The ideas stay yours. The structure changes so AI systems can find and surface the right answer for the right query.

## Outcome

The original content returned in Answer-Ready format:
- Every major section under a query-style H2 heading
- Each section opens with a direct answer (not a build-up)
- Prose lists replaced with bullet points or numbered steps
- Paragraphs trimmed to 1–3 sentences
- Conversational asides and rhetorical framing removed
- FAQ section cleaned up and expanded
- Inline links preserved throughout
- Voice intact — the words are still the author's

---

## What This Skill Does NOT Change

- The ideas, angles, opinions, and examples — these stay as-is
- Inline hyperlinks — kept exactly where they are
- The FAQ section structure — kept and expanded, not removed
- Brand voice — the source material grounds the output; it doesn't drift

---

## Step 1: Receive the Content

Ask if not provided:

> "Paste the content you want to reformat. I'll restructure it for AI search extraction — same ideas, same voice, same links. Just a different shape."

If the content is in a Google Doc or file, ask for it or read it directly.

---

## Step 2: Analyse Before Rewriting

Before touching anything, scan for:

1. **Section count** — how many distinct topics or arguments are there?
2. **Prose lists** — any sequences or sets described in running sentences?
3. **Process steps** — any "here's how to" or sequential logic?
4. **FAQ section** — does one exist? How many questions?
5. **Conversational elements** — parenthetical asides, rhetorical questions, irony markers?
6. **Paragraph length** — identify the longest blocks to trim

Report back in one short paragraph: what you found and what will change.

---

## Step 3: Apply the Formatting Rules

Work through the content section by section. Apply every rule below.

### H2 Headings — make them query-shaped

Every major section gets an H2. The heading should read like a question someone would type into Perplexity or ChatGPT, or a direct claim that answers such a question.

**Before:** `The real problem with most content isn't the creation`
**After:** `## The Real Challenge Isn't Creating Content`

**Before:** `Why AI content falls flat`
**After:** `## Why So Much AI Content Sounds the Same`

Rules:
- H2s should be 4–8 words
- Title case
- No full stops
- Each H2 should be distinct — no two sections covering the same angle

### Answer-First Structure

Every section opens with the direct answer or core claim. Supporting detail follows.

**Before:** `Everywhere you look, there's more content. More posts, more emails... The reaction most people have is to swing one of two ways...`
**After:** `The best content repurposing strategy doesn't ask AI to come up with your ideas. It uses AI to help you share your ideas in more places.`

Rule: if the first sentence of a section doesn't answer the implicit question of that H2, rewrite it until it does.

### Bullet Points for Lists

Any group of three or more items described in prose becomes a bullet list.

**Before:** `You might be recording podcasts, running webinars, giving talks, hosting training sessions...`
**After:**
```
* Podcasts
* Webinars
* Workshops
* Training sessions
* Guest interviews
```

Rule: keep bullets short — label-length when possible, one sentence max.

### Numbered Steps for Processes

Any sequence where order matters becomes a numbered list.

**Before:** `Use AI to multiply your ideas, not generate them. You create the original content... Then AI turns that one piece into LinkedIn posts, Instagram captions...`
**After:**
```
1. Create one original piece of long-form content.
2. Use that content as the source for everything else.
3. Repurpose it into platform-native formats while keeping your original voice.
```

### Short Paragraphs

Maximum 3 sentences per paragraph. Aim for 1–2.

When a paragraph runs longer, find the natural split point and break it. Each paragraph should carry one clear idea.

### Remove Conversational Noise

Strip these without replacing them:
- Parenthetical asides: `(Ironic, much?)`, `(Because you didn't put any in.)`
- Rhetorical questions used as transitions: `Here's what both approaches get wrong.`
- Irony markers and meta-commentary
- Filler transitions: `And the thing is...`, `The thing about...`

Do NOT strip:
- Opinions and strong claims — these are citable
- Specific examples and client stories — these are what makes content worth extracting
- Inline links — preserve every one exactly as written

### Paragraph Opener Rule

Never start a paragraph with "And", "But", "So", or "The thing is". Rewrite the opener to be a direct statement.

---

## Step 4: Expand the FAQ

If there's an existing FAQ section, keep it and improve it. If there isn't one, add one at the end.

**FAQ rules:**
- Each question should match how someone would actually type it into a search engine
- Each answer: 2–4 sentences, direct, no fluff
- Minimum 5 questions
- Cover: what it is, how it works, who it's for, common objections, one "isn't this just X?" question
- Bold the Q, plain text the A

**Example format:**
```
**What is a content repurposing strategy?**
A content repurposing strategy is a system for turning one piece of long-form content into multiple pieces for different platforms. Instead of creating everything from scratch, you create once and distribute many times.

**Will repurposed content still sound like me?**
Yes, provided the original source material comes from your own words and ideas. When AI reshapes what you actually said rather than inventing new content, the voice holds.
```

---

## Step 5: Final Check Before Delivering

Run through this list:

- [ ] Every major section has a query-shaped H2
- [ ] Every section opens with the answer, not a wind-up
- [ ] All prose lists are now bullet points
- [ ] All process steps are numbered
- [ ] No paragraph longer than 3 sentences
- [ ] Conversational asides removed
- [ ] All original inline links intact
- [ ] FAQ has at least 5 questions with direct answers
- [ ] The voice still sounds like the author — no drift into generic AI tone

---

## Step 6: Deliver

Output the full reformatted piece in a code block (so it's easy to copy).

Then add a brief note — 2–3 sentences — on the main structural changes made and why.

Ask: "Any sections you want me to adjust, or parts of the original you want brought back?"

---

## Rules

*No rules yet — entries will be added here when the user flags issues during runs.*

## Self-Update

If the user flags an issue — wrong transformation, voice drift, something that shouldn't have been removed — update the `## Rules` section immediately with the correction. Format: `- {YYYY-MM-DD}: {What was wrong and the rule to prevent it}`.
