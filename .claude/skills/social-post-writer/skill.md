---
name: social-post-writer
description: >
  Write a complete Facebook or LinkedIn post for Cathy Topping using one of 24 proven copy
  frameworks. Triggers on: "write a post", "social post", "Facebook post", "LinkedIn post",
  "promote my offer", "share a story", "post about X", "testimonial post", "social content",
  "copy framework". Routes to the correct framework based on goal — offer posts, story posts,
  authority posts, urgency posts, voice-led and belief-shifting posts. Does NOT trigger for
  Instagram captions or Threads threads — those have their own skills.
---

<learnings>
Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply any notes to this run.
</learnings>

<outcome>
Two complete, publish-ready posts — not outlines, not drafts. Each uses a different framework. One is approximately 300 words, the other approximately 600 words. Both open with something real and specific, name the problem before the solution, have exactly one CTA, and pass the brand voice check. The user can copy-paste either directly to Facebook or LinkedIn without further editing.
</outcome>

<edge_cases>
**User doesn't know which framework** — ask what the goal is (share a story, promote an offer, shift a belief, build authority) and recommend one. Don't ask them to choose from the full list unprompted.

**User provides minimal detail** — start with what's given. Write the opening and ask for the one specific thing that's missing (the proof, the result, the story, the client). Don't stall for a full brief.

**User asks for just one post** — write both anyway. Two options at different lengths are more useful than one.

**Post feels too long after writing** — check the framework first. Some are meant to be 400–600 words (Success Story, Sweet Spot Story). If it's genuinely too long, cut the middle, not the opening or CTA.

**No CTA provided** — ask specifically: "What do you want people to do after reading this?" Don't invent a CTA.

**User asks for emojis or hashtags** — add them only if explicitly requested. Default is none.
</edge_cases>

<always_apply>
1. **Invoke brand-voice skill** before writing. Every post must pass the brand voice quick check — open with something real, no hollow affirmations, no em-dashes, no staccato rule-of-three sentences.

2. **Write the full post** — not an outline. Deliver finished, ready-to-publish copy.

3. **One CTA per post.** Don't mix DM CTAs, link CTAs, and comment CTAs in the same post.

4. **Always deliver two posts.** Pick two frameworks suited to the goal — one naturally short (Reading Their Minds, Direct Offer Short Form, Qualifier, Quick Win), one naturally long (Pain-Agitate-Solve, Sweet Spot Story, Success Story, Breakthrough Moment, Future Vision). Label them clearly: SHORT (~300 words) and LONG (~600 words). Don't use the same framework twice.

5. **No emojis, no hashtags** unless the user specifically asks.
</always_apply>

<intake>
Ask the user:

1. Which framework? (show the list below, or ask what they want to achieve and recommend one)
2. What offer is this for?
3. What's the proof, story, or specific detail to use? (testimonial, milestone, insight, client result — whatever the framework needs)
4. Who is the audience for this post? (which of Cathy's ICA segments)
5. Is there a deadline or urgency involved? (only relevant for Countdown / Last Chance)

**Work with whatever the user provides. Recommend a framework if they're not sure — ask what the goal is.**

**For story-type frameworks** (Epiphany, Sweet Spot Story, Breakthrough Moment, Success Story): before asking for the story detail in question 3, silently read `brand_context/story-bank.md`. If the Origin & Background Stories section or any recent entry fits the post's topic or goal, surface it as a suggested starting point — Cathy may not think to mention it. Don't skip question 3 if the fit is unclear; surface the suggestion alongside it.
</intake>

<frameworks>
| Goal | Framework | File |
|---|---|---|
| Launching or promoting an established offer | Signature Offer | references/signature-offer.md |
| Short, direct offer post | Direct Offer: Short Form | references/direct-offer-short-form.md |
| Detailed offer post (mini sales page format) | Direct Offer: Long Form | references/direct-offer-long-form.md |
| Validating a new offer with early beta clients | Beta Offer | references/beta-offer.md |
| Speaking directly to a ready-to-buy audience | Offer Post: Ready-to-Buy | references/offer-post-ready-to-buy.md |
| Sharing a client result or success story | Success Story | references/success-story.md |
| Sharing a personal breakthrough or insight | Breakthrough Moment | references/breakthrough-moment.md |
| Personal origin/transformation story | Epiphany | references/epiphany.md |
| Your experience meets their problem | The Sweet Spot Story | references/sweet-spot-story.md |
| Celebrating a business milestone | Milestone | references/milestone.md |
| Delivering a quick tip that leads to an offer | Quick Win | references/quick-win.md |
| Problem → agitate → solution | Pain-Agitate-Solve | references/pain-agitate-solve.md |
| Calling out what they've personally tried | What Have They Tried Before | references/what-have-they-tried-before.md |
| Calling out the popular fix that backfires | The Common Fix That's Making It Worse | references/common-fix-making-it-worse.md |
| Shifting a belief using your methodology | Show Don't Tell | references/show-dont-tell.md |
| Shifting a belief using proof (perspective pivot) | The 3Ps: Perspective Pivot With Proof | references/three-ps.md |
| Showing deep understanding of their situation | Reading Their Minds | references/reading-their-minds.md |
| Painting a picture of their possible future | Future Vision | references/future-vision.md |
| Spotlighting a feature and its real benefit | Benefits Behind the Features | references/benefits-behind-features.md |
| Qualifying ideal clients clearly | The Qualifier | references/qualifier.md |
| Sharing social proof | Testimonials | references/testimonials.md |
| End-of-launch urgency (deadline approaching) | Countdown / Last Chance | references/countdown-and-last-chance.md |
| Challenging a belief or naming a pattern — no teaching, just recognition | Direct Reframe | references/direct-reframe.md |
| Building authority through story, no hard sell — insight arrives late | Story-Led Post | references/story-led-post.md |
</frameworks>

<offer_files>
If the intake identifies a specific named offer, read the matching file before writing:

| Offer | File |
|---|---|
| Custom Quiz Build | `offers/offer-custom-quiz-build.md` |
| Done-For-You Funnel Build | `offers/offer-funnel-builds.md` |
| AI Growth Lab | `offers/offer-ai-growth-lab.md` |
| AI Momentum Session | `offers/offer-ai-momentum-session.md` |
| Claude System Build | `offers/offer-claude-system-build.md` |
| Copywriter in Your Pocket | `offers/offer-copywriter-in-your-pocket.md` |

If the post is not promoting a specific offer (story post, authority post, thought leadership), skip this step.
</offer_files>

<feedback>
After delivering the post, ask:
> "Any feedback on this? A quick note helps improve next time."

If feedback is given, append to `.claude/skills/social-post-writer/learnings.md`:
```
### [DATE]
[feedback]
```
Create the file if it doesn't exist.
</feedback>

<routing>
Once framework is confirmed, load the appropriate reference file. Follow its structure. Adapt everything to Cathy's specific offer and audience — nothing generic.
</routing>
