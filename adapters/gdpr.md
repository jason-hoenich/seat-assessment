# General Data Protection Regulation (GDPR)

**Version:** 2016/679
**Last Updated:** 2025-01-27
**Official Reference:** https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32016R0679

Mapping of SEAT outcomes to GDPR articles and principles, focusing on data protection awareness and accountability.

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
| strategic-alignment | Art. 5(2), Art. 24, Art. 25, Art. 32 | Required | Policy Document, Assessment Report | 5 | GDPR requires a strategic approach to data protection, embedding it by design and default, and demonstrating accountability. Cadence: Annual. |
| governance-documentation | Art. 5(2), Art. 24, Art. 30, Art. 32 | Required | Policy Document | 4 | Comprehensive documentation is key to demonstrating GDPR compliance, including policies, procedures, and records of processing. Cadence: Annual. |
| executive-support | Art. 5(2), Art. 24, Art. 39 | Required | Board Minutes | 5 | Top management is ultimately responsible for GDPR compliance and must ensure adequate resources and oversight. Cadence: Annual. |
| continuous-improvement | Art. 5(2), Art. 24, Art. 32, Art. 33, Art. 34 | Required | Assessment Report, Incident Report | 4 | GDPR implies continuous improvement through regular review of security measures and learning from data breaches. Cadence: Continuous. |
| targeted-communication | Art. 12, Art. 13, Art. 14 | Required | Communication Artifact, Training Record, Curriculum Document | 4 | Clear and transparent communication with data subjects about their rights and data processing activities is fundamental. Cadence: As Needed. |
| cultural-relevance | Art. 5(1)(a), Recital 78 | Recommended | Feedback Survey, Communication Artifact | 2 | Fostering a data protection culture within the organization is crucial for effective compliance. Cadence: Continuous. |
| active-participation | Art. 15-22, Art. 33 | Required | Incident Report, Feedback Survey | 4 | Enabling data subjects to exercise their rights and ensuring personnel understand breach reporting obligations. Cadence: Continuous. |
| feedback-responsiveness | Art. 12, Art. 33, Art. 34 | Required | Feedback Survey, Incident Report | 3 | Prompt and effective response to data subject requests and data breaches is a core GDPR requirement. Cadence: As Needed. |
| performance-measurement | Art. 5(2), Art. 24, Art. 32 | Required | Metric Report, Assessment Report | 4 | Organizations must be able to demonstrate compliance with GDPR principles and the effectiveness of their measures. Cadence: Annual. |
| risk-driven-assessment | Art. 32, Art. 35 | Required | Assessment Report, Policy Document, Curriculum Document | 5 | A risk-based approach, including DPIAs for high-risk processing, is central to GDPR compliance. Cadence: As Needed. |
| behavioral-impact | Art. 32(1)(d) | Expected | Simulation Results, Incident Report | 3 | Assessing the impact of training on employee behavior contributes to the overall security of processing. Cadence: Quarterly. |
| relevant-tailored-training | Art. 32(4) | Required | Curriculum Document, Training Record | 5 | Personnel handling personal data must receive appropriate and tailored training on data protection principles and procedures. Cadence: Annual. |
| effective-learning-methods | Art. 32(1)(d) | Expected | Training Record, Simulation Results, Feedback Survey | 3 | Training methods should be effective in ensuring personnel understand their data protection responsibilities. Cadence: As Needed. |
| accessible-inclusive-training | Art. 32(4) | Required | Communication Artifact | 3 | Training must be accessible and provided to all personnel who process personal data. Cadence: Continuous. |
| flexible-effective-delivery | Art. 32(1)(d) | Expected | Training Record | 4 | Delivery methods should be flexible to ensure effective learning and retention of data protection knowledge. Cadence: Annual. |
| integrated-training-lifecycle | Art. 32(4) | Expected | Training Record | 4 | Data protection training should be integrated into the employee lifecycle, from onboarding through ongoing development. Cadence: Onboarding. |
