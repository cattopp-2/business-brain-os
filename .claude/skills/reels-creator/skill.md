---
name: reels-creator
description: Takes a video transcript and produces B-roll Reels concepts for Erika Chalkley / Your Right To Be — hook concepts, scroll-stop text overlays, captions in Erika's voice, B-roll direction notes, and a CSV for Canva Bulk Create. Use this skill when Erika has a transcript and wants to turn it into Reels content.
---

# Reels Creator

Takes a video transcript and produces everything needed to build B-roll Reels:

- 5–8 hook concepts pulled from the transcript
- Scroll-stop text overlay copy for each (3–6 words on screen)
- Caption in Erika's voice
- B-roll direction note (what kind of footage fits)
- CSV for Canva Bulk Create — paste in, hit generate, slides fill themselves

All output saved to `Content\[topic-slug]-[YYYY-MM-DD]\`.

---

## Step 1 — Receive Transcript

If a transcript has not already been provided, ask:

> "Paste the transcript below, or give me the file path and I'll read it."

Read the file if a path is given. Once the transcript is in hand, proceed immediately to Step 2.

---

## Step 2 — Extract Hook Concepts

Read `brand_context/voice-profile.md` and `brand_context/samples.md`.

Read the transcript carefully. Extract 5–8 hook concepts. Each hook must:

- Come directly from something in the transcript — a tension named, a moment described, a reframe landed
- Lead with conflict, contradiction, or a thing people assume that isn't true
- Be specific to Erika's world: somatic, feminist, body-led, culturally-aware
- Work as a scroll-stop opener — the viewer sees 3 seconds of B-roll and this text and decides to watch

For each hook concept, note:
- The core idea (one sentence)
- Where it lives in the transcript (a quote or paraphrase)

Present the list for review:

> **Hook concepts:**
> 1. [core idea]
> 2. [core idea]
> *(etc.)*
>
> Any you'd cut or swap before I write them up?

Wait for confirmation before continuing.

---

## Step 3 — Write Reels Copy

For each approved hook concept, produce:

**Text overlay** (what appears on screen over the B-roll)
- 3–6 words maximum
- Bold, direct, no softening
- Reads in under 2 seconds
- No exclamation marks. No hustle. No hollow affirmations.
- Examples of the right register: "Your body already knew." / "Rest is not a reward." / "This is what burnout looks like."

**Caption** (what goes in the post caption below the Reel)
- Opens mid-scene or with the hook developed one step further
- 3–5 short paragraphs
- Voice: embodied, feminist, warm — like a woman thinking aloud who has done the work herself
- One CTA at the end. Specific, not vague.
- No em-dashes. UK spelling. No hollow affirmations.

**B-roll direction** (a note for Erika on what footage fits)
- One or two sentences describing the visual feel
- Examples: "Slow hand movement, close-up — pouring tea, writing, touching fabric." / "Walking outdoors, unhurried. Face optional." / "Still shot of a body at rest — lying down, seated, looking away from camera."

Present all reels for review, one at a time or as a full set — ask Erika which she prefers:

> "I have [N] Reels written. Would you like to review them all at once, or one at a time?"

After approval, save the full set to:
```
Content\[topic-slug]-[YYYY-MM-DD]\reels-copy.md
```

Format in that file:

```
# Reels Copy — [topic-slug]

---

## Reel [N]

**Text overlay:** [overlay text]

**Caption:**
[full caption]

**B-roll direction:** [note]

---
```

---

## Step 4 — Generate CSV for Canva Bulk Create

Build a CSV with one row per Reel:

| Column | Content |
|--------|---------|
| `reel_number` | 1, 2, 3… |
| `overlay_text` | The text overlay (3–6 words) |
| `caption` | Full caption text |
| `hashtags` | 5–8 niche hashtags — mix specific (#somaticcoaching, #feministcoaching) with slightly broader (#womenswellbeing, #bodybasedhealing). No generic tags. |

Show Erika a preview of the CSV rows as a table before saving.

Save to:
```
Content\[topic-slug]-[YYYY-MM-DD]\reels-bulk-create.csv
```

Tell Erika:
> "CSV saved to `reels-bulk-create.csv`. To build the Reels text overlays in Canva:
> 1. Open your Reels template (the one with your B-roll text overlay layout)
> 2. Click **Apps** → **Bulk Create**
> 3. Upload the CSV
> 4. Map `overlay_text` to your text layer
> 5. Click **Generate** — Canva builds a slide per row from your brand kit"

---

## Step 5 — Summary

Tell Erika:
> "Done. Saved to `Content\[topic-slug]-[YYYY-MM-DD]\`:"

| File | Contents |
|------|----------|
| `reels-copy.md` | [N] Reels — overlay text, captions, B-roll direction |
| `reels-bulk-create.csv` | CSV for Canva Bulk Create |

---

## Writing Rules

- Read `Brand Assets/brand-voice.md` before writing any copy
- Use the transcript's actual language — specificity comes from the source, not invention
- No em-dashes. UK spelling. No exclamation marks for enthusiasm.
- No hollow affirmations: "You've got this", "So powerful", "Amazing"
- No hustle language: grind, scale, push through, level up, show up
- Short punchy lines — white space is part of the writing
- One CTA per caption. Specific, never vague.
