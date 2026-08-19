---
name: seo-blog-writer
description: >
  Write a fully optimised SEO blog post targeting a specific keyword and deliver it in a
  copy-paste-ready format. Triggers on: "write a blog", "blog post", "SEO blog",
  "blog about [keyword/topic]", "I need a blog for [keyword]", "SEO content",
  "write me an article". Produces a structured post with intro, H2/H3 sections, E-E-A-T
  signals, and meta description. Does NOT trigger for social posts, emails, or sales pages —
  even if they are long-form content.
---

# SEO Blog Writer

Turn a target keyword into a fully optimised, publish-ready blog post — written inside Claude in a format that can be copied directly into a Google Doc or CMS.

## Learnings
Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply any notes to this run.

## Outcome
A complete blog post including: meta title (≤60 chars), meta description (≤160 chars), H1, intro, 5–7 H2 sections with body copy, FAQ section, and internal/external link suggestions — delivered as a Google Doc with the link saved to the Airtable record where applicable. E-E-A-T check passed before delivery.

## Edge Cases

**No keyword provided and no CSV match** — ask the user to provide a keyword directly. Do not proceed on a topic alone.

**User wants to skip structure approval (Step 2)** — advise against it: a 60-second approval saves a full rewrite. If they insist, write the post and flag any structural choices they may want to change.

**User wants a very short post (under 700 words)** — flag the trade-off: short posts rarely rank well for competitive keywords. Write it, but note the length and suggest a minimum target if they want SEO performance.

**Topic is already covered on the site** — flag this and offer two options: refresh the existing post, or take a new angle that differentiates. Don't produce a near-duplicate without flagging it.

**User provides a very specific keyword not in the CSV** — proceed with the keyword as given. Don't require a CSV match to write.

**Keyword has clear commercial intent but user wants to write informational content** — note the mismatch and let them decide. Sometimes the audience is right even when the intent doesn't match the keyword type.

## Feedback
After delivering the post, ask:
> "Any feedback on this? A quick note helps improve next time."

If feedback is given, append to `.claude/skills/seo-blog-writer/learnings.md`:
```
### [DATE]
[feedback]
```
Create the file if it doesn't exist.

Follow the steps below in order. Do not skip ahead.

---

## Step 0: Keyword (if not already provided)

If the user has given you a target keyword, skip this step and go to Step 1.

If the user has given you a topic or idea but not a specific keyword, offer to find the best match:

> "I can check your keyword opportunities list to find the best keyword for this topic. Want me to look? Or do you have a specific keyword in mind?"

If yes: Read `SEO Strategy/Keyword Opportunities.csv`. Find keywords that match the topic — look at the keyword text, not just exact matches. Present the top 2–3:

> "Best matches from your keyword list:
> 1. [keyword] — [volume]/month, difficulty [score]
> 2. [keyword] — [volume]/month, difficulty [score]
>
> Which fits best, or shall I use a different keyword?"

Wait for confirmation before continuing.

---

## Step 1: Intake

Ask the user for:

**Required:**
1. The target keyword for the blog post (confirmed in Step 0, or provided here)

**Optional:**
2. Any specific angle, hook, or topic focus they want the blog to take
3. Any internal pages or blog posts on their site that could be linked to from this post
4. Any external sources, statistics, or research they want referenced

Wait for the keyword before proceeding.

---

## Step 1b: SERP Research

Before planning the structure, look at what is already ranking for this keyword. This tells you what Google currently rewards — the depth, the angles, the questions covered — so the post can be better than what exists, not just different.

Search the keyword using the WebSearch tool. Look at the top 3–5 results and note:
- What headings (H2s) do they use? What topics do they cover?
- What angle are they taking — generic advice, personal story, practical guide?
- What's missing, shallow, or not specific enough to Aurelia's audience?

Do this silently. Do not report the raw search results to the user. Use the findings to inform the structure in Step 2 — the H2s should reflect both what Google rewards and where there's an opportunity to go deeper or be more specific.

If the top results are all from very high-authority sites (national newspapers, government sites, major brands), note this to the user — it may indicate the keyword is harder to rank for than the SD score suggests.

---

## Step 2: Plan the Blog Structure

Build the full blog structure before writing. Present this to the user so they can approve or adjust before the full post is written.

**Meta Title** (max 60 characters — count them)
Include the target keyword. Make it specific and benefit-led. Do not pad to fill the limit — every character should earn its place.

**Meta Description** (max 160 characters — count them)
Write as a compelling reason to click, not a summary. Include the keyword. Focus on what the reader will get.

**H1: Blog Title**
Can be longer and more conversational than the meta title. Include the keyword. Write the kind of headline someone would actually click on.

**H2 Structure**
Plan 5–7 H2s that together give complete, useful coverage of the topic. Each H2 should:
- Address a distinct subtopic or question a reader would have
- Follow a logical reading order — broader to more specific
- Reflect genuine search intent, not just keyword variations

**FAQ Section**
4–6 questions that capture "People Also Ask" style intent around the keyword. These should feel like real questions, not reworded versions of the H2s.

**Word Count Target**
Default to 1,000–1,500 words for a standard post. Note the target before writing.

Present the full structure and wait for the user to confirm or request changes before writing the post.

---

## Step 2b: Update the Keyword CSV

**Skip this step** if the keyword and outline were provided directly by the user or pre-baked from an Airtable brief — the keywords were not sourced from the CSV, so no update is needed.

Only run this step if the keyword was found via the CSV in Step 0.

Once the structure is confirmed, update `SEO Strategy/Keyword Opportunities.csv` for every keyword being used in this post.

For each keyword (primary + all secondaries):
1. Find the row where the keyword text matches (case-insensitive, exact match on the keyword column)
2. If a match is found: set the `Added to the plan` column to `yes` and set the `Notes` column to `Blog: [post title]` — using the H1 title confirmed in Step 2
3. If no match is found: skip silently — don't add new rows

Do this silently. Do not report each individual update. When done, confirm once:

> "Keywords marked in Keyword Opportunities.csv."

Then move to Step 3.

---

## Step 3: Write the Blog Post

Write the full post in this order. Use the formatting below exactly so it can be copied cleanly into a Google Doc.

---

**META TITLE:** [title here — max 60 characters]
**META DESCRIPTION:** [description here — max 160 characters]

---

# [H1: Blog Title]

[Introductory paragraph — 3–5 sentences. Include the keyword naturally in the first 1–2 sentences. Hook the reader by signalling that this post will genuinely answer what they came for. No filler openings like "In today's world..." or "Have you ever wondered..."]

---

## [H2: First Subheading]

[100–200 words. Answer the implied question of the heading clearly and usefully. Use natural language — not bullet-pointed filler. Include the target keyword and semantically related terms where they fit naturally. Write for the reader first, search engines second.]

---

*(Repeat for each confirmed H2)*

---

## Frequently Asked Questions

**Q: [Question]**
A: [Answer in 2–5 sentences. Natural language, not keyword-stuffed.]

*(Repeat for each FAQ)*

---

**INTERNAL LINKS TO ADD:**
[2–4 suggestions for internal links — pages or posts on their site that relate to this content. Anchor text suggestion → page or post title]

**EXTERNAL LINKS TO ADD:**
[2–3 suggestions for authoritative external sources — statistics, research, professional bodies, or well-known reference sites. If the user provided sources in Step 1, include those. Otherwise suggest the type of source and what to search for.]

---

## Step 4: E-E-A-T Check

Before presenting the post, run through this checklist internally. Fix anything that fails before showing the output.

**Experience**
- Does the writing feel like it comes from someone who has actually done or lived this — not just researched it?
- Are there specific examples, real scenarios, or practical details that go beyond surface-level advice?

**Expertise**
- Is the content accurate and thorough?
- Does it cover the topic in enough depth to be genuinely useful — not just an overview?
- Are claims backed up or at least grounded in something real?

**Authoritativeness**
- Does the post reference or point toward credible sources where relevant?
- Is it structured like a reliable, complete resource — not a thin opinion piece?

**Trustworthiness**
- Is every claim honest and defensible?
- Is the writing free from hype, hollow phrases, and vague generalisations?
- Does it treat the reader as an intelligent adult?

If any section fails the check, rewrite it before outputting the post.

---

## Writing Standards

**SEO — Keyword Placement**
- Target keyword in: meta title, meta description, H1, first paragraph, at least one H2, and naturally throughout the body
- Semantic and related terms woven in naturally — do not list them, just use them
- Do not keyword-stuff. One natural mention is worth more than three forced ones
- FAQ section structured to capture People Also Ask intent

**Language**
- No hollow phrases: "game-changer", "transform", "elevate", "revolutionise", "bridge the gap", "dive in", "in today's fast-paced world"
- No filler openings that delay the point
- No rule-of-three sentence structures
- Mix short and long sentences — avoid staccato throughout
- No em-dashes

**Voice**
Write in a natural first-person voice as if from the author. Warm, clear, and direct — conversational without being casual.

**Length**
Hit the word count target set in Step 2. If the content genuinely warrants going longer, note this to the user rather than padding to fill it.

---

## Step 5: Generate FAQ Schema

Before saving to Google Doc, generate a JSON-LD FAQPage schema block from the FAQ section of the post.

Build the schema using every Q&A pair:

```
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "[Question text]",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "[Answer text]"
      }
    }
  ]
}
</script>
```

Rules:
- Include every FAQ Q&A — do not truncate
- Strip Markdown formatting from answer text (no bold markers, no backticks)
- Plain prose only inside JSON values — no HTML tags
- Valid JSON — no trailing commas

---

## Step 6: Publish to Google Doc + Update Airtable

Once the post has passed the E-E-A-T check and the schema is generated:

1. Create a Google Doc titled with the H1 blog title
2. Paste the full formatted post into the doc, with these fields at the top in this order:
   - META TITLE: [value]
   - META DESCRIPTION: [value]
   - KEYWORD: [target keyword]
   - SLUG: [lowercase H1, spaces as hyphens, no special characters]
   
   Then the H1, all H2s, FAQ, and link suggestions below.
3. Append the FAQ schema at the end of the doc under this heading:

```
--- FAQ SCHEMA ---
Paste into Code Snippets > Add New > HTML
Location: Insert After Content
Name: FAQ Schema - [H1 blog title]

[the script block here]
```

4. Copy the Google Doc URL
5. If this blog came from an Airtable record (passed in context or known from the current session):
   - Update the "Link to Google Doc" field (fldvwAf8Y8gSYt5cV) on the record in the Website Blogs table (base: appxFaTh8wdrUZREh)
   - Use the Google Doc URL as the field value
6. Confirm to the user:
   > "Blog post saved to Google Doc: [link]. FAQ schema included at the bottom. Airtable record updated."

If no Airtable record is known, still create the Google Doc and share the link — skip the Airtable update.


