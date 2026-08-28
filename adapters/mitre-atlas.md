# MITRE ATLAS

Mapping of SEAT outcomes to MITRE ATLAS, using its adversary tactics, techniques, and case studies as the threat model that grounds AI-focused awareness training, assessment, and red-team exercises.

**Version:** living  
**Adapter last updated:** 2026-07-22  
**Official reference:** https://atlas.mitre.org/  
**Adapter id:** `mitre-atlas`

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
| Strategic Alignment | `strategic-alignment` | ATLAS threat model (all tactics) | Recommended | Policy Document, Assessment Report | Annual | 3 |
| Governance Documentation | `governance-documentation` | ATLAS: ML Supply Chain Compromise | Recommended | Policy Document, Assessment Report | Annual | 3 |
| Continuous Improvement | `continuous-improvement` | ATLAS case studies (living) | Expected | Assessment Report, Incident Report | Quarterly | 3 |
| Targeted Communication | `targeted-communication` | ATLAS: Data Poisoning, Model Evasion | Expected | Communication Artifact, Training Record, Curriculum Document | Continuous | 3 |
| Active Participation | `active-participation` | ATLAS: Reconnaissance, LLM Prompt Injection | Expected | Incident Report, Feedback Survey | Continuous | 3 |
| Performance Measurement | `performance-measurement` | ATLAS tactics (detection coverage) | Expected | Metric Report, Assessment Report | Quarterly | 3 |
| Risk Driven Assessment | `risk-driven-assessment` | ATLAS: ML Attack Staging, Model Evasion | Expected | Assessment Report, Simulation Results | Semi-Annual | 4 |
| Behavioral Impact | `behavioral-impact` | ATLAS case studies | Recommended | Simulation Results, Incident Report | Quarterly | 3 |
| Relevant Tailored Training | `relevant-tailored-training` | ATLAS techniques (by role) | Expected | Curriculum Document, Training Record | Annual | 3 |
| Effective Learning Methods | `effective-learning-methods` | ATLAS case studies (scenario fuel) | Expected | Training Record, Simulation Results | As Needed | 4 |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | ATLAS threat model (ML roles) | Recommended | Training Record | Onboarding | 3 |

## Mapping notes

**Strategic Alignment (ATLAS threat model (all tactics)).** ATLAS gives program strategy a real adversary model for AI systems. Prioritizing awareness and controls around the tactics seen against ML systems, rather than hypothetical fears, is what keeps the strategy grounded in observed threat.

**Governance Documentation (ATLAS: ML Supply Chain Compromise).** Techniques like ML supply chain compromise and poisoning of public datasets or models argue for documented policy on vetted model and data sources. ATLAS supplies the concrete failure modes that policy needs to address.

**Continuous Improvement (ATLAS case studies (living)).** ATLAS is updated as new techniques and case studies are documented. A continuous-improvement loop that refreshes training scenarios and test cases against the latest ATLAS entries keeps the program current with a moving threat landscape.

**Targeted Communication (ATLAS: Data Poisoning, Model Evasion).** Translating ATLAS techniques such as training-data poisoning and model evasion into role-relevant language, especially for the ML and data teams who can spot them, is what turns an abstract threat catalog into awareness that changes behavior.

**Active Participation (ATLAS: Reconnaissance, LLM Prompt Injection).** Many ATLAS tactics begin with reconnaissance or probing of a deployed model. Staff who recognize and report those early signs, including prompt-injection attempts, give human detection ahead of impact.

**Performance Measurement (ATLAS tactics (detection coverage)).** Measuring how well the organization detects and responds to ATLAS-mapped techniques turns the knowledge base into a coverage metric, showing which adversary behaviors against AI systems the program can catch.

**Risk Driven Assessment (ATLAS: ML Attack Staging, Model Evasion).** ATLAS gives red teams a structured technique set to exercise AI systems against. Prioritizing that testing by exposure, the models with the widest reach and most sensitive data, is risk-driven assessment with a concrete adversary playbook.

**Behavioral Impact (ATLAS case studies).** Simulations built from documented ATLAS case studies, such as evasion or prompt injection against a real system, measure whether people respond correctly to an actual attack pattern rather than a contrived one.

**Relevant Tailored Training (ATLAS techniques (by role)).** ATLAS is written for security engineers and ML teams more than general staff. Training that maps its techniques to the people who build and defend models, rather than pushing red-team detail to everyone, is what makes it useful.

**Effective Learning Methods (ATLAS case studies (scenario fuel)).** The documented ATLAS case studies are ready-made, realistic scenarios. Using them as the basis for hands-on exercises teaches recognition of real AI attacks far better than abstract description.

**Integrated Training Lifecycle (ATLAS threat model (ML roles)).** Embedding AI adversary awareness from onboarding for ML and data-engineering roles, using the ATLAS model, builds threat literacy into the people who ship models rather than bolting it on after an incident.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.