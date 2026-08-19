---
name: email-ideas-generator
description: >
  Generate email ideas and opening moments for standalone marketing emails — finds a
  compelling mid-scene opener and structures a full single email around it. Triggers on:
  "email idea", "email angle", "what to write an email about", "help me open this email",
  "email about X", "give me email angles", "I don't know how to start this email".
  Generates the opening moment first, then builds the full email structure. Does NOT trigger
  for multi-email sequences — use email-sequence-writer for those.
---

# Email Ideas Generator — Cathy Topping

## What This Skill Does
Helps Cathy find strong, specific opening moments for marketing emails, then builds a full email structure around each one. The opening moment is the hardest part — everything else follows from it.

## Learnings
Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply any notes to this run.

## Outcome
Four to six mid-scene opening moment options — each one or two sentences, specific, usable as-is. Once Cathy picks one, a complete email structure (not the full written email) is produced: opening, bridge, pivot, offer, CTA, sign-off, optional PS. The structure is ready to pass to the brand-voice skill for full writing.

## Edge Cases

**Cathy has no topic at all** — generate opening moments from her known business context: what she's building, client conversations, AI Growth Lab, observations about how people use AI. Don't ask for a topic if she's genuinely stuck — generate options to get the thinking started.

**Opening moments feel too similar** — actively vary the categories before presenting. Not all client moments. Mix in personal life, business observation, a number, a before/after contrast. The variety is the point.

**Cathy doesn't like any of the options** — ask what felt off (too formal? too sales-y? not specific enough? doesn't match the offer?). Regenerate with that steer rather than trying small variations of the same set.

**Cathy wants the full email written, not just the structure** — pass the chosen opening moment and structure to the brand-voice skill and write the email in full. This is a natural next step, not out of scope.

**Opening moment references a real event Cathy hasn't described** — ask for the specific detail rather than inventing it. A made-up detail that doesn't match reality will need rewriting.

---

## Feedback
After delivering the email structure, ask:
> "Any feedback on this? A quick note helps improve next time."

If feedback is given, append to `.claude/skills/email-ideas-generator/learnings.md`:
```
### [DATE]
[feedback]
```
Create the file if it doesn't exist.

## The Core Principle: Opening Mid-Scene

The best emails don't open with a statement about the audience, a question designed to hook, or a warm-up sentence. They open mid-scene — already inside a specific moment that's happening or just happened.

The reader is dropped into Cathy's world before they've had a chance to recognise it as a sales email.

**What a mid-scene opening looks like:**
- Something that just happened to Cathy ("I just caught myself doing a task that AI could do for me...")
- A real number or milestone with context ("I've had three separate conversations this week about the same thing...")
- Something a client said or did ("One of my AI Growth Lab members messaged me this morning...")
- A small, specific moment of friction or realisation ("I spent 40 minutes yesterday on something that should have taken five...")
- Something Cathy noticed or read that made her think ("Someone in my inbox this week told me they won't use AI because it doesn't sound human enough...")

**What it does NOT look like:**
- "Have you ever wondered..."
- "If you're a coach who struggles with..."
- "I want to talk about something important today..."
- "Content creation can be really hard..."

The test: could the first sentence appear in a text message to a friend? If yes, it's probably in the right territory.

---

## How to Run This Skill

### Step 1: Gather context

Ask Cathy:
1. What's the email broadly about, or what offer/topic does she want to lead to? (Even a rough direction is enough)
2. Anything happened recently — in her business, with a client, in the industry — that's connected to that topic? (This is optional but gold if she has something)

If she has no topic and just wants ideas, skip to Step 2 and generate prompts based on her known business context.

### Step 1a: Check the story bank (silent)

Before generating opening moments, read `brand_context/story-bank.md`. Note any entries — including the Origin & Background Stories — that connect to the topic or offer confirmed in Step 1. Use these as raw material when generating options in Step 2. If a story bank entry is a strong fit for one of the opening moments, draw on it and briefly flag the source so Cathy knows where it came from.

### Step 1b: Load offer details (if applicable)

If Step 1 identifies a specific named offer the email will lead to, read the matching file before generating opening moments:

| Offer | File |
|---|---|
| Custom Quiz Build | `offers/offer-custom-quiz-build.md` |
| Done-For-You Funnel Build | `offers/offer-funnel-builds.md` |
| AI Growth Lab | `offers/offer-ai-growth-lab.md` |
| AI Momentum Session | `offers/offer-ai-momentum-session.md` |
| Claude System Build | `offers/offer-claude-system-build.md` |
| Copywriter in Your Pocket | `offers/offer-copywriter-in-your-pocket.md` |

If the email is general (no specific offer), skip this step.

### Step 2: Generate opening moment options

Produce 4–6 specific mid-scene opening moments she could use. Each should:
- Be one or two sentences maximum
- Sound like it actually happened (or could have)
- Drop the reader into a scene, not a statement
- Be grounded in the real texture of Cathy's business life: client conversations, her own process, things she's building or testing, observations about how people use AI

Label each one with the type of scene it draws from (see categories below), so Cathy can see the range.

**Scene categories to draw from:**

*Business & work*
- **Something Cathy just did or noticed** — a task, a realisation, a mistake, a win, a thing she caught herself doing
- **A client moment** — something a client said, achieved, struggled with, or sent her (keep it real, not idealised)
- **A conversation or message** — something from her inbox, a DM, a comment, a call
- **A number or milestone** — real and specific, with the context that makes it interesting
- **An industry observation** — something she saw, read, or heard that made her think
- **A before/after contrast** — the specific thing that changed, not the abstract transformation

*Real life*
- **Personal life** — something that happened at home, with her kids, in her day-to-day. The connection to the business point doesn't need to be forced — a moment that genuinely mirrors or contrasts the topic is enough. (Sarah's food poisoning email is the template here: a real thing happened, and it happened to be a timely reminder of the business point)
- **Seasonal or time-of-year** — the specific feeling or reality of this time of year, not just a vague "it's that time again" reference. Back to school chaos, the post-Christmas slump, the end-of-year reflection that everyone's doing whether they want to or not
- **Something in the world** — a news story, a cultural moment, a shift people are noticing. Use sparingly and only when the connection is genuine, not shoehorned. The goal is to meet people where their attention already is, not to piggyback on something unrelated

### Step 3: Let Cathy choose

Once she picks an opening moment (or combines elements from a few), move to structure.

### Step 4: Build the email structure

Using the chosen opening, map out the full email in sections. Don't write it in full — provide a structural plan she can take into writing (or hand back to Claude to write in full using the brand voice skill).

**Standard structure:**

**Opening moment** (1–3 sentences)
The mid-scene drop-in. Already established.

**The bridge** (2–4 sentences)
Connect the opening moment to something the reader recognises. This is where the messy reality gets named — plainly, specifically, without dramatising it. List the situations if there are multiple. No need to frame them or comment on them.

**The pivot** (1–2 sentences)
A short, clean turn toward the offer or point. Not "that's why I built X" — something more specific to the moment.

**The offer or point** (3–6 sentences)
What Cathy has, what it does, what it looks like in practice. Concrete deliverables, not vague outcomes. This lands late — the reader should feel like they've arrived here naturally.

**The CTA** (1–2 sentences)
One thing. Direct and specific. Not "click here to find out more."

**Sign-off**
"Cheers, Cathy" or "Cathy x"

**P.S. (optional)**
Something genuinely useful: a practical note, a real aside, a caveat. Never a second CTA.

---

## Voice Reminders for This Skill

When generating opening moments and structure, always keep in mind:

- Specificity beats polish. "I spent 40 minutes on something that took Claude 30 seconds" is better than "I realised AI could save me time"
- The messy reality section should name actual situations, not describe feelings about them
- Deliberate informality is welcome — lowercase, casual asides, a slightly off-formal word — but the underlying structure should be clear and organised
- No analogies, no rule-of-three staccato, no em-dashes
- UK spelling throughout

---

## Example: Skill in Action

**Cathy says:** "I want to write an email about the Sales Page Shortcut workshop but I'm not sure how to open it."

**Skill generates opening moment options:**

1. *(Something Cathy just did)* "I tested the Sales Page Skill on a free Claude account this week. No setup, no tweaking. Just uploaded the Brand Voice Skill and asked it to write. It was annoyingly good on the first go."

2. *(A client moment)* "One of my clients sent me a draft sales page last month. She'd spent two days on it and it still didn't sound like her. We fixed it in 45 minutes using the Skills."

3. *(A conversation)* "Someone asked me this week how long it takes to write a sales page. I said: with the right setup, a couple of hours. She didn't believe me."

4. *(A number)* "I've iterated on my sales page process for two years. The version I'm teaching on Thursday is the one I wish I'd had at the start."

5. *(An observation)* "Most sales page advice assumes you're starting from scratch every time. The people I work with don't have that kind of time."

6. *(Before/after contrast)* "Before I built the Skills, writing a sales page meant a full day, a lot of second-guessing, and copy that sounded vaguely like me on a good day."

**Cathy picks option 3.**

**Skill produces structure:**

- Opening: "Someone asked me this week how long it takes to write a sales page. I said: with the right setup, a couple of hours. She didn't believe me."
- Bridge: Name what sales page writing actually feels like for most people — the blank doc, the time it takes, the version that still doesn't sound right
- Pivot: The Skills change this because they're not starting from scratch — they're built on two years of iteration
- Offer: What's inside the workshop, what they'll leave with, that it works on a free Claude account
- CTA: Link to register, with price/date
- Sign-off: Cathy x
- P.S.: Early bird closes [date] / or a note about who this is specifically for
