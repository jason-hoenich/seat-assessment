# NIS2 Directive

Mapping of SEAT outcomes to NIS2 Directive requirements for essential and important entities.

**Version:** 2022/2555  
**Adapter last updated:** 2026-05-22  
**Official reference:** https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32022L2555  
**Adapter id:** `nis2`

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
| Strategic Alignment | `strategic-alignment` | Art. 21, Art. 23 | Required | Policy Document, Assessment Report, Board Minutes | Annual | 5 | Yes |
| Governance Documentation | `governance-documentation` | Art. 21, Art. 23 | Required | Policy Document, Assessment Report | Annual | 4 | Yes |
| Executive Support | `executive-support` | Art. 20 | Required | Board Minutes, Training Record | Annual | 5 | Yes |
| Continuous Improvement | `continuous-improvement` | Art. 21, Art. 23 | Required | Assessment Report, Incident Report | Continuous | 4 | Yes |
| Targeted Communication | `targeted-communication` | Art. 21(2)(g) | Required | Communication Artifact, Training Record, Curriculum Document | Continuous | 4 | Yes |
| Cultural Relevance | `cultural-relevance` | Art. 21(2)(g), Art. 20(2) | Recommended | Feedback Survey, Communication Artifact | Continuous | 2 | Yes |
| Active Participation | `active-participation` | Art. 23, Art. 24 | Required | Incident Report, Feedback Survey | Continuous | 4 | Yes |
| Feedback Responsiveness | `feedback-responsiveness` | Art. 23 | Expected | Incident Report, Feedback Survey | As Needed | 3 | Yes |
| Performance Measurement | `performance-measurement` | Art. 21(2)(f) | Required | Metric Report, Assessment Report, Effectiveness Review, Maturity Score Trends, Gap Analysis | Continuous | 5 | Yes |
| Risk Driven Assessment | `risk-driven-assessment` | Art. 21(1), Art. 21(2) | Required | Assessment Report, Policy Document | Annual | 5 | Yes |
| Behavioral Impact Assessment | `behavioral-impact-assessment` | Art. 21(2)(f), Art. 21(2)(g) | Required | Simulation Results, Incident Report, Behavioral Change Metrics, Pre/Post Training Comparison | Quarterly | 4 | **Not assessed** |
| Relevant Tailored Training | `relevant-tailored-training` | Art. 21(2)(g), Art. 20(2) | Required | Curriculum Document, Training Record, Role-Specific Content Map | Annual | 5 | Yes |
| Effective Learning Methods | `effective-learning-methods` | Art. 21(2)(g), Art. 21(2)(f) | Required | Training Record, Simulation Results, Feedback Survey, Effectiveness Metrics | As Needed | 4 | Yes |
| Accessible Inclusive Training | `accessible-inclusive-training` | Art. 21(2)(g) | Required | Communication Artifact, Accessibility Documentation, Coverage Reports | Continuous | 3 | Yes |
| Flexible Effective Delivery | `flexible-effective-delivery` | Art. 21(2)(g) | Expected | Training Record, Delivery Method Documentation | Annual | 4 | Yes |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | Art. 21(2)(g), Art. 21(2)(i) | Required | Training Record, Onboarding Checklist, Role-Change Retraining Records | Onboarding | 4 | Yes |

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