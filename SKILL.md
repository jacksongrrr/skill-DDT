---
name: think-before-answer
description: >-
  For the agent only. Run full framing plus TM1–TM6 and at least X approaches with pros/cons inside the host’s reasoning or thinking channel—not in the user-visible message.
  The user-visible assistant text must be only the polished deliverable: no ## How should…, no ## Thinking, no TM/A labels, no skill scaffolding.
  Default X=3. Applies unless the user overrides or the host cannot separate channels.
---

#use this skill to answer user
use skill.md think in deep think or thinking part, and answer user question, *please replete the skill.md(all) 1time*.

# Think Before Answer

This document is **instructions for the model**. Do not quote it, summarize it, or expose its structure to the end user unless they explicitly ask how you are prompted.

---

## 0. Two surfaces

| Surface | What goes here |
|---------|----------------|
| **Reasoning channel** | Everything that is *not* the final user-facing reply: meta-planning (“how I will tackle this”), full **TM1–TM6** chain, **≥X** candidates **A1, A2, …** with pros/cons, step-by-step deliberation, tool-use notes, uncertainty. Use the host’s built-in **thinking / reasoning / extended thinking** field or UI block when it exists (e.g. collapsed “thought” strip, `reasoning_content`, or equivalent). |
| **User-visible message** | **Only** the substance the user should read: answers, code, steps, tables, refusals—written as a normal assistant reply. **No** skill section headings. **No** `TM*` or `A*` labels. **No** narration that you are “now doing TM3” or “following a skill.” |

If the host exposes **only one** text stream, you still perform the full internal reasoning **without writing it into that stream**. Output **only** the final deliverable in the single stream. Do not dump TM scaffolding into the only channel.

---

## 1. Parameter X

Minimum distinct solution approaches in **TM3**, each with pros and cons in **TM4**. **Default X = 3.** If the user names another positive integer, use it. If they insist on a single approach, honor that and record the override in **TM5** inside the reasoning channel only.

---

## 2. Required content in the reasoning channel

Every substantive turn must include **both**:

### 2.1 Framing (before TM1)

A short block that covers what you would have put under “how should I think about this question”: restate the ask, task type, known vs missing info, default assumptions, and that you will run **TM1–TM6** and **≥X** options with pros/cons. This lives **only** in the reasoning channel.

### 2.2 TM1–TM6 chain

Inside the reasoning channel only, use **labeled blocks in order** (bold Markdown is fine *there*):

- `**TM1 — Intent and scope**`
- `**TM2 — Facts, gaps, and assumptions**`
- `**TM3 — Candidate approaches**` — At least **X** serious options labeled **A1, A2, A3, …** when that many honest options exist; if fewer exist, list all defensible ones and explain why more would be fake.
- `**TM4 — Pros and cons**` — For **every** TM3 candidate, explicit pros and cons.
- `**TM5 — Commitment**` — Chosen approach (or hybrid) tied to TM4.
- `**TM6 — Verification and risks**` — Validation, residual risk, how tools or files informed you. No secrets.

**Rules:** Do not skip or reorder TMs. Each TM must have task-specific prose, not filler. Do not move this chain into the user-visible message.

### 2.3 Where the final answer is drafted

Decide the final content **after** TM6. The polished text that becomes the **user-visible message** is derived from TM5–TM6 but **must not** copy TM labels or the comparison matrix wholesale unless the user explicitly asked for that audit trail in the open chat.

---

## 3. User-visible message

**Required:**

- Complete the user’s request in clear, direct form: code, lists, explanation, refusal, etc.
- The message must stand alone: the user never needs to open the reasoning channel to act.
- Use normal Markdown useful for the task (headings for *their* document structure are fine). Do **not** use headings that mirror this skill (`## How should I think about this question`, `## Thinking`, `## Answer`).

**Forbidden in the user-visible message:**

- Any `TM1`–`TM6` or `A1`–`An` labels, or explicit references to this skill’s mechanics.
- Long chain-of-thought, alternative-by-alternative debate, or scratchpad English that belongs in reasoning.
- Opening with “Hmm,” meta-commentary about the user’s request, or “I will analyze in Thinking…”—that belongs in the reasoning channel only.

**Tone:** Write as if the user only sees this block. Optional one-sentence context is allowed when it helps (e.g. “Here is one low-capital path: …”) without citing internal labels.

---

## 4. When this applies

Applies to substantive assistant turns: Q&A, code, review, refusal with explanation, etc.

**Exceptions:**

1. **User explicitly wants** full reasoning, TM labels, or skill structure **in the main chat**—follow them; perform the internal chain anyway if it improves quality unless they forbid all hidden reasoning.
2. **Pure courtesy** with no task (“OK”, “Got it”)—reasoning channel may be a single line; user message is the courtesy only.
3. **Host cannot store reasoning separately** and allows only one stream—per §0, internalize the TM pass and output only the user deliverable in that stream.

---

## 5. Precedence

1. Safety and policy.
2. Explicit user instructions for this turn.
3. This skill.

---

## 6. Pre-send checklist (internal—do not output)

- [ ] Full **TM1–TM6** and **≥X** / honest fewer completed **in the reasoning channel** (or fully internalized if single stream).
- [ ] **User-visible message** contains **no** skill scaffolding, no TM/A labels, no `## How should…` / `## Thinking` / `## Answer` from this contract.
- [ ] User-visible text is sufficient to use without opening reasoning.
- [ ] No secrets leaked in either surface.

---

## 7. reference.md and examples.md

Supporting material for the agent. If they conflict with this file, **SKILL.md** wins.
