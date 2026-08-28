# PCI DSS 4.0

Mapping of SEAT outcomes to PCI DSS 4.0 requirements.

**Version:** 4.0  
**Adapter last updated:** 2025-01-27  
**Official reference:** https://www.pcisecuritystandards.org/document_library/  
**Adapter id:** `pci-dss-4.0`

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
| Strategic Alignment | `strategic-alignment` | 12.3, 12.3.1 | Required | Risk Assessment, Policy Document, Assessment Report | Semi-Annual | 5 | Yes |
| Governance Documentation | `governance-documentation` | 12.1, 12.5.2 | Required | Policy Document, Other | Annual | 4 | Yes |
| Executive Support | `executive-support` | 12.4.1 | Expected | Board Minutes, Other | Annual | 4 | Yes |
| Continuous Improvement | `continuous-improvement` | 12.6.2, 12.3, 12.10.6 | Required | Assessment Report, Other | Annual | 5 | Yes |
| Targeted Communication | `targeted-communication` | 12.6.1, 12.6.3 | Required | Training Record, Communication Artifact, Curriculum Document | Annual | 4 | Yes |
| Cultural Relevance | `cultural-relevance` | 12.6 | Recommended | Feedback Survey, Communication Artifact | Continuous | 2 | Yes |
| Active Participation | `active-participation` | 12.6.3.3 | Required | Incident Report, Feedback Survey | Continuous | 4 | Yes |
| Feedback Responsiveness | `feedback-responsiveness` | 12.6.4 | Expected | Training Record, Feedback Survey | Annual | 3 | Yes |
| Performance Measurement | `performance-measurement` | 12.6.2, 12.3.1 | Required | Metric Report, Assessment Report | Annual | 4 | Yes |
| Risk Driven Assessment | `risk-driven-assessment` | 12.3, 12.3.1 | Required | Risk Assessment, Assessment Report, Policy Document | Semi-Annual | 5 | Yes |
| Behavioral Impact Assessment | `behavioral-impact-assessment` | 12.6.3.1, 12.6.3.3 | Required | Simulation Results, Incident Report | Quarterly | 4 | **Not assessed** |
| Relevant Tailored Training | `relevant-tailored-training` | 12.6.3, 6.2.2 | Required | Curriculum Document, Training Record | Annual | 5 | Yes |
| Effective Learning Methods | `effective-learning-methods` | 12.6 | Expected | Simulation Results, Feedback Survey | As Needed | 3 | Yes |
| Accessible Inclusive Training | `accessible-inclusive-training` | 12.6.1 | Required | Communication Artifact | Continuous | 3 | Yes |
| Flexible Effective Delivery | `flexible-effective-delivery` | 12.6.3 | Required | Training Record | Annual | 4 | Yes |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | 12.6.3 | Required | Training Record | Onboarding | 4 | Yes |

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