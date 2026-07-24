# NIST Cybersecurity Framework 2.0

**Version:** 2.0
**Last Updated:** 2025-01-27
**Official Reference:** https://www.nist.gov/cyberframework

Mapping of SEAT outcomes to NIST CSF 2.0 controls and practices.

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
| strategic-alignment | GV.RM-03, GV.PO-01 | Expected | Policy Document, Assessment Report, Board Minutes | 5 | Cybersecurity risk management activities and outcomes are included in enterprise risk management processes. Policy for managing cybersecurity risks is established based on organizational context. Cadence: Annual. |
| governance-documentation | GV.PO-01, GV.PO-02 | Expected | Policy Document, Assessment Report | 4 | Policy for managing cybersecurity risks is established and regularly reviewed, updated, communicated, and enforced. Cadence: Annual. |
| executive-support | GV.RM-01, GV.RR-01 | Expected | Board Minutes, Policy Document | 5 | Risk management objectives are established and agreed to by organizational stakeholders. Roles, responsibilities, and authorities for cybersecurity are established. Cadence: Semi-Annual. |
| continuous-improvement | GV.OV-01, ID.IM-01 | Expected | Assessment Report, Metric Report | 4 | Results of organization-wide cybersecurity risk management activities are used to inform and adjust the risk management strategy. Cadence: Quarterly. |
| targeted-communication | PR.AT-02 | Expected | Communication Artifact, Training Record, Curriculum Document | 3 | Individuals in specialized roles are provided with awareness and training tailored to their specific responsibilities. Cadence: As Needed. |
| cultural-relevance | PR.AT-01 | Recommended | Communication Artifact, Feedback Survey | 2 | Personnel are provided with awareness and training that is culturally appropriate and accessible. Cadence: Continuous. |
| active-participation | PR.AT-01 | Expected | Feedback Survey, Incident Report | 3 | Fostering a security-aware culture that encourages active employee participation in security initiatives. Cadence: Continuous. |
| feedback-responsiveness | ID.IM-01, RS.CO-01 | Expected | Feedback Survey | 3 | Continuous evaluation is applied to identify improvements based on stakeholder feedback. Cadence: Quarterly. |
| performance-measurement | GV.OV-01, ID.RA-01 | Expected | Metric Report, Assessment Report | 4 | Results of cybersecurity risk management activities and performance are tracked and used to inform strategy. Cadence: Quarterly. |
| risk-driven-assessment | ID.RA-01, GV.RM-03 | Expected | Assessment Report, Policy Document, Curriculum Document | 5 | Cybersecurity risks are identified and understood, informing awareness program priorities. Cadence: Semi-Annual. |
| behavioral-impact-assessment | PR.AT-01, DE.CM-01 | Recommended | Simulation Results, Incident Report | 3 | Monitoring and assessing changes in employee security behaviors and incident response. Cadence: Quarterly. |
| relevant-tailored-training | PR.AT-02 | Expected | Curriculum Document, Training Record, Assessment Report | 4 | Training content is specific to roles and identified organizational risks. Cadence: Annual. |
| effective-learning-methods | PR.AT-01 | Recommended | Training Record, Simulation Results, Feedback Survey | 3 | Utilizing engaging and practical training approaches that demonstrate effectiveness. Cadence: As Needed. |
| accessible-inclusive-training | PR.AT-01 | Expected | Communication Artifact | 3 | Ensuring training is available and understandable to all personnel regardless of role or background. Cadence: Continuous. |
| flexible-effective-delivery | PR.AT-01 | Expected | Training Record | 4 | Optimizing training delivery for behavioral impact and knowledge retention rather than fixed time requirements. Cadence: As Needed. |
| integrated-training-lifecycle | PR.AT-01, PR.AT-02 | Expected | Training Record | 4 | Embedding training into employee lifecycle from onboarding through ongoing professional development. Cadence: Onboarding. |
