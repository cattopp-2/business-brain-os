---
name: video-transcript-repurpose
description: Takes a video transcript and turns it into a full content suite for Erika Chalkley / Your Right To Be — SEO blog post, Facebook posts, Instagram carousel captions, a standalone marketing email, and three Canva visuals (IG carousel, single post graphic, blog featured image). Saves all outputs to a dated local folder. Use this skill when the user has a video transcript and wants to repurpose it across all channels in one workflow.
---

# Video Transcript Repurpose

Takes a video transcript and produces a complete, channel-ready content suite:

- SEO blog post
- Two Facebook posts (Direct Reframe + Story-Led)
- Instagram carousel captions
- One standalone marketing email
- Three Canva designs (IG carousel, single post graphic, blog featured image)
- All files saved to `Content\[topic-slug]-[YYYY-MM-DD]\`

Follow the steps in order. Show progress at each step. Do not skip ahead.

---

## Step 1 — Receive Transcript

If the transcript has not already been provided, ask:

> "Paste the video transcript below, or give me the file path and I'll read it."

If a file path is given, read the file using the Read tool. Once the transcript is in hand, proceed immediately to Step 2 without asking further questions.

---

## Step 2 — Analyse the Transcript

Read the full transcript carefully. Silently extract all of the following:

- **`topic-slug`** — lowercase-hyphenated label for the folder (e.g. `boundaries-at-work`, `winter-rest-ritual`, `somatic-grief-practices`)
- **Main theme** — one sentence: what is this video fundamentally about?
- **5–7 key insights** — specific, standalone points drawn from the transcript; each will become a carousel slide. Use the transcript's actual language where possible.
- **Best quote** — the single most quotable sentence from the transcript (verbatim or very lightly edited for clarity)
- **Target keyword** — the most likely SEO search term someone would use to find this content
- **Email hook angle** — a specific real moment, image, or observation from the transcript that could open a marketing email mid-scene (1–2 sentences)

Present the analysis clearly:

> **Topic slug:** [slug]
> **Main theme:** [one sentence]
>
> **Key insights:**
> 1. [insight]
> 2. [insight]
> 3. [insight]
> 4. [insight]
> 5. [insight]
> *(add more if needed)*
>
> **Best quote:** "[quote]"
>
> **Target keyword:** [keyword]
>
> **Email hook:** [1–2 sentences — the specific moment from the transcript]
>
> Does this capture the video accurately? Any adjustments before I start generating content?

Wait for confirmation or corrections before continuing.

---

## Step 3 — Create Output Folder

Create the output folder at:
```
C:\Users\catto\Dropbox\00 Clients\Erika\Content\[topic-slug]-[YYYY-MM-DD]\
```

Save a copy of the transcript to `transcript.md` in that folder.

Tell the user:
> "Output folder created at `Content\[topic-slug]-[YYYY-MM-DD]`. I'll save each piece there as we go. Starting with the blog post."

---

## Step 4 — Blog Post

Read `brand_context/voice-profile.md` and `brand_context/samples.md` — samples.md includes a full blog post showing how Erika's voice moves in long-form. Match that texture.

Invoke the **`seo-blog-writer`** skill with:
- Target keyword from Step 2
- Angle/hook: the main theme from Step 2
- Source material: the transcript — use its specific language, examples, and insights throughout

Follow the full seo-blog-writer process (structure plan → approval → full post → E-E-A-T check).

Once the post is final, save the complete output (including meta title, meta description, H1, all H2s, FAQ, and link suggestions) to:
```
Content\[topic-slug]-[YYYY-MM-DD]\blog-post.md
```

Tell the user: "Blog post saved. Ready for Facebook posts?"
Wait for confirmation before continuing.

---

## Step 5 — Facebook Posts

Read `brand_context/voice-profile.md` and `brand_context/samples.md`.

Produce two Facebook posts from the transcript. Each run produces one of each style.

**Style 1 — Direct Reframe**
- Opens with a sharp observation or reframe drawn directly from the transcript
- Short paragraphs, every line earns its place
- Builds the point from the video's core insight
- Optional soft CTA at the end (save for later, comment below, DM for details)
- No em-dashes. UK spelling. No hollow affirmations.

**Style 2 — Story-Led**
- Opens mid-scene in a real personal moment or observation connected to the transcript topic
- Lets the story breathe for several paragraphs before arriving at the insight
- The offer or point lands late and feels earned, not forced
- CTA is casual and low-pressure
- Conversational asides in brackets are natural here

Voice: embodied, feminist, warm, direct. Reflects Erika's world — somatic, body-led, culturally-contextual. Not hustle. Not corporate wellness.

Present both posts for review. After approval, save to:
```
Content\[topic-slug]-[YYYY-MM-DD]\facebook-posts.md
```

Wait for confirmation before continuing.

---

## Step 6 — Instagram Captions

Read `brand_context/voice-profile.md` and `brand_context/samples.md`.

Write carousel captions using the 5–7 key insights from Step 2. Format:

**Slide 1 — Cover**
Bold hook that earns the swipe. Names a tension or opens a loop. Plus one subline that deepens it.

**Slides 2 to N-1 — Content slides**
One insight per slide. Short punchy line(s) with space between them. ~30 words max. Each slide should stand alone as a micro-insight.

**Final slide — CTA slide**
Pays off the carousel's promise. One specific action — not "follow for more."

**Overall feed caption** (what appears under the post in feed)
2–3 sentences: hook + what's in the carousel + CTA. Works as a standalone teaser.

**Hashtags**
5–8 specific niche hashtags after the caption. Mix niche (#somaticcoaching, #feministcoaching) with slightly broader (#womenswellbeing, #bodybasedhealing). No generic tags.

Voice: short punchy lines with space between them, often ends with a question or an invitation. Body-led language. No exclamation marks for enthusiasm.

Present for review. After approval, save to:
```
Content\[topic-slug]-[YYYY-MM-DD]\instagram-captions.md
```

Wait for confirmation before continuing.

---

## Step 7 — Email

Read `brand_context/voice-profile.md` and `brand_context/samples.md`.

Write one complete standalone marketing email using the email hook angle from Step 2.

**Opening moment** (1–3 sentences)
Mid-scene drop-in. Already in the transcript. The reader is inside a specific moment before they've registered it as a marketing email.

**The bridge** (2–4 sentences)
Connect the opening to what the reader recognises. Name the real tension plainly — specific situations, not feelings about them.

**The pivot** (1–2 sentences)
Short, clean turn toward the offer or point.

**The offer or point** (3–6 sentences)
What Erika has, what it does, what it looks like in practice. Concrete deliverables. Lands late — feels earned.

**CTA** (1–2 sentences)
One action. Specific and direct. Not "click here to find out more."

**Sign-off**
"Warmly, Erika" or "Erika x"

**P.S.** (optional)
A practical note, a genuine aside, or a caveat. Never a second CTA.

Voice: like a letter to a trusted circle — personal, reflective, story-led. UK spelling. No em-dashes.

Write the email in full (not as a structural outline). Present for review. After approval, save to:
```
Content\[topic-slug]-[YYYY-MM-DD]\email.md
```

Wait for confirmation before continuing.

---

## Step 8 — Canva Visuals

Tell the user: "Moving to Canva now — I'll build all three designs and give you edit links."

Create `Content\[topic-slug]-[YYYY-MM-DD]\canva-links.md` now and add each URL as designs are completed.

Read `brand_context/voice-profile.md` and `brand_context/samples.md` before writing any copy for the designs.

---

### 8a — Instagram Carousel (CSV for Canva Bulk Create)

Generate a CSV so Erika can paste it into Canva's Bulk Create feature and have every slide populated from her brand template automatically.

1. Using the carousel copy approved in Step 6, build the CSV. One row per slide:

| Column | What goes in it |
|--------|----------------|
| `slide_number` | 1, 2, 3… |
| `hook` | The bold headline for that slide (cover: hook line; content slides: insight headline; CTA slide: CTA line) |
| `body` | Supporting copy (~30 words max). Leave blank for cover and CTA slides. |
| `caption` | Full feed caption — populate on row 1 only, leave blank for all other rows |
| `hashtags` | Hashtags — populate on row 1 only, leave blank for all other rows |

2. Write the CSV to:
```
Content\[topic-slug]-[YYYY-MM-DD]\carousel-bulk-create.csv
```

3. Show Erika a preview of the CSV rows in a simple table so she can spot any errors before opening Canva.

4. Tell Erika:
> "CSV saved to `carousel-bulk-create.csv`. To build the carousel in Canva:
> 1. Open your Instagram carousel template
> 2. Click **Apps** in the left panel → **Bulk Create**
> 3. Upload the CSV
> 4. Map each column to the matching text layer in your template
> 5. Click **Generate** — Canva builds every slide automatically from your brand kit"

5. Append to `canva-links.md`: `**IG Carousel:** CSV → use Bulk Create in Canva`

<!--
REDACTED — Canva MCP carousel flow (restore by removing this comment block if switching back)

Note: `generate-design` produces single-page designs only — it cannot generate multi-slide carousels. Generate the cover slide, then Erika duplicates slides manually in Canva using the approved copy from Step 6.

1. Call `list-brand-kits` to retrieve Erika's Canva brand kit ID (look for "Your Right To Be 2026")
2. Call `generate-design`:
   - `query`: "Instagram carousel cover slide — [brief topic summary]"
   - `design_type`: `instagram_post`
   - `brand_kit_id`: from step 1 if found
   - `user_intent`: "Create an Instagram carousel cover slide for Erika Chalkley / Your Right To Be about [topic]"
3. Call `create-design-from-candidate` with the candidate ID returned from `generate-design` to get a real editable `design_id`
4. Call `start-editing-transaction` with the `design_id`
5. Call `perform-editing-operations` — use `replace_text` to place the Slide 1 hook copy onto the cover. Use `page_index: 1`.
6. Call `commit-editing-transaction`
7. Call `get-design` to retrieve the edit URL
8. Append to `canva-links.md`: `**IG Carousel:** [edit URL]`
9. Tell Erika: "Carousel cover created. Duplicate the slide [N] times in Canva and add the remaining slide copy from `instagram-captions.md`."

END REDACTED
-->

---

### 8b — Single Post Graphic

1. Call `generate-design`:
   - `query`: "Single branded quote card — [best quote from Step 2]"
   - `design_type`: `instagram_post`
   - `brand_kit_id`: from 8a if found
   - `user_intent`: "Create a branded quote graphic for Erika Chalkley / Your Right To Be"
2. Call `create-design-from-candidate` with the candidate ID to get a real editable `design_id`
3. Call `start-editing-transaction`
4. Call `perform-editing-operations` — insert the best quote (from Step 2) as main text and "— Erika Chalkley" as attribution
5. Call `commit-editing-transaction`
6. Call `get-design` to retrieve the edit URL
7. Append to `canva-links.md`: `**Single Post Graphic:** [edit URL]`

---

### 8c — Blog Featured Image

Note: `design_type: blog_banner` does NOT exist. Use `facebook_cover` or `poster` instead.

1. Call `generate-design`:
   - `query`: "Blog header image — [topic]"
   - `design_type`: `poster`
   - `brand_kit_id`: from 8a if found
   - `user_intent`: "Create a blog featured image for Erika Chalkley / Your Right To Be for the post: [H1 blog title from Step 4]"
2. Call `create-design-from-candidate` with the candidate ID to get a real editable `design_id`
3. Call `start-editing-transaction`
4. Call `perform-editing-operations` — insert the blog H1 title as the main headline text on the graphic
5. Call `commit-editing-transaction`
6. Call `get-design` to retrieve the edit URL
7. Append to `canva-links.md`: `**Blog Featured Image:** [edit URL]`

---

After all three designs are complete, present all three edit URLs to the user clearly.

---

## Step 9 — Summary File

Create `Content\[topic-slug]-[YYYY-MM-DD]\_summary.md`:

```markdown
# Content Suite: [Topic Slug]
Generated: [YYYY-MM-DD]

