---
name: youtube-description-creator
description: Write a keyword-optimised YouTube description for Cathy Topping's @yourwebtoolkit channel. Takes a video transcript and target keyword, then produces a full description with title, bullets, timecodes, related videos, CTA snippets, and hashtags. Use this skill when the user wants a YouTube description for a new video.
---

# YouTube Description Creator

Write a complete, keyword-optimised YouTube description for a new video on the @yourwebtoolkit channel.

---

## Step 1 — Identify the Target Keyword

Ask: "What is this video about? Give me a brief description of what it covers."

Wait for the answer, then run all three checks below in parallel.

---

### Check 1 — Keyword Opportunities

Read `C:\Users\catto\Dropbox\02 AI Solutions\SEO Strategy\Keyword Opportunities.csv`.

Look for keywords that are topically relevant to the video AND have not yet been assigned to a page (the `Added to the plan` column is blank). A keyword is relevant if it matches what someone would search for to find this video.

---

### Check 2 — Existing Content in Airtable

Search the Website SEO Strategy Airtable base (`appxFaTh8wdrUZREh`, table `tblln1TvIWF1pwPF7`) for records where the Title, Primary Keyword, or Secondary Keywords are topically related to the video.

An existing post is a good match if:
- The video could logically be embedded on that page to add value for the reader
- The post's keyword is relevant to what the video covers

---

### Present findings

**If Check 2 finds a matching existing post:**
Present it as the first option:
> **Option A — Embed in existing post**
> "[Post title]" at [URL] already targets "[primary keyword]" ([search volume] searches/month, difficulty [diff]).
> Embedding the video here would strengthen that post for SEO. You could use "[primary keyword]" as your YouTube target keyword to align them.

**If Check 1 finds an unassigned keyword:**
Present it as an option (or the only option if Check 2 found nothing):
> **Option B — New keyword from your research**
> "[keyword]" — [volume] searches/month, difficulty [difficulty]. Not yet assigned to any page.

**If neither check finds anything relevant:**
> **Option C — Suggested keywords**
> Nothing in your current data matched this video topic. Based on what the video covers, here are 3 keyword options worth targeting on YouTube:
> - [suggestion 1]
> - [suggestion 2]
> - [suggestion 3]
> Note: YouTube search volumes differ from Google — these are directional suggestions, not from your data.

Show all valid options and ask Cathy to pick one before continuing.

**Once Cathy selects a keyword**, proceed to Step 2.

---

## Step 2 — Collect the Transcript

Ask for the video transcript file. Accepted formats:
   - **.sbv** (YouTube's native subtitle export) — includes exact timestamps, preferred
   - **.srt** (SubRip subtitle format) — includes exact timestamps, equally good
   - **.txt** (plain text) — no timestamps; timecodes will be estimated from content proportion

Wait for the file before proceeding.

---

## Step 3 — Write the Title

Write one keyword-optimised video title:
- Lead with the keyword or a close variation
- Specific and benefit-led — tell viewers exactly what they'll learn or see
- Under 70 characters where possible
- UK spelling, no hollow affirmations, no em-dashes

---

## Step 4 — Write the Description

Structure the description in this exact order:

### Opening paragraph
2–3 sentences. Opens with the keyword naturally. Sets up what the video covers and why it matters. UK spelling, conversational, no jargon.

### Fascinator bullets (4–5)
Describe the specific things covered in the video. Each bullet should make the viewer want to watch.

Format:
```
✅ [Specific thing they'll see or learn]
✅ [Specific thing they'll see or learn]
```

No hollow bullets like "Why this matters" or "The importance of X". Be specific — mention real tools, real steps, real outcomes from the video content.

---

## Step 5 — Append CTA Snippets

Add these sections exactly as written below (do not alter the copy):

```
Build an AI copy assistant that nails your brand voice every time
Grab The Copy Whisperer here
👉 https://copywriterinyourpocket.com/copy-whisperer

Ready to systemise your content and sales with AI? Let's plan it out
Book a one-to-one Strategy Session with me to map it out
👉 https://yourwebtoolkit.com/contact/
```

---

## Step 6 — Pull Related Videos

Visit https://www.youtube.com/@yourwebtoolkit and find 4 videos that are topically related to this video.

Format each as:
```
📹 [Video title]: [full YouTube URL]
```

List them under the heading:
```
YOU MIGHT ALSO LIKE
```

---

## Step 7 — Write Timecodes

Using the transcript, write timecodes for each major section or topic shift in the video.

Format:
```
00:00 Introduction
00:45 [Topic section]
02:10 [Topic section]
```

- **SBV or SRT file provided**: Use the exact timestamps from the file. Convert to `MM:SS` format (drop hours unless the video is over an hour). Pick the timestamp at the start of each meaningful section — not every line.
- **TXT file provided**: Estimate timecodes based on the proportion of the transcript each section occupies relative to the total length. Note "(estimated)" after each label so Cathy can verify before publishing.

Keep sections meaningful — aim for 6–10 timecodes per video, not one per minute.

---

## Step 8 — Append Hashtags

Add both hashtag sets, each on a new line:

**Short set:**
```
#claude #claudeai #chatgpt #aicopywriting #aicopywritingsoftware #aicopywritingtool #brandvoice
```

**Full set:**
```
#claude #claudeai #chatgpt #aicopywriting #aicopywritingsoftware #aicopywritingtool #brandvoice #customgpt #chatgptprompts #chatgpt4 #chatgpttutorial #chatgpttips #chatgpt5 #chatgptcourse #aicontent #aichat #aiexplained #aiforbeginners #aiprompt #aitools
```

---

## Output Format

Present the full description as one block, ready to copy-paste into YouTube Studio. Use this order:

1. Title (labelled separately above the description block)
2. Opening paragraph
3. Fascinator bullets
4. CTA snippets
5. YOU MIGHT ALSO LIKE + 4 related videos
6. Timecodes
7. Hashtags (short set first, full set below)

---

## Writing Rules

- UK spelling throughout (optimise, prioritise, colour, etc.)
- No em-dashes — use a comma or full stop
- No hollow affirmations ("Amazing!", "Game-changing")
- No emojis in the written description copy (CTA snippets already include ✅ and 👉 — keep those as-is, do not add others)
- Voice: direct, specific, warm — like showing a colleague something useful
