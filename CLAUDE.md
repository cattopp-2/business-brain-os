# CLAUDE.md

This file provides guidance to Claude Code when working in this repository.

---

## Client Setup

Before this system can run, four files must be populated with the client's information. Nothing else needs changing — the skills work without modification.

**Files to populate on install:**

1. `context/USER.md` — who the client is, their brand, their goals
2. `context/ceo-north-star.md` — their strategic north star and 90-day priorities
3. `brand-context/icp.md` — their ideal customer profile
4. `brand-context/voice-profile.md` — their brand voice (run `mkt-brand-voice` to generate this)
5. `offers/` — one file per offer they sell

Once those are in place, the system is ready to use.

---

## Session Start — Read These First

At the start of every session, complete these steps in order before doing anything else:

**Step 1 — Read context files**

1. **`context/SOUL.md`** — how to behave, what to prioritise, working rules
2. **`context/USER.md`** — who the client is, their technical level, communication preferences
3. **`context/ceo-north-star.md`** — their strategic north star: mission, offers, 90-day priorities, and the filter for all decisions. Read every session.
4. **`context/revenue-tracker.md`** — current income, monthly target, and pipeline. Flag if confirmed income is significantly below monthly target.
5. **`context/rhythm.md`** — standing operating procedure. Check: is today Monday (run the weekly checks)? Are any daily items overdue?
6. **`context/weekly-focus.md`** — the 2–3 strategic priorities for this week.
7. **`context/tomorrow.md`** — consolidated open threads from the last session (if it exists). Primary starting point for open threads.
8. **`context/memory/[today's date].md`** — what happened today (if the file exists)

If `context/tomorrow.md` exists and the client says "let's keep going" or "pick up where we left off", start from the open threads listed there.

**When sharing open threads: paste the full list from `tomorrow.md` verbatim — do not summarise, paraphrase, or leave items out.**

**Step 2 — Silent sync check**

After reading the context files, run these checks silently. Only report items that need attention.

**2a. Skill sync** — Scan `.claude/skills/` and compare against the Skills Architecture tables in this file. Flag any folder that isn't in the tables, or any table entry whose folder is missing. Wait for approval before editing CLAUDE.md.

**2b. Brand context staleness** — Check the last-modified date on each file in `brand-context/`. If any file has not been modified in 30+ days, flag it as potentially stale.

At the end of every session: run `/wrap-up`.

---

## What This Is

A Claude Code marketing hub that generates business content — social posts, emails, sales pages, funnels — using skills, brand voice, and audience context.

**Primary brand:** Set in `context/USER.md`. Always assume this brand unless the client explicitly says otherwise.

---

## Skills Architecture

Skills live at `.claude/skills/` and are available to all projects under this folder.

### How skills connect

`brand-voice` is the foundation. Every other copy skill invokes it first. It loads brand voice rules and — once the brand/audience is confirmed — reads the relevant audience language file from `brand-context/`.

### Content Intelligence System (main workflow)

| Skill / Command | Purpose |
|---|---|
| `content-idea-extractor` / `/content-ideas` | Read a transcript, doc, or Google Doc → extract 10–15 ideas → approve → save to Airtable (optional) |
| `content-router` / `/content-router` | Type an idea or pick one → choose format → routes to the right skill automatically |

### Copy skills

| Skill | Purpose | Templates |
|---|---|---|
| `sales-page-writer` | Full sales/opt-in pages | 8 offer types |
| `email-sequence-writer` | Full email sequences | 5 types |
| `social-post-writer` | Facebook/LinkedIn posts | 22 copy frameworks |
| `authority-piece` | Blog post + LinkedIn article + Facebook post from a single topic | n/a |

### Platform-specific skills

| Skill | Purpose |
|---|---|
| `content-suite` | Full content suite from a single idea — 2 FB/LI posts, key line, 4 Threads threads, email |
| `instagram-captions` | Single image or carousel captions in brand voice |
| `instagram-carousel-creator` | Write slide copy and build Instagram carousel design in Canva |
| `threads-writer` | 5–7 post Threads/Twitter thread |
| `value-bomb` | One-sentence comment CTA post that leads to DM conversations |
| `reels-creator` | Take a video transcript and produce B-roll Reels concepts |
| `repurpose-video` | Turn one YouTube video into a full week of social content |
| `video-transcript-repurpose` | Turn a video transcript into a full content suite |
| `youtube-description-creator` | Write keyword-optimised YouTube descriptions |

### Setup skills (run once during onboarding)

| Skill | Purpose |
|---|---|
| `setup-user-profile` | Interview skill — asks questions and writes `context/USER.md` from your answers |
| `setup-north-star` | Interview skill — asks questions and writes `context/ceo-north-star.md` and `context/revenue-tracker.md` |
| `setup-brand-voice` | Guides you through collecting writing samples, then runs `mkt-brand-voice` to generate your voice profile |
| `setup-icp` | Interview skill — asks questions and writes `brand-context/icp.md` and your first audience language file |
| `setup-brand-stories` | Collects brand stories and testimonials, compiles `story-bank.md` and `testimonials.md`, updates ICP and voice profile |

### Strategic skills

