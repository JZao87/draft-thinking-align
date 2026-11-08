# draft-thinking-align

Recover a clear thinking chain from messy drafts (bold/red/highlight/headings)—confirm first, one question at a time, never overwrite the source.

## Who it's for

Messy brainstorm documents whose formatting already marks intent: bold, red, highlight, headings, lists, and comments.

## Not for

Final copyedit, inventing research, or coding.

## How it works

1. Read the named file.
2. List thinking nodes (`claim | evidence | example | open | instruction | other`).
3. Stop at the confirm gate until that list is confirmed.
4. Ask intent marks one at a time (comment, red, highlight, bold, heading, list).
5. Chain the nodes; gaps stay named `TBD`.
6. Run in-draft commands only after asking.
7. Search, show the source and a short excerpt, and insert only with approval.
8. Package as one table-of-contents document or a folder split by block.
9. Save a new file. The source stays untouched.

Full rules: [SKILL.md](SKILL.md).

## Install

Copy this folder into your Claude or Cursor skills directory. Invoke it when organizing a messy draft, and point it at one file path.

## Layout

- [SKILL.md](SKILL.md)
- [references/](references/) — output template and question prompts
- [examples/](examples/) — redacted before/after walkthrough

## License

[MIT](LICENSE)
