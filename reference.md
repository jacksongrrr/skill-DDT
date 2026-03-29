# Think Before Answer — Reference

Supplement to [SKILL.md](SKILL.md). Apply sections 0–3 of SKILL.md first; open this file when you need extra detail.

If this file disagrees with SKILL.md, SKILL.md wins.

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

## 3. Section 2 — "Thinking" dimensions

Pick what fits; omit what does not apply. Omissions must not break the reasoning chain.

### 3.1 General

1. Stated goal vs deeper goals such as efficiency, safety, maintainability, compliance.
2. Stakeholders when relevant: team, end users, operations.
3. One-shot answer vs long-lived design.
4. Evidence strength: inference, docs, experiment, authority, or explicit uncertainty.

### 3.2 Software

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
| Hollow Thinking | Labels only, no sentences | At least one sentence per point |
| Answer in section 1 | Final verdict in framing | Keep framing non-final |
| Duplicate paste | Sections 2 and 3 identical | Compress Answer |
| False certainty | Strong claims with no basis | State inference and how to verify |
| Ignoring tools | Output contradicts tool output | Align with tool results |

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

1. If Thinking were removed, could the user still see why Answer is justified?
2. If Answer were removed, could the user reconstruct a usable conclusion from Thinking? If not, Answer is incomplete.
3. Are the three titles character-exact?
4. Any leaked secrets, tokens, or private data?
5. User rules on language, format, and prohibitions satisfied?

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
