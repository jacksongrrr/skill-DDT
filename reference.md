# Think Before Answer — Reference

Supplement to [SKILL.md](SKILL.md). Apply sections 0–3 of SKILL.md first; open this file when you need extra detail.

If this file disagrees with SKILL.md, SKILL.md wins.

---

## 0. Reasoning channel vs formal answer (DeepSeek-style)

**Thinking** holds the long trace: TM1–TM6, alternatives, pros/cons, step-by-step work. **Answer** holds the **artifact** the user would get if the UI hid the reasoning stream—clean steps, code, conclusions, refusals. A short bridge sentence in **Answer** is fine; duplicating the whole reasoning trace there is not.

---

## 1. Why split understanding and conclusion

1. **Checkability**: Readers can judge premises and spot skipped steps.
2. **Teaching**: Others can reuse the reasoning pattern.
3. **Collaboration**: Assumptions that need alignment appear in the open.
4. **Debugging errors**: Easier to see whether the mistake was intent, fact, or logic.

Do not recite this benefits list to the user unless they ask why the format exists.

---

## 2. Section 1 — "How should I think about this question"

### 2.1 Optional internal structure

You may use plain paragraphs. Logical threads can include:

- **Paraphrase**: Same request in other words to surface ambiguity.
- **Information state**: Known vs missing; whether you must ask follow-ups.
- **Task type**: Explain, compare, implement, debug, review, creative, other.
- **Success criteria**: What counts as done.

### 2.2 Length

| Complexity | Guidance |
|------------|----------|
| Low | 2–4 sentences |
| Medium | One paragraph plus optional list |
| High | At most two paragraphs; move depth to section 2 |

### 2.3 Do not

- Put the final answer that belongs in section 3.
- Stack generic filler with no concrete intent.
- Mirror the user's wording without adding structure.

---

## 3. Section 2 — "Thinking" structure

SKILL.md **§3.2** is authoritative: **TM1–TM6** must all appear **in order**, each labeled and filled with **task-specific** prose. **TM3** must list **≥ X** candidates (default X = 3) when that many honest options exist; **TM4** must give **pros and cons for every** TM3 candidate.

The lists below are **content reminders** to weave **inside** the TM passes where relevant. They are **not** a substitute for skipping TM labels.

### 3.1 General (often TM1–TM2 and parts of TM5–TM6)

1. Stated goal vs deeper goals such as efficiency, safety, maintainability, compliance.
2. Stakeholders when relevant: team, end users, operations.
3. One-shot answer vs long-lived design.
4. Evidence strength: inference, docs, experiment, authority, or explicit uncertainty.

### 3.2 Software (often TM2–TM4 when comparing implementations)

- Stack: language version, framework, OS, dependencies.
- Change scope: minimal fix vs refactor; public API impact.
- Testing: how to verify; edge cases.
- Performance and security: complexity, permissions, injection, secrets.
- Consistency with the codebase: patterns and naming.

### 3.3 Writing and communication

- Audience: expert vs general; formality.
- Structure: narrative vs argument flow.
- Fact volatility: prices, law, version numbers.

### 3.4 Math and logic

- Definitions and theorem preconditions.
- Validity of each transformation step.
- Numerical stability when relevant.

### 3.5 Sensitive topics

- Dual-use risk.
- Jurisdiction and compliance differences.
- Refusal plus lawful alternatives when applicable.

### 3.6 Refusal or policy-limited tasks

Still run **TM1–TM6**. **TM3** may list only compliant response patterns (e.g. refuse, redirect, high-level safe education). **TM4** compares their pros and cons for safety and user experience. Do not invent harmful “approaches” to pad X.

---

## 4. Section 3 — delivery

Section 2 may be long; section 3 should ship value:

1. Lead with the conclusion when appropriate, then key reasons, then optional depth.
2. Avoid verbatim duplication of section 2; use short bridges.
3. Steps, commands, paths, and checklists should be executable or verifiable.
4. Mark uncertainty and how to verify or what to supply next.

---

## 5. Scenario notes

### 5.1 Screenshots or logs

In Thinking, note signals extracted. In Answer, give diagnosis and fixes, or the smallest extra info you need.

### 5.2 Code only

If the user forbids long prose, note that in Thinking, keep Thinking short, put code in Answer, keep all three headings.

### 5.3 Multiple questions

Section 1 states how you will split and order sub-questions. Use subsections in 2 and 3 if helpful.

### 5.4 Continuations

State which prior-turn assumptions you rely on. You may open Thinking with incremental analysis under the same constraints.

---

## 6. Anti-patterns

| Issue | Symptom | Fix |
|-------|---------|-----|
| Wrong title word | Misspelling "should" | Use the exact SKILL.md string |
| Skipped TM | Missing TM4 or merged TM2+TM3 | Emit TM1–TM6 in order with labels |
| Too few options | TM3 lists one approach when three honest ones exist | Add real alternatives or justify scarcity |
| TM4 mismatch | Pros/cons missing for an TM3 candidate | Cover every A1, A2, … from TM3 |
| Hollow Thinking | Labels only, no sentences | Substantive prose per TM block |
| Answer in section 1 | Final verdict in framing | Keep framing non-final |
| Duplicate paste | Sections 2 and 3 identical | Compress Answer |
| False certainty | Strong claims with no basis | State inference and how to verify |
| Ignoring tools | Output contradicts tool output | Align with tool results |
| Reasoning in Answer | Long CoT or TM replay under `## Answer` | Move trace to `## Thinking`; keep Answer formal |

---

## 7. Tools and other skills

### 7.1 Tools

In Thinking, briefly why a tool ran and how output changed the plan. In Answer, quote only what the user needs, not full raw dumps.

### 7.2 Code context

Summarize file roles in Thinking; use normal code citation conventions in Answer.

### 7.3 Other prompts or skills

More specific domain rules take precedence over this layout. If you merge rules, say so in Thinking. Prefer keeping the three headings when possible for readability.

---

## 8. Readability

- Use headings and lists for long answers.
- Fence code with language tags; one command per line or clear breaks.
- Follow the user's language and typographic preferences for mixed Chinese and English when the user sets them.

---

## 9. Extended self-check

1. Are **TM1–TM6** all present, in order, each with a label line and non-generic content?
2. Does **TM3** meet the **≥ X** rule or document why fewer candidates are honest?
3. Does **TM4** list **pros and cons for every** TM3 candidate?
4. If Thinking were removed, could the user still see why Answer is justified?
5. If Answer were removed, could the user reconstruct a usable conclusion from Thinking? If not, Answer is incomplete.
6. Are the three section titles character-exact?
7. Any leaked secrets, tokens, or private data?
8. User rules on language, format, and prohibitions satisfied?

---

## 10. Glossary

| Term | Meaning |
|------|---------|
| Three-part layout | Section 1 + Thinking + Answer |
| Metacognitive framing | Explicit statement of how you approach the problem |
| Deliverable | What the user copies or executes from section 3 |
| Constraint | Bounds on valid solutions |

Keep terminology aligned with SKILL.md.

---

## 11. Maintainer notes

Track versions in the repository README. Major changes to title strings, exceptions, or precedence belong in SKILL.md first, then reference and examples.

---

## 12. Internal scaffolding

You may reorganize these into Thinking without using them as visible subheadings:

- What is the user actually asking?
- What facts do I have; what is missing?
- What reasonable options exist; which do I choose; at what cost?
- What could be wrong; how do I verify?
- What is the smallest sufficient Answer?

---

## 13. Closing

SKILL.md defines the non-negotiable contract. This file adds detail and troubleshooting. When behavior changes, update SKILL.md, then reference.md and examples.md.
