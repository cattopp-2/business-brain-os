---
name: sales-page-writer
description: >
  Write a complete, conversion-optimised sales page or opt-in page for any of Cathy
  Topping's offer types. Triggers on: "sales page", "landing page", "opt-in page",
  "registration page", "write my sales page", "I need a page for my offer", "write a page
  for my course/programme/workshop/membership/lead magnet/masterclass". Routes to one of 8
  offer-type templates (1:1, group programme, online course, digital product, lead magnet,
  masterclass, workshop, membership). Does NOT trigger for email sequences, social posts,
  or blog posts.
---

<learnings>
Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply any notes to this run.
</learnings>

<outcome>
A complete sales page from hero section to footer — headline confirmed by the user, all sections written in full using the correct template, fascinator bullets included throughout, quality check passed. The user gets copy they can hand to a designer or paste into their page builder without further editing. Clearly marked placeholders only where the user hasn't yet provided the detail (e.g. [ADD TESTIMONIAL], [INSERT PRICE]).
</outcome>

<edge_cases>
**No testimonials** — proceed without. Flag the social proof section and add: [ADD TESTIMONIAL — one sentence on the result they got]. Suggest Cathy pull from client messages or DMs if she has them.

**Offer details are vague** — don't write a vague page. Ask specifically: what's included, what's the transformation, what's the price. A page built on vague brief produces copy that won't convert.

**User wants just one section** — write only that section. Don't produce the full page unless asked.

**Price isn't confirmed yet** — write the rest of the page and leave the investment section as: [PRICE TBC — INSERT HERE]. Flag it clearly.

**User wants to skip headline approval** — advise against it; the headline sets the angle for the entire page. If they insist, proceed — but note that copy may need revision if the headline changes later.

**Offer doesn't fit neatly into one template** — pick the closest template, note the deviation, and adapt. Don't force it into a template that doesn't fit.
</edge_cases>

<always_apply>
These steps apply to EVERY sales page regardless of offer type:

1. **Invoke brand-voice skill** before writing a single word of copy. All headlines, problem framing, bullets, FAQs, CTAs, and about sections must pass the brand voice quick check before delivery.

2. **Use headline-creator skill** to generate headline options for the user to choose from before writing the rest of the page. Do not proceed past the hero section until the user has selected a headline.

3. **Use fascinator-bullets skill** for all bullet points — problem bullets, transformation bullets, features bullets, and bonuses. Do not write plain benefit lists.

4. **Read references/writing-rules.md** and apply throughout.

5. **Run references/quality-check.md** before delivering the final page.
</always_apply>

<intake>
Ask the user:

1. What type of offer is this?
   - 1:1 coaching / consulting
   - Group programme
   - Online course
   - Digital product (template, toolkit, swipe file)
   - Lead magnet / freebie opt-in
   - Free masterclass / webinar registration
   - Paid workshop
   - Membership / subscription

2. What is the offer name and what does it include?

3. Who is it for? (ICA / target audience)

4. What is the price / investment?

5. Do you have testimonials to include? (paste them or say no)

6. Anything else to know — bonuses, urgency, founding member offer, enrolment window?

**Work with whatever the user provides. Don't demand a full brief before starting — begin with what you have and ask for specific gaps as they come up.**
</intake>

<feedback>
After delivering the page, ask:
> "Any feedback on this? A quick note helps improve next time."

If feedback is given, append to `.claude/skills/sales-page-writer/learnings.md`:
```
### [DATE]
[feedback]
```
Create the file if it doesn't exist.
</feedback>

<routing>
Once offer type is confirmed, load the appropriate template from references/:

| Offer Type | Template File |
|---|---|
| 1:1 coaching / consulting | references/one-to-one.md |
| Group programme | references/group-programme.md |
| Online course | references/online-course.md |
| Digital product | references/digital-product.md |
| Lead magnet / freebie | references/lead-magnet.md |
| Free masterclass / webinar | references/free-masterclass.md |
| Paid workshop | references/paid-workshop.md |
| Membership / subscription | references/membership.md |

Follow the loaded template structure in order. Do not skip sections unless explicitly told to. Adapt every line to the specific offer — nothing generic.
</routing>
