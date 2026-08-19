# Setup: Your Brand Stories

## What This Skill Does

Helps you capture your brand stories and client testimonials, saves them as individual files, compiles them into `brand-context/story-bank.md` and `brand-context/testimonials.md`, and weaves key story elements into your ICP and voice profile so every copy skill can draw on them.

Stories are what make content feel real. Without them, the system writes professionally — but generically. With them, it writes like you.

Run this once during setup. Add new stories and testimonials to the folders any time — re-run the skill to recompile.

---

## Rules

- Ask one question at a time. Never list multiple questions in one message.
- Wait for the answer before moving to the next.
- Don't summarise or paraphrase stories — preserve the raw detail. The mess and specificity is what makes them usable.
- Accept partial answers. Not everyone has polished stories ready. Work with fragments and note where gaps exist.
- After gathering, write all files without asking for approval.

---

## Step 1 — Check for existing files

Before asking anything, check both folders:

- `brand-context/brand-stories/` — for any files beyond README.md
- `brand-context/testimonials/` — for any files beyond README.md

**If files exist in either folder:** Say:
"I can see you've already saved [X stories / Y testimonials] in your folders. I'll use those as a starting point. Do you want to add anything else before I compile everything, or shall I get started?"

- If they say go: skip to Step 4 (compile).
- If they want to add more: continue to Step 2.

**If both folders are empty:** Go to Step 2.

---

## Step 2 — Route them

Say:

"To build your story bank I need two things — your own brand stories, and any client results or testimonials you have. We can do this by you pasting material in now, or if you've already saved content into the brand-stories/ and testimonials/ folders I can read from there. Most people do a mix of both.

Shall we start with your stories, or do you have testimonials ready to go first?"

Go to whichever they choose. Handle the other type after.

---

## Path A — Brand Stories

### Story interview questions (one at a time)

1. "Why did you start your business? Tell me the real version — not the polished elevator pitch. What was actually going on?"

2. "Was there a moment — a turning point, a decision, a failure — that shaped how you work today? Tell me about it."

3. "Tell me about a client result you're most proud of. What was their situation before, what did you do, and what changed for them? Be specific — the more detail the better."

4. "Is there a story you tell a lot — something that comes up in conversations, on calls, in posts — that explains your approach or why you do things the way you do?"

5. "Any other stories worth saving — personal moments, behind-the-scenes things, hard lessons, unexpected wins?"

After each story:
- Save it immediately as a separate file in `brand-context/brand-stories/` using this naming convention: `story-[slug].md` — e.g. `story-origin.md`, `story-client-jane.md`, `story-turning-point-2023.md`
- Acknowledge simply. ("Got it — saved." / "That's a strong one.")
- Ask the next question or move to testimonials.

### If they have material to paste

Accept anything — a post they've written, a newsletter, a sales page with their story on it, notes about a client result. Save each piece as a separate file in `brand-context/brand-stories/`.

---

## Path B — Testimonials

Ask:

"Paste your testimonials in one at a time — or if you have several, paste them all at once and I'll separate them. Include as much context as you can: who said it, what offer it was for, when, what result they got."

After each testimonial:
- Save as a separate file in `brand-context/testimonials/` using this naming: `testimonial-[slug].md` — e.g. `testimonial-jane-membership.md`, `testimonial-dm-sales-page-nov25.md`
- Acknowledge simply.
- Ask: "Do you have another one?"

Continue until they're done or have at least 3–5.

If they have fewer than 3: "Even one strong testimonial makes a difference. Do you have any DMs, comments, or email replies where someone said something about working with you — even something casual?"

---

## Step 3 — Check what's in the folders

Before compiling, read all files in both folders (excluding READMEs). Confirm what you have:

"I've got [X stories] and [Y testimonials]. Compiling now."

---

## Step 4 — Compile story-bank.md

Read all files in `brand-context/brand-stories/` (excluding README.md). Compile into `brand-context/story-bank.md`:

```markdown
# Story Bank — [Brand Name]

[Number] brand stories. Used by copy skills when writing posts, emails, and sales pages that need a personal hook, example, or anecdote.
Last compiled: [today's date]

---

## [Story title — derived from filename or content]

[Full story text — preserved exactly as given. No editing, no polishing.]

**Tags:** [1–3 tags describing what this story is useful for: origin / turning-point / client-result / methodology / personal / failure / win]

---

[Repeat for each story]
```

---

## Step 5 — Compile testimonials.md

Read all files in `brand-context/testimonials/` (excluding README.md). Compile into `brand-context/testimonials.md`:

```markdown
# Testimonials — [Brand Name]

[Number] testimonials. Used by copy skills for social proof, results, and client quotes.
Last compiled: [today's date]

---

## [Offer / context — derived from filename or content]

> "[Quote — exact words]"

**Who:** [Name or description if given]
**Offer:** [What they bought or what they were doing]
**Result:** [The specific outcome mentioned, if any]

---

[Repeat for each testimonial]
```

---

## Step 6 — Update ICP and voice profile

Read `brand-context/icp.md` and `brand-context/voice-profile.md`.

**Update icp.md:** Add a section at the bottom called `## Client Results` with 2–3 specific outcomes from the testimonials — the kind of results the ideal client can expect.

**Update voice-profile.md:** Add a section called `## Stories to draw from` listing the story titles and a one-line summary of each — so copy skills know what stories are available and when to use them.

Save both files.

---

## Step 7 — Confirm

Say:

"Done. Here's what's saved:

- [X] stories in brand-context/brand-stories/
- [Y] testimonials in brand-context/testimonials/
- Compiled into story-bank.md and testimonials.md
- ICP and voice profile updated with client results and story references

To add more: drop files into the brand-stories/ or testimonials/ folders and run setup-brand-stories again. It'll pick up everything and recompile.

The copy skills will now pull from these automatically when they need a story hook, a result, or a client quote."
