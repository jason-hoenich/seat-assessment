# NIST Cybersecurity Framework 2.0

Mapping of SEAT outcomes to NIST CSF 2.0 controls and practices.

**Version:** 2.0  
**Adapter last updated:** 2025-01-27  
**Official reference:** https://www.nist.gov/cyberframework  
**Adapter id:** `nist-csf-2.0`

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
| Strategic Alignment | `strategic-alignment` | GV.RM-03, GV.PO-01 | Expected | Policy Document, Assessment Report, Board Minutes | Annual | 5 | Yes |
| Governance Documentation | `governance-documentation` | GV.PO-01, GV.PO-02 | Expected | Policy Document, Assessment Report | Annual | 4 | Yes |
| Executive Support | `executive-support` | GV.RM-01, GV.RR-01 | Expected | Board Minutes, Policy Document | Semi-Annual | 5 | Yes |
| Continuous Improvement | `continuous-improvement` | GV.OV-01, ID.IM-01 | Expected | Assessment Report, Metric Report | Quarterly | 4 | Yes |
| Targeted Communication | `targeted-communication` | PR.AT-02 | Expected | Communication Artifact, Training Record, Curriculum Document | As Needed | 3 | Yes |
| Cultural Relevance | `cultural-relevance` | PR.AT-01 | Recommended | Communication Artifact, Feedback Survey | Continuous | 2 | Yes |
| Active Participation | `active-participation` | PR.AT-01 | Expected | Feedback Survey, Incident Report | Continuous | 3 | Yes |
| Feedback Responsiveness | `feedback-responsiveness` | ID.IM-01, RS.CO-01 | Expected | Feedback Survey | Quarterly | 3 | Yes |
| Performance Measurement | `performance-measurement` | GV.OV-01, ID.RA-01 | Expected | Metric Report, Assessment Report | Quarterly | 4 | Yes |
| Risk Driven Assessment | `risk-driven-assessment` | ID.RA-01, GV.RM-03 | Expected | Assessment Report, Policy Document, Curriculum Document | Semi-Annual | 5 | Yes |
| Behavioral Impact Assessment | `behavioral-impact-assessment` | PR.AT-01, DE.CM-01 | Recommended | Simulation Results, Incident Report | Quarterly | 3 | **Not assessed** |
| Relevant Tailored Training | `relevant-tailored-training` | PR.AT-02 | Expected | Curriculum Document, Training Record, Assessment Report | Annual | 4 | Yes |
| Effective Learning Methods | `effective-learning-methods` | PR.AT-01 | Recommended | Training Record, Simulation Results, Feedback Survey | As Needed | 3 | Yes |
| Accessible Inclusive Training | `accessible-inclusive-training` | PR.AT-01 | Expected | Communication Artifact | Continuous | 3 | Yes |
| Flexible Effective Delivery | `flexible-effective-delivery` | PR.AT-01 | Expected | Training Record | As Needed | 4 | Yes |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | PR.AT-01, PR.AT-02 | Expected | Training Record | Onboarding | 4 | Yes |

## Mapping notes

**Strategic Alignment (GV.RM-03, GV.PO-01).** Cybersecurity risk management activities and outcomes are included in enterprise risk management processes. Policy for managing cybersecurity risks is established based on organizational context.

**Governance Documentation (GV.PO-01, GV.PO-02).** Policy for managing cybersecurity risks is established and regularly reviewed, updated, communicated, and enforced.

**Executive Support (GV.RM-01, GV.RR-01).** Risk management objectives are established and agreed to by organizational stakeholders. Roles, responsibilities, and authorities for cybersecurity are established.

**Continuous Improvement (GV.OV-01, ID.IM-01).** Results of organization-wide cybersecurity risk management activities are used to inform and adjust the risk management strategy.

**Targeted Communication (PR.AT-02).** Individuals in specialized roles are provided with awareness and training tailored to their specific responsibilities.

**Cultural Relevance (PR.AT-01).** Personnel are provided with awareness and training that is culturally appropriate and accessible.

**Active Participation (PR.AT-01).** Fostering a security-aware culture that encourages active employee participation in security initiatives.

**Feedback Responsiveness (ID.IM-01, RS.CO-01).** Continuous evaluation is applied to identify improvements based on stakeholder feedback.

**Performance Measurement (GV.OV-01, ID.RA-01).** Results of cybersecurity risk management activities and performance are tracked and used to inform strategy.

**Risk Driven Assessment (ID.RA-01, GV.RM-03).** Cybersecurity risks are identified and understood, informing awareness program priorities.

**Behavioral Impact Assessment (PR.AT-01, DE.CM-01).** Monitoring and assessing changes in employee security behaviors and incident response.

**Relevant Tailored Training (PR.AT-02).** Training content is specific to roles and identified organizational risks.

**Effective Learning Methods (PR.AT-01).** Utilizing engaging and practical training approaches that demonstrate effectiveness.

**Accessible Inclusive Training (PR.AT-01).** Ensuring training is available and understandable to all personnel regardless of role or background.

**Flexible Effective Delivery (PR.AT-01).** Optimizing training delivery for behavioral impact and knowledge retention rather than fixed time requirements.

**Integrated Training Lifecycle (PR.AT-01, PR.AT-02).** Embedding training into employee lifecycle from onboarding through ongoing professional development.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.