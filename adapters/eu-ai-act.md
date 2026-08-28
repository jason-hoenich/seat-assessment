# EU AI Act

Mapping of SEAT outcomes to EU AI Act obligations for providers and deployers, centered on the Article 4 AI literacy duty as amended by the Digital Omnibus on AI (June 2026).

**Version:** 2024/1689 (Digital Omnibus, June 2026)  
**Adapter last updated:** 2026-07-08  
**Official reference:** https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689  
**Adapter id:** `eu-ai-act`

## How an assistant applies this adapter

You need the respondent's per-question scores (1-5) from `assessment/questions.md`, produced by the flow in `AGENTS.md`. Then:

1. **Compute each outcome score.** Every outcome is scored from the questions listed for it in `adapters/outcomes.md`. Average those question scores, skipping any answered N/A, and round to one decimal.
2. **Decide met or gap, per assurance level.** The threshold depends on the row's assurance level, not a single global number:
   - Required: outcome score >= 4.5
   - Expected: outcome score >= 2.5
   - Recommended: outcome score >= 1.5
   At or above the row's threshold is **met**. Below it is a **gap**. There is no partial state; the platform scores this as met or not met, and this export matches it.
3. **Rows marked "Not assessed".** Some requirements map to a SEAT outcome that no core question feeds. Report these as **not assessed**, never as a gap, and leave them out of the overall score entirely. A gap means the program was measured and fell short. Not assessed means the 21-question core instrument does not cover it. Say so plainly, list the evidence the framework expects so the respondent knows what it would take, and note that the hosted assessment at https://app.humanrisk.com asks the additional framework-specific questions that score these outcomes.
4. **List missing evidence.** For any row that is a gap at Required or Expected assurance, report that row's evidence types as missing evidence together with its framework reference.
5. **Compute the overall alignment score.** Using only the scored rows: the effective score is the outcome score when met, and `(outcome score / 5) * threshold * 0.5` when it is a gap, which is the penalty the platform applies. Multiply each effective score by the row weight, sum, and divide by the total weight of the scored rows. Round to one decimal. The result is on a 0 to 5 scale, not a percentage.

Report the overall score, met/gap per requirement, any not-assessed requirements, and missing evidence for each gap. Do not invent requirements that are not in the table below, and never answer the assessment questions on the respondent's behalf.

## Mapping table

| SEAT outcome | Outcome id | Framework reference | Assurance | Evidence expected | Cadence | Weight | Scored |
|---|---|---|---|---|---|---|---|
| Strategic Alignment | `strategic-alignment` | Art. 4 | Expected | Policy Document, Assessment Report | Annual | 4 | Yes |
| Governance Documentation | `governance-documentation` | Art. 4 | Required | Policy Document, Training Record, Assessment Report | Annual | 5 | Yes |
| Executive Support | `executive-support` | Art. 4 | Expected | Board Minutes, Training Record | Annual | 3 | Yes |
| Continuous Improvement | `continuous-improvement` | Art. 4, Art. 50 | Expected | Assessment Report, Policy Document | Continuous | 3 | Yes |
| Targeted Communication | `targeted-communication` | Art. 4 | Required | Communication Artifact, Curriculum Document, Training Record | Continuous | 5 | Yes |
| Active Participation | `active-participation` | Art. 4, Art. 50 | Recommended | Feedback Survey, Incident Report | Continuous | 3 | Yes |
| Performance Measurement | `performance-measurement` | Art. 4 | Expected | Metric Report, Assessment Report | Annual | 4 | Yes |
| Risk Driven Assessment | `risk-driven-assessment` | Art. 4 | Expected | Assessment Report, Policy Document | Annual | 4 | Yes |
| Relevant Tailored Training | `relevant-tailored-training` | Art. 4 | Required | Curriculum Document, Training Record | Annual | 5 | Yes |
| Accessible Inclusive Training | `accessible-inclusive-training` | Art. 4 | Required | Training Record, Metric Report | Continuous | 4 | Yes |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | Art. 4, Art. 26 | Expected | Training Record, Curriculum Document, Other | Onboarding | 3 | Yes |

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