---
name: seo-technical-audit
description: >
  Read Ubersuggest site audit CSVs for yourwebtoolkit.com and produce a prioritised list
  of technical SEO fixes with plain-English explanations. Triggers on: "technical audit",
  "site audit", "Ubersuggest audit", "technical SEO", "technical fixes",
  "what does the audit say", "review the site health". Requires Ubersuggest CSV export.
  Does NOT cover keyword strategy or content planning — use seo-keyword-planner or
  seo-strategy-report for those.
---

# SEO Technical Audit

Load the Ubersuggest audit CSV(s) the user selects, group issues by type and severity, and produce a prioritised fix list with plain-English explanations.

---

## Step 1: List Available Audit Files

The Ubersuggest audit reports for yourwebtoolkit.com are in:
`SEO Strategy/ubersuggest site audit yourwebtoolkit.com/`

List the files in that directory and present them to the user. Ask:

> "Which audit report(s) would you like to review? I can work through one or several — just let me know which ones to load."

Do not load any files until the user confirms which ones to use.

---

## Step 2: Load the Selected Files

Read only the files the user chose. Extract all issue rows.

Key columns to look for: page URL, issue type, issue description, severity (Critical / Warning / Notice, or similar). If column names vary across files, map them to a consistent internal format:

| Internal field | What to look for in the CSV |
|---------------|----------------------------|
| URL | page URL, address |
| Issue Type | issue, problem, check type |
| Description | description, details |
| Severity | severity, priority, level |

---

## Step 3: Group and Count Issues

Group all issues by type (e.g. broken links, missing meta description, duplicate title tag, low word count, missing H1, redirect chain, slow page speed, missing alt text).

For each issue type, count:
- How many pages affected
- Severity breakdown (how many Critical / Warning / Notice)

---

## Step 4: Output the Report

---

**Technical Audit Summary — yourwebtoolkit.com**
*Source: [filenames loaded] | [date if available in filename]*

**Issue Overview**

| Issue Type | Pages Affected | Highest Severity | Priority |
|-----------|---------------|-----------------|----------|

Sort by: Critical first, then by pages-affected count descending.

**Prioritised Fix List**

For each issue type (highest priority first):

**[Issue Type]** — [n pages affected]
- **What it is:** plain-English explanation of why this matters for SEO
- **How to fix:** specific action — e.g. "Add a unique meta description of 120–160 characters to each of these pages"
- **Pages affected:** list up to 5 URLs; if more, note "and X more"

---

**Recommended Starting Points**

3–5 highest-impact fixes to tackle first, with reasoning — note quick wins (low effort, high impact) separately from longer-term technical work.

---

## Scope

This skill processes Ubersuggest audit CSVs only. It does not analyse rank movements (use `seo-rank-tracker`), audit individual page copy (use `seo-page-optimiser`), or check strategy documents (use `seo-strategy-checker`).
