---
name: content-suite
description: >
  Write a full content suite from a single idea — 2 FB/LI posts, a key line, 4 Threads threads,
  and an email. Triggers on: "write a content suite", "full suite from this idea", "write content
  for this idea", "all formats for this", "suite of content". Ask for offer/promotion and CTA
  before writing. Suggest two frameworks from the thought leadership pool, confirm before writing.
  Does NOT trigger for single posts, single threads, or email-only requests — those have their
  own skills.
---

# Content Suite

Take one idea and turn it into 8 publish-ready pieces across four formats — in Cathy's brand voice.

---

## Learnings

Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply any notes to this run.

---

## Step 1 — Intake (one question at a time)

Ask these questions in order. Wait for an answer before moving to the next.

**Q1.** What's the idea and source material?
- New idea → describe it in a sentence or two, plus any voice notes, story, or source material
- From an existing piece → paste it or describe the key points

**Q2.** What offer or promotion is this connected to?
(e.g. Claude System Build, Custom Quiz Build, general authority — not for a specific offer)
If a named offer is mentioned, read the matching file from `offers/` before writing.

**Q3.** What's the CTA — what do you want people to do after reading?
(DM you, reply to the email, follow, visit a link, etc.)

---

## Step 2 — Suggest Frameworks

Based on the idea and source material, suggest two frameworks for the FB/LI posts — one that suits a tighter piece (~300 words) and one for a fuller piece (~500–600 words). Both can be any length; these are starting points, not rules.

Pick from the thought leadership pool only (listed below). State your suggestion and the one-line reason for each. Wait for Cathy to confirm or override before writing.

**Thought leadership framework pool:**

| Framework | Best for |
|---|---|
| Pain-Agitate-Solve | Problem the audience is living right now → cost of staying stuck → offer as the fix |
| Success Story | A specific client result — journey from before to after, with the strategies that made the difference |
| Breakthrough Moment | A pivotal insight or discovery — what changed and how to apply it |
| Sweet Spot Story | The overlap between your experience and their problem — you've been there |
| Epiphany | A personal transformation story — how your journey shaped the work you do |
| Reading Their Minds | Set the scene of a specific moment in their day — deep empathy before the solution |
| Future Vision | Paint a specific, achievable picture of what's possible — then the path to get there |
| Show Don't Tell | Name a common belief, shift it through methodology, show a piece of your actual method |
| Quick Win | One specific, actionable tip from client work — builds trust before the offer |
| What Have They Tried Before | Name what the client has already tried and why it didn't reach the root cause |
| The Common Fix That's Making It Worse | Call out the popular advice everyone's using — explain why it backfires |
| The 3Ps — Perspective Pivot With Proof | Shift a belief with a real client story as the evidence |
| Benefits Behind the Features | Lead with a specific feature of the offer, connect it directly to the real outcome |
| Milestone | A specific achievement — lessons from the journey + practical takeaways |

---

## Step 3 — Invoke Brand Voice

Read `.claude/skills/brand-voice/SKILL.md` before writing. Apply Cathy's voice rules to all eight pieces:
- No em-dashes
- No hollow affirmations
- No staccato rule-of-three patterns
- Open with something real and specific — not a generalisation
- Plain, direct language — thinking aloud, not polished marketing

---

## Step 4 — Write the Full Suite

Once the offer, CTA, and frameworks are confirmed, write all eight pieces in one pass. Label each clearly.

---

### A. FB/LI Posts (two posts)

**Post 1 — [Framework name] (~300 words)**
Follow the framework structure from `.claude/skills/social-post-writer/references/[framework-file].md`.
Adapt everything to Cathy's idea, offer, and audience — nothing generic.
One CTA only. No emojis, no hashtags unless asked.

**Post 2 — [Framework name] (~500–600 words)**
Follow the framework structure from `.claude/skills/social-post-writer/references/[framework-file].md`.
One CTA only. No emojis, no hashtags unless asked.

---

### B. Key Line

The single sharpest line from either post. Not a summary — the one sentence that carries the whole idea. Can be lifted verbatim or sharpened from the source.

---

### C. Threads (four threads)

Write all four using the framework structures in `.claude/skills/threads-writer/skill.md`.

Each thread: 5–7 posts, under 280 characters per post. Posts separated by a horizontal rule. No post numbers.

**Thread 1 — Credibility** ("If [problem], here's what I'd do")
Hook → credibility statement → 3 steps → CTA

**Thread 2 — Audience Call In** ("If you're [X person], follow me")
Hook → value (what they'll get) → gift (lead magnet if exists, skip if not) → one-line close

**Thread 3 — Contrarian** ("You aren't broken, [X] is — here's why")
Hook → dismantle the common belief → reframe → CTA

**Thread 4 — Results + Lesson** ("I got [result] by doing X — here's how")
Hook → the move → lesson in transferable steps → CTA

---

### D. Email (~250–300 words)

More direct than the posts — "I'm talking to you specifically."
Shorter sentences. One question somewhere in the body. Conversational sign-off (not a broadcast closing).
Use the idea's source material and voice notes directly — lift phrases where they fit.
One CTA, same as the posts.

---

## Step 5 — Save to Airtable

After delivering all eight pieces, ask: "Want to save these to Airtable?"

If yes, save to base `appcNLyoNspCp5AC2`, table `tbliPVBb8lRJGmvTS`.

Save each piece as a separate record. Set today's date on the relevant platform field (do NOT tick the posted/scheduled checkbox):
- FB/LI posts → `FB Personal Profile` (fld0F11Nv1IUZyulc) and `LinkedIn Scheduled` (fld0ccNjgI9kgaMVW)
- Threads → `Threads` (fldshgOp8XKQ7zFQr)
- Email → `Broadcast Email To Be Scheduled` (fldb0RTejwyNjC8Wj)

For each record set:
- `Hook/Subject Line` — the opening line of the piece (or subject line for the email)
- `Content` — the full text
- `Pillar` — match to the most relevant pillar

---

## Step 6 — Feedback

After delivering all pieces, ask:
> "Any feedback on this? A quick note helps improve next time."

If feedback is given, append to `.claude/skills/content-suite/learnings.md`:
```
### [DATE]
[feedback]
```
Create the file if it doesn't exist.
