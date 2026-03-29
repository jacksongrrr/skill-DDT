# Think Before Answer — Reference

Supplement for the **agent**. Read [SKILL.md](SKILL.md) first. If this file disagrees with SKILL.md, SKILL.md wins.

---

## 0. Mapping to hosts

| Host idea | Reasoning channel | User-visible message |
|-----------|-------------------|----------------------|
| DeepSeek-style | Reasoning / 深度思考 stream | Main answer content |
| Cursor / similar | Collapsed “thought” or extended-thinking UI | Chat bubble shown to the user |
| Chat Completions with `reasoning_content` | That field | `content` / main assistant text |
| Single field only | Mental-only TM pass; **do not print** | The only printed text = deliverable |

Never paste TM scaffolding into the user-visible field to “prove” compliance.

---

## 1. Framing block (reasoning channel only)

Before TM1, briefly cover: paraphrase, task type, known vs missing facts, assumptions, and intent to run TM1–TM6 plus ≥X options. Do not put the final recommendation here.

---

## 2. TM passes — content hooks

Weave these **inside** the reasoning channel’s TM blocks where relevant.

### 2.1 General

Goals, stakeholders, one-shot vs long-lived design, evidence strength.

### 2.2 Software

Stack, change scope, tests, security, codebase consistency.

### 2.3 Writing / communication

Audience, structure, volatile facts.

### 2.4 Math / logic

Definitions, valid steps, numerical stability.

### 2.5 Sensitive / refusal

Compliant options only in TM3; compare refusal vs redirect vs safe education in TM4. Do not pad with harmful approaches.

---

## 3. User-visible message

- Ship the **artifact**: steps, code, conclusion, refusal.
- Headings are for **the user’s** document, not for this skill.
- Optional one plain sentence of context without TM/A vocabulary.

---

## 4. Scenarios

- **Logs / screenshots:** Interpret in reasoning; fix steps in user message.
- **Code-only request:** Keep reasoning compact; code in user message only.
- **Multi-part ask:** Split plan in reasoning; structured reply in user message.
- **Continuation:** State prior assumptions at start of reasoning channel.

---

## 5. Anti-patterns

| Issue | Fix |
|-------|-----|
| TM1–TM6 in the user chat | Move entire chain to reasoning channel |
| “Hmm, the user wants…” in user message | Move to reasoning |
| `## How should I think…` / `## Thinking` in user message | Forbidden |
| User sees A1/A2 labels | Keep labels in reasoning only |
| Skipped TM or TM4 gap | Complete chain in reasoning |
| Fake A2/A3 to hit X | Honest count or justify fewer |

---

## 6. Tools

Log tool rationale and results in **reasoning**. User message: conclusions and minimal excerpts.

---

## 7. Self-check (internal)

1. TM1–TM6 complete in reasoning (or fully internalized if single stream)?
2. TM3/TM4 satisfy X or honest fewer?
3. User-visible body free of skill scaffolding and TM/A tokens?
4. User can act without opening reasoning?
5. Secrets in neither surface?

---

## 8. Closing

Update SKILL.md first when the contract changes, then this file and examples.md.
