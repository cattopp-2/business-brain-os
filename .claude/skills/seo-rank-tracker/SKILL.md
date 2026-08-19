---
name: seo-rank-tracker
description: >
  Review keyword rank movements for yourwebtoolkit.com from a rank tracking CSV, surface
  the biggest opportunities and drops, and produce a prioritised action list. Triggers on:
  "rank tracker", "check rankings", "what's moved in rankings", "SEO performance",
  "rank movements", "ranking report", "what keywords have moved", "monthly SEO review".
  Does NOT audit technical SEO — use seo-technical-audit for that. Does NOT plan content —
  use seo-keyword-planner for that.
---

# SEO Rank Tracker

Load the latest rank tracking snapshot, identify what's moved, and output a clear action list — quick wins, climbers, drops, and content cluster gaps.

---

## Step 1: Load the Data

Look in `SEO Strategy/` for a file matching the pattern `Your Web Toolkit Rank Tracking*.csv`. If there are multiple, load the most recently modified one.

Extract columns: keyword, current position, previous position, position change (or calculate: current minus previous), page URL, search volume (if present).

---

## Step 2: Categorise the Movements

Group keywords into four buckets:

| Bucket | Criteria |
|--------|----------|
| **Quick Win Zone** | Currently positions 11–20 (one push could hit page 1) |
| **Big Movers Up** | Improved by 10+ positions |
| **Drops to Watch** | Fell by 10+ positions |
| **New to the List** | Keywords appearing in this snapshot for the first time |

---

## Step 3: Cross-Reference Content Clusters

Map significant movers against Cathy's two priority clusters:

- **Quiz Builder** — pillar at `/quiz-builder-for-website/` + supporting blogs
- **AI Tools for Marketing** — pillar at `/ai-tools-for-marketing/` + supporting blogs

Flag any cluster pages that are dropping, any in the quick win zone, and any cluster keywords entirely absent from the rankings (potential content gaps).

---

## Step 4: Output the Report

---

### Rank Movement Summary — [date range from the CSV]

**Quick Wins — Go After These Now**

Keywords at positions 11–20, with page URL, current position, and volume (if available). For each: one specific action — what to do to push this to page 1.

**Biggest Climbers**

| Keyword | From → To | Page URL |
|---------|-----------|----------|
| Top 5 by improvement | | |

**Drops to Monitor**

| Keyword | From → To | Page URL | Likely reason |
|---------|-----------|----------|---------------|

**Content Cluster Gaps**

Cluster keywords with no ranking or positions 50+. Note whether the page exists or if a new page/post is needed.

**Recommended Focus This Month**

A prioritised list of 3–5 specific actions based on the above. Be concrete — "optimise the H1 and meta title on /quiz-builder-for-website/ to target [keyword]", not "improve the quiz builder page".

---

## Scope

This skill reads the rank tracking CSV only — no XMLs, XLSX, or other CSVs are loaded. For a deeper keyword or content analysis, use `seo-keyword-planner`. For specific page copy fixes, use `seo-page-optimiser`.
