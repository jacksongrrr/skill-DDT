# Think Before Answer — Examples

For the **agent** only. Contract: [SKILL.md](SKILL.md). **Reasoning channel** = internal thinking strip / `reasoning_content` / equivalent. **User-visible** = what appears in the main chat.

---

## Example 1 — Business idea (matches common failure mode)

**User (Chinese):** 帮我想一个普通人赚钱的商业模式

**Reasoning channel** (everything that must **not** appear as the main bubble):

```text
[Framing]
Open-ended business-model request for “ordinary person” = low capital, executable side income, realistic constraints. Will run TM1–TM6, ≥3 approaches A1–A3+ with pros/cons, then pick one primary recommendation for the user-facing reply.

**TM1 — Intent and scope**
User wants a concrete monetization pattern for someone without special credentials or large capital; answer should be actionable this year.

**TM2 — Facts, gaps, and assumptions**
No city, skills, or hours given. Assume urban/suburban, 5–10h/week side time, online + local mix unless corrected.

**TM3 — Candidate approaches**
- **A1** — Local service arbitrage (errands, cleaning, pet care via platforms).
- **A2** — Skill productization (template, mini-course, Notion pack) sold once or low-touch.
- **A3** — Content + affiliate or lead-gen in a narrow niche.

**TM4 — Pros and cons**
(A1: fast cash, proven demand; cons: time-for-money, platform fees.)
(A2: scalable margin; cons: marketing learning curve, saturation risk.)
(A3: compounding audience; cons: slow to revenue, algorithm risk.)

**TM5 — Commitment**
Lead with A1 as fastest validation, mention A2 as upgrade path; note A3 if user enjoys writing/video.

**TM6 — Verification and risks**
Suggest MVP test (3 customers / 2 weeks); legal/tax basics; no income guarantees.
```

**User-visible message** (no TM, no “I will analyze…”, no skill headings):

```markdown
下面是一个适合普通人、启动成本相对低、可先做验证的方向：**本地生活服务 + 平台接单**（跑腿、临时保洁、上门喂宠、简单安装等）。

**为什么适合起步：** 需求真实、现金回流快，不需要先做大流量；缺点是要用时间换钱，平台会抽成。

**两周内最小验证：** 选 1 个你方便做的细分（例如“同小区跑腿/取送”），在常用本地平台或小区群挂牌；目标先完成 **3 单真实服务**，记录耗时、客单价、复购意愿。

**若想以后少绑在时间上：** 把重复话术、报价清单、服务流程整理成模板（向“轻量产品化”过渡）；有表达习惯再考虑垂直内容或小型数字产品。

以上为思路示例，不构成投资或法律建议；落地前请留意当地资质与税务要求。
```

---

## Example 2 — REST vs GraphQL (English user)

**Reasoning channel:** Full TM1–TM6 with A1 REST-first, A2 GraphQL, A3 hybrid; pros/cons; TM5 conditional recommendation; TM6 validation.

**User-visible:** A clean comparison table plus “If … then …” recommendations—**no** A1/A2 labels, no TM mentions.

---

## Example 3 — Courtesy only

**User:** OK

**Reasoning channel:** `No substantive task; courtesy only.`

**User-visible:** `OK`

---

## Example 4 — Single stream host

If only one assistant text field exists: perform TM1–TM6 **without writing them**, then output **only** the same kind of user-visible body as Example 1’s second block.
