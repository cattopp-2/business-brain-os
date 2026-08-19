---
name: authority-piece
description: Write an authority piece for Cathy — blog post + LinkedIn article + Facebook post — from a topic or idea. Always invokes brand-voice first, asks questions one at a time before writing anything, then saves all three pieces to the correct Airtable tables and creates a Google Doc. Trigger when Cathy wants to write a thought leadership piece, an expert blog post, or an authority article for yourwebtoolkit.com.
---

# Authority Piece Skill

Creates a complete authority piece: a blog post for yourwebtoolkit.com, a LinkedIn article, and a Facebook post. All three pieces are saved to Airtable. The blog post is also saved as a Google Doc.

---

## Before You Start

Invoke `brand-voice` first. This loads the voice rules and reads `cathy-writing-examples.md`. Do not write a single word of copy until the brand voice skill has been loaded.

---

## Step 1: Take the Topic

Accept whatever the user provides — a single sentence, a rough draft, a stat, a URL, an idea. If nothing has been provided, ask:

"What's the topic or idea for this authority piece?"

---

## Step 2: Research (Optional)

Ask: "Do you want me to pull crib notes from any source articles or recent news to find angles?"

If yes and a URL has been provided: fetch the URL and summarise the key stats, facts, and angles as crib notes. Present these to Cathy before asking questions.

If yes and no URL provided: ask what topic to research, then invoke the `last30days` skill to surface relevant recent angles.

If no: move straight to Step 3.

---

## Step 3: Questions — One at a Time

Before writing anything, ask questions to draw out Cathy's specific take, real examples, and personal angles. The copy must come from her answers, not from AI expansion of the seed idea.

**Rules:**
- Ask ONE question at a time. Wait for the answer before asking the next.
- Never present a numbered list of questions.
- Start with the most important question first — usually her actual reaction or POV on the topic.
- Aim for 3–5 questions total. Stop when you have enough to write with her voice and specific angles.
- Do NOT write any copy until Step 4.

Good questions to draw out:
- What's her actual reaction to this topic — not the surface observation, but what does it make her think that others probably aren't saying?
- What has she seen, built, or experienced that illustrates the point?
- What's a specific client example or real moment that brings it to life?
- Who is she writing this for — someone who already knows about this, or someone who's just starting to think about it?
- Where does this piece lead — is there a soft CTA, and to what?

---

## Step 4: Write the Blog Post

Write the full blog post using:
- Her answers from Step 3 as the primary source of angles and observations
- Her own words and phrasing wherever she has provided them
- Brand voice rules applied throughout — no dashes, no colons introducing subjects, no contrast-reveal structures, no staccato three-sentences, no reveal-setups
- Word count: 800–1,200 words
- Short paragraphs, natural subheadings where the length warrants them
- CTA at the end: link to contact page (yourwebtoolkit.com/contact) and/or the AI marketing systems page (https://yourwebtoolkit.com/ai-marketing-systems/)
- Source any stats or external references at the bottom

Present the blog post. Wait for approval or feedback before continuing.

---

## Step 5: Keyword Mapping

Once the blog post is approved, ask: "Do you want to map this to a keyword?"

If yes: read `SEO Strategy/Keyword Opportunities.csv`. Find keywords that match the topic — look at keyword text, volume, and difficulty. Present the top 2–3 candidates with volume and difficulty scores. Wait for Cathy to select one before continuing.

If no: skip to Step 6.

---

## Step 6: LinkedIn Article

Adapt the approved blog post for LinkedIn.

- Generate 5 headline options using the `headline-creator` skill. Present them and wait for Cathy to pick one.
- Keep the same core content and voice — minimal changes needed
- LinkedIn articles work with the same content as the blog; the main difference is the headline and the opening line framing

Present the LinkedIn article. Wait for approval.

---

## Step 7: Facebook Post

Write a shorter Facebook post based on the blog content:
- 150–250 words
- Same angles and voice as the blog
- Ends with a link CTA to the blog post
- Uses her own phrasing from the blog wherever possible — do not rewrite the angles, just compress them

Present the Facebook post. Wait for approval.

---

## Step 8: Save Everything

Once all three pieces are approved, save them to the correct locations. Do all three saves together.

### Blog post

**Airtable — Website SEO Strategy**
- Base ID: appxFaTh8wdrUZREh
- Table: Website Blogs (tblln1TvIWF1pwPF7)
- Fields to populate:
  - Type: "Blog Post"
  - Title (fldf0HUCTavw4dfiZ): H1 blog title
  - Primary Keyword (flditqxSIR9XQ56Xr): confirmed keyword (if mapped)
  - Search Volume (fldgghIEkxgZDlWQL): from CSV (if mapped)
  - Difficulty (flducAoc2z1SXgumW): from CSV (if mapped)
  - Status (fldbHRoeGBhby73vE): "Draft"
  - Related Pillar Page (fldATqcyioYyAZuL7): closest match (use typecast: true)
  - Link to Google Doc (fldvwAf8Y8gSYt5cV): Google Doc URL (created below)

**Google Doc**
- Create a Google Doc with the full blog post content including meta title, meta description, all body copy, FAQs if included, and internal/external link notes
- Use the H1 as the document title
- After creating, copy the Google Doc URL into the Airtable record above

### LinkedIn article

**Airtable — Content for 2026**
- Base ID: appcNLyoNspCp5AC2
- Table: Content (tbliPVBb8lRJGmvTS)
- Fields to populate:
  - Hook/Subject Line (fldCvYcmSFGxzM7S5): chosen headline
  - Content (fldOuQQzhsU7g6VZm): full article text
  - Status (fldQUrc34BUzz0xYz): ["Ready to post - LI"]
  - Pillar (fld3ob4dQq0BxuYoC): "Thought Leadership - Using AI to Work Smarter (Not at 100mph)"
  - Type of Post (fld9PkFYqmpu18mD2): ["linked in article"]
  - LI Article date (fld9cfe1LjiENrEkV): today's date (YYYY-MM-DD)

### Facebook post

**Airtable — Content for 2026**
- Base ID: appcNLyoNspCp5AC2
- Table: Content (tbliPVBb8lRJGmvTS)
- Fields to populate:
  - Hook/Subject Line (fldCvYcmSFGxzM7S5): opening line of the FB post
  - Content (fldOuQQzhsU7g6VZm): full FB post text
  - Status (fldQUrc34BUzz0xYz): ["Ready to post FB"]
  - Pillar (fld3ob4dQq0BxuYoC): "Thought Leadership - Using AI to Work Smarter (Not at 100mph)"
  - Type of Post (fld9PkFYqmpu18mD2): ["long form content"]
  - FB Personal Profile date (fld0F11Nv1IUZyulc): today's date (YYYY-MM-DD)

---

## Key Rules

- Never ask "which brand?" — always Your Web Toolkit
- Ask questions one at a time, never as a list
- Do not expand a draft or seed idea without first asking questions to surface Cathy's own angles
- The blog post should be built from her answers, not from AI assumptions
- Always read the writing examples file (loaded via brand-voice) before writing
- The authority piece is not salesy — it establishes expertise and ends with a soft CTA only
