---
name: instagram-captions
description: >
  Write Instagram captions for Cathy Topping — single image or carousel — from a fresh idea
  or repurposed content. Triggers on: "Instagram caption", "IG caption", "caption for
  Instagram", "write my captions", "Instagram content", "caption for this post",
  "repurpose this for Instagram". Works from any source: blog post, email, Facebook post,
  or raw idea. For designed carousel slides built in Canva, use instagram-carousel-creator
  instead.
---

# Instagram Captions

Write Instagram captions that stop the scroll — single image or carousel — in Cathy's brand voice.

## Learnings
Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply any notes to this run.

---

## Step 1 — Intake

Ask:

1. **Starting point** — are we working from:
   - A new idea (describe it briefly)
   - Existing content to repurpose (blog post / email / Facebook post — paste it or give me the key points)

2. **Format** — single image caption or carousel series?
   - *Single* → one caption
   - *Carousel* → 5–7 slide captions

3. **Offer** — which offer is this for?
   - AI Growth Lab (done-with-you community for coaches)
   - Copywriter in Your Pocket (copywriting products and tools)
   - Custom Quiz Build (done-for-you quiz funnel)
   - Funnel Builds (done-for-you funnel)
   - AI Momentum Session (1:1 strategy session)
   - General / not offer-specific

4. **Call to action** — what do you want people to do? (comment, DM, click link in bio, save, tag someone — or "no CTA, just value")

Wait for the answers before writing.

---

## Step 2 — Invoke Brand Voice

Invoke the `brand-voice` skill before writing. Apply Cathy's voice throughout — direct, warm but not gushing, honest, practical, occasionally self-deprecating, human. No hollow phrases, no em-dashes, no staccato rule-of-three sentences, no affirmations. UK spelling.

If an offer was specified, read the relevant offer file from `offers/`:
- AI Growth Lab → `offers/offer-ai-growth-lab.md`
- Copywriter in Your Pocket → `offers/offer-copywriter-in-your-pocket.md`
- Custom Quiz Build → `offers/offer-custom-quiz-build.md`
- Funnel Builds → `offers/offer-funnel-builds.md`
- AI Momentum Session → `offers/offer-ai-momentum-session.md`

---

## Step 3 — Write

### Single image caption

Structure:
- **Hook** (line 1) — the first line is what shows before "more." Make it stop the scroll. A specific observation, a bold statement, or an unexpected angle. No generic openers.
- **Body** (2–5 short paragraphs or punchy lines) — the value, the story, the teaching. Use line breaks freely — Instagram reads vertically.
- **CTA** (final line) — one clear action. Or, if the user said no CTA, end with a thought that lands.
- **Hashtags** — 5–8 specific hashtags after the caption, on a new line. Mix niche (#AIforcoaches, #quizfunnel, #copywriting) with slightly broader (#contentmarketing, #digitalmarketing, #onlinebusiness). No generic (#love, #instagood).

Word count target: 150–300 words.

---

### Carousel series

Write captions for each slide:

**Slide 1 — Cover** (the swipe hook)
This appears as the visible caption AND sets up the carousel. Write a strong hook that creates curiosity or promises value. 1–2 sentences max. The reader should feel compelled to swipe.

**Slides 2–6 — Content slides**
Each slide caption: 1–3 short sentences. Clear, specific, standalone value. Number them if it helps (e.g. "2 of 7: The first thing to fix is..."). Each slide should work as a micro-lesson.

**Final slide — CTA slide**
Summary + action. What was the point? What should they do now? Keep it direct.

**Overall caption** (appears in feed under the post)
Write a 2–3 sentence caption that works as a standalone teaser: hook + what's in the carousel + CTA. This is what people see before tapping in.

---

## Step 4 — Present

Show the caption(s) clearly formatted. Offer to:
- Adjust the hook
- Try a different tone (more personal / more direct / shorter)
- Rewrite the CTA
- Generate hashtag alternatives

---

## Step 5 — Save to Airtable

Once the caption is approved, call `mcp__claude_ai_Airtable__create_records_for_table` with:
- Base: `appcNLyoNspCp5AC2`
- Table: `tbliPVBb8lRJGmvTS`
- Fields:
  - `Hook/Subject Line` (`fldCvYcmSFGxzM7S5`) — the hook line (first line of caption)
  - `Content` (`fldOuQQzhsU7g6VZm`) — full caption text
  - `Status` (`fldQUrc34BUzz0xYz`) — "Instagram ready to post"
  - `Type of Post` (`fld9PkFYqmpu18mD2`) — "Instagram"
  - `Promotion` (`fldcIsU925uOoBuCm`) — offer name if one was selected (omit if none)

Confirm the record was saved.

---

## Feedback
After delivering the caption(s), ask:
> "Any feedback on this? A quick note helps improve next time."

If feedback is given, append to `.claude/skills/instagram-captions/learnings.md`:
```
### [DATE]
[feedback]
```
Create the file if it doesn't exist.

## Writing Rules

- **Hook is everything** — if line 1 doesn't earn attention, the rest doesn't matter
- **Line breaks are your friend** — Instagram reads in short bursts, not paragraphs
- **Specific beats general** — "3 coaches in my community this month" not "many people"
- **No em-dashes** — use a comma, a full stop, or a line break instead
- **No hollow affirmations** — no "You've got this", "Amazing", "So powerful"
- **No staccato rule-of-three** — avoid "Short. Sharp. Punchy." sentence patterns
- **Voice is direct and warm** — honest, practical, occasionally self-deprecating. Not influencer-speak, not corporate, not motivational poster
