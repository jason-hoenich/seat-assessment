# MITRE ATLAS

**Version:** living
**Last Updated:** 2026-07-22
**Official Reference:** https://atlas.mitre.org/

Mapping of SEAT outcomes to MITRE ATLAS, using its adversary tactics, techniques, and case studies as the threat model that grounds AI-focused awareness training, assessment, and red-team exercises.

An ATT&CK-style, living knowledge base of real-world adversary tactics and techniques against AI and ML systems, backed by documented case studies. It is a threat-modeling and red-team reference, not a program or compliance framework, so it has no teeth of its own. For a human risk program its value is scenario fuel: ATLAS techniques and case studies make training concrete and give assessment a real adversary model to test against. References here name the ATLAS tactic or technique rather than AML.T identifiers, to avoid citing a specific technique number this adapter has not verified.

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
| strategic-alignment | ATLAS threat model (all tactics) | Recommended | Policy Document, Assessment Report | 3 | ATLAS gives program strategy a real adversary model for AI systems. Prioritizing awareness and controls around the tactics actually seen against ML systems, rather than hypothetical fears, is what keeps the strategy grounded in observed threat. Cadence: Annual. |
| governance-documentation | ATLAS: ML Supply Chain Compromise | Recommended | Policy Document, Assessment Report | 3 | Techniques like ML supply chain compromise and poisoning of public datasets or models argue for documented policy on vetted model and data sources. ATLAS supplies the concrete failure modes that policy needs to address. Cadence: Annual. |
| continuous-improvement | ATLAS case studies (living) | Expected | Assessment Report, Incident Report | 3 | ATLAS is updated as new techniques and case studies are documented. A continuous-improvement loop that refreshes training scenarios and test cases against the latest ATLAS entries keeps the program current with a moving threat landscape. Cadence: Quarterly. |
| targeted-communication | ATLAS: Data Poisoning, Model Evasion | Expected | Communication Artifact, Training Record, Curriculum Document | 3 | Translating ATLAS techniques such as training-data poisoning and model evasion into role-relevant language, especially for the ML and data teams who can spot them, is what turns an abstract threat catalog into awareness that changes behavior. Cadence: Continuous. |
| active-participation | ATLAS: Reconnaissance, LLM Prompt Injection | Expected | Incident Report, Feedback Survey | 3 | Many ATLAS tactics begin with reconnaissance or probing of a deployed model. Staff who recognize and report those early signs, including prompt-injection attempts, give human detection ahead of impact. Cadence: Continuous. |
| performance-measurement | ATLAS tactics (detection coverage) | Expected | Metric Report, Assessment Report | 3 | Measuring how well the organization detects and responds to ATLAS-mapped techniques turns the knowledge base into a coverage metric, showing which adversary behaviors against AI systems the program can actually catch. Cadence: Quarterly. |
| risk-driven-assessment | ATLAS: ML Attack Staging, Model Evasion | Expected | Assessment Report, Simulation Results | 4 | ATLAS gives red teams a structured technique set to exercise AI systems against. Prioritizing that testing by exposure, the models with the widest reach and most sensitive data, is risk-driven assessment with a concrete adversary playbook. Cadence: Semi-Annual. |
| behavioral-impact | ATLAS case studies | Recommended | Simulation Results, Incident Report | 3 | Simulations built from documented ATLAS case studies, such as evasion or prompt injection against a real system, measure whether people respond correctly to an actual attack pattern rather than a contrived one. Cadence: Quarterly. |
| relevant-tailored-training | ATLAS techniques (by role) | Expected | Curriculum Document, Training Record | 3 | ATLAS is written for security engineers and ML teams more than general staff. Training that maps its techniques to the people who build and defend models, rather than pushing red-team detail to everyone, is what makes it useful. Cadence: Annual. |
| effective-learning-methods | ATLAS case studies (scenario fuel) | Expected | Training Record, Simulation Results | 4 | The documented ATLAS case studies are ready-made, realistic scenarios. Using them as the basis for hands-on exercises teaches recognition of real AI attacks far better than abstract description. Cadence: As Needed. |
| integrated-training-lifecycle | ATLAS threat model (ML roles) | Recommended | Training Record | 3 | Embedding AI adversary awareness from onboarding for ML and data-engineering roles, using the ATLAS model, builds threat literacy into the people who ship models rather than bolting it on after an incident. Cadence: Onboarding. |
