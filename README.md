[![zread](https://img.shields.io/badge/Ask_Zread-_.svg?style=flat&color=00b0aa&labelColor=000000&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB3aWR0aD0iMTYiIGhlaWdodD0iMTYiIHZpZXdCb3g9IjAgMCAxNiAxNiIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTQuOTYxNTYgMS42MDAxSDIuMjQxNTZDMS44ODgxIDEuNjAwMSAxLjYwMTU2IDEuODg2NjQgMS42MDE1NiAyLjI0MDFWNC45NjAxQzEuNjAxNTYgNS4zMTM1NiAxLjg4ODEgNS42MDAxIDIuMjQxNTYgNS42MDAxSDQuOTYxNTZDNS4zMTUwMiA1LjYwMDEgNS42MDE1NiA1LjMxMzU2IDUuNjAxNTYgNC45NjAxVjIuMjQwMUM1LjYwMTU2IDEuODg2NjQgNS4zMTUwMiAxLjYwMDEgNC45NjE1NiAxLjYwMDFaIiBmaWxsPSIjZmZmIi8%2BCjxwYXRoIGQ9Ik00Ljk2MTU2IDEwLjM5OTlIMi4yNDE1NkMxLjg4ODEgMTAuMzk5OSAxLjYwMTU2IDEwLjY4NjQgMS42MDE1NiAxMS4wMzk5VjEzLjc1OTlDMS42MDE1NiAxNC4xMTM0IDEuODg4MSAxNC4zOTk5IDIuMjQxNTYgMTQuMzk5OUg0Ljk2MTU2QzUuMzE1MDIgMTQuMzk5OSA1LjYwMTU2IDE0LjExMzQgNS42MDE1NiAxMy43NTk5VjExLjAzOTlDNS42MDE1NiAxMC42ODY0IDUuMzE1MDIgMTAuMzk5OSA0Ljk2MTU2IDEwLjM5OTlaIiBmaWxsPSIjZmZmIi8%2BCjxwYXRoIGQ9Ik0xMy43NTg0IDEuNjAwMUgxMS4wMzg0QzEwLjY4NSAxLjYwMDEgMTAuMzk4NCAxLjg4NjY0IDEwLjM5ODQgMi4yNDAxVjQuOTYwMUMxMC4zOTg0IDUuMzEzNTYgMTAuNjg1IDUuNjAwMSAxMS4wMzg0IDUuNjAwMUgxMy43NTg0QzE0LjExMTkgNS42MDAxIDE0LjM5ODQgNS4zMTM1NiAxNC4zOTg0IDQuOTYwMVYyLjI0MDFDMTQuMzk4NCAxLjg4NjY0IDE0LjExMTkgMS42MDAxIDEzLjc1ODQgMS42MDAxWiIgZmlsbD0iI2ZmZiIvPgo8cGF0aCBkPSJNNCAxMkwxMiA0TDQgMTJaIiBmaWxsPSIjZmZmIi8%2BCjxwYXRoIGQ9Ik00IDEyTDEyIDQiIHN0cm9rZT0iI2ZmZiIgc3Ryb2tlLXdpZHRoPSIxLjUiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIvPgo8L3N2Zz4K&logoColor=ffffff)](https://zread.ai/jacksongrrr/skill-DDT)
Made by Jacksong(宋梓铭)
# think-before-answer

Portable **agent** prompt pack: heavy reasoning stays in the host’s **reasoning / thinking channel**; the **user-visible** assistant text is only the polished deliverable.

`SKILL.md` is **not** meant to be shown to end users. It tells the model where to put TM1–TM6 and alternatives, and what must **never** leak into the main chat.

## Core innovation

**Problem:** Models shortcut to one line of reasoning, or they dump meta-planning (“I will use TM1–TM6…”), section headings, and chain-of-thought into the **same** surface the user reads—so the chat looks like an internal spec instead of an answer.

**What this pack does:** It **separates surfaces**:

1. **Reasoning channel** — Framing, TM1–TM6, ≥X approaches with pros/cons, deliberation, tool notes.
2. **User-visible message** — Only what the user should read: answers, code, steps, refusals—**no** `## How should I think…`, **no** `## Thinking`, **no** TM/A labels, **no** “following the skill” narration.

## Is that diagnosis fair? A sharp read

**Partly yes.** Pushing structure into a hidden reasoning strip improves chat UX and auditability for power users who open the trace.

**Limits:** If the host has **no** separate reasoning field, the model must internalize the TM pass and still avoid printing scaffolding—compliance is harder to verify externally. Mandatory X options can still be gamed with shallow alternates.

## What it does (contract summary)

- **Reasoning channel**: Full TM1–TM6, default **X = 3** candidates with pros/cons, framing before TM1. See [prompts/think-before-answer/SKILL.md](prompts/think-before-answer/SKILL.md).
- **User-visible message**: Standalone deliverable only; forbidden skill scaffolding listed in SKILL.md §3.
- **Single-stream hosts**: Internalize reasoning; output only the deliverable. See SKILL.md §0.

## Layout

```text
prompts/think-before-answer/
├── SKILL.md       # Agent contract
├── reference.md   # Host mapping, anti-patterns
└── examples.md    # Reasoning vs user-visible split
```

## How to use

Inject `SKILL.md` into **system / developer** instructions for the model. Optionally add `reference.md` or `examples.md` for context. Do not paste SKILL.md into end-user chats as “documentation” unless you intend to.

#Or olso can inject skill in openclaw.

## Effect

# Use skill:

<img width="395" height="440" alt="屏幕截图 2026-03-29 120458" src="https://github.com/user-attachments/assets/da4644c8-68d3-4470-818f-60e5d9b5c413" />

# no skill use:

<img width="418" height="1197" alt="屏幕截图 2026-03-29 120444" src="https://github.com/user-attachments/assets/f3ab5e3f-6fab-4802-97be-06569d2e4f4d" />


## License

MIT — see [LICENSE](LICENSE).
