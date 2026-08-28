# Digital Operational Resilience Act (DORA)

Mapping of SEAT outcomes to DORA requirements for financial entities.

**Version:** 1.0  
**Adapter last updated:** 2025-01-27  
**Official reference:** https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32022R2554  
**Adapter id:** `dora`

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
| Strategic Alignment | `strategic-alignment` | Art. 5, Art. 6 | Required | Policy Document, Board Minutes, Assessment Report | Annual | 5 |
| Governance Documentation | `governance-documentation` | Art. 6, Art. 13 | Required | Policy Document, Assessment Report | Annual | 4 |
| Executive Support | `executive-support` | Art. 5 | Required | Board Minutes, Training Record | Annual | 5 |
| Continuous Improvement | `continuous-improvement` | Art. 6, Art. 13, Art. 17, Art. 24 | Required | Assessment Report, Incident Report, Action Plan | Continuous | 5 |
| Targeted Communication | `targeted-communication` | Art. 13, Art. 14 | Required | Communication Artifact, Training Record, Curriculum Document | Continuous | 4 |
| Cultural Relevance | `cultural-relevance` | Art. 13 | Recommended | Feedback Survey, Communication Artifact | Continuous | 2 |
| Active Participation | `active-participation` | Art. 17, Art. 45 | Required | Incident Report, Feedback Survey | Continuous | 4 |
| Feedback Responsiveness | `feedback-responsiveness` | Art. 17 | Expected | Incident Report, Feedback Survey, Action Plan | As Needed | 3 |
| Performance Measurement | `performance-measurement` | Art. 6, Art. 13, Art. 24 | Required | Metric Report, Assessment Report | Quarterly | 4 |
| Risk Driven Assessment | `risk-driven-assessment` | Art. 6, Art. 24 | Required | Assessment Report, Policy Document | Annual | 5 |
| Behavioral Impact | `behavioral-impact` | Art. 26 | Expected | Simulation Results, Incident Report | Triennial | 3 |
| Relevant Tailored Training | `relevant-tailored-training` | Art. 13 | Required | Curriculum Document, Training Record | Annual | 5 |
| Effective Learning Methods | `effective-learning-methods` | Art. 13 | Expected | Training Record, Simulation Results, Feedback Survey | As Needed | 3 |
| Accessible Inclusive Training | `accessible-inclusive-training` | Art. 13 | Required | Communication Artifact | Continuous | 3 |
| Flexible Effective Delivery | `flexible-effective-delivery` | Art. 13 | Expected | Training Record | Annual | 4 |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | Art. 13 | Required | Training Record | Onboarding | 4 |

## Mapping notes

**Strategic Alignment (Art. 5, Art. 6).** DORA mandates that ICT risk management is integrated into overall risk management and overseen by the management body.

**Governance Documentation (Art. 6, Art. 13).** Comprehensive documentation of the ICT risk management framework and awareness programs is a core requirement.

**Executive Support (Art. 5).** DORA places ultimate responsibility for ICT risk and digital operational resilience on the management body, requiring their active engagement and training.

**Continuous Improvement (Art. 6, Art. 13, Art. 17, Art. 24).** DORA emphasizes continuous improvement of digital operational resilience based on incidents, testing, and evolving risks.

**Targeted Communication (Art. 13, Art. 14).** DORA requires comprehensive awareness programs and clear communication strategies for incidents, tailored where necessary.

**Cultural Relevance (Art. 13).** While not explicitly stated, effective awareness programs should consider cultural context for better engagement and understanding.

**Active Participation (Art. 17, Art. 45).** DORA requires robust incident reporting processes and encourages participation in information sharing arrangements.

**Feedback Responsiveness (Art. 17).** Learning from incidents and addressing feedback is crucial for improving resilience.

**Performance Measurement (Art. 6, Art. 13, Art. 24).** DORA requires continuous monitoring and regular testing to measure and enhance digital operational resilience.

**Risk Driven Assessment (Art. 6, Art. 24).** Risk assessments and testing are fundamental to DORA, driving the focus of resilience efforts.

**Behavioral Impact (Art. 26).** DORA's advanced testing (TLPT) implicitly assesses human behavior and response to sophisticated threats.

**Relevant Tailored Training (Art. 13).** Training must be tailored to the roles and responsibilities of staff, including senior management.

**Effective Learning Methods (Art. 13).** DORA implies that training methods should be effective in enhancing cyber maturity and preparedness.

**Accessible Inclusive Training (Art. 13).** Training must be accessible and compulsory for all relevant personnel.

**Flexible Effective Delivery (Art. 13).** While annual training is compulsory, the delivery should be effective in building resilience.

**Integrated Training Lifecycle (Art. 13).** Training is a continuous and compulsory part of staff development under DORA.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.