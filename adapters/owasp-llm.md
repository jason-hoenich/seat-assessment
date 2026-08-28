# OWASP Top 10 for LLM Applications 2025

Mapping of SEAT outcomes to the OWASP Top 10 for LLM Applications (2025) risk categories, extending security awareness to the people who build and operate LLM-powered features.

**Version:** 2025  
**Adapter last updated:** 2026-07-22  
**Official reference:** https://genai.owasp.org/llm-top-10/  
**Adapter id:** `owasp-llm`

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
| Strategic Alignment | `strategic-alignment` | LLM06: Excessive Agency | Expected | Policy Document, Assessment Report | Annual | 4 | Yes |
| Governance Documentation | `governance-documentation` | LLM03: Supply Chain, LLM06: Excessive Agency | Required | Policy Document, Assessment Report | Annual | 4 | Yes |
| Continuous Improvement | `continuous-improvement` | LLM04: Data and Model Poisoning, LLM09: Misinformation | Expected | Assessment Report, Incident Report | Quarterly | 3 | Yes |
| Targeted Communication | `targeted-communication` | LLM01: Prompt Injection, LLM02: Sensitive Information Disclosure | Required | Communication Artifact, Training Record, Curriculum Document | Continuous | 4 | Yes |
| Active Participation | `active-participation` | LLM01: Prompt Injection, LLM07: System Prompt Leakage | Expected | Incident Report, Feedback Survey | Continuous | 4 | Yes |
| Feedback Responsiveness | `feedback-responsiveness` | LLM05: Improper Output Handling | Expected | Feedback Survey, Incident Report | As Needed | 3 | Yes |
| Performance Measurement | `performance-measurement` | LLM01: Prompt Injection, LLM06: Excessive Agency | Required | Metric Report, Assessment Report | Quarterly | 4 | Yes |
| Risk Driven Assessment | `risk-driven-assessment` | LLM06: Excessive Agency, LLM01: Prompt Injection | Required | Assessment Report, Policy Document | Semi-Annual | 5 | Yes |
| Behavioral Impact | `behavioral-impact` | LLM09: Misinformation | Expected | Simulation Results, Incident Report | Quarterly | 4 | **Not assessed** |
| Relevant Tailored Training | `relevant-tailored-training` | LLM01: Prompt Injection, LLM02: Sensitive Information Disclosure | Required | Curriculum Document, Training Record, Assessment Report | Annual | 5 | Yes |
| Effective Learning Methods | `effective-learning-methods` | LLM01: Prompt Injection, LLM05: Improper Output Handling | Expected | Training Record, Simulation Results, Feedback Survey | As Needed | 4 | Yes |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | LLM02: Sensitive Information Disclosure, LLM06: Excessive Agency | Expected | Training Record | Onboarding | 4 | Yes |

## Mapping notes

**Strategic Alignment (LLM06: Excessive Agency).** LLM06 is about giving an LLM feature more autonomy, permissions, or tools than its function needs. Program strategy defines what LLM features are allowed to do and where a human stays in the loop, which is the governance boundary that keeps agency in check.

**Governance Documentation (LLM03: Supply Chain, LLM06: Excessive Agency).** Documented policy on approved models, plugins, and the permission scope of LLM features is the baseline that limits supply-chain exposure (LLM03) and unchecked agency (LLM06). Without it there is no standard to test a new LLM feature against.

**Continuous Improvement (LLM04: Data and Model Poisoning, LLM09: Misinformation).** LLM threats move fast. A continuous-improvement loop that folds new poisoning and misinformation patterns into guidance and tests is what keeps LLM defenses from ossifying around last year's attack set.

**Targeted Communication (LLM01: Prompt Injection, LLM02: Sensitive Information Disclosure).** Role-targeted communication teaches builders to treat all model input as untrusted (LLM01) and teaches every user not to paste secrets or regulated data into prompts (LLM02). These are behaviors, and behavior is changed by relevant messaging, not a generic banner.

**Active Participation (LLM01: Prompt Injection, LLM07: System Prompt Leakage).** A workforce that reports odd LLM behavior, suspected injection, or a leaked system prompt gives early human detection of attacks that pass automated filters. Participation turns users into a sensor layer for LLM01 and LLM07.

**Feedback Responsiveness (LLM05: Improper Output Handling).** LLM05 covers treating model output as trusted downstream. Responsive feedback channels surface where output is being consumed unsafely so it can be fixed before it reaches a browser, shell, or database.

**Performance Measurement (LLM01: Prompt Injection, LLM06: Excessive Agency).** Measuring how the organization's LLM features hold up against injection attempts and how well they stay within their intended agency is the detection layer for LLM01 and LLM06. Point-in-time review misses drift as features gain new tools.

**Risk Driven Assessment (LLM06: Excessive Agency, LLM01: Prompt Injection).** Risk-driven testing sends the deepest adversarial effort at the LLM features with the widest agency and the most sensitive reach, where a successful injection does the most damage. Blast radius, not feature count, sets the priority.

**Behavioral Impact (LLM09: Misinformation).** LLM09 is amplified by users who accept confident but wrong output. Measuring whether people verify LLM answers, through realistic scenarios, quantifies real resistance to misinformation rather than assumed skepticism.

**Relevant Tailored Training (LLM01: Prompt Injection, LLM02: Sensitive Information Disclosure).** Developers who build LLM features need training on injection defense and on keeping secrets and regulated data out of prompts and logs. General staff need the lighter version. Tailoring the depth to the role is what makes the training land.

**Effective Learning Methods (LLM01: Prompt Injection, LLM05: Improper Output Handling).** Hands-on exercises where people try to break a real LLM feature teach recognition of injection and unsafe output handling far better than slides. The skill is pattern recognition, and pattern recognition is built by doing.

**Integrated Training Lifecycle (LLM02: Sensitive Information Disclosure, LLM06: Excessive Agency).** Embedding LLM secure-use habits from developer onboarding, and refreshing them when someone starts building agentic features, builds durable defaults against disclosure and over-permissioning rather than relying on a one-time course.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.