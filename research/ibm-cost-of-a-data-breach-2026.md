# IBM Cost of a Data Breach Report 2026

Breach-cost benchmark evidence on the AI governance gap, mapped to the SEAT outcomes it informs.

**Publisher:** IBM, research conducted by Ponemon Institute
**Coverage:** 3,558 interviews across 602 organizations that suffered a breach between March 2025 and February 2026; 16 countries and geographic regions, 17 industries
**Published:** 2026-07-29
**Source last updated:** 2026-09-06
**Official reference:** https://www.ibm.com/reports/data-breach
**Source id:** `ibm-codb-2026`
**Source type:** Breach-cost benchmark from organizational interviews (practitioner and C-suite self-report). Its distinctive value is cost benchmarking; treat behavioral claims cautiously.

## How an assistant applies this source

You need the respondent's per-question scores (1-5) and their outcome scores, produced by the flow in `AGENTS.md` and `adapters/outcomes.md`. Then:

1. **Compute outcome scores first.** Every finding below is anchored to SEAT outcomes by outcome id.
2. **Findings are evidence, never scores.** Nothing here changes a score, adds a requirement, or creates a gap. Compliance status comes only from `adapters/`.
3. **Only use figures that appear in this file,** and always name the population, because this report has three different dollar figures for three different groups (see the cost note).
4. **The governance-gap percentages are the load-bearing figures for SEAT, not the dollar figures.** A respondent scoring low on governance is looking at their own posture in the population that got breached.
5. **Do not use the cost figures to imply causation.** These are the costs breached organizations reported; they establish scale and a business case, not that a specific control would have prevented a specific breach.

## Findings mapped to SEAT outcomes

| Finding | Figure | SEAT outcome | Outcome id | What a low score here exposes |
|---|---|---|---|---|
| Governance is missing exactly where breaches happen | 68% of breached organizations lacked AI governance to manage AI or detect shadow AI, worse than 63% the prior year | Governance Documentation | `governance-documentation` | Governance that is not just absent but eroding during the fastest AI-adoption year on record |
| Access controls are the exception, not the rule | Among organizations with an AI-related breach, 92% lacked proper AI access controls; only 40% of all organizations use access controls on AI models and data | Governance Documentation | `governance-documentation` | Documented policy with no enforcing control behind it, which is the gap that does not require attacker sophistication |
| Shadow AI is now measurable and expensive | Shadow AI incidents more than doubled to 43% of security incidents from 20%; breaches involving shadow AI averaged USD 5.39M against USD 4.63M last year | Risk Driven Assessment | `risk-driven-assessment` | An assessment that treats shadow AI as hypothetical when it is now a measured and costed incident category |
| Oversight is being deprioritized during peak adoption | Only 38% required IT approval before AI deployment, down from 45%; only 19% coordinated governance and security team efforts | Strategic Alignment | `strategic-alignment` | AI decisions made without the approval gate and without governance and security talking to each other |
| The cost of inaction has a number | Global average breach cost reached a record USD 4.99M, up 12% (from USD 4.44M in 2025) | Executive Support | `executive-support` | A program that cannot put a figure on what it protects against, arguing for budget without the number that wins the argument |

## Notes by outcome

**Governance Documentation (`governance-documentation`).** This is the center of the report for SEAT. The 68% figure is the "activity without measurement" argument arriving in someone else's data, and the year-over-year worsening from 63% is the sharper point: adoption accelerated and governance went backwards. Pair it with the 92% and 40% access-control figures to separate policy from enforcement. A respondent can have a written AI policy and still sit in the 60% that lacks governance, because governance here includes the controls and monitoring that make a policy real.

**Risk Driven Assessment (`risk-driven-assessment`).** The doubling of shadow-AI incidents to 43%, with a dollar figure attached, converts shadow AI from a talking point into an assessable risk category. Use it when a respondent scores low on risk-driven assessment and has no line item for AI at all.

**Strategic Alignment (`strategic-alignment`).** The 38%-down-from-45% approval figure and the 19% coordination figure are both organizational-structure findings. They argue that the awareness program cannot own AI risk alone, because the failure is upstream, in who approves AI and whether governance and security are even in the same conversation.

**Executive Support (`executive-support`).** The USD 4.99M average is the business-case number. It is a benchmark, not the respondent's own exposure, so present it as the scale of the problem class rather than as their expected loss.

## Provenance and limits

Organizational self-report gathered through 3,558 structured interviews at 602 breached organizations, modeled into cost estimates by Ponemon Institute. It is the strongest available source for the scale and cost of breaches and for what breached organizations report about their own governance posture. It is the wrong source for attacker behavior, for how a general workforce behaves, or for causal claims that a given control prevents a given breach.

**Cost figures belong to three different populations. Keep them separate.**

- USD 4.99M is the global average cost of a data breach across all breaches this year, up 12% from USD 4.44M in 2025 (2024 was USD 4.88M).
- USD 5.39M is the average cost of breaches that involved shadow AI, against USD 4.63M last year. This is the figure some coverage confuses with the overall average.
- The roughly USD 6M figures are narrower still: model inversion breaches USD 6.07M, prompt injection breaches USD 5.89M, financial-services breaches USD 6.29M.

There is no USD 6M "overall average" in this report. Any claim that the overall average rose to USD 6M from USD 4.99M is a misread; USD 4.99M is this year's overall average, not last year's.

The AI-compromise cause figures (cloud security misconfigurations 27%, compromise of connected apps/APIs/plug-ins 27%) are shares of AI-related breaches by incident type, and more than one response was permitted, so they do not sum to 100.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) research sources. CC BY-ND 4.0.
