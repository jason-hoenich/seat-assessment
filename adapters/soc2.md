# SOC 2

Mapping of SEAT outcomes to SOC 2 Trust Services Criteria (TSC) and Common Criteria (CC).

**Version:** 2017 TSC  
**Adapter last updated:** 2025-01-27  
**Official reference:** https://www.aicpa.org/interestareas/frc/assuranceadvisoryservices/aicpasoc2report  
**Adapter id:** `soc2`

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
| Strategic Alignment | `strategic-alignment` | CC3.1, CC9.1 | Required | Assessment Report, Policy Document | Annual | 5 | Yes |
| Governance Documentation | `governance-documentation` | CC2.1, CC5.1 | Required | Policy Document, Other | Annual | 4 | Yes |
| Executive Support | `executive-support` | CC1.2 | Required | Board Minutes | Annual | 5 | Yes |
| Continuous Improvement | `continuous-improvement` | CC4.1, CC7.1 | Required | Assessment Report, Metric Report | Continuous | 4 | Yes |
| Targeted Communication | `targeted-communication` | CC2.2 | Required | Communication Artifact, Training Record, Curriculum Document | As Needed | 4 | Yes |
| Cultural Relevance | `cultural-relevance` | CC1.1 | Recommended | Feedback Survey, Communication Artifact | Continuous | 2 | Yes |
| Active Participation | `active-participation` | CC2.2, CC7.2 | Expected | Incident Report, Feedback Survey | Continuous | 3 | Yes |
| Feedback Responsiveness | `feedback-responsiveness` | CC4.1 | Expected | Feedback Survey | Quarterly | 3 | Yes |
| Performance Measurement | `performance-measurement` | CC4.1, CC7.1 | Required | Metric Report, Assessment Report | Quarterly | 4 | Yes |
| Risk Driven Assessment | `risk-driven-assessment` | CC3.1, CC9.1 | Required | Assessment Report, Policy Document, Curriculum Document | Annual | 5 | Yes |
| Behavioral Impact | `behavioral-impact` | CC2.2, CC7.2 | Expected | Simulation Results, Incident Report | Quarterly | 3 | **Not assessed** |
| Relevant Tailored Training | `relevant-tailored-training` | CC2.2 | Required | Curriculum Document, Training Record | Annual | 4 | Yes |
| Effective Learning Methods | `effective-learning-methods` | CC2.2 | Expected | Training Record, Simulation Results, Feedback Survey | As Needed | 3 | Yes |
| Accessible Inclusive Training | `accessible-inclusive-training` | CC2.2 | Required | Communication Artifact | Continuous | 3 | Yes |
| Flexible Effective Delivery | `flexible-effective-delivery` | CC2.2 | Expected | Training Record | Annual | 4 | Yes |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | CC2.2 | Expected | Training Record | Onboarding | 4 | Yes |

## Mapping notes

**Strategic Alignment (CC3.1, CC9.1).** Aligning security awareness with overall risk management and organizational objectives through risk identification and assessment.

**Governance Documentation (CC2.1, CC5.1).** Formal documentation and regular review of program governance and controls to support internal control functioning.

**Executive Support (CC1.2).** Leadership commitment and oversight for the control environment, with board exercising independent oversight.

**Continuous Improvement (CC4.1, CC7.1).** Regular assessment and adaptation of the program based on ongoing monitoring and evaluation findings.

**Targeted Communication (CC2.2).** Tailoring communications and training to specific roles and groups to improve security knowledge and behavior.

**Cultural Relevance (CC1.1).** Fostering a security-aware culture that aligns with organizational values and commitment to integrity.

**Active Participation (CC2.2, CC7.2).** Encouraging and measuring active employee involvement in security initiatives, including modeling appropriate security behaviors.

**Feedback Responsiveness (CC4.1).** Establishing and acting on employee feedback channels to improve control effectiveness through ongoing evaluations.

**Performance Measurement (CC4.1, CC7.1).** Tracking and reporting program effectiveness using KPIs and continuous monitoring procedures.

**Risk Driven Assessment (CC3.1, CC9.1).** Using risk assessments to guide awareness content and priorities through systematic risk identification and response.

**Behavioral Impact (CC2.2, CC7.2).** Assessing changes in employee security behaviors and their impact on security posture through training programs.

**Relevant Tailored Training (CC2.2).** Training content is specific to roles and identified risks, tailored to improve security knowledge and behavior.

**Effective Learning Methods (CC2.2).** Utilizing engaging and practical training approaches that demonstrate effectiveness in improving security behaviors.

**Accessible Inclusive Training (CC2.2).** Ensuring training is available and understandable to all relevant personnel through comprehensive awareness programs.

**Flexible Effective Delivery (CC2.2).** Optimizing training delivery for behavioral impact and knowledge retention, while meeting program requirements.

**Integrated Training Lifecycle (CC2.2).** Embedding training into employee lifecycle from onboarding through ongoing professional development.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.