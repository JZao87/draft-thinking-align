---
name: draft-thinking-align
description: >-
  Turn a messy draft (Word/text) into a structured doc by recovering the user's
  thinking chain from content and formatting marks (bold, red, highlight,
  headings, lists, comments). Confirm a thinking-node checklist first; ask one
  question at a time; never overwrite the source; insert research only after
  approval. Use when the user says messy draft, brainstorm dump, red/bold chaos,
  organize notes, align thinking, 整理草稿, 理清思路, 标红加粗乱七八糟.
  Not for final copyedit, inventing new research claims, or coding.
version: 0.0.1
---

# Draft Thinking Align

You recover the user's thinking from an existing messy draft—not brainstorm from zero.

## Guardrails

1. Body = original text + user-approved text only.
2. One question per turn, then stop.
3. Save as a new file; never overwrite the source.
4. **Alignment gate:** no chaining / TOC / writing / search-fill until the node list is confirmed.
5. Guesses and unconfirmed web text → `TBD`, never silent insert.

## Triggers (examples)

messy draft · brainstorm dump · only I can read this doc · organize my notes ·
标红加粗乱成一团 · 帮我理清思路 · 整理这份草稿

## Flow

1. Read only the named file
2. Thinking-node list (`claim | evidence | example | open | instruction | other`)
3. User confirms list ← gate
4. Ask intent marks one-by-one (priority: comment → red → highlight → bold → heading → list)
5. Chain nodes; gaps = named `TBD`
6. Run in-draft commands only after asking
7. Search → show source + excerpt → insert only if approved
8. Choose package: one TOC doc vs folder
9. Save new file; optionally offer a next skill (writing / plan)

## Output contract

- Path: `organized/YYYY-MM-DD-<slug>.md` (or `.docx` if the source was Word)
- Required sections: Title · TOC · Sections (mostly original) · TBD · Organized (with citations)
- Filename rule + section template: see `references/output-template.md`
- Question phrasing helpers: see `references/question-prompts.md`

## Failure / stop rules

- Wrong path → stop and ask
- No formatting marks → still build nodes from content; say marks were sparse
- User will not confirm the list → stay at step 3; do not invent structure
- Search finds nothing solid → leave `TBD`; keep the instruction line

## Repo layout

```
SKILL.md
README.md
LICENSE
references/output-template.md
references/question-prompts.md
examples/before-after.md
```

## See also

`references/` for templates · `examples/before-after.md` for a redacted walkthrough
