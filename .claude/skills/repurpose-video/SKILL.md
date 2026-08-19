---
name: repurpose-video
description: Take a YouTube video from the Airtable YouTube Videos table and repurpose it into a full set of social content — YouTube description + 2× Facebook posts + 1× LinkedIn post + 1× Threads thread. Saves everything to Airtable with the Source Video linked, and marks the video as Repurposed.
---

# Repurpose Video

Turn one YouTube video into a full week of social content. Reads the transcript from Airtable, writes the content, saves it all back — every piece linked to the source video.

---

## Step 1 — Select a Video

List videos from the YouTube Videos table that are not yet repurposed:

- Base: `appcNLyoNspCp5AC2`
- Table: `tblLSfQ9t1jtI6g7v`

Fetch all records and filter to those where Status (`fldumq4ay2ZL6xx1w`) is NOT "Repurposed" (`seliJEQZp6OHnH6Ux`). Show as a numbered list:

```
1. [Title] — [Status]
2. [Title] — [Status]
```

Ask: "Which video do you want to repurpose?"

Wait for the answer. Note the record ID of the selected video — you'll need it throughout.

---

## Step 2 — Read the Transcript

Read the selected video's Airtable record. The transcript is in field `fldjE2dc1jiDv5tSc` (Transcript). Also read:
- `fldOuZk9GMhcAVBbt` (Title)
- `fldKJ1QGhmugMjPg2` (Target Keyword)
- `fld5MelbDqleLTuPq` (Description) — check if already written

If the Transcript field is empty, check `fld36NhGbKPlmraoG` (Transcript File Path) and read the file from that path.

If no transcript is available anywhere:
> "There's no transcript saved for this video yet. Can you paste the transcript or give me the file path?"

---

## Step 3 — YouTube Description

**If the Description field is already populated**, ask:
> "There's already a YouTube description saved for this video. Do you want to skip writing a new one, or rewrite it?"

**If Description is empty (or user wants to rewrite)**, follow the `youtube-description-creator` skill to write a full YouTube description. Read `.claude/skills/youtube-description-creator/SKILL.md` and follow it from Step 1, passing in the video title and transcript. The keyword from the Airtable record (`fldKJ1QGhmugMjPg2`) is the pre-confirmed keyword — skip the keyword selection step if it's already set.

Output the full description for review.

Ask: "Happy with the YouTube description? I'll save it and move on to the social posts."

Wait for confirmation before saving.

---

## Step 4 — Write Social Content

The brand for all content from this workflow is **Your Web Toolkit** (DFY services, AI implementation) unless the video is clearly for a different brand — check the video title and transcript to confirm.

---

### Facebook Posts 1 & 2

Read `.claude/skills/social-post-writer/SKILL.md` and follow it, using the video transcript as the source material and proof.

- Review the transcript and select two frameworks that fit the content — recommend one value/teaching framework (e.g. Quick Win, Pain-Agitate-Solve, Show Don't Tell) and one story/results framework (e.g. Breakthrough Moment, Sweet Spot Story, The 3Ps). State which frameworks you're using before writing.
- The transcript is the proof, story, and specific detail — draw real moments and insights from it, not generic copy.
- CTA: link to the video in comments, or soft DM, based on the video's goal.
- The short-framework post becomes Facebook Post 1. The long-framework post becomes Facebook Post 2.

---

### LinkedIn Post

Adapt the stronger of the two Facebook posts for a LinkedIn audience — professional framing, slightly more formal tone, same voice rules. Aim for 150–250 words. Opens with a punchy observation or counterintuitive statement, makes 2–3 clear points, ends with a question or soft CTA.

---

### Threads Thread

Write a 5–7 post Threads thread. Follow `.claude/skills/threads-writer/SKILL.md` for structure, passing the video content as the source. Keep each post under 280 characters. Make post 1 the hook, posts 2–5 the substance, final post the CTA.

---

Present all 4 pieces for review under clear headings. Ask:

> "Here's all the social content from this video. Any changes before I save to Airtable?"

Wait for confirmation (or tweaks).

---

## Step 5 — Save to Airtable

### 5a — Save the YouTube description

Update the video record with the confirmed description:

- Base: `appcNLyoNspCp5AC2`
- Table: `tblLSfQ9t1jtI6g7v`
- Record ID: [the selected video's record ID]
- Field `fld5MelbDqleLTuPq` (Description) → the full YouTube description text

After saving, output the direct link to the record:
`https://airtable.com/appcNLyoNspCp5AC2/tblLSfQ9t1jtI6g7v/[record ID]`

---

### 5b — Save social content to the Content table

Create 4 records in the Content table (`tbliPVBb8lRJGmvTS`), one per piece. Save all 4 in a single batch call.

**Fields for each record:**

| Field | ID | Value |
|---|---|---|
| Hook/Subject Line | `fldCvYcmSFGxzM7S5` | The opening line / hook of the post |
| Content | `fldOuQQzhsU7g6VZm` | Full post content |
| Type of Post | `fld9PkFYqmpu18mD2` | `["selEb69MbfmGbBmKq"]` (video) |
| Status | `fldQUrc34BUzz0xYz` | `["selacnZ9NLFaOJHHs"]` (Claude wrote first draft) |
| Source Video | `fldeRHzNZAZZFldqg` | `[{ "id": "[video record ID]" }]` |
| Notes | `fld0mRtTVW8oRLMsz` | `"Repurposed from: [video title]"` |

**For the Threads thread record only**, also set:

| Field | ID | Value |
|---|---|---|
| Threads | `fldshgOp8XKQ7zFQr` | Today's date (YYYY-MM-DD) |

The Notes field entry tells anyone browsing the Content table exactly where this post came from — useful alongside the link.

---

### 5c — Update video status to Repurposed

Update the video record:

- Field `fldumq4ay2ZL6xx1w` (Status) → `seliJEQZp6OHnH6Ux` (Repurposed)

---

## Step 6 — Confirm

> "Done. Saved 4 content pieces to Airtable, all linked to '[video title]'. YouTube description updated on the video record. The video is now marked as Repurposed.
>
> View the video record: https://airtable.com/appcNLyoNspCp5AC2/tblLSfQ9t1jtI6g7v/[record ID]
>
> Want to schedule any of these posts, or repurpose another video?"

---

## Writing Rules

- UK spelling throughout (optimise, prioritise, colour, etc.)
- No em-dashes — use a comma or full stop
- No hollow affirmations ("Amazing!", "This is game-changing")
- No staccato three-word sentences standing alone for effect
- No "So I did X. And it worked. Here's what happened." sentence rhythm
- Voice: direct, specific, warm — like telling a client something useful over coffee
