---
name: proposal-writer
description: >
  Write a branded client proposal as a self-contained HTML file. Triggers on: "proposal",
  "write a proposal", "client proposal", "put together a proposal". Takes a discovery call
  transcript (pasted or Google Doc) and generates a complete proposal in the YWT brand design
  system. Asks only for information the transcript doesn't already answer. Saves output to
  proposals/[client-slug]-proposal.html.
---

<learnings>
Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply any notes to this run.
</learnings>

<outcome>
Two files delivered in sequence:
1. `proposals/[client-slug]-draft.md` — a markdown draft covering all proposal content, reviewed and confirmed by Cathy before HTML is built
2. `proposals/[client-slug]-proposal.html` — the final print-ready HTML built from the confirmed draft

HTML sections: header, title band, intro, brief, option card(s), cost comparison (if multi-option), next steps, T&Cs, and footer. Brand colours, fonts, and print styles match the YWT design system exactly. T&Cs are generated from the actual scope and pricing — not a generic block.
</outcome>

<edge_cases>
**Pricing not confirmed in transcript** — ask specifically before writing the options section. Don't leave pricing as TBC if it can be answered with one question.

**Single option requested** — omit the comparison table. The option card still uses the full card structure (charcoal header, body with pricing table or includes list).

**Client is a repeat client** — check if a prior proposal exists in `proposals/` for this client. If so, note any pricing or scope changes from the last one in the intro.

**Transcript is vague on deliverables** — extract what's there, then ask Cathy to confirm the list before writing. Don't invent scope.

**No transcript provided** — switch to a purely intake-driven flow. Ask each intake question in turn before writing.
</edge_cases>

<always_apply>
1. **Read all existing files in `proposals/`** before writing. Use them to stay consistent with Cathy's pricing patterns, framing style, and section structures. They are the reference library — the more that exist, the better.

2. **Read the transcript first.** Extract as much as possible before asking anything. Only ask for what's missing.

3. **Generate T&Cs from the proposal content.** Use the scope, option type(s), and pricing to write specific T&Cs — payment terms per option, revision rounds, client responsibilities relevant to what's included. Do not copy-paste a generic block.

4. **Do not invoke brand-voice skill.** Proposals are professional service documents, not marketing copy. They use Cathy's voice but don't need the full brand-voice treatment.

5. **Save the draft first, HTML second.** Write the markdown draft to `proposals/[client-slug]-draft.md`. Wait for Cathy to confirm before building the HTML at `proposals/[client-slug]-proposal.html`.
</always_apply>

<intake>
Read the transcript first. Then ask only for what's missing — one question at a time:

1. **Client name and business** — if not clear from the transcript
2. **Deliverables** — confirm the list extracted from the transcript: "Here's what I pulled from the call: [list]. Does this look right, or anything to add/remove?"
3. **Single or multi-option?** — "Do you want to offer one option or present two or three?"
4. **Pricing** — confirm figures for each option / deliverable. If transcript has numbers, confirm them rather than asking blind.
5. **Timeline** — any start date, deadline, or urgency mentioned?
6. **Anything to emphasise** — a specific result, a concern raised on the call, or a framing Cathy wants front and centre in the intro
</intake>

<phases>
## Phase 1 — Markdown Draft

After all intake questions are resolved, write a markdown draft to `proposals/[client-slug]-draft.md` with the following sections in order:

1. **Intro** — personal greeting, reference something specific from the call, explain what follows
2. **Your Brief** — numbered list of what was established on the call
3. **Option(s)** — for each option: name, description, deliverables or includes, pricing, Recommended flag if applicable
4. **Cost Comparison** — if multi-option, a simple table of upfront + ongoing costs
5. **Next Steps** — conversational CTA (reply or short call, no buy button)
6. **Terms & Conditions** — tailored to this proposal's scope: payment terms per option, revision rounds, client responsibilities, definitions, liability. Not a generic block.

Once saved, prompt:
> "Draft saved to `proposals/[client-slug]-draft.md`. Review it and let me know when you're happy — or paste any changes — and I'll build the HTML."

**Do not proceed to Phase 2 until Cathy confirms.**

## Phase 2 — HTML

Build the HTML from the confirmed draft content. Do not regenerate the T&Cs — use what's in the draft. Save to `proposals/[client-slug]-proposal.html`.
</phases>

<html_structure>
Build the HTML using this structure and the YWT design system (CSS variables, fonts, print styles) from the existing proposals as the exact template. Do not introduce new styles — reuse what's there.

**Sections in order:**

1. `<header class="proposal-header">` — teal background, white YWT logo (URL: https://yourwebtoolkit.com/wp-content/uploads/2016/04/Your-Web-Toolkit-Logo_white.png), client name + website + date (right-aligned, white text)

2. `.title-band` — teal background, centred. H1: "[Type] Proposal" (e.g. "Content & Copy Proposal", "SEO & Website Proposal"). Subtitle: one-sentence framing.

3. `.content` max-width 800px, centred:

   a. **Intro** (`.intro` with amber left border) — personal greeting. Reference something specific from the call. Explain what follows.

   b. `<hr class="divider">`

   c. **Your Brief** (`.section-block`) — section-label "Your Brief", H2 "What We're Working With", then `.brief-list` with numbered items extracted from transcript.

   d. `<hr class="divider">`

   e. **Option card(s)** — one `.section-block` per option. Each has:
      - `.option-card` with `.option-card-header` (charcoal bg, H2 option name, optional `.option-tag` label)
      - `.option-card-body` with description, then pricing/includes as appropriate:
        - Use `.pricing-table` for itemised deliverables with individual prices
        - Use `.includes-list` for what's included in a fixed-price package
        - Use `.price-pill` for the headline price
      - One option may carry a `Recommended` tag if Cathy has a preference

   f. **Cost summary** (if multi-option) — `.comparison-table` with upfront + monthly rows

   g. `<hr class="divider">`

   h. **Next Steps** — `.next-steps` (light-grey box). Conversational CTA — reply or short call. No buy button.

   i. `<hr class="divider">`

   j. **T&Cs** — section-label "Terms & Conditions", H2 "Terms of Service". Generated from this proposal's actual scope. Include sections: Definitions, Quotations, Approval, Payment, Client Responsibilities, Scope of Work, Retention of Title, Liability. Tailor payment terms to what's in the proposal (e.g. if there's a build fee, specify 50% deposit; if it's retainer-only, specify advance billing; if items are under £600, payable in full). Font-size 13px throughout.

4. `.proposal-footer` — charcoal background. Left: "Your Web Toolkit" in heading font. Right: cathy@yourwebtoolkit.com | yourwebtoolkit.com

5. Include `@media print` styles matching the existing proposal pattern (break-inside: avoid on cards, tables, next-steps; font-size: 14px; reduced padding).
</html_structure>

<feedback>
After delivering the file path, ask:
> "Any feedback on this? A quick note helps improve next time."

If feedback is given, append to `.claude/skills/proposal-writer/learnings.md`:
```
### [DATE]
[feedback]
```
Create the file if it doesn't exist.
</feedback>
