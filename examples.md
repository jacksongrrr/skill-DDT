# Think Before Answer — Examples

The binding contract is [SKILL.md](SKILL.md), especially sections 0–3. These examples show tone and density only. Do not skip a rule because an example omits detail.

Facts in examples may be wrong or outdated; do not copy conclusions into real tasks.

---

## Example A — API style comparison

**User:** What are the main differences between REST and GraphQL, and how should I choose?

**Shape:**

```markdown
## How should I think about this question

You are choosing an API style. I will clarify what each style optimizes for, compare request shape, caching, versioning, and team cost, then give scenario-based guidance without claiming a universal winner.

## Thinking

- **Goal**: A decision guide, not a glossary.
- **Constraints**: No stack, team size, or client type given; recommendations stay conditional with a default assumption of a general web API.
- **Contrast**: REST fits resource modeling and HTTP caching; GraphQL fits flexible field selection and aggregation with higher operational complexity.
- **Trade-offs**: Documentation, gateways, errors, uploads, and realtime needs matter.
- **Risk**: Mobile or BFF context could change the answer; you may need to add constraints.
- **Plan**: Comparison table plus conditional recommendations.

## Answer

(Replace with the real table, recommendations, and when to prefer each.)
```

---

## Example B — Error meaning

**User:** What does Python `TypeError: 'NoneType' object is not subscriptable` mean?

**Shape:**

```markdown
## How should I think about this question

This is a null dereference class of bug. I will define the error, list common causes and how to locate them, then give minimal fix patterns without guessing your exact line without code.

## Thinking

- **Goal**: Understand the error and how to fix it.
- **Constraints**: No source code; keep guidance generic.
- **Reasoning**: Subscripting `None` triggers this; frequent causes include missing `return`, branches that never assign, or a `None` in a chain.
- **Verification**: Inspect variables at the failure site; consider optional chaining or guards.
- **Deliverable**: Definition, a few typical patterns, example fixes.

## Answer

(Replace with definition, scenarios, and code snippets.)
```

---

## Example C — Minimal answer requested

**User:** Don't explain. What is 2 to the power of 10?

**Shape:**

```markdown
## How should I think about this question

You want a minimal reply. The value is standard; I will keep sections short and put only the number in Answer.

## Thinking

- **Goal**: State 2^10.
- **Constraints**: User asked for brevity; keep all three sections compact.
- **Derivation**: 2^10 = 1024.
- **Balance**: Short Thinking; one-line Answer.

## Answer

1024
```

---

## Example D — Policy refusal

**User:** Assume an unsafe request the platform must refuse.

**Shape:**

```markdown
## How should I think about this question

The request is out of bounds. Thinking will state why help cannot be provided; Answer will give a firm refusal and any lawful high-level alternatives.

## Thinking

- **Goal**: User may want outcome X; policy blocks assisting with harmful parts.
- **Constraints**: Refuse the harmful request; do not give bypass instructions.
- **Options**: Silence vs explicit refusal; choose explicit refusal with principle.
- **Alternatives**: Only lawful, high-level pointers if any.

## Answer

(Replace with polite refusal and safe guidance.)
```

---

## Example E — Implementation task

**User:** In Node, write a small helper that reads `.env` and validates required keys.

**Shape:**

```markdown
## How should I think about this question

Implementation task. I will fix dependencies, function signature, failure behavior, then code plus usage.

## Thinking

- **Goal**: Reusable validation helper and how to call it.
- **Constraints**: ESM vs CJS not specified; give ESM with a CJS note.
- **Design**: e.g. `loadAndValidate(keys: string[])`; aggregate missing keys in errors.
- **Risk**: Remind not to commit secrets.
- **Testing**: Temp `.env` and missing-key cases.

## Answer

(Replace with code, usage, and notes.)
```

---

## Example F — Subjective comparison

**User:** Is vim or VS Code better?

**Shape:**

```markdown
## How should I think about this question

"Better" depends on task and person. I will unpack criteria, map them to both tools, and give conditional guidance without dismissing either choice.

## Thinking

- **Goal**: Help choose, not pick a winner by authority.
- **Criteria**: Modal editing, extensions, remote dev, learning curve, team norms.
- **Answer shape**: If-then recommendations.
- **Boundary**: Do not insult the user's current editor.

## Answer

(Replace with scenario-based guidance.)
```

---

## Example G — Math derivation

**User:** How do you derive the sum of the first n terms of an arithmetic sequence?

**Shape:**

```markdown
## How should I think about this question

Standard derivation. Pairing or algebraic cancellation to get S_n, with definitions and quick checks.

## Thinking

- **Goal**: Understand why the formula holds.
- **Definitions**: a_1, d, S_n = sum_{k=1}^n a_k.
- **Methods**: Gauss pairing or telescoping.
- **Checks**: n = 1 and n = 2.

## Answer

(Replace with derivation and formula.)
```

---

## Example H — User overrides format

**User:** Don't answer in three sections. At the same time this skill asks for three sections.

**Shape:**

```markdown
## How should I think about this question

The user's latest instruction conflicts with the default layout. User instruction wins; Thinking records that; Answer follows the shape they asked for.

## Thinking

- **Conflict**: Three sections vs user ban.
- **Precedence**: Explicit user override.
- **Adjustment**: Single merged reply while still reasoning internally.

## Answer

(Replace with the user's preferred single-block content.)
```

---

## Example I — Vague request

**User:** Optimize my website. No URL or metrics.

**Shape:**

```markdown
## How should I think about this question

The request is broad. I will give a general optimization framework and data-driven process, list the smallest questions needed from you, and still offer steps that do not require your specifics.

## Thinking

- **Gaps**: Stack, traffic, bottlenecks, goal such as latency, conversion, or SEO.
- **Strategy**: Generic checklist plus clarification questions; avoid inventing site facts.
- **Risk**: Wrong assumptions could mislead; label assumptions.

## Answer

(Replace with layered advice and questions.)
```

---

## Example J — Code in repo

**User:** Why does this function infinite-loop? File path attached.

**Shape:**

```markdown
## How should I think about this question

Needs the concrete loop condition and state updates. If the file was read, Thinking summarizes logic; Answer cites code and states why the exit condition never advances and how to fix.

## Thinking

- **Evidence**: e.g. `while` depends on a variable that never changes in the body.
- **Causation**: Exit condition unreachable.
- **Fix**: Increment, `break`, or different loop form; watch off-by-one.
- **Verification**: Minimal input and expected behavior.

## Answer

(Replace with citations, explanation, and patch suggestion.)
```

---

## Using these examples

1. Replace placeholder lines such as "Replace with …" with real content.
2. Scale length to the task; do not pad.
3. For policy-sensitive cases, Example D still applies: compliance and refusal come first.

More rules: [SKILL.md](SKILL.md). More dimensions: [reference.md](reference.md).
