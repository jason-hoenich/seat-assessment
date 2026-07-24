# Cybersecurity Maturity Model Certification (CMMC)

**Version:** 2.0
**Last Updated:** 2025-01-27
**Official Reference:** https://www.acq.osd.mil/cmmc/

Mapping of SEAT outcomes to CMMC 2.0 practices for defense contractors handling CUI.

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
| strategic-alignment | RM.L2-3.11.1, GOV.L2-P1.1 | Required | Assessment Report, Policy Document | 5 | CMMC requires periodic risk assessment and a documented cybersecurity program plan that aligns with organizational objectives. Cadence: Annual. |
| governance-documentation | GOV.L2-P1.1, GOV.L2-P1.2 | Required | Policy Document | 4 | CMMC mandates documented cybersecurity program plans, policies, and procedures for all practices. Cadence: Annual. |
| executive-support | GOV.L2-P1.1, GOV.L2-P1.3 | Required | Policy Document | 5 | Leadership commitment and adequate resource allocation are critical for CMMC compliance and program effectiveness. Cadence: Annual. |
| continuous-improvement | GOV.L2-P1.4, AT.L2-3.1.5 | Required | Assessment Report, Metric Report | 4 | CMMC requires ongoing monitoring of cybersecurity program effectiveness and updating training as needed. Cadence: Continuous. |
| targeted-communication | AT.L2-3.1.2 | Required | Training Record, Curriculum Document, Communication Artifact | 4 | CMMC requires security awareness training that addresses risks associated with specific activities and organizational policies. Cadence: Annual. |
| cultural-relevance | AT.L2-3.1.2 | Recommended | Feedback Survey, Communication Artifact | 2 | Effective awareness programs consider organizational context and culture to improve engagement and understanding. Cadence: Continuous. |
| active-participation | IR.L2-3.6.1, AT.L2-3.1.2 | Required | Incident Report, Training Record | 4 | CMMC requires operational incident handling capability and training on reporting procedures. Cadence: Continuous. |
| feedback-responsiveness | AT.L2-3.1.5, GOV.L2-P1.4 | Expected | Feedback Survey, Training Record | 3 | CMMC requires updating training based on evolving needs and program effectiveness reviews. Cadence: As Needed. |
| performance-measurement | AT.L2-3.1.4, GOV.L2-P1.4 | Required | Metric Report, Assessment Report, Training Record | 4 | CMMC mandates annual security awareness training and monitoring of cybersecurity program effectiveness. Cadence: Annual. |
| risk-driven-assessment | RM.L2-3.11.1, AT.L2-3.1.2 | Required | Assessment Report, Curriculum Document, Policy Document | 5 | CMMC requires periodic risk assessment and training that addresses identified organizational risks. Cadence: Annual. |
| behavioral-impact | AT.L2-3.1.4, IR.L2-3.6.1 | Expected | Simulation Results, Incident Report | 3 | Assessing behavioral changes through simulations and incident data supports CMMC compliance verification. Cadence: Quarterly. |
| relevant-tailored-training | AT.L2-3.1.2, AT.L3-3.1.3 | Required | Curriculum Document, Training Record | 5 | CMMC requires training tailored to roles and specific organizational risks, with specialized training for privileged functions. Cadence: Annual. |
| effective-learning-methods | AT.L2-3.1.2 | Expected | Training Record, Feedback Survey | 3 | CMMC implies that training methods should effectively inform personnel about risks and procedures. Cadence: As Needed. |
| accessible-inclusive-training | AT.L2-3.1.1 | Required | Training Record, Communication Artifact | 3 | CMMC requires security awareness training for all information system users, including personnel and contractors. Cadence: Continuous. |
| flexible-effective-delivery | AT.L2-3.1.4 | Required | Training Record | 4 | CMMC specifies minimum annual training frequency, but effective delivery methods are implied for compliance. Cadence: Annual. |
| integrated-training-lifecycle | AT.L2-3.1.1, AT.L2-3.1.4 | Required | Training Record | 4 | CMMC requires initial and recurring security awareness training for all information system users. Cadence: Onboarding. |
