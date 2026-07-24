# NIS2 Directive

**Version:** 2022/2555
**Last Updated:** 2026-05-22
**Official Reference:** https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32022L2555

Mapping of SEAT outcomes to NIS2 Directive requirements for essential and important entities.

## How an assistant applies this adapter

Given per-question maturity scores (1-5), compute outcome scores by averaging the scores of all questions that map to each SEAT outcome (see outcomes.md for the mapping). Then for each requirement below:

- **Met:** outcome score >= threshold for that requirement's assurance level
- **Partial:** outcome score > 0 but below threshold
- **Gap:** outcome score is 0 or no questions answered for that outcome

Thresholds by assurance level:
- Required: >= 4.5
- Expected: >= 2.5
- Recommended: >= 1.5

For gaps and partial results on Required or Expected requirements, list the missing evidence types.

## Outcome-to-Requirement Mapping

| SEAT Outcome | Framework Reference | Assurance | Evidence Required | Weight | Notes |
|---|---|---|---|---|---|
| strategic-alignment | Art. 21, Art. 23 | Required | Policy Document, Assessment Report, Board Minutes | 5 | NIS2 requires cybersecurity risk management measures to be integrated into overall risk management and aligned with business continuity planning. Cadence: Annual. |
| governance-documentation | Art. 21, Art. 23 | Required | Policy Document, Assessment Report | 4 | Comprehensive documentation of cybersecurity policies, procedures, and risk management measures is mandatory under NIS2. Cadence: Annual. |
| executive-support | Art. 20 | Required | Board Minutes, Training Record | 5 | NIS2 places direct responsibility on management bodies for cybersecurity risk management and requires their active oversight. Cadence: Annual. |
| continuous-improvement | Art. 21, Art. 23 | Required | Assessment Report, Incident Report | 4 | NIS2 emphasizes continuous improvement of cybersecurity measures based on evolving threats and incident learnings. Cadence: Continuous. |
| targeted-communication | Art. 21(2)(g) | Required | Communication Artifact, Training Record, Curriculum Document | 4 | Art. 21(2)(g) requires basic cyber hygiene practices and cybersecurity training. Effective delivery requires communications tailored to different roles and responsibilities. Cadence: Continuous. |
| cultural-relevance | Art. 21(2)(g), Art. 20(2) | Recommended | Feedback Survey, Communication Artifact | 2 | NIS2 Art. 20(2) requires management bodies to follow training and encourages regular employee training. Building a security culture where training is valued, not resented, supports this mandate. Cadence: Continuous. |
| active-participation | Art. 23, Art. 24 | Required | Incident Report, Feedback Survey | 4 | NIS2 requires robust incident reporting processes and encourages active participation in cybersecurity initiatives. Cadence: Continuous. |
| feedback-responsiveness | Art. 23 | Expected | Incident Report, Feedback Survey | 3 | Learning from incidents and addressing feedback is crucial for improving cybersecurity resilience under NIS2. Cadence: As Needed. |
| performance-measurement | Art. 21(2)(f) | Required | Metric Report, Assessment Report, Effectiveness Review, Maturity Score Trends, Gap Analysis | 5 | Art. 21(2)(f) explicitly mandates policies and procedures to assess the effectiveness of cybersecurity risk-management measures. This is the most significant departure from US frameworks -- not whether controls exist, but whether they work. SEAT maturity assessments directly satisfy this requirement. Cadence: Continuous. |
| risk-driven-assessment | Art. 21(1), Art. 21(2) | Required | Assessment Report, Policy Document | 5 | Risk assessment is fundamental to NIS2, driving the selection and implementation of appropriate cybersecurity measures. Cadence: Annual. |
| behavioral-impact-assessment | Art. 21(2)(f), Art. 21(2)(g) | Required | Simulation Results, Incident Report, Behavioral Change Metrics, Pre/Post Training Comparison | 4 | Art. 21(2)(f) requires effectiveness assessment. For awareness programs, behavioral impact data is the primary evidence that training (Art. 21(2)(g)) is producing results. Without behavioral measurement, effectiveness claims are unsupported. Cadence: Quarterly. |
| relevant-tailored-training | Art. 21(2)(g), Art. 20(2) | Required | Curriculum Document, Training Record, Role-Specific Content Map | 5 | Art. 21(2)(g) requires basic cyber hygiene practices and cybersecurity training. Art. 20(2) requires management bodies to follow training themselves. Together, these mandate training at every level of the organization with content appropriate to each audience. Cadence: Annual. |
| effective-learning-methods | Art. 21(2)(g), Art. 21(2)(f) | Required | Training Record, Simulation Results, Feedback Survey, Effectiveness Metrics | 4 | Art. 21(2)(f) requires effectiveness assessment of all cybersecurity measures, including training. Methods must be demonstrably effective, not just delivered. Track comprehension and behavioral change, not just completion. Cadence: As Needed. |
| accessible-inclusive-training | Art. 21(2)(g) | Required | Communication Artifact, Accessibility Documentation, Coverage Reports | 3 | Art. 21(2)(g) applies to basic cyber hygiene practices for all personnel. Training must reach every employee, including remote workers, contractors within scope, and staff with accessibility needs. Cadence: Continuous. |
| flexible-effective-delivery | Art. 21(2)(g) | Expected | Training Record, Delivery Method Documentation | 4 | Art. 21(1) proportionality principle applies to delivery -- methods should be appropriate to the entity size and risk profile. A 200-person manufacturer and a 5,000-person hospital need different delivery approaches. Cadence: Annual. |
| integrated-training-lifecycle | Art. 21(2)(g), Art. 21(2)(i) | Required | Training Record, Onboarding Checklist, Role-Change Retraining Records | 4 | Art. 21(2)(i) covers human resources security across the employee lifecycle. Combined with Art. 21(2)(g) training requirements, this means cybersecurity training must be embedded in onboarding, role changes, and offboarding -- not treated as a standalone annual event. Cadence: Onboarding. |
