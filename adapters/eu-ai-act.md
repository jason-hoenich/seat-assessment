# EU AI Act

Mapping of SEAT outcomes to EU AI Act obligations for providers and deployers, centered on the Article 4 AI literacy duty as amended by the Digital Omnibus on AI (June 2026).

**Version:** 2024/1689 (Digital Omnibus, June 2026)  
**Adapter last updated:** 2026-07-08  
**Official reference:** https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689  
**Adapter id:** `eu-ai-act`

## How an assistant applies this adapter

You need the respondent's per-question scores (1-5) from `assessment/questions.md`, produced by the flow in `AGENTS.md`. Then:

1. **Compute each outcome score.** Every question carries a SEAT outcome id (see `adapters/outcomes.md`). For an outcome, average the scores of its questions, skipping any answered N/A, and round to one decimal. An outcome with no answered questions scores 0.
2. **Decide met or gap, per assurance level.** The threshold depends on the mapping's assurance level, not a single global number:
   - Required: outcome score >= 4.5
   - Expected: outcome score >= 2.5
   - Recommended: outcome score >= 1.5
   An outcome is met when its score is at or above the threshold for that row, otherwise it is a gap.
3. **List missing evidence.** For any unmet row whose assurance level is Required or Expected, report that row's evidence types as missing evidence, together with its framework reference.
4. **Compute the overall alignment score.** For each row the effective score is the outcome score when met. When not met it is `(outcome score / 5) * threshold * 0.5`, the penalty the platform applies. Multiply each effective score by the row weight (default 1), sum, divide by total weight, round to one decimal. The result is on a 0 to 5 scale, not a percentage.

Report met, gap, and missing evidence per requirement, then the overall score. Do not invent requirements that are not in the table below, and never answer the assessment questions on the respondent's behalf.

## Mapping table

| SEAT outcome | Outcome id | Framework reference | Assurance | Evidence expected | Cadence | Weight |
|---|---|---|---|---|---|---|
| Strategic Alignment | `strategic-alignment` | Art. 4 | Expected | Policy Document, Assessment Report | Annual | 4 |
| Governance Documentation | `governance-documentation` | Art. 4 | Required | Policy Document, Training Record, Assessment Report | Annual | 5 |
| Executive Support | `executive-support` | Art. 4 | Expected | Board Minutes, Training Record | Annual | 3 |
| Continuous Improvement | `continuous-improvement` | Art. 4, Art. 50 | Expected | Assessment Report, Policy Document | Continuous | 3 |
| Targeted Communication | `targeted-communication` | Art. 4 | Required | Communication Artifact, Curriculum Document, Training Record | Continuous | 5 |
| Active Participation | `active-participation` | Art. 4, Art. 50 | Recommended | Feedback Survey, Incident Report | Continuous | 3 |
| Performance Measurement | `performance-measurement` | Art. 4 | Expected | Metric Report, Assessment Report | Annual | 4 |
| Risk Driven Assessment | `risk-driven-assessment` | Art. 4 | Expected | Assessment Report, Policy Document | Annual | 4 |
| Relevant Tailored Training | `relevant-tailored-training` | Art. 4 | Required | Curriculum Document, Training Record | Annual | 5 |
| Accessible Inclusive Training | `accessible-inclusive-training` | Art. 4 | Required | Training Record, Metric Report | Continuous | 4 |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | Art. 4, Art. 26 | Expected | Training Record, Curriculum Document, Other | Onboarding | 3 |

## Mapping notes

**Strategic Alignment (Art. 4).** Art. 4 measures must account for the context in which AI systems are used and the persons they are used on. An AI literacy program disconnected from how the organization deploys AI does not satisfy the duty. Program strategy should inventory AI use cases and align literacy measures to them.

**Governance Documentation (Art. 4).** The Omnibus reframed Art. 4 from an outcome guarantee to demonstrable measures. That makes documentation the compliance artifact: what measures were taken, for whom, on what basis, reviewed when. An undocumented literacy effort is legally indistinguishable from no effort.

**Executive Support (Art. 4).** Art. 4 applies to staff and other persons dealing with the operation and use of AI systems on the organization's behalf, which includes decision-makers who approve AI deployments. Management that mandates AI adoption without understanding its failure modes undermines the duty.

**Continuous Improvement (Art. 4, Art. 50).** AI systems, use cases, and obligations change faster than annual training cycles. Art. 50 transparency obligations apply from 2 August 2026 with watermarking for already-marketed systems grace-perioded to 2 December 2026; literacy measures need a review loop that tracks these dates and new deployments.

**Targeted Communication (Art. 4).** Art. 4 explicitly requires measures to take into account technical knowledge, experience, education and training of staff, and the context of use. A single generic AI awareness module for the whole workforce fails this on its face. Persona-targeted delivery is written into the article.

**Active Participation (Art. 4, Art. 50).** Shadow AI use is the practical failure mode of AI literacy. A program where employees disclose AI use and report AI-related concerns produces the behavioral evidence that literacy measures are working; a program where AI use stays hidden produces none.

**Performance Measurement (Art. 4).** Art. 4 does not mandate effectiveness measurement the way NIS2 Art. 21(2)(f) does; completion of a literacy course can technically count as a measure. But "appropriate" measures invite the question of appropriateness, and measured programs are far easier to defend to a market surveillance authority than certificate binders.

**Risk Driven Assessment (Art. 4).** Appropriate measures scale with the risk of the AI systems in use. Literacy measures for staff operating consequential systems should be deeper than for casual chatbot users. A risk-tiered training map is the natural evidence that proportionality was considered.

**Relevant Tailored Training (Art. 4).** The core of the duty. AI literacy training tailored to role, prior knowledge, and the specific systems in use, covering both operating AI competently and recognizing its risks (hallucination, over-reliance, data leakage, deepfakes). Generic AI 101 content for everyone is the compliance-theater version.

**Accessible Inclusive Training (Art. 4).** Art. 4 covers staff and other persons operating or using AI systems on the organization's behalf, which reaches contractors and third parties, not just employees. Coverage reporting across the full population in scope is the evidence.

**Integrated Training Lifecycle (Art. 4, Art. 26).** Literacy needs change when a person's AI exposure changes: onboarding, new tool rollouts, role changes into AI-operating positions. Art. 26 human oversight competence requirements for high-risk deployers (deferred to Dec 2027 / Aug 2028) will raise the bar for specific roles; building the lifecycle now avoids retrofitting later.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.