---
name: draft-thinking-align
description: >-
  Turn a messy draft (Word/text) into a structured doc by recovering the user's
  thinking chain from content and formatting marks (bold, red, highlight,
  headings, lists, comments). Confirm a thinking-node checklist first; ask one
  question at a time; never overwrite the source; insert research only after
  approval. On a second pass (再整理 / 二次整理 / organize again), keep confirmed
  intents and ask only about new or changed content. Use when the user says
  messy draft, brainstorm dump, red/bold chaos, organize notes, align thinking,
  整理草稿, 理清思路, 标红加粗乱七八糟, 再整理一遍, 二次整理.
  Not for final copyedit, inventing new research claims, or coding.
version: 0.0.2
---

# Draft Thinking Align

You recover the user's thinking from an existing messy draft—not brainstorm from zero.

## Guardrails

1. Body = original text + user-approved text only.
2. One question per turn, then stop.
3. Save as a new file; never overwrite the source.
4. **Alignment gate:** no chaining / TOC / writing / search-fill until the node list is confirmed.
5. Guesses and unconfirmed web text → `TBD`, never silent insert.
6. **Second pass:** do not re-ask intents already confirmed; only ask about new or changed content.

## Triggers (examples)

messy draft · brainstorm dump · only I can read this doc · organize my notes ·
标红加粗乱成一团 · 帮我理清思路 · 整理这份草稿 ·
再整理一遍 · 二次整理 · organize this again · I edited the organized file

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

If this is a second pass, follow **Second pass** after step 1, then continue from the gate with only new or changed nodes.

## Second pass (re-organize)

Use this branch when the user is organizing a draft that this skill (or the user) has already organized once.

**Detect it when any of these is true:**

- The user says 再整理、二次整理、再整理一遍、organize again, second pass, or "I edited the organized file—organize it again."
- The named file already looks like a prior output of this skill: a 整理说明, italic "整理：" notes, a confirmed-intent log, or a dated `organized/` filename.

**Then do this:**

1. Treat the named file as the current source of truth (not the very first messy draft). Never overwrite it, and never overwrite the original messy draft either.
2. Recover prior confirmations: prefer a diff against the previous organized file and/or the original draft when those paths are available. If they are not, use in-file 整理 notes and already-resolved marks as the confirmation record.
3. Split the node list into **inherited** (already confirmed; text and marks unchanged) vs **new/changed** (new sentences, new or altered marks, a former `TBD` that is now filled, or wording the user edited).
4. Still stop at the alignment gate, but confirm the split. Do not re-ask intent for inherited nodes unless the user reopens them or the underlying text/mark changed.
5. Ask only new/changed intent marks, still one question per turn, same priority (comment → red → highlight → bold → heading → list).
6. Keep inherited decisions and existing marks (red / bold / highlight). In the new file, 整理 notes should say which decisions were already confirmed and which were confirmed on this pass.
7. Save a new dated file (`organized/YYYY-MM-DD-<slug>.md` or `.docx`).

If the user says "只聚焦新增 / only the new parts," summarize that inherited decisions will be kept, skip re-listing them in detail, and start with the first new mark.

## Output contract

- Path: `organized/YYYY-MM-DD-<slug>.md` (or `.docx` if the source was Word)
- Required sections: Title · TOC · Sections (mostly original) · TBD · Organized (with citations)
- A second-pass file should also list inherited confirmations vs this-pass confirmations vs remaining TBD.
- Filename rule + section template: see `references/output-template.md`
- Question phrasing helpers: see `references/question-prompts.md`

## Failure / stop rules

- Wrong path → stop and ask
- No formatting marks → still build nodes from content; say marks were sparse
- User will not confirm the list → stay at step 3; do not invent structure
- Search finds nothing solid → leave `TBD`; keep the instruction line
- Second pass but you cannot tell new from old → say so, ask the user to point at the new parts (or provide the previous file); do not re-ask every old mark by default

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
