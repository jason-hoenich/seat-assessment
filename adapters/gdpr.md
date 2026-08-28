# General Data Protection Regulation (GDPR)

Mapping of SEAT outcomes to GDPR articles and principles, focusing on data protection awareness and accountability.

**Version:** 2016/679  
**Adapter last updated:** 2025-01-27  
**Official reference:** https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32016R0679  
**Adapter id:** `gdpr`

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
| Strategic Alignment | `strategic-alignment` | Art. 5(2), Art. 24, Art. 25, Art. 32 | Required | Policy Document, Assessment Report, Other | Annual | 5 |
| Governance Documentation | `governance-documentation` | Art. 5(2), Art. 24, Art. 30, Art. 32 | Required | Policy Document, Other | Annual | 4 |
| Executive Support | `executive-support` | Art. 5(2), Art. 24, Art. 39 | Required | Board Minutes, Other | Annual | 5 |
| Continuous Improvement | `continuous-improvement` | Art. 5(2), Art. 24, Art. 32, Art. 33, Art. 34 | Required | Assessment Report, Incident Report, Other | Continuous | 4 |
| Targeted Communication | `targeted-communication` | Art. 12, Art. 13, Art. 14 | Required | Communication Artifact, Training Record, Curriculum Document | As Needed | 4 |
| Cultural Relevance | `cultural-relevance` | Art. 5(1)(a), Recital 78 | Recommended | Feedback Survey, Communication Artifact | Continuous | 2 |
| Active Participation | `active-participation` | Art. 15-22, Art. 33 | Required | Incident Report, Feedback Survey | Continuous | 4 |
| Feedback Responsiveness | `feedback-responsiveness` | Art. 12, Art. 33, Art. 34 | Required | Feedback Survey, Incident Report | As Needed | 3 |
| Performance Measurement | `performance-measurement` | Art. 5(2), Art. 24, Art. 32 | Required | Metric Report, Assessment Report | Annual | 4 |
| Risk Driven Assessment | `risk-driven-assessment` | Art. 32, Art. 35 | Required | Assessment Report, Policy Document, Curriculum Document | As Needed | 5 |
| Behavioral Impact | `behavioral-impact` | Art. 32(1)(d) | Expected | Simulation Results, Incident Report | Quarterly | 3 |
| Relevant Tailored Training | `relevant-tailored-training` | Art. 32(4) | Required | Curriculum Document, Training Record | Annual | 5 |
| Effective Learning Methods | `effective-learning-methods` | Art. 32(1)(d) | Expected | Training Record, Simulation Results, Feedback Survey | As Needed | 3 |
| Accessible Inclusive Training | `accessible-inclusive-training` | Art. 32(4) | Required | Communication Artifact | Continuous | 3 |
| Flexible Effective Delivery | `flexible-effective-delivery` | Art. 32(1)(d) | Expected | Training Record | Annual | 4 |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | Art. 32(4) | Expected | Training Record | Onboarding | 4 |

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