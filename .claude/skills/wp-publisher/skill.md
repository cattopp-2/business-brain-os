---
name: wp-publisher
description: >
  Publishes a finished blog post to yourwebtoolkit.com as a WordPress draft via the REST API.
  Triggers on: "publish this to WordPress", "send this to WordPress", "push this to the site",
  "/wp-publish". Takes a finished post (pasted content or seo-blog-writer output), extracts
  all required fields, confirms category and Yoast meta, then calls wp_publish_post.py.
---

# WP Publisher

Takes a finished blog post and publishes it to yourwebtoolkit.com as a draft via the WordPress REST API. Always publishes as a draft — Cathy reviews and publishes manually.

## Learnings
Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply notes to this run.

---

## Category IDs

| ID | Category |
|----|----------|
| 74 | AI Marketing |
| 75 | Quiz Builder |
| 72 | AI Copywriting |
| 73 | Copywriting Tips |
| 58 | Content |
| 31 | Email Marketing |

---

## Step 1 — Intake

Ask for the blog post if not already provided. Accept either:
- Pasted post content (including META TITLE / META DESCRIPTION lines if from seo-blog-writer)
- A Google Doc link (read it via the Google Docs MCP)

Once you have the content, extract these fields automatically — do not ask for them one by one:

| Field | Where to find it |
|-------|-----------------|
| `title` | The H1 heading (without the `#`) |
| `slug` | Lowercase H1, spaces replaced with hyphens, no special characters |
| `meta_title` | The META TITLE line, or generate from H1 if missing |
| `meta_desc` | The META DESCRIPTION line, or generate from intro if missing |
| `content` | Everything from the H1 onwards, converted to WordPress HTML (see Step 2) |

Then show a summary for confirmation:

```
Title:       [title]
Slug:        [slug]
Meta title:  [meta_title]
Meta desc:   [meta_desc]
Category:    [suggested category name] (ID [n])
```

For category: pick the best match from the list above based on the post topic. State your choice and the reason in one line.

Wait for confirmation or corrections before proceeding.

---

## Step 2 — Convert to WordPress HTML

Convert the Markdown content to clean WordPress HTML:

- `# Heading` → `<h1>Heading</h1>` (only one H1 — the post title)
- `## Heading` → `<h2>Heading</h2>`
- `### Heading` → `<h3>Heading</h3>`
- Paragraphs → wrapped in `<p>` tags
- `**bold**` → `<strong>bold</strong>`
- `*italic*` → `<em>italic</em>`
- `[text](url)` → `<a href="url">text</a>`
- Horizontal rules (`---`) → omit (used as section dividers in the skill output, not content)
- Lines starting with `**Q:**` (FAQ section) → keep as `<p><strong>Q: ...</strong><br>A: ...</p>`
- Do NOT include the META TITLE or META DESCRIPTION lines in the content — those are Yoast fields only
- Do NOT include INTERNAL LINKS or EXTERNAL LINKS suggestion blocks in the content

---

## Step 3 — Write the JSON and publish the post

1. Write the post data to `scripts/post_data.json`:

```json
{
  "title": "...",
  "content": "...",
  "slug": "...",
  "meta_title": "...",
  "meta_desc": "...",
  "categories": [74],
  "status": "draft"
}
```

2. Run the publish script:

```
python "C:\Users\catto\Dropbox\02 AI Solutions\scripts\wp_publish_post.py" "C:\Users\catto\Dropbox\02 AI Solutions\scripts\post_data.json"
```

3. Report the result:

```
Draft created on yourwebtoolkit.com
ID:  [id]
URL: [url]

Review and publish at: https://yourwebtoolkit.com/wp-admin/post.php?post=[id]&action=edit
```

---

## Step 4 — Featured Image

If the Airtable record has an Images attachment field with images, offer to generate or source a featured image:
> "Do you want me to create a featured image for this post? I can generate one — just say yes and describe any preferences, or leave it to me."

If Cathy says yes, generate an image via the `viz-image-gen` skill, then upload it to WP media library and set it as `featured_media` on the post.

If images are already attached to the Airtable record, upload the most suitable one (largest dimensions, or one named like a featured image) as the featured image.

---

## Step 5 — FAQ Schema

If the source content includes a FAQ schema block, remind Cathy to add it manually:

> "FAQ schema is in the Google Doc. In WP admin: Code Snippets > Add New > set scope to HTML > paste the schema block > set location to Insert After Content > save inactive. Activate once the post is live."

If no FAQ schema is present, skip this step silently.

---

## Step 6 — Update Airtable after review

Once Cathy confirms she's checked and is happy with the post, update the Airtable record in the Website SEO base (base ID: appxFaTh8wdrUZREh, table: Website Blogs, tblln1TvIWF1pwPF7):

| Field | Value |
|-------|-------|
| `fld2b7yQNkD5ZbXUh` (URL) | The live post URL |
| `fldYSsN8WvT8Cn3ZK` (Publishing Date) | Today's date |
| `fldbHRoeGBhby73vE` (Status) | "Published" |

Prompt: "Once you've reviewed the draft and are happy, let me know and I'll update the Airtable record with the URL, date, and status."

---

## Rules

- Always publish as `"status": "draft"` — never publish live without Cathy explicitly asking
- Always confirm fields before publishing — never skip Step 1
- If meta title or meta description are missing from the source content, generate them rather than leaving them blank. Meta title ≤60 chars, meta description ≤160 chars, keyword in both.

---

## Feedback
After completing, ask:
> "Any feedback on this? A quick note helps improve next time."

If feedback is given, append to `learnings.md` in this skill's folder:
```
### [DATE]
[feedback]
```
