# think-before-answer

Portable prompt pack: enforce a three-part assistant reply so framing and reasoning appear before the deliverable.

## Core innovation

**Problem it targets:** Models often **shortcut the reasoning space**. For a question that could legitimately be attacked from many angles—competing designs, rival interpretations, alternative heuristics, or several validation strategies—the default behavior is frequently **single-track**: one comfortable narrative, one implementation pattern, or one unstated assumption carried to the end. The user never sees the other nine plausible moves.

**What this pack does about it:** It is a **procedural anti-sloth contract**. The model must (1) externalize framing before the answer, (2) run a fixed **TM1–TM6** pass so basic meta-steps are not silently skipped, and (3) enumerate **at least X** candidate approaches with **explicit pros and cons** before committing. That raises the cost of “only ever using one method” in the visible transcript and makes omission of real alternatives easier to spot.

## Is that diagnosis fair? A sharp read

**Partly yes.** Single-track answers are a common failure mode when users need optionality, risk awareness, or audit trails. Forcing labeled passes and a minimum alternative count is a **reasonable lever** for teaching, review, and higher-stakes assistance where you want the model to *show* that it considered more than one path.

**But the remedy is not a proof of depth.** Compliance with headings and bullet counts does **not** guarantee genuinely diverse cognition. The model can still satisfy TM1–TM6 with thin boilerplate, invent **fake** extra approaches to hit X, or spread one idea across three “different” labels. Conversely, a **single** deep, well-checked line of reasoning can beat ten shallow gestures—this skill does not rank those cases automatically. You may also pay in **tokens, latency, and readability**; for trivial or closed questions, mandatory multiplicity can be **performative** rather than informative.

**Bottom line:** The innovation is **process transparency and anti-collapse pressure**, not a theorem that the model “really thought ten ways.” Treat it as a **guardrail and disclosure format**, not as evidence that every listed approach was equally serious or independent.

## What it does

Executable contract for the model:

- **When**: Every user-visible substantive reply uses three sections unless the user forbids it, or the reply is pure courtesy with no task content, or only an internal invisible intermediate applies. See `SKILL.md` section 1.
- **Shape**: Three fixed Markdown H2 headings in a fixed order. See `SKILL.md` section 2.
- **Roles**: Section 1 is not the final deliverable; section 2 is reasoning; section 3 is what the user copies or runs. See `SKILL.md` section 3.
- **DeepSeek-style separation**: Put **all** deep reasoning and chain-of-thought under **`## Thinking`**; keep **`## Answer`** to the **formal** result only—the same separation as DeepSeek-style “深度思考 / reasoning” vs the main answer panel. See `SKILL.md` §0 (subsection *DeepSeek-style split*).
- **Thinking chain**: Section 2 must run **TM1–TM6** in order (labeled blocks, task-specific prose). See `SKILL.md` section 3.2.
- **Alternatives**: Section 2 must list **at least X** solution approaches in **TM3** (default **X = 3**) and give **pros and cons for each** in **TM4**, unless fewer honest options exist or the user overrides X. See `SKILL.md` sections 0 and 3.2.

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

- **Current**: 1.2.1 — Documents DeepSeek-style split: deep reasoning in **Thinking**, formal output in **Answer**.

Breaking changes include changing the three title strings, TM labels, X default, or section-1/3 obligations; bump the major version when you do.

## License

MIT — see [LICENSE](LICENSE).
