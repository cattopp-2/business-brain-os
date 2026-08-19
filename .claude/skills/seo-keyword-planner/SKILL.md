---
name: seo-keyword-planner
description: >
  Map a keyword CSV into a structured content cluster — pillar page plus supporting blogs —
  with intent classification, volume prioritisation, and a publishing order. Triggers on:
  "keyword planner", "content cluster", "keyword plan", "map keywords", "pillar and blogs",
  "turn keywords into a plan", "what should I write about from this keyword list",
  "content planning from keywords". Does NOT write the content — use seo-blog-writer
  for that.
---

# SEO Keyword Planner

Turn a keyword list into a structured content cluster — pillar + supporting blogs — with intent, volume priority, and a clear publishing plan.

---

## Step 1: Intake

Ask:
1. Which topic cluster are you planning? (e.g. quiz builder, AI tools, email marketing)
2. Which keyword file to use — or paste the keywords directly?

Available keyword files in `SEO Strategy/`:
- `Keyword suggestions - quizzes.csv` — quiz builder cluster
- `ubersuggest_Quizzes (3).csv` — additional quiz keyword data

Load only the file the user names. If they paste keywords directly, use those. Do not load multiple CSVs unless explicitly asked.

---

## Step 2: Parse the Keywords

Extract: keyword, monthly search volume, competition level or difficulty score. Sort by volume descending.

Filter out keywords with fewer than 10 monthly searches — note how many were removed.

---

## Step 3: Classify Search Intent

For each keyword, assign one intent:

| Intent | Signal words | What it means |
|--------|-------------|---------------|
| Informational | what is, how to, why, guide, tips | Wants to learn |
| Commercial | best, vs, review, for [use case], top | Researching before buying |
| Transactional | hire, buy, get, service, near me | Ready to act |
| Navigational | Brand names, [tool] login | Looking for something specific |

---

## Step 4: Build the Cluster Plan

**Pillar Page**
Select the highest-volume, broadest keyword that best represents the topic. This is the pillar page keyword. Recommend the URL slug.

**Supporting Blogs**
Group remaining keywords by theme and intent. For each group, propose one blog post that targets the primary keyword and naturally includes 2–3 secondary keywords from the group. Aim for 5–8 supporting posts unless the keyword pool is smaller.

**Existing pages**
If a recommended keyword is already targeted by an existing yourwebtoolkit.com page (based on the keyword or URL pattern), mark it as "Existing page — optimise" rather than "Create new".

---

## Step 5: Output the Plan

**Pillar Page**

| Keyword | Volume | Intent | Recommended URL | Status |
|---------|--------|--------|-----------------|--------|

**Supporting Blog Posts** (sorted by volume, highest first)

| Blog Title | Primary Keyword | Volume | Secondary Keywords | Intent | Status |
|-----------|----------------|--------|--------------------|--------|--------|

Followed by a short paragraph noting: total cluster size, the 3 priority pieces to publish first (highest volume + commercial/informational intent), and any notable content gaps.

---

## Scope

This skill works with keyword CSV data only. It does not write blog posts (use `seo-blog-writer`) or build full client strategy reports (use `seo-strategy-report`).
