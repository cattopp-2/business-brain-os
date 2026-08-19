# Setup: Your Brand Voice

## What This Skill Does

Guides you through finding and saving 5–10 examples of your natural writing, then runs `mkt-brand-voice` to build your voice profile automatically.

The voice profile is what every copy skill reads before it writes a word. Without it, the system writes in generic AI-speak. With it, it writes in your voice.

Run this once during Module 3 setup. You can add more examples or regenerate your voice profile any time.

---

## Rules

- Ask one question at a time. Never list multiple questions in one message.
- Wait for the answer before moving to the next.
- Do not offer suggestions for what their examples should contain — what they choose reveals their voice.
- Accept anything they paste without editing or commenting on it.
- After the examples are saved, run `mkt-brand-voice` immediately — do not ask for approval first.

---

## Step 1 — Explain what you need

Say this:

"We're going to build your voice profile — the file that tells the system how you write. To do that, I need 5 to 10 pieces of your actual writing. Not your most polished work — the stuff that sounds most like you. Emails, social posts, Facebook comments, old newsletters, voice notes you've had transcribed. Anything you wrote yourself without heavy editing.

The more natural, the better. If you've only got three right now, start with those. You can always add more later.

Do you want to start pasting examples, or do you want me to help you think about where to look first?"

**If they want to start pasting:** go to Step 2.

**If they need help finding examples:** go to the Finding Examples path below before Step 2.

---

## Finding Examples Path

Work through these prompts one at a time until they've identified at least 5 sources:

1. "Do you send regular emails to a list? Your last few newsletters would be perfect — especially any you wrote quickly without overthinking."

2. "What about Facebook or LinkedIn posts from the last year? The ones where you were just talking to your audience, not crafting a marketing message."

3. "Any long comments you've left in Facebook groups or on other people's posts? Those tend to be the most unfiltered version of your voice."

4. "What about onboarding emails to new clients, or any emails where you explained your process or welcomed someone?"

5. "If none of those feel right — have you ever transcribed a voice note or a Loom? That's often the most natural writing there is because it wasn't written at all."

Once they've identified sources, ask them to start pasting. Go to Step 2.

---

## Step 2 — Collect the examples

Ask them to paste one example at a time:

"Paste your first example whenever you're ready — just drop the text in here. Tell me what it's from (email, Facebook post, etc.) if you can, but don't worry if you can't remember."

After each example:
- Acknowledge it simply. ("Got it." / "Perfect." / "That's a good one.")
- Ask: "Do you have another one to add?"
- Continue until they have at least 5, or they say they're done.

If they stop before 5, say: "Five is the minimum for a solid voice profile — can you find one or two more? Even a short email or a quick Facebook post works."

---

## Step 3 — Save writing-examples.md

Once you have at least 5 examples, write `brand-context/writing-examples.md` using this structure:

```markdown
# Writing Examples — [Their Brand Name]

5–10 examples of natural writing. Used by `mkt-brand-voice` to build the voice profile.

---

## Example 1 — [Source they gave, or "Unknown"]

[Example text]

---

## Example 2 — [Source]

[Example text]

---

[Continue for each example]
```

Do not edit or clean up their examples. Preserve exactly what they pasted — typos, informal language, line breaks, everything.

After saving, confirm: "Saved. I've got [number] examples in writing-examples.md. Now I'll run the brand voice skill to build your voice profile."

---

## Step 4 — Run mkt-brand-voice

Run `mkt-brand-voice` with the Extract mode, using the examples in `brand-context/writing-examples.md` as the source material.

After it completes:

"Your voice profile is ready in brand-context/voice-profile.md. Have a read through — specifically the section that shows sample sentences in your voice. Does it sound like you?

If something feels off, the best fix is usually more examples. Add them to writing-examples.md and run mkt-brand-voice again."

Then suggest they move to Module 4: mapping their audience.
