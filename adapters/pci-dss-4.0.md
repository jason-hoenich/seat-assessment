# PCI DSS 4.0

**Version:** 4.0
**Last Updated:** 2025-01-27
**Official Reference:** https://www.pcisecuritystandards.org/document_library/

Mapping of SEAT outcomes to PCI DSS 4.0 requirements.

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
| strategic-alignment | 12.3, 12.3.1 | Required | Assessment Report, Policy Document | 5 | PCI DSS 4.0 emphasizes targeted risk analysis to align security measures with specific risks to the CDE. Cadence: Semi-Annual. |
| governance-documentation | 12.1, 12.5.2 | Required | Policy Document | 4 | Formal, documented policies and procedures are foundational for PCI DSS compliance. Cadence: Annual. |
| executive-support | 12.4.1 | Expected | Board Minutes | 4 | Executive oversight and resource allocation are critical for maintaining compliance. Required for service providers. Cadence: Annual. |
| continuous-improvement | 12.6.2, 12.3, 12.10.6 | Required | Assessment Report | 5 | PCI DSS 4.0 promotes security as a continuous process, requiring regular updates based on new threats. Cadence: Annual. |
| targeted-communication | 12.6.1, 12.6.3 | Required | Training Record, Communication Artifact, Curriculum Document | 4 | Training must be provided to all personnel, tailored to their roles and specific threats. Cadence: Annual. |
| cultural-relevance | 12.6 | Recommended | Feedback Survey, Communication Artifact | 2 | While not explicitly called out, effective awareness programs consider cultural context for better engagement. Cadence: Continuous. |
| active-participation | 12.6.3.3 | Required | Incident Report, Feedback Survey | 4 | Encouraging and enabling personnel to report suspicious activities is a direct PCI DSS requirement. Cadence: Continuous. |
| feedback-responsiveness | 12.6.4 | Expected | Training Record, Feedback Survey | 3 | Feedback mechanisms, especially acknowledgements, are required and should drive program improvements. Cadence: Annual. |
| performance-measurement | 12.6.2, 12.3.1 | Required | Metric Report, Assessment Report | 4 | Metrics are essential for demonstrating the effectiveness of the awareness program and informing TRAs. Cadence: Annual. |
| risk-driven-assessment | 12.3, 12.3.1 | Required | Assessment Report, Policy Document | 5 | PCI DSS 4.0 mandates targeted risk analyses to ensure security controls, including awareness, address specific risks. Cadence: Semi-Annual. |
| behavioral-impact-assessment | 12.6.3.1, 12.6.3.3 | Required | Simulation Results, Incident Report | 4 | Assessing behavioral changes related to phishing and incident reporting is directly supported by PCI DSS. Cadence: Quarterly. |
| relevant-tailored-training | 12.6.3, 6.2.2 | Required | Curriculum Document, Training Record | 5 | Training must be tailored to job roles and cover specific threats relevant to the CDE. Cadence: Annual. |
| effective-learning-methods | 12.6 | Expected | Simulation Results, Feedback Survey | 3 | PCI DSS encourages engaging and effective training methods to ensure understanding and retention. Cadence: As Needed. |
| accessible-inclusive-training | 12.6.1 | Required | Communication Artifact | 3 | Training must be accessible to all personnel who impact CDE security. Cadence: Continuous. |
| flexible-effective-delivery | 12.6.3 | Required | Training Record | 4 | PCI DSS is prescriptive about annual training frequency, but content delivery can be flexible as long as requirements are met. Cadence: Annual. |
| integrated-training-lifecycle | 12.6.3 | Required | Training Record | 4 | Training is required upon hire and annually, integrating it into the employee lifecycle. Cadence: Onboarding. |
