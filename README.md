# think-before-answer

Portable prompt pack: enforce a three-part assistant reply so framing and reasoning appear before the deliverable.

## What it does

Executable contract for the model:

- **When**: Every user-visible substantive reply uses three sections unless the user forbids it, or the reply is pure courtesy with no task content, or only an internal invisible intermediate applies. See `SKILL.md` section 1.
- **Shape**: Three fixed Markdown H2 headings in a fixed order. See `SKILL.md` section 2.
- **Roles**: Section 1 is not the final deliverable; section 2 is reasoning; section 3 is what the user copies or runs. See `SKILL.md` section 3.

Full rules: [prompts/think-before-answer/SKILL.md](prompts/think-before-answer/SKILL.md).

## Layout

This repository is **not** tied to a specific IDE. Files live under a generic prompts folder:

```text
prompts/think-before-answer/
├── SKILL.md       # Contract: YAML frontmatter + structure + exceptions
├── reference.md   # Optional depth: scenarios, anti-patterns, tools
└── examples.md    # Illustrative shapes
```

## How to use

- **System prompt**: Paste or load `SKILL.md` into your system or developer instructions.
- **RAG / prompt library**: Index `prompts/think-before-answer/` and inject when you want this behavior.
- **IDE integrations**: If your tool expects a different path, copy or symlink this folder to that tool’s prompt or rules directory.

Optional files: pull in `reference.md` or `examples.md` when you want extra guidance without bloating the primary prompt.

## Version

- **Current**: 1.1.0 — English contract; generic `prompts/` layout; headings are English strings in `SKILL.md` section 2.

Breaking changes include changing the three title strings or section-1/3 obligations; bump the major version when you do.

## License

MIT — see [LICENSE](LICENSE).
