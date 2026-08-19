---
name: instagram-carousel-creator
description: >
  Write slide copy AND build the Instagram carousel design in Canva for Cathy Topping.
  Triggers on: "carousel", "Instagram carousel", "carousel design", "build a carousel in
  Canva", "design my carousel", "multi-slide Instagram post", "visual carousel". Produces
  both the written slide copy and the Canva design in one run. For caption-only carousels
  without Canva design, use instagram-captions instead.
---

# Instagram Carousel Creator

Takes a content idea or brief and produces a complete, on-brand Instagram carousel — writing all slide copy in Cathy's brand voice, duplicating the master template in Canva, populating every slide, and returning an edit link.

## Learnings
Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply any notes to this run.

---

## Config

```
MASTER_TEMPLATE_ID: DAHI5EEd8V0
```

This template is never edited directly. A fresh copy is created for each run.

---

## Step 1 — Intake

The topic or idea is already provided (from Airtable, a brief, or the user). Do not ask for it again.

Ask only:

1. **CTA on the final slide** — what should people do? (e.g. "save this", "DM me [word]", "link in bio", "book a call")
2. **Offer to reference** — which offer is this connected to, if any?
   - AI Growth Lab (done-with-you community for coaches)
   - Copywriter in Your Pocket (copywriting products and tools)
   - Custom Quiz Build (done-for-you quiz funnel)
   - Funnel Builds (done-for-you funnel)
   - AI Momentum Session (1:1 strategy session)
   - None — general content

Wait for both answers before proceeding.

---

## Step 2 — Load Brand Voice

Invoke the `brand-voice` skill before writing any copy. Apply Cathy's voice throughout — direct, warm but not gushing, honest, practical, occasionally self-deprecating, human. No em-dashes, no hollow affirmations, UK spelling.

If an offer was specified, also read the relevant file from `offers/`:
- AI Growth Lab → `offers/offer-ai-growth-lab.md`
- Copywriter in Your Pocket → `offers/offer-copywriter-in-your-pocket.md`
- Custom Quiz Build → `offers/offer-custom-quiz-build.md`
- Funnel Builds → `offers/offer-funnel-builds.md`
- AI Momentum Session → `offers/offer-ai-momentum-session.md`

---

## Step 3 — Read Template Structure

Call `get-design-content` with:
- `design_id`: `DAHI5EEd8V0`
- `content_types`: `["richtexts"]`

This returns the placeholder text from all slides. Use it to determine:
- How many slides the template has (the master has 8 pages)
- Which elements are headlines vs. body copy (infer from placeholder text length and content)

Note: `get-design-content` does **not** return `element_id` values. Element IDs are obtained from the `start-editing-transaction` response in Step 6 — map them by `page_index` to match each slide.

Do not start an editing session on the master template.

---

## Step 4 — Write Slide Copy

Write copy for each slide based on the detected structure. Keep content slides tight — carousels are read quickly, on a phone.

**Slide 1 — Cover**
Bold hook headline that earns the swipe. Opens a loop, names a tension, or makes a claim the reader wants to understand. Plus one subline that deepens the hook.

**Slides 2 to N-1 — Content slides**
Each slide: one short headline + 2–3 punchy lines. Max ~30 words per slide. Each slide should stand alone as a micro-insight — the reader should feel something or learn something from that one screen.

**Slide N — CTA slide**
CTA headline that pays off the carousel's promise. One specific action. No vague "follow for more."

Present the full slide plan clearly (e.g. "Slide 1:", "Slide 2:", etc.) mapped to each element. **Wait for approval before proceeding to Canva.**

---

## Step 5 — Duplicate the Template

Once copy is approved, call `merge-designs` with:
- `type`: `"create_new_design"`
- `title`: `"Carousel — [topic-slug] — [YYYY-MM-DD]"`
- `operations`: one `insert_pages` operation with `source.type: "design"`, `source.design_id: "DAHI5EEd8V0"`, and `source.page_numbers: [1, 2, 3, 4, 5, 6, 7, 8]`

Always specify `page_numbers` explicitly. Omitting it only copies page 1 due to a known API bug.

Verify the result has `page_count: 8`. Store the returned design ID as `NEW_DESIGN_ID`.

---

## Step 6 — Populate the Slides

**6a — Start the transaction**

Call `start-editing-transaction` with `NEW_DESIGN_ID`. The response returns `richtexts` with `element_id` and `page_index` for every text element across all 8 pages. Use `page_index` to map elements to the correct slide:
- `page_index: 1` → cover slide (Slide 1 copy)
- `page_index: 2–7` → content slides (Slides 2–7 copy)
- `page_index: 8` → CTA slide (Slide 8 copy)

Identify which element on each page is the headline (larger, shorter placeholder) and which is the body (smaller, longer placeholder).

**6b — Replace text (bulk)**

Call `perform-editing-operations` with all `replace_text` operations in a single bulk call — one operation per text element across all pages. Pass `page_index: 1` and the full `pages` array from the transaction response.

**6c — Auto-fix overflow**

After `perform-editing-operations` returns, check every text element in the response for overflow:
- If `top + height > 1080` (the footer bar start), the text is overflowing the visible area
- For each overflowing element: calculate `scale = (1080 - top) / height` and apply `format_text` with `font_size` reduced to `round(current_font_size × scale)` (minimum 12px). Use 48px as the assumed body font size and 72px for headlines if the current size is unknown.
- Send all overflow fixes in a single `perform-editing-operations` call
- If any element still overflows after the fix, reduce by a further 10% (one retry only)

**6d — Commit**

Call `commit-editing-transaction` to save.

---

## Step 7 — Present Result

Call `get-design` with `NEW_DESIGN_ID` to retrieve the edit URL. Return:
- The Canva edit link for your review, adjustments, and export
- A clean slide-by-slide summary of what's on each slide

---

## Step 8 — Save to Airtable

Call `mcp__claude_ai_Airtable__create_records_for_table` with:
- Base: `appcNLyoNspCp5AC2`
- Table: `tbliPVBb8lRJGmvTS`
- Fields:
  - `Hook/Subject Line` (`fldCvYcmSFGxzM7S5`) — slide 1 cover headline
  - `Content` (`fldOuQQzhsU7g6VZm`) — the overall feed caption (2–3 sentence teaser), with the Canva edit link appended: `\n\nCanva: [edit link]`
  - `Status` (`fldQUrc34BUzz0xYz`) — "Instagram ready to post"
  - `Type of Post` (`fld9PkFYqmpu18mD2`) — "Instagram"
  - `Promotion` (`fldcIsU925uOoBuCm`) — offer name if one was selected (omit if none)

Confirm the record was saved.

---

## Feedback
After delivering the Canva link and saving to Airtable, ask:
> "Any feedback on this? A quick note helps improve next time."

If feedback is given, append to `.claude/skills/instagram-carousel-creator/learnings.md`:
```
### [DATE]
[feedback]
```
Create the file if it doesn't exist.

## Writing Rules

- **Cover earns the swipe** — if slide 1 doesn't create curiosity or name a real tension, the rest doesn't matter
- **Every slide should land on its own** — someone might screenshot slide 4; make it worth sharing
- **Max ~30 words per content slide** — tight, scannable, one idea per slide
- **No em-dashes** — use a comma, a full stop, or a line break
- **No hollow affirmations** — no "You've got this", "So powerful", "Amazing"
- **UK spelling throughout**
- **One CTA only** on the final slide — specific, not vague
