# Digital Operational Resilience Act (DORA)

**Version:** 1.0
**Last Updated:** 2025-01-27
**Official Reference:** https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32022R2554

Mapping of SEAT outcomes to DORA requirements for financial entities.

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
| strategic-alignment | Art. 5, Art. 6 | Required | Policy Document, Board Minutes, Assessment Report | 5 | DORA mandates that ICT risk management is integrated into overall risk management and overseen by the management body. Cadence: Annual. |
| governance-documentation | Art. 6, Art. 13 | Required | Policy Document, Assessment Report | 4 | Comprehensive documentation of the ICT risk management framework and awareness programs is a core requirement. Cadence: Annual. |
| executive-support | Art. 5 | Required | Board Minutes, Training Record | 5 | DORA places ultimate responsibility for ICT risk and digital operational resilience on the management body, requiring their active engagement and training. Cadence: Annual. |
| continuous-improvement | Art. 6, Art. 13, Art. 17, Art. 24 | Required | Assessment Report, Incident Report | 5 | DORA emphasizes continuous improvement of digital operational resilience based on incidents, testing, and evolving risks. Cadence: Continuous. |
| targeted-communication | Art. 13, Art. 14 | Required | Communication Artifact, Training Record, Curriculum Document | 4 | DORA requires comprehensive awareness programs and clear communication strategies for incidents, tailored where necessary. Cadence: Continuous. |
| cultural-relevance | Art. 13 | Recommended | Feedback Survey, Communication Artifact | 2 | While not explicitly stated, effective awareness programs should consider cultural context for better engagement and understanding. Cadence: Continuous. |
| active-participation | Art. 17, Art. 45 | Required | Incident Report, Feedback Survey | 4 | DORA requires robust incident reporting processes and encourages participation in information sharing arrangements. Cadence: Continuous. |
| feedback-responsiveness | Art. 17 | Expected | Incident Report, Feedback Survey | 3 | Learning from incidents and addressing feedback is crucial for improving resilience. Cadence: As Needed. |
| performance-measurement | Art. 6, Art. 13, Art. 24 | Required | Metric Report, Assessment Report | 4 | DORA requires continuous monitoring and regular testing to measure and enhance digital operational resilience. Cadence: Quarterly. |
| risk-driven-assessment | Art. 6, Art. 24 | Required | Assessment Report, Policy Document | 5 | Risk assessments and testing are fundamental to DORA, driving the focus of resilience efforts. Cadence: Annual. |
| behavioral-impact | Art. 26 | Expected | Simulation Results, Incident Report | 3 | DORA's advanced testing (TLPT) implicitly assesses human behavior and response to sophisticated threats. Cadence: Triennial. |
| relevant-tailored-training | Art. 13 | Required | Curriculum Document, Training Record | 5 | Training must be tailored to the roles and responsibilities of staff, including senior management. Cadence: Annual. |
| effective-learning-methods | Art. 13 | Expected | Training Record, Simulation Results, Feedback Survey | 3 | DORA implies that training methods should be effective in enhancing cyber maturity and preparedness. Cadence: As Needed. |
| accessible-inclusive-training | Art. 13 | Required | Communication Artifact | 3 | Training must be accessible and compulsory for all relevant personnel. Cadence: Continuous. |
| flexible-effective-delivery | Art. 13 | Expected | Training Record | 4 | While annual training is compulsory, the delivery should be effective in building resilience. Cadence: Annual. |
| integrated-training-lifecycle | Art. 13 | Required | Training Record | 4 | Training is a continuous and compulsory part of staff development under DORA. Cadence: Onboarding. |
