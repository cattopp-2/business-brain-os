---
name: content-router
description: >
  Route a content idea to the correct writing skill — blog, Facebook/LinkedIn post,
  Facebook-specific style, email, Threads thread, or Instagram captions. Triggers on:
  "content router", "I want to write about X", "what should I do with this idea",
  "repurpose this", "turn this into a post/email/blog", "write something from my Airtable",
  "I've got an idea". Pulls ideas from Airtable or takes them directly. Handles SEO keyword
  selection automatically for blogs. Does NOT write the content itself — it routes to the
  right skill and passes context through.
---

# Content Router

Pick an idea. Choose a format. Get the right skill for the job — without having to remember which skill to call.

## Learnings
Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply any notes to this run.

## Outcome
The user is routed to the right skill with their idea and all gathered context already passed through. No repeated intake questions — the idea travels with the routing. If the format is blog, the keyword step is handled before handoff. After the content is written, the user is offered the option to repurpose it into another format.

## Edge Cases

**Airtable connection fails** — ask the user to type the idea instead. Don't block the session on a connectivity issue.

**User's idea is vague** — ask for one sentence: what is this content trying to do or say? Clarify before routing. A vague brief produces vague output.

**User picks blog but has no keyword** — go straight to seo-blog-writer Step 0 (keyword search from the opportunities CSV). Don't skip the keyword step.

**User wants multiple formats from one idea upfront** — write the first format in full first. Offer additional formats after delivery, not before. Trying to route to multiple skills at once creates fragmented output.

**User wants to repurpose something very long** — summarise the key points of the source material and confirm with the user before routing to the writing skill.

**User isn't sure which format** — ask: "Is this more of an idea you want to explore (blog/email) or something you want to promote quickly (social post)?" That usually narrows it.

---

## Step 1 — Source of the Idea

Ask:

> "Are we starting from:
> 1. An idea in your Airtable queue (Ready to draft)
> 2. An idea you'll describe now
> 3. Existing content you want to repurpose (paste it or describe it)"

Wait for the answer.

**If Airtable:**
List the current "Ready to draft" records using `mcp__claude_ai_Airtable__list_records_for_table`:
- Base ID: `appcNLyoNspCp5AC2`
- Table ID: `tbliPVBb8lRJGmvTS`
- Filter by Status = "Ready to draft" (`selUjgf122gznExRG`)
- Show: Hook/Subject Line, Content, Promotion fields
- Present as a numbered list

Ask: "Which one do you want to work on?" Wait for selection.

**If typed idea:**
Ask for a one-sentence description of the idea and the brand/offer it serves (if relevant).

**If repurposing:**
Ask them to paste the source content, or describe its key points. Note what format it currently is (blog / email / post) — this helps the output skill adapt appropriately.

---

## Step 2 — Format

Ask:

> "What format do you want?
> 1. Blog post (I'll find the right keyword first)
> 2. Facebook/LinkedIn post
> 3. Facebook-specific style (Short & Punchy or Longer & Conversational)
> 4. Email (single email or full sequence?)
> 5. Threads thread
> 6. Instagram captions (single image or carousel?)"

Wait for the answer.

---

## Step 3 — Route

### Blog post

Before writing, find the best keyword for this topic.

Read `SEO Strategy/Keyword Opportunities.csv`. Look for keywords that match or relate to the idea topic — check the keyword text against the idea description.

Present the top 2–3 matches:

> "Here are the best keyword matches from your opportunities list:
> 1. [keyword] — [monthly volume] searches/month, difficulty [score]
> 2. [keyword] — [monthly volume] searches/month, difficulty [score]
> 3. [keyword] — [monthly volume] searches/month, difficulty [score]
>
> Which one fits best? Or do you want to use a different keyword entirely?"

Wait for confirmation.

Once the keyword is confirmed, proceed as the seo-blog-writer skill from Step 2 onward (structure planning → writing → E-E-A-T check). Read `.claude/skills/seo-blog-writer/SKILL.md` and follow it from Step 2, passing in the confirmed keyword and the idea as the angle/context.

---

### Facebook/LinkedIn post

Read `.claude/skills/social-post-writer/SKILL.md` and follow it. Pass the idea as the starting point — skip any intake questions that are already answered from Step 1.

---

### Facebook-specific style

Read `.claude/skills/facebook-post-styles/SKILL.md` and follow it. Pass the idea as the starting point.

---

### Email

Ask: single email or full sequence?

- **Single email** → Read `.claude/skills/email-ideas-generator/SKILL.md` and follow it with the idea as the topic.
- **Full sequence** → Read `.claude/skills/email-sequence-writer/SKILL.md` and follow it. Ask which sequence type if not clear from context.

---

### Threads thread

Read `.claude/skills/threads-writer/SKILL.md` and follow it. Pass the idea as the starting point — skip intake questions already answered.

---

### Instagram captions

Ask: single image or carousel?

Read `.claude/skills/instagram-captions/SKILL.md` and follow it. Pass the idea as the starting point — skip intake questions already answered.

---

## Step 4 — After Writing

Once the content is written, offer:

> "Want to take this idea somewhere else? I can turn it into:
> - A [format not yet used]
> - Any other format from the list above"

This turns one idea into multiple pieces without starting over.

---

## Feedback
After routing and the content is delivered, ask:
> "Any feedback on this? A quick note helps improve next time."

If feedback is given, append to `.claude/skills/content-router/learnings.md`:
```
### [DATE]
[feedback]
```
Create the file if it doesn't exist.

## Notes

- **The idea travels with you** — whatever context was gathered in Steps 1–2 carries into the skill. Don't make Cathy repeat herself.
- **Repurposing works both ways** — a blog becomes a thread, a thread becomes a Facebook post, an email becomes Instagram captions. The router handles all directions.
- **Keyword step is blog-specific** — for all other formats, go straight to writing.
- **If the Airtable list is long**, show only the 10 most recent "Ready to draft" records and offer to show more.
