---
name: seo-page-optimiser
description: Audit a specific page against the SEO checklists and output a prioritised fix list with rewrite suggestions. Use this skill to optimise an existing page, check if a page is properly set up for its target keyword, or work through the SEO checklist before or after publishing.
---

# SEO Page Optimiser

Take an existing page, run it against the relevant SEO checklist, and output a prioritised fix list — with specific rewrite suggestions for any copy elements that need changing.

---

## Step 1: Intake

Ask:
1. What's the URL of the page you want to optimise?
2. Is this a **pillar/service page** or a **blog post**?

Then ask how they'd like to provide the page content:

> "Please paste the current meta title, meta description, H1, main subheadings, and a sample of the body copy. Or say 'extract it' and I'll pull it from the WordPress export."

**If they say "extract it":**

For a blog post, run this against `SEO Strategy/Your Web Toolkit Posts.xml`:

```python
import xml.etree.ElementTree as ET
import re

target_url = "PASTE_URL_HERE"

with open("SEO Strategy/Your Web Toolkit Posts.xml", "r", encoding="utf-8") as f:
    content = f.read()

items = re.findall(r"<item>(.*?)</item>", content, re.DOTALL)
for item in items:
    link = re.search(r"<link>(.*?)</link>", item)
    if link and target_url in link.group(1):
        title = re.search(r"<title><!\[CDATA\[(.*?)\]\]></title>", item)
        body = re.search(r"<content:encoded><!\[CDATA\[(.*?)\]\]></content:encoded>", item)
        print("TITLE:", title.group(1) if title else "not found")
        print("BODY:", body.group(1)[:3000] if body else "not found")
        break
```

For a pillar/service page, use `SEO Strategy/Your Web Toolkit Pages.xml` with the same pattern.

Only load the XML file when the user explicitly asks to extract. Default to pasting.

---

## Step 2: Load the Relevant Checklist(s)

- **Blog post:** read `SEO Strategy/SEO Checklist - For Humans.md`
- **Pillar/service page:** read both `SEO Strategy/SEO Checklist - For Humans.md` and `SEO Strategy/Pillar Page Optimisation Best Practices.md`

---

## Step 3: Run the Audit

Work through every checklist item. For each one:
- **Pass** — the element meets the criterion
- **Fail** — the element does not; draft a specific fix with actual suggested copy
- **Can't check** — data wasn't provided; note what's missing

For fails involving meta title, meta description, or H1: always write the full suggested replacement, not just a description of what to change.

---

## Step 4: Output the Fix List

---

**Page Audit: [URL]**
*Target keyword: [stated or inferred]*

| Priority | Element | Issue | Suggested Fix |
|----------|---------|-------|---------------|
| High | Meta title | Keyword missing | "[suggested meta title — max 60 chars]" |
| High | H1 | Doesn't include keyword | "[suggested H1]" |
| Medium | Meta description | Over 160 characters | "[suggested meta description]" |
| Low | Image alt text | Missing on hero image | "[suggested alt text]" |

**Priority key:**
- High — directly impacts rankings
- Medium — improves CTR or user experience
- Low — good practice, lower urgency

**Passing elements:** [brief list of what's already correct]

**Overall assessment:** [2–3 sentences — how well-optimised is this page, and what's the single most important fix to make first?]

---

## Scope

This skill audits one page at a time. It does not build full strategy reports (use `seo-strategy-report`), write new blog posts from scratch (use `seo-blog-writer`), or review rank movements (use `seo-rank-tracker`).
