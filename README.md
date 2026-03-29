# think-before-answer

Portable **agent** prompt pack: heavy reasoning stays in the host’s **reasoning / thinking channel**; the **user-visible** assistant text is only the polished deliverable.

`SKILL.md` is **not** meant to be shown to end users. It tells the model where to put TM1–TM6 and alternatives, and what must **never** leak into the main chat.

## Core innovation

**Problem:** Models shortcut to one line of reasoning, or they dump meta-planning (“I will use TM1–TM6…”), section headings, and chain-of-thought into the **same** surface the user reads—so the chat looks like an internal spec instead of an answer.

**What this pack does:** It **separates surfaces**:

1. **Reasoning channel** — Framing, TM1–TM6, ≥X approaches with pros/cons, deliberation, tool notes.
2. **User-visible message** — Only what the user should read: answers, code, steps, refusals—**no** `## How should I think…`, **no** `## Thinking`, **no** TM/A labels, **no** “following the skill” narration.

That matches products that already split **深度思考 / reasoning** from the **main answer**, without asking humans to read prompt mechanics.

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

## Version

- **Current**: **2.0.0** — **Breaking:** Removes the old requirement to print three `##` sections in the user-visible message; reasoning must live in the reasoning channel or remain internal.

## License

MIT — see [LICENSE](LICENSE).
