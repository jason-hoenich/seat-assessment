# NIS2 Directive

Mapping of SEAT outcomes to NIS2 Directive requirements for essential and important entities.

**Version:** 2022/2555  
**Adapter last updated:** 2026-05-22  
**Official reference:** https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32022L2555  
**Adapter id:** `nis2`

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
| Strategic Alignment | `strategic-alignment` | Art. 21, Art. 23 | Required | Policy Document, Assessment Report, Board Minutes | Annual | 5 |
| Governance Documentation | `governance-documentation` | Art. 21, Art. 23 | Required | Policy Document, Assessment Report | Annual | 4 |
| Executive Support | `executive-support` | Art. 20 | Required | Board Minutes, Training Record | Annual | 5 |
| Continuous Improvement | `continuous-improvement` | Art. 21, Art. 23 | Required | Assessment Report, Incident Report | Continuous | 4 |
| Targeted Communication | `targeted-communication` | Art. 21(2)(g) | Required | Communication Artifact, Training Record, Curriculum Document | Continuous | 4 |
| Cultural Relevance | `cultural-relevance` | Art. 21(2)(g), Art. 20(2) | Recommended | Feedback Survey, Communication Artifact | Continuous | 2 |
| Active Participation | `active-participation` | Art. 23, Art. 24 | Required | Incident Report, Feedback Survey | Continuous | 4 |
| Feedback Responsiveness | `feedback-responsiveness` | Art. 23 | Expected | Incident Report, Feedback Survey | As Needed | 3 |
| Performance Measurement | `performance-measurement` | Art. 21(2)(f) | Required | Metric Report, Assessment Report, Effectiveness Review, Maturity Score Trends, Gap Analysis | Continuous | 5 |
| Risk Driven Assessment | `risk-driven-assessment` | Art. 21(1), Art. 21(2) | Required | Assessment Report, Policy Document | Annual | 5 |
| Behavioral Impact Assessment | `behavioral-impact-assessment` | Art. 21(2)(f), Art. 21(2)(g) | Required | Simulation Results, Incident Report, Behavioral Change Metrics, Pre/Post Training Comparison | Quarterly | 4 |
| Relevant Tailored Training | `relevant-tailored-training` | Art. 21(2)(g), Art. 20(2) | Required | Curriculum Document, Training Record, Role-Specific Content Map | Annual | 5 |
| Effective Learning Methods | `effective-learning-methods` | Art. 21(2)(g), Art. 21(2)(f) | Required | Training Record, Simulation Results, Feedback Survey, Effectiveness Metrics | As Needed | 4 |
| Accessible Inclusive Training | `accessible-inclusive-training` | Art. 21(2)(g) | Required | Communication Artifact, Accessibility Documentation, Coverage Reports | Continuous | 3 |
| Flexible Effective Delivery | `flexible-effective-delivery` | Art. 21(2)(g) | Expected | Training Record, Delivery Method Documentation | Annual | 4 |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | Art. 21(2)(g), Art. 21(2)(i) | Required | Training Record, Onboarding Checklist, Role-Change Retraining Records | Onboarding | 4 |

## Mapping notes

**Strategic Alignment (Art. 21, Art. 23).** NIS2 requires cybersecurity risk management measures to be integrated into overall risk management and aligned with business continuity planning.

**Governance Documentation (Art. 21, Art. 23).** Comprehensive documentation of cybersecurity policies, procedures, and risk management measures is mandatory under NIS2.

**Executive Support (Art. 20).** NIS2 places direct responsibility on management bodies for cybersecurity risk management and requires their active oversight.

**Continuous Improvement (Art. 21, Art. 23).** NIS2 emphasizes continuous improvement of cybersecurity measures based on evolving threats and incident learnings.

**Targeted Communication (Art. 21(2)(g)).** Art. 21(2)(g) requires basic cyber hygiene practices and cybersecurity training. Effective delivery requires communications tailored to different roles and responsibilities.

**Cultural Relevance (Art. 21(2)(g), Art. 20(2)).** NIS2 Art. 20(2) requires management bodies to follow training and encourages regular employee training. Building a security culture where training is valued, not resented, supports this mandate.

**Active Participation (Art. 23, Art. 24).** NIS2 requires robust incident reporting processes and encourages active participation in cybersecurity initiatives.

**Feedback Responsiveness (Art. 23).** Learning from incidents and addressing feedback is crucial for improving cybersecurity resilience under NIS2.

**Performance Measurement (Art. 21(2)(f)).** Art. 21(2)(f) explicitly mandates policies and procedures to assess the effectiveness of cybersecurity risk-management measures. This is the most significant departure from US frameworks -- not whether controls exist, but whether they work. SEAT maturity assessments directly satisfy this requirement.

**Risk Driven Assessment (Art. 21(1), Art. 21(2)).** Risk assessment is fundamental to NIS2, driving the selection and implementation of appropriate cybersecurity measures.

**Behavioral Impact Assessment (Art. 21(2)(f), Art. 21(2)(g)).** Art. 21(2)(f) requires effectiveness assessment. For awareness programs, behavioral impact data is the primary evidence that training (Art. 21(2)(g)) is producing results. Without behavioral measurement, effectiveness claims are unsupported.

**Relevant Tailored Training (Art. 21(2)(g), Art. 20(2)).** Art. 21(2)(g) requires basic cyber hygiene practices and cybersecurity training. Art. 20(2) requires management bodies to follow training themselves. Together, these mandate training at every level of the organization with content appropriate to each audience.

**Effective Learning Methods (Art. 21(2)(g), Art. 21(2)(f)).** Art. 21(2)(f) requires effectiveness assessment of all cybersecurity measures, including training. Methods must be demonstrably effective, not just delivered. Track comprehension and behavioral change, not just completion.

**Accessible Inclusive Training (Art. 21(2)(g)).** Art. 21(2)(g) applies to basic cyber hygiene practices for all personnel. Training must reach every employee, including remote workers, contractors within scope, and staff with accessibility needs.

**Flexible Effective Delivery (Art. 21(2)(g)).** Art. 21(1) proportionality principle applies to delivery -- methods should be appropriate to the entity size and risk profile. A 200-person manufacturer and a 5,000-person hospital need different delivery approaches.

**Integrated Training Lifecycle (Art. 21(2)(g), Art. 21(2)(i)).** Art. 21(2)(i) covers human resources security across the employee lifecycle. Combined with Art. 21(2)(g) training requirements, this means cybersecurity training must be embedded in onboarding, role changes, and offboarding -- not treated as a standalone annual event.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.