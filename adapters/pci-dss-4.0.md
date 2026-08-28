# PCI DSS 4.0

Mapping of SEAT outcomes to PCI DSS 4.0 requirements.

**Version:** 4.0  
**Adapter last updated:** 2025-01-27  
**Official reference:** https://www.pcisecuritystandards.org/document_library/  
**Adapter id:** `pci-dss-4.0`

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
| Strategic Alignment | `strategic-alignment` | 12.3, 12.3.1 | Required | Risk Assessment, Policy Document, Assessment Report | Semi-Annual | 5 |
| Governance Documentation | `governance-documentation` | 12.1, 12.5.2 | Required | Policy Document, Other | Annual | 4 |
| Executive Support | `executive-support` | 12.4.1 | Expected | Board Minutes, Other | Annual | 4 |
| Continuous Improvement | `continuous-improvement` | 12.6.2, 12.3, 12.10.6 | Required | Assessment Report, Other | Annual | 5 |
| Targeted Communication | `targeted-communication` | 12.6.1, 12.6.3 | Required | Training Record, Communication Artifact, Curriculum Document | Annual | 4 |
| Cultural Relevance | `cultural-relevance` | 12.6 | Recommended | Feedback Survey, Communication Artifact | Continuous | 2 |
| Active Participation | `active-participation` | 12.6.3.3 | Required | Incident Report, Feedback Survey | Continuous | 4 |
| Feedback Responsiveness | `feedback-responsiveness` | 12.6.4 | Expected | Training Record, Feedback Survey | Annual | 3 |
| Performance Measurement | `performance-measurement` | 12.6.2, 12.3.1 | Required | Metric Report, Assessment Report | Annual | 4 |
| Risk Driven Assessment | `risk-driven-assessment` | 12.3, 12.3.1 | Required | Risk Assessment, Assessment Report, Policy Document | Semi-Annual | 5 |
| Behavioral Impact Assessment | `behavioral-impact-assessment` | 12.6.3.1, 12.6.3.3 | Required | Simulation Results, Incident Report | Quarterly | 4 |
| Relevant Tailored Training | `relevant-tailored-training` | 12.6.3, 6.2.2 | Required | Curriculum Document, Training Record | Annual | 5 |
| Effective Learning Methods | `effective-learning-methods` | 12.6 | Expected | Simulation Results, Feedback Survey | As Needed | 3 |
| Accessible Inclusive Training | `accessible-inclusive-training` | 12.6.1 | Required | Communication Artifact | Continuous | 3 |
| Flexible Effective Delivery | `flexible-effective-delivery` | 12.6.3 | Required | Training Record | Annual | 4 |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | 12.6.3 | Required | Training Record | Onboarding | 4 |

## Mapping notes

**Strategic Alignment (12.3, 12.3.1).** PCI DSS 4.0 emphasizes targeted risk analysis to align security measures with specific risks to the CDE.

**Governance Documentation (12.1, 12.5.2).** Formal, documented policies and procedures are foundational for PCI DSS compliance.

**Executive Support (12.4.1).** Executive oversight and resource allocation are critical for maintaining compliance. Required for service providers.

**Continuous Improvement (12.6.2, 12.3, 12.10.6).** PCI DSS 4.0 promotes security as a continuous process, requiring regular updates based on new threats.

**Targeted Communication (12.6.1, 12.6.3).** Training must be provided to all personnel, tailored to their roles and specific threats.

**Cultural Relevance (12.6).** While not explicitly called out, effective awareness programs consider cultural context for better engagement.

**Active Participation (12.6.3.3).** Encouraging and enabling personnel to report suspicious activities is a direct PCI DSS requirement.

**Feedback Responsiveness (12.6.4).** Feedback mechanisms, especially acknowledgements, are required and should drive program improvements.

**Performance Measurement (12.6.2, 12.3.1).** Metrics are essential for demonstrating the effectiveness of the awareness program and informing TRAs.

**Risk Driven Assessment (12.3, 12.3.1).** PCI DSS 4.0 mandates targeted risk analyses to ensure security controls, including awareness, address specific risks.

**Behavioral Impact Assessment (12.6.3.1, 12.6.3.3).** Assessing behavioral changes related to phishing and incident reporting is directly supported by PCI DSS.

**Relevant Tailored Training (12.6.3, 6.2.2).** Training must be tailored to job roles and cover specific threats relevant to the CDE.

**Effective Learning Methods (12.6).** PCI DSS encourages engaging and effective training methods to ensure understanding and retention.

**Accessible Inclusive Training (12.6.1).** Training must be accessible to all personnel who impact CDE security.

**Flexible Effective Delivery (12.6.3).** PCI DSS is prescriptive about annual training frequency, but content delivery can be flexible as long as requirements are met.

**Integrated Training Lifecycle (12.6.3).** Training is required upon hire and annually, integrating it into the employee lifecycle.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.