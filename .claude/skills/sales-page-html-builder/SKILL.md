# Sales Page HTML Builder

## Purpose

Take finished sales page copy (from the `sales-page-writer` skill or any other source) and build a complete, branded HTML landing page that matches the design system used across Cathy's pillar pages. Output is a single self-contained HTML file saved to the correct folder.

---

## Trigger

When the user has finished sales page copy and asks to turn it into HTML / build the page / create the landing page.

---

## Before You Build

Read these two files first — every time, no exceptions:
- `references/design-system.md` — the full CSS to embed in the page
- `references/section-templates.md` — the HTML patterns for every section type

---

## Step 1: Ask the Offer Name

Ask: **"What's the offer name for this page?"**

This becomes:
- The folder name: `context/00 Website/01 Pillar Pages/<offer-name>/`
- The filename: `<offer-name>.html` (lowercase, hyphens not spaces)

Example: "AI Momentum Session" → folder `AI Momentum Session/` → file `ai-momentum-session.html`

---

## Step 2: Check the Folder

Before building, check whether `context/00 Website/01 Pillar Pages/<offer-name>/` already exists.

- **If it exists:** Save the HTML file into that folder (do not create a new one)
- **If it does not exist:** Create the folder, then save the file

---

## Step 3: Identify Sections in the Copy

Scan the copy for these section types. Each section type maps to a specific HTML template in `references/section-templates.md`:

| Section type | What to look for in copy |
|---|---|
| **Hero** | Page/offer title, main headline, subtitle, first CTA |
| **Pain / Problem** | "Sound familiar?", "Does this ring true?", problem statements, reader frustrations |
| **CTA strip** | Short punchy bridge line between sections, often 1–2 sentences |
| **What it is / Solution** | "Here's what [offer] is…", "This is how it works at a high level…" |
| **Case studies** | Client stories, wins, testimonials with a named person |
| **Outcomes / What changes** | "By the end…", "You'll walk away with…", "What becomes possible…" |
| **What's included / Deliverables** | Numbered list of inclusions, bullet list of what they get |
| **How it works / Process** | Numbered phases, steps, timeline |
| **Is this for you?** | Audience fit section, yes/no lists, "This is for you if…", "This is NOT for you if…" |
| **Investment / Pricing** | Price, payment options, what's included in the price |
| **FAQ** | Questions and answers |
| **Footer CTA** | Final call to action, closing line, contact/book link |

Not every page will have every section. Only include what the copy actually contains.

---

## Step 4: Assign Section Backgrounds

The page must alternate white and light-grey backgrounds so no two adjacent sections look the same.

**Fixed sections (always teal, never count toward alternation):**
- Hero
- CTA strip (any mid-page teal bridge line)
- Footer CTA

**All other sections** get their background assigned dynamically based on their position in the final sequence:
- Position 1 (first non-teal section after hero): **white**
- Position 2: **light-grey**
- Position 3: **white**
- Position 4: **light-grey**
- And so on, alternating through to the footer CTA

CTA strips interrupt the flow visually but do not reset the alternation counter — pick up where you left off after the strip.

---

## Step 5: Build the HTML

Use the CSS from `references/design-system.md` and the section patterns from `references/section-templates.md`.

**Page structure:**
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>[Offer Name] | Your Web Toolkit</title>
  [Google Fonts link]
  <style>
    [Full CSS from design-system.md]
  </style>
</head>
<body>
  [Hero section]
  [Sections in order, with dynamically assigned backgrounds]
  [Footer CTA]
</body>
</html>
```

**Rules for all copy:**
- Use the exact copy from the input — do not rewrite, summarise, or improve it
- If the copy contains `[PLACEHOLDER]` text (e.g., for images, testimonial names, prices), keep it as-is and wrap in a comment: `<!-- PLACEHOLDER: replace before publishing -->`
- All CTA buttons link to `https://yourwebtoolkit.com/contact/` unless the copy specifies a different URL

---

## Step 6: Save the File

Save to: `context/00 Website/01 Pillar Pages/<offer-name>/<offer-name>.html`

---

## Step 7: Quality Check

Run through `references/quality-check.md` before confirming delivery. Fix any issues found, then confirm: "HTML saved to `context/00 Website/01 Pillar Pages/<offer-name>/<offer-name>.html`. Ready to paste into Divi."