## Overview
**Topic:** [main theme — one sentence]
**Target keyword:** [keyword]

## Files in This Folder
| File | Contents |
|------|----------|
| blog-post.md | SEO blog post — [word count] words |
| facebook-posts.md | 2 Facebook posts (Direct Reframe + Story-Led) |
| instagram-captions.md | [N]-slide carousel captions + feed caption + hashtags |
| email.md | Standalone marketing email |
| canva-links.md | 3 Canva design edit links |
| transcript.md | Original transcript |

## Canva Design Links
- **IG Carousel:** [edit URL]
- **Single Post Graphic:** [edit URL]
- **Blog Featured Image:** [edit URL]
```

Tell the user:

> "All done. Everything is saved in `Content\[topic-slug]-[YYYY-MM-DD]\`. Here's what was created:"

Then show the summary table and Canva links.

---

## Writing Rules (Apply Across All Steps)

- **Read `brand_context/voice-profile.md` and `brand_context/samples.md` at each content step** — never write without checking the voice guide
- **Use the transcript's actual language** — specificity comes from the source material, not invented detail
- **No em-dashes** — use a comma, a full stop, or a line break
- **No hollow affirmations** — no "You've got this", "So powerful", "Amazing"
- **No hustle language** — no grind, scale, push through, level up, show up
- **No exclamation marks for enthusiasm** — earn it through language
- **UK spelling throughout** — honour, recognise, centre, organisation, practise (verb)
- **Short paragraphs** — often one sentence; white space is part of the writing
- **One CTA per piece** — specific, never vague
- **Approval gate after each step** — always wait for the user to confirm before moving to the next content type
