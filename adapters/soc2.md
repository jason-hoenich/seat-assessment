# SOC 2

**Version:** 2017 TSC
**Last Updated:** 2025-01-27
**Official Reference:** https://www.aicpa.org/interestareas/frc/assuranceadvisoryservices/aicpasoc2report

Mapping of SEAT outcomes to SOC 2 Trust Services Criteria (TSC) and Common Criteria (CC).

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
| strategic-alignment | CC3.1, CC9.1 | Required | Assessment Report, Policy Document | 5 | Aligning security awareness with overall risk management and organizational objectives through risk identification and assessment. Cadence: Annual. |
| governance-documentation | CC2.1, CC5.1 | Required | Policy Document | 4 | Formal documentation and regular review of program governance and controls to support internal control functioning. Cadence: Annual. |
| executive-support | CC1.2 | Required | Board Minutes | 5 | Leadership commitment and oversight for the control environment, with board exercising independent oversight. Cadence: Annual. |
| continuous-improvement | CC4.1, CC7.1 | Required | Assessment Report, Metric Report | 4 | Regular assessment and adaptation of the program based on ongoing monitoring and evaluation findings. Cadence: Continuous. |
| targeted-communication | CC2.2 | Required | Communication Artifact, Training Record, Curriculum Document | 4 | Tailoring communications and training to specific roles and groups to improve security knowledge and behavior. Cadence: As Needed. |
| cultural-relevance | CC1.1 | Recommended | Feedback Survey, Communication Artifact | 2 | Fostering a security-aware culture that aligns with organizational values and commitment to integrity. Cadence: Continuous. |
| active-participation | CC2.2, CC7.2 | Expected | Incident Report, Feedback Survey | 3 | Encouraging and measuring active employee involvement in security initiatives, including modeling appropriate security behaviors. Cadence: Continuous. |
| feedback-responsiveness | CC4.1 | Expected | Feedback Survey | 3 | Establishing and acting on employee feedback channels to improve control effectiveness through ongoing evaluations. Cadence: Quarterly. |
| performance-measurement | CC4.1, CC7.1 | Required | Metric Report, Assessment Report | 4 | Tracking and reporting program effectiveness using KPIs and continuous monitoring procedures. Cadence: Quarterly. |
| risk-driven-assessment | CC3.1, CC9.1 | Required | Assessment Report, Policy Document, Curriculum Document | 5 | Using risk assessments to guide awareness content and priorities through systematic risk identification and response. Cadence: Annual. |
| behavioral-impact | CC2.2, CC7.2 | Expected | Simulation Results, Incident Report | 3 | Assessing changes in employee security behaviors and their impact on security posture through training programs. Cadence: Quarterly. |
| relevant-tailored-training | CC2.2 | Required | Curriculum Document, Training Record | 4 | Training content is specific to roles and identified risks, tailored to improve security knowledge and behavior. Cadence: Annual. |
| effective-learning-methods | CC2.2 | Expected | Training Record, Simulation Results, Feedback Survey | 3 | Utilizing engaging and practical training approaches that demonstrate effectiveness in improving security behaviors. Cadence: As Needed. |
| accessible-inclusive-training | CC2.2 | Required | Communication Artifact | 3 | Ensuring training is available and understandable to all relevant personnel through comprehensive awareness programs. Cadence: Continuous. |
| flexible-effective-delivery | CC2.2 | Expected | Training Record | 4 | Optimizing training delivery for behavioral impact and knowledge retention, while meeting program requirements. Cadence: Annual. |
| integrated-training-lifecycle | CC2.2 | Expected | Training Record | 4 | Embedding training into employee lifecycle from onboarding through ongoing professional development. Cadence: Onboarding. |
