# MITRE ATLAS

Mapping of SEAT outcomes to MITRE ATLAS, using its adversary tactics, techniques, and case studies as the threat model that grounds AI-focused awareness training, assessment, and red-team exercises.

**Version:** living  
**Adapter last updated:** 2026-07-22  
**Official reference:** https://atlas.mitre.org/  
**Adapter id:** `mitre-atlas`

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
| Strategic Alignment | `strategic-alignment` | ATLAS threat model (all tactics) | Recommended | Policy Document, Assessment Report | Annual | 3 | Yes |
| Governance Documentation | `governance-documentation` | ATLAS: ML Supply Chain Compromise | Recommended | Policy Document, Assessment Report | Annual | 3 | Yes |
| Continuous Improvement | `continuous-improvement` | ATLAS case studies (living) | Expected | Assessment Report, Incident Report | Quarterly | 3 | Yes |
| Targeted Communication | `targeted-communication` | ATLAS: Data Poisoning, Model Evasion | Expected | Communication Artifact, Training Record, Curriculum Document | Continuous | 3 | Yes |
| Active Participation | `active-participation` | ATLAS: Reconnaissance, LLM Prompt Injection | Expected | Incident Report, Feedback Survey | Continuous | 3 | Yes |
| Performance Measurement | `performance-measurement` | ATLAS tactics (detection coverage) | Expected | Metric Report, Assessment Report | Quarterly | 3 | Yes |
| Risk Driven Assessment | `risk-driven-assessment` | ATLAS: ML Attack Staging, Model Evasion | Expected | Assessment Report, Simulation Results | Semi-Annual | 4 | Yes |
| Behavioral Impact | `behavioral-impact` | ATLAS case studies | Recommended | Simulation Results, Incident Report | Quarterly | 3 | **Not assessed** |
| Relevant Tailored Training | `relevant-tailored-training` | ATLAS techniques (by role) | Expected | Curriculum Document, Training Record | Annual | 3 | Yes |
| Effective Learning Methods | `effective-learning-methods` | ATLAS case studies (scenario fuel) | Expected | Training Record, Simulation Results | As Needed | 4 | Yes |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | ATLAS threat model (ML roles) | Recommended | Training Record | Onboarding | 3 | Yes |

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