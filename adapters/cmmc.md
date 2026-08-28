# Cybersecurity Maturity Model Certification (CMMC)

Mapping of SEAT outcomes to CMMC 2.0 practices for defense contractors handling CUI.

**Version:** 2.0  
**Adapter last updated:** 2025-01-27  
**Official reference:** https://www.acq.osd.mil/cmmc/  
**Adapter id:** `cmmc`

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
| Strategic Alignment | `strategic-alignment` | RM.L2-3.11.1, GOV.L2-P1.1 | Required | Assessment Report, Policy Document, Other | Annual | 5 |
| Governance Documentation | `governance-documentation` | GOV.L2-P1.1, GOV.L2-P1.2 | Required | Policy Document, Other | Annual | 4 |
| Executive Support | `executive-support` | GOV.L2-P1.1, GOV.L2-P1.3 | Required | Other, Policy Document | Annual | 5 |
| Continuous Improvement | `continuous-improvement` | GOV.L2-P1.4, AT.L2-3.1.5 | Required | Assessment Report, Metric Report, Other | Continuous | 4 |
| Targeted Communication | `targeted-communication` | AT.L2-3.1.2 | Required | Training Record, Curriculum Document, Communication Artifact | Annual | 4 |
| Cultural Relevance | `cultural-relevance` | AT.L2-3.1.2 | Recommended | Feedback Survey, Communication Artifact | Continuous | 2 |
| Active Participation | `active-participation` | IR.L2-3.6.1, AT.L2-3.1.2 | Required | Incident Report, Training Record | Continuous | 4 |
| Feedback Responsiveness | `feedback-responsiveness` | AT.L2-3.1.5, GOV.L2-P1.4 | Expected | Feedback Survey, Training Record | As Needed | 3 |
| Performance Measurement | `performance-measurement` | AT.L2-3.1.4, GOV.L2-P1.4 | Required | Metric Report, Assessment Report, Training Record | Annual | 4 |
| Risk Driven Assessment | `risk-driven-assessment` | RM.L2-3.11.1, AT.L2-3.1.2 | Required | Assessment Report, Curriculum Document, Policy Document | Annual | 5 |
| Behavioral Impact | `behavioral-impact` | AT.L2-3.1.4, IR.L2-3.6.1 | Expected | Simulation Results, Incident Report | Quarterly | 3 |
| Relevant Tailored Training | `relevant-tailored-training` | AT.L2-3.1.2, AT.L3-3.1.3 | Required | Curriculum Document, Training Record | Annual | 5 |
| Effective Learning Methods | `effective-learning-methods` | AT.L2-3.1.2 | Expected | Training Record, Feedback Survey | As Needed | 3 |
| Accessible Inclusive Training | `accessible-inclusive-training` | AT.L2-3.1.1 | Required | Training Record, Communication Artifact | Continuous | 3 |
| Flexible Effective Delivery | `flexible-effective-delivery` | AT.L2-3.1.4 | Required | Training Record | Annual | 4 |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | AT.L2-3.1.1, AT.L2-3.1.4 | Required | Training Record | Onboarding | 4 |

## Mapping notes

**Strategic Alignment (RM.L2-3.11.1, GOV.L2-P1.1).** CMMC requires periodic risk assessment and a documented cybersecurity program plan that aligns with organizational objectives.

**Governance Documentation (GOV.L2-P1.1, GOV.L2-P1.2).** CMMC mandates documented cybersecurity program plans, policies, and procedures for all practices.

**Executive Support (GOV.L2-P1.1, GOV.L2-P1.3).** Leadership commitment and adequate resource allocation are critical for CMMC compliance and program effectiveness.

**Continuous Improvement (GOV.L2-P1.4, AT.L2-3.1.5).** CMMC requires ongoing monitoring of cybersecurity program effectiveness and updating training as needed.

**Targeted Communication (AT.L2-3.1.2).** CMMC requires security awareness training that addresses risks associated with specific activities and organizational policies.

**Cultural Relevance (AT.L2-3.1.2).** Effective awareness programs consider organizational context and culture to improve engagement and understanding.

**Active Participation (IR.L2-3.6.1, AT.L2-3.1.2).** CMMC requires operational incident handling capability and training on reporting procedures.

**Feedback Responsiveness (AT.L2-3.1.5, GOV.L2-P1.4).** CMMC requires updating training based on evolving needs and program effectiveness reviews.

**Performance Measurement (AT.L2-3.1.4, GOV.L2-P1.4).** CMMC mandates annual security awareness training and monitoring of cybersecurity program effectiveness.

**Risk Driven Assessment (RM.L2-3.11.1, AT.L2-3.1.2).** CMMC requires periodic risk assessment and training that addresses identified organizational risks.

**Behavioral Impact (AT.L2-3.1.4, IR.L2-3.6.1).** Assessing behavioral changes through simulations and incident data supports CMMC compliance verification.

**Relevant Tailored Training (AT.L2-3.1.2, AT.L3-3.1.3).** CMMC requires training tailored to roles and specific organizational risks, with specialized training for privileged functions.

**Effective Learning Methods (AT.L2-3.1.2).** CMMC implies that training methods should effectively inform personnel about risks and procedures.

**Accessible Inclusive Training (AT.L2-3.1.1).** CMMC requires security awareness training for all information system users, including personnel and contractors.

**Flexible Effective Delivery (AT.L2-3.1.4).** CMMC specifies minimum annual training frequency, but effective delivery methods are implied for compliance.

**Integrated Training Lifecycle (AT.L2-3.1.1, AT.L2-3.1.4).** CMMC requires initial and recurring security awareness training for all information system users.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.