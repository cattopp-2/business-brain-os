---
name: email-sequence-writer
description: >
  Write a complete, on-brand email sequence — freebie welcome, freebie to book-a-call,
  webinar registration, fill your webinar, and post-webinar upsell.
  Triggers on: "email sequence", "nurture sequence", "welcome series", "welcome emails",
  "webinar emails", "follow-up sequence", "drip campaign", "onboarding emails",
  "upsell sequence". Routes to one of 5 sequence templates based on funnel type. Does NOT
  trigger for single standalone emails — use email-ideas-generator for those.
---

<learnings>
Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply any notes to this run.
</learnings>

<outcome>
A complete sequence of all emails written in full — subject lines, bodies, CTAs, PS lines, sign-offs — ready to load into the email platform. Nothing left for the user to fill in except clearly marked placeholders (e.g. [DATE], [LINK], [PRICE]). The user should be able to copy each email directly into their CRM without further editing.
</outcome>

<edge_cases>
**User doesn't know which sequence type** — ask what they're launching (a freebie, a webinar, a high-ticket offer) and recommend the sequence type. Show the 5 options only if they're genuinely unsure.

**No testimonials available** — proceed without. Note which emails typically include social proof and leave a placeholder: [ADD TESTIMONIAL HERE — one sentence on the result].

**Deadline or date is missing** — ask specifically if the sequence requires it (webinar registration and upsell sequences do). Don't proceed on urgency-driven emails without a real date.

**User wants fewer emails** — advise which can be cut and which are critical to the sequence logic. Don't just drop emails without flagging the gap.

**User wants to change sequence type mid-way** — stop, confirm the new type, reload the correct template, and start from the point of divergence. Don't try to adapt a half-written sequence to a different template.

**User has no offer details yet** — a sequence can't be written without the offer name, price, and what's included. Ask for these before starting. Offer to write a framework draft with placeholders if they're still finalising.
</edge_cases>

<always_apply>
These steps apply to every sequence regardless of type:

1. **Load brand voice** before writing. Read `brand-context/voice-profile.md` if it exists. Every email must pass the voice quick check — mid-scene openings, specific problems named, no hollow affirmations, signed off in the sender's natural style.

2. **Use PS statements from `references/ps-statements.md`** for all PS lines. Do not write generic PS lines — always choose from the swipe file and rewrite in the sender's voice.

3. **Write every email in full** — not structural notes, not bullet-point outlines. Deliver finished, ready-to-send copy.

4. **One CTA per email.** Never mix reply CTAs, link CTAs, and booking CTAs in the same email.

5. **Apply writing rules:**
   - No em-dashes
   - Short paragraphs, lots of white space
   - Open mid-scene — drop the reader into a moment already happening
   - Sign off: naturally in the sender's voice (check voice-profile.md or ask if unsure)
   - Subject lines: specific and honest, max 6 words where possible
   - No emojis, no hashtags
</always_apply>

<intake>
Ask the user:

1. Which sequence type?
   - Freebie to low-ticket offer (6 emails)
   - Freebie to book a call — high-ticket 1:1 (6 emails)
   - Fill your webinar — invite warm list to register (6 emails)
   - Webinar registration — confirmations and reminders for registrants (4 emails)
   - Upsell from webinar/masterclass — post-event sales sequence (5 emails)

2. What is the freebie, event, or offer name?

3. What is the paid offer being sold? (if applicable — not needed for webinar registration)

4. Who is the audience? (who is this for, and what's their specific struggle)

5. Do you have any testimonials or case studies to use?

6. Specific details needed: event date and time, links, price, deadline (if applicable)?

**Work with whatever the user provides. Start with what you have and ask for specific gaps as they come up.**
</intake>

<offer_files>
Once the offer or freebie is identified, check whether a matching file exists in `offers/`. If it does, read it before writing the first email. If not, proceed with the details the user has provided.
</offer_files>

<feedback>
After delivering the sequence, ask:
> "Any feedback on this? A quick note helps improve next time."

If feedback is given, append to `.claude/skills/email-sequence-writer/learnings.md`:
```
### [DATE]
[feedback]
```
Create the file if it doesn't exist.
</feedback>

<routing>
Once sequence type is confirmed, load the appropriate template:

| Sequence Type | Template File |
|---|---|
| Freebie to low-ticket offer | references/freebie-to-low-ticket.md |
| Freebie to book a call | references/freebie-to-book-a-call.md |
| Fill your webinar | references/fill-your-webinar.md |
| Webinar registration | references/webinar-registration.md |
| Upsell from webinar/masterclass | references/upsell-from-webinar.md |

Follow the loaded template structure in order. Write every email in full. Do not skip emails unless the user explicitly asks to.
</routing>