| Skill / Command | Purpose |
|---|---|
| `ceo-check` / `/ceo-check` | Check any task or decision against your CEO north star |
| `blog-weekly-review` / `/blog-weekly-review` | Monday morning blog brief — pipeline snapshot, rank movements, next keyword candidates |
| `end-of-day` / `/end-of-day` | 5-minute end-of-day close ritual. Updates `tomorrow.md` and today's memory file. |
| `wrap-up` | End-of-session wrap-up — writes daily memory block, logs skill feedback |

### Client-facing skills

| Skill / Command | Purpose |
|---|---|
| `proposal-writer` / `/proposal-writer` | Generate a branded client proposal HTML from a discovery call transcript |

### Utility skills

| Skill | Purpose |
|---|---|
| `headline-creator` | Conversion-focused headlines for any format |
| `fascinator-bullets` | Curiosity-driven bullet points |
| `email-ideas-generator` | Mid-scene email openings |
| `email-subject-line-generator` | 10 subject line options from email content |
| `wp-publisher` / `/wp-publish` | Publish a finished blog post to WordPress as a draft |
| `sales-page-html-builder` | Convert finished sales page copy into a complete branded HTML landing page |
| `story-researcher` | Research story angles across 4 types and surface 6–10 usable hooks |
| `last30days` | Research any topic from the last 30 days on Reddit, X, and the web |

### Orchestrator skills

| Skill | Purpose |
|---|---|
| `00-slides` | Create presentations from a topic, outline, or transcript — research, structure, and HTML slides |

### Marketing strategy skills (mkt-)

| Skill | Purpose |
|---|---|
| `mkt-brand-voice` | Extract or build a brand voice — produces voice-profile.md and samples.md |
| `mkt-icp` | Build or refine an ideal customer profile through interview or research |
| `mkt-positioning` | Map the competitor landscape and generate positioning angles |
| `mkt-longform-article` | Transform a video transcript into a magazine-style editorial article |
| `str-trending-research` | Research what's trending in the last 30 days |
| `str-ai-seo` | Optimise content for AI search engines (GEO) |

### Visual and design tools (viz-)

| Skill | Purpose |
|---|---|
| `viz-image-gen` | Interactive image generation via GPT Image or Gemini — guided 6-element framework |
| `viz-excalidraw-diagram` | Generate Excalidraw diagram JSON files for workflows, architectures, and concepts |

### Tool belt (tool-)

| Skill | Purpose |
|---|---|
| `tool-humanizer` | Remove AI-generated writing patterns and restore natural human voice |
| `tool-youtube` | Fetch YouTube transcripts, video metadata, and thumbnails via yt-dlp (free, no API key needed) |
| `tool-image-search` | Search for licensable images via Openverse, Wikimedia, and Imgflip (no API key needed) |
| `tool-pdf-generator` | Generate clean, minimal PDFs from markdown content (requires pandoc) |
| `tool-fact-checker` | Systematic fact verification — standalone or in pipeline mode |
| `tool-ai-formatter` | Reformat finished long-form content into Answer-Ready structure for AI search |

### Dev and meta skills

| Skill | Purpose |
|---|---|
| `create-agent-skill` | Build a new skill for this system — scaffolds it correctly and registers it in CLAUDE.md |
| `create-agent-skills` | Guided help for creating, writing, and refining Claude Code skills |
| `meta-memory-write` | Save durable facts to context/MEMORY.md with add, replace, and remove actions |

---

## Brand Context Files

`brand-context/` holds audience language sourced from real client conversations. `brand-voice` reads these automatically once the brand is identified.

| File | Topic |
|---|---|
| `icp.md` | **Master ICP** — who their customer is, what they want, fears, real language. Read first for any promotional copy. |
| `audience-language-[topic].md` | Audience language for a specific topic or offer area. Add one file per topic. |
| `voice-profile.md` | Brand voice profile — generated by `mkt-brand-voice` from writing samples. |
| `writing-examples.md` | 5–10 examples of the client's actual writing in their natural voice. |

---

## Key Conventions

- **Brand voice is non-negotiable.** Always invoke the `brand-voice` skill before writing copy.
- **Humanizer gate on all publishable content.** Every skill that produces copy must run `tool-humanizer` as its final step before delivering output.
- **Audience language grounds the copy.** When writing for a specific topic, read the relevant `brand-context/audience-language-*.md` file.
- **Rules sections are hard constraints.** Before running any skill, check if its `skill.md` has a `## Rules` section. Apply every entry without exception.
- **Binary outputs go to `projects/`.** Non-text files (PDF, PNG, JPG, MP4, etc.) save to `projects/[project-name]/[filename]`.
- **Website and landing page HTML goes to `brand-context/00 Website/`.** Use a descriptive subfolder name.
- **Offer details live in `offers/`** — read these when writing promotional copy for a named offer.
- **Skills self-improve.** Every skill has a `learnings.md` file that captures session feedback. Read it at the start of every run.

---

## WordPress HTML — Known Fixes

Apply these rules to every HTML file built for WordPress. WordPress themes inject their own list styles which override custom CSS unless forced.

### Custom lists

Always use `!important` on both the `<ul>` and `<li>` to prevent WordPress overriding them:

```css
.custom-list {
  list-style: none !important;
  padding: 0 !important;
  margin: 0;
}
.custom-list li {
  list-style: none !important;
  position: relative;
  padding-left: 20px;
}
.custom-list li::before {
  content: '→';
  position: absolute;
  left: 0;
}
```
