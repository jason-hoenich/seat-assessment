# General Data Protection Regulation (GDPR)

Mapping of SEAT outcomes to GDPR articles and principles, focusing on data protection awareness and accountability.

**Version:** 2016/679  
**Adapter last updated:** 2025-01-27  
**Official reference:** https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32016R0679  
**Adapter id:** `gdpr`

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
| Strategic Alignment | `strategic-alignment` | Art. 5(2), Art. 24, Art. 25, Art. 32 | Required | Policy Document, Assessment Report, Other | Annual | 5 | Yes |
| Governance Documentation | `governance-documentation` | Art. 5(2), Art. 24, Art. 30, Art. 32 | Required | Policy Document, Other | Annual | 4 | Yes |
| Executive Support | `executive-support` | Art. 5(2), Art. 24, Art. 39 | Required | Board Minutes, Other | Annual | 5 | Yes |
| Continuous Improvement | `continuous-improvement` | Art. 5(2), Art. 24, Art. 32, Art. 33, Art. 34 | Required | Assessment Report, Incident Report, Other | Continuous | 4 | Yes |
| Targeted Communication | `targeted-communication` | Art. 12, Art. 13, Art. 14 | Required | Communication Artifact, Training Record, Curriculum Document | As Needed | 4 | Yes |
| Cultural Relevance | `cultural-relevance` | Art. 5(1)(a), Recital 78 | Recommended | Feedback Survey, Communication Artifact | Continuous | 2 | Yes |
| Active Participation | `active-participation` | Art. 15-22, Art. 33 | Required | Incident Report, Feedback Survey | Continuous | 4 | Yes |
| Feedback Responsiveness | `feedback-responsiveness` | Art. 12, Art. 33, Art. 34 | Required | Feedback Survey, Incident Report | As Needed | 3 | Yes |
| Performance Measurement | `performance-measurement` | Art. 5(2), Art. 24, Art. 32 | Required | Metric Report, Assessment Report | Annual | 4 | Yes |
| Risk Driven Assessment | `risk-driven-assessment` | Art. 32, Art. 35 | Required | Assessment Report, Policy Document, Curriculum Document | As Needed | 5 | Yes |
| Behavioral Impact | `behavioral-impact` | Art. 32(1)(d) | Expected | Simulation Results, Incident Report | Quarterly | 3 | **Not assessed** |
| Relevant Tailored Training | `relevant-tailored-training` | Art. 32(4) | Required | Curriculum Document, Training Record | Annual | 5 | Yes |
| Effective Learning Methods | `effective-learning-methods` | Art. 32(1)(d) | Expected | Training Record, Simulation Results, Feedback Survey | As Needed | 3 | Yes |
| Accessible Inclusive Training | `accessible-inclusive-training` | Art. 32(4) | Required | Communication Artifact | Continuous | 3 | Yes |
| Flexible Effective Delivery | `flexible-effective-delivery` | Art. 32(1)(d) | Expected | Training Record | Annual | 4 | Yes |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | Art. 32(4) | Expected | Training Record | Onboarding | 4 | Yes |

## Mapping notes

**Strategic Alignment (Art. 5(2), Art. 24, Art. 25, Art. 32).** GDPR requires a strategic approach to data protection, embedding it by design and default, and demonstrating accountability.

**Governance Documentation (Art. 5(2), Art. 24, Art. 30, Art. 32).** Comprehensive documentation is key to demonstrating GDPR compliance, including policies, procedures, and records of processing.

**Executive Support (Art. 5(2), Art. 24, Art. 39).** Top management is ultimately responsible for GDPR compliance and must ensure adequate resources and oversight.

**Continuous Improvement (Art. 5(2), Art. 24, Art. 32, Art. 33, Art. 34).** GDPR implies continuous improvement through regular review of security measures and learning from data breaches.

**Targeted Communication (Art. 12, Art. 13, Art. 14).** Clear and transparent communication with data subjects about their rights and data processing activities is fundamental.

**Cultural Relevance (Art. 5(1)(a), Recital 78).** Fostering a data protection culture within the organization is crucial for effective compliance.

**Active Participation (Art. 15-22, Art. 33).** Enabling data subjects to exercise their rights and ensuring personnel understand breach reporting obligations.

**Feedback Responsiveness (Art. 12, Art. 33, Art. 34).** Prompt and effective response to data subject requests and data breaches is a core GDPR requirement.

**Performance Measurement (Art. 5(2), Art. 24, Art. 32).** Organizations must be able to demonstrate compliance with GDPR principles and the effectiveness of their measures.

**Risk Driven Assessment (Art. 32, Art. 35).** A risk-based approach, including DPIAs for high-risk processing, is central to GDPR compliance.

**Behavioral Impact (Art. 32(1)(d)).** Assessing the impact of training on employee behavior contributes to the overall security of processing.

**Relevant Tailored Training (Art. 32(4)).** Personnel handling personal data must receive appropriate and tailored training on data protection principles and procedures.

**Effective Learning Methods (Art. 32(1)(d)).** Training methods should be effective in ensuring personnel understand their data protection responsibilities.

**Accessible Inclusive Training (Art. 32(4)).** Training must be accessible and provided to all personnel who process personal data.

**Flexible Effective Delivery (Art. 32(1)(d)).** Delivery methods should be flexible to ensure effective learning and retention of data protection knowledge.

**Integrated Training Lifecycle (Art. 32(4)).** Data protection training should be integrated into the employee lifecycle, from onboarding through ongoing development.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.