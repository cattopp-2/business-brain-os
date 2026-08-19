---
name: create-agent-skill
description: >
  Build a new skill for this OS — scaffolds it using the correct project conventions,
  wires up learnings, and registers it in CLAUDE.md. Triggers on: "build me a skill",
  "create a skill", "I want a skill for", "turn this into a skill", "new skill for".
  Does NOT trigger for creating hooks, subagents, or slash commands — those have their own skills.
---

<learnings>
Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply any notes to this run.
</learnings>

<outcome>
A complete, working skill file at `.claude/skills/[skill-name]/skill.md` — built to project conventions, with all required sections populated, learnings wired in, and a proposed CLAUDE.md entry ready for approval. The skill is immediately usable on the next run.
</outcome>

<always_apply>
1. Every skill must follow the XML-tag format used in this project — not markdown headers for the main body.
2. Every skill must include a `<learnings>` block that reads from the skill's own folder first.
3. Every skill must include an `<outcome>` block describing what finished output looks like.
4. Every skill that writes copy must invoke brand-voice before producing output.
5. Every skill must end with a `<feedback>` block asking for one piece of feedback after delivery.
6. Skill files live at `.claude/skills/[skill-name]/skill.md` — never anywhere else.
7. After creating the skill, add a section for it in `context/learnings.md`.
8. Propose a one-line CLAUDE.md entry and wait for approval before editing that file.
</always_apply>

<intake>
Ask these questions one at a time. Do not front-load.

**Q1:** What does this skill do — what's the task it handles, and what triggers it? (A few sentences is enough. Examples help.)

**Q2:** Show me 2–3 examples of good output from this skill, or describe what "done well" looks like. (If they don't have examples, ask what the output format should be and what makes it effective.)

**Q3:** Does this skill write copy or content? If yes, which brand context files does it need? (Offer to list available files from `brand-context/` if they're not sure.)

**Q4:** Does it need to reference any specific offer files from `offers/`? (Only relevant if it's writing promotional content for a named offer.)

Then proceed to build — do not ask more questions. Make reasonable assumptions and state them.
</intake>

<build_steps>

## Step 1 — Name and slug

Derive a lowercase hyphenated slug from the skill name. Check that `.claude/skills/[slug]/` does not already exist before proceeding.

## Step 2 — Scaffold the skill file

Build the skill file using this template. Populate every section based on intake answers.

```
---
name: [slug]
description: >
  [What the skill does in one sentence]. Triggers on: "[phrase1]", "[phrase2]", "[phrase3]".
  Does NOT trigger for: [exclusions if relevant].
---

<learnings>
Check for `learnings.md` in this skill's folder. If it exists, read it before starting and apply any notes to this run.
</learnings>

<outcome>
[What the finished output looks like — be specific. Mention format, length, quality bar. "The user can X without further editing."]
</outcome>

<edge_cases>
[2–4 edge cases: what to do if the user provides minimal input, asks for something adjacent, or the task is ambiguous. Written as "**Situation** — what to do."]
</edge_cases>

<always_apply>
[3–6 non-negotiable rules for this skill. Numbered list.]
</always_apply>

<intake>
[Questions to ask the user before starting work. One at a time. Maximum 4.]
</intake>

[Main methodology steps — as many as needed, each as a ## Step N — [name] section]

<feedback>
After delivering output, ask: "Any feedback on this? A quick note helps improve next time."
If feedback is given: note it and tell them it will be logged at wrap-up.
</feedback>
```

If the skill writes copy: add brand-voice invocation as Step 1 of the methodology, before any writing.

If the skill loads offer or brand context files: specify exactly which files and when in the methodology.

## Step 3 — Create the files

1. Create the folder: `.claude/skills/[slug]/`
2. Write the skill file to `.claude/skills/[slug]/skill.md`

## Step 4 — Wire up learnings

Read `context/learnings.md`. Add a new section at the end:

```
## [skill-name]

No learnings yet.

---
```

Write the updated file.

## Step 5 — Register in CLAUDE.md

Identify which table in CLAUDE.md this skill belongs in (copy skills, platform-specific, utility, SEO, etc.). Propose the entry:

> "Add to [table name]: `[skill-name]` | [one-line purpose description]"

Show the proposed row and wait for approval. On approval: edit CLAUDE.md.

Also update the command in `.claude/commands/create-agent-skill.md` if the command currently points to the old Anthropic skill — update it to point to this one.

</build_steps>

<feedback>
After delivering the new skill, ask: "Any feedback on this skill creator? A quick note helps improve next time."
If feedback is given: note it and tell them it will be logged at wrap-up.
</feedback>
