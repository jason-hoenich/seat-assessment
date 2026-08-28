# Digital Operational Resilience Act (DORA)

Mapping of SEAT outcomes to DORA requirements for financial entities.

**Version:** 1.0  
**Adapter last updated:** 2025-01-27  
**Official reference:** https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32022R2554  
**Adapter id:** `dora`

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
| Strategic Alignment | `strategic-alignment` | Art. 5, Art. 6 | Required | Policy Document, Board Minutes, Assessment Report | Annual | 5 | Yes |
| Governance Documentation | `governance-documentation` | Art. 6, Art. 13 | Required | Policy Document, Assessment Report | Annual | 4 | Yes |
| Executive Support | `executive-support` | Art. 5 | Required | Board Minutes, Training Record | Annual | 5 | Yes |
| Continuous Improvement | `continuous-improvement` | Art. 6, Art. 13, Art. 17, Art. 24 | Required | Assessment Report, Incident Report, Action Plan | Continuous | 5 | Yes |
| Targeted Communication | `targeted-communication` | Art. 13, Art. 14 | Required | Communication Artifact, Training Record, Curriculum Document | Continuous | 4 | Yes |
| Cultural Relevance | `cultural-relevance` | Art. 13 | Recommended | Feedback Survey, Communication Artifact | Continuous | 2 | Yes |
| Active Participation | `active-participation` | Art. 17, Art. 45 | Required | Incident Report, Feedback Survey | Continuous | 4 | Yes |
| Feedback Responsiveness | `feedback-responsiveness` | Art. 17 | Expected | Incident Report, Feedback Survey, Action Plan | As Needed | 3 | Yes |
| Performance Measurement | `performance-measurement` | Art. 6, Art. 13, Art. 24 | Required | Metric Report, Assessment Report | Quarterly | 4 | Yes |
| Risk Driven Assessment | `risk-driven-assessment` | Art. 6, Art. 24 | Required | Assessment Report, Policy Document | Annual | 5 | Yes |
| Behavioral Impact | `behavioral-impact` | Art. 26 | Expected | Simulation Results, Incident Report | Triennial | 3 | **Not assessed** |
| Relevant Tailored Training | `relevant-tailored-training` | Art. 13 | Required | Curriculum Document, Training Record | Annual | 5 | Yes |
| Effective Learning Methods | `effective-learning-methods` | Art. 13 | Expected | Training Record, Simulation Results, Feedback Survey | As Needed | 3 | Yes |
| Accessible Inclusive Training | `accessible-inclusive-training` | Art. 13 | Required | Communication Artifact | Continuous | 3 | Yes |
| Flexible Effective Delivery | `flexible-effective-delivery` | Art. 13 | Expected | Training Record | Annual | 4 | Yes |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | Art. 13 | Required | Training Record | Onboarding | 4 | Yes |

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