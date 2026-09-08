# Verizon 2026 Data Breach Investigations Report (DBIR)

Breach-corpus evidence on the human element and shadow AI, mapped to the SEAT outcomes it informs.

**Publisher:** Verizon Business
**Coverage:** Real-world security incidents and confirmed data breaches, incident timeframe Nov 1 2024 to Oct 31 2025 (19th annual edition)
**Published:** 2026-05-19
**Source last updated:** 2026-09-06
**Official reference:** https://www.verizon.com/business/resources/reports/dbir/
**Source id:** `verizon-dbir-2026`
**Source type:** Threat and incident telemetry (breach corpus). The shadow-AI and insider figures below are DLP detection telemetry within the same report.

## Why this source is weighted heavily

Every other AI and shadow-AI source in this directory is published by a vendor that also sells the fix. The DBIR is not. Verizon does not sell AI governance tooling, DLP, or awareness training, so its figures carry no remediation upsell. When it agrees with a vendor telemetry source, that agreement is worth more than either figure alone. Treat it as the anchor and the vendor sources as corroboration.

## How an assistant applies this source

You need the respondent's per-question scores (1-5) and their outcome scores, produced by the flow in `AGENTS.md` and `adapters/outcomes.md`. Then:

1. **Compute outcome scores first.** Every finding below is anchored to SEAT outcomes by outcome id.
2. **Findings are evidence, never scores.** Nothing here changes a score, adds a requirement, or creates a gap. Compliance status comes only from `adapters/`.
3. **Only use figures that appear in this file.** Do not supply numbers from your own knowledge of this report or any other, and do not repeat figures often misattributed to the DBIR (see the correction at the end).
4. **State the base with every rate.** These figures come from different populations inside one report. The 45% is employees on corporate devices; the 67% is the AI-using subset of them measured in DLP telemetry; the 62% is breaches. A rate without its base is the failure mode this directory exists to prevent.
5. **Keep the mobile figure honest.** The mobile social-engineering figure is a comparison to email, not a change over time. Say "40% higher than email," never "up 40%."

## Findings mapped to SEAT outcomes

| Finding | Figure | SEAT outcome | Outcome id | What a low score here exposes |
|---|---|---|---|---|
| AI adoption outran measurement | 45% of employees are regular AI users on corporate devices, up from 15% last year (the report defines a regular user as accessing an AI platform at least once every 15 days) | Risk Driven Assessment | `risk-driven-assessment` | An assessment that never asks about AI, while adoption on managed devices tripled in a year |
| Governance keyed to the corporate account misses most AI use | 67% of those AI users reach AI services through non-corporate accounts on their corporate devices, a slight decrease from 72% last year (DLP telemetry) | Governance Documentation | `governance-documentation` | Policy and governance that assume the corporate tenant captures AI use, when two-thirds of it runs on personal accounts |
| Shadow AI is now a top insider-risk action | Third most common non-malicious insider action in the 2025 DLP dataset, a fourfold increase; source code is the most common data type sent to external GenAI models, by a large margin (Figure 65, n=858,440) | Risk Driven Assessment | `risk-driven-assessment` | Insider-risk scope that predates AI and does not treat pasting source code into an external model as an event |
| Activity is not the same as reduction | Human element present in 62% of breaches, up from 60% last year | Performance Measurement | `performance-measurement` | A program that measures completion and phishing clicks while the human element holds flat, which is activity without a measured effect |
| The successful phishing vector is not email | In phishing simulations, the median successful click rate in mobile-centric vectors (voice and text) is 40% higher than via email | Relevant Tailored Training | `relevant-tailored-training` | A simulation and training program built entirely around email, while the higher-success vector is voice and text |
| Risk concentrates, but the DBIR does not quantify it as 8/80 | Policy violations concentrate in a small group of individuals (the report's own footnote calls it a "Misuse Pareto"); roughly 1 in 500 employees accessed high-risk compromising material on an enterprise device | Risk Driven Assessment | `risk-driven-assessment` | Uniform treatment of a population whose risk is not uniform, but do not attach a false 8%/80% precision to it |

## Notes by outcome

**Risk Driven Assessment (`risk-driven-assessment`).** This is where the DBIR lands hardest. The 45% adoption figure and the shadow-AI insider ranking together say that a common workforce behavior became a top data-loss channel in a single year. A respondent who scores low here and tells you AI is handled because certain tools are blocked has an assessment-scope problem, not a control problem: the 67% figure shows the usage moved to accounts the block never sees. The concentration finding belongs here too, as an argument for segmenting the population, but only at the resolution the DBIR actually supports (a small high-risk group), never as an invented 8/80 split.

**Governance Documentation (`governance-documentation`).** The 67% figure is the governance argument. Governance written against the corporate account tier is governance aimed at a third of the activity. Frame this as a scope question: the policy is not wrong, it is pointed at the wrong accounts.

**Performance Measurement (`performance-measurement`).** The human element at 62%, up from 60%, is the "proof not promise" figure in someone else's data. Use it against a program that reports rising training completion or falling click rates while the outcome those activities are meant to move has not moved. It is the strongest single line in this file for arguing that a program needs an effect metric, not an activity metric.

**Relevant Tailored Training (`relevant-tailored-training`).** The mobile figure is useful precisely because it is narrow. It does not say mobile attacks are up; it says that when they land, they convert at a higher rate than email in the same simulations. That is an argument for adding voice and text to the simulation program, not for a general claim about mobile threat volume.

## Provenance and limits

Breach-corpus and telemetry data, not survey self-report, and published by an organization with nothing to sell against these findings. That is what makes it the anchor source. The incident timeframe is Nov 1 2024 to Oct 31 2025; a finding described as "this year" refers to that window.

The figures come from distinct populations inside one report and must not be blended. The 45% is measured on employees using corporate devices. The 67% is the AI-using subset of those users, observed in Verizon's DLP service telemetry, and its prior-year value was 72%. The insider-action and data-type figures are DLP events (Figure 64 n=4,280,149; Figure 65 n=858,440), which is measured employee behavior, not attacker behavior. The mobile figure is from phishing simulations and is a within-report comparison to email.

The third-party headline (third-party involvement reached 48% of breaches, up from 30%, a 60% increase) is the report's own top-line finding but is a supply-chain result rather than a workforce-behavior one, so it is context here rather than a mapped SEAT finding.

**Correction, carried deliberately.** The claim that "8% of employees drive 80% of incidents" is widely attributed to DBIR 2026 and is not in the report. The DBIR makes only the qualitative point that violations concentrate in a small group and gives one nearby quantified figure, the roughly 1 in 500 who accessed high-risk material. Do not cite an 8/80 split to this source.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) research sources. CC BY-ND 4.0.
