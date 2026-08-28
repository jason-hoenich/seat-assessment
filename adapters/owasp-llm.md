# OWASP Top 10 for LLM Applications 2025

Mapping of SEAT outcomes to the OWASP Top 10 for LLM Applications (2025) risk categories, extending security awareness to the people who build and operate LLM-powered features.

**Version:** 2025  
**Adapter last updated:** 2026-07-22  
**Official reference:** https://genai.owasp.org/llm-top-10/  
**Adapter id:** `owasp-llm`

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
| Strategic Alignment | `strategic-alignment` | LLM06: Excessive Agency | Expected | Policy Document, Assessment Report | Annual | 4 |
| Governance Documentation | `governance-documentation` | LLM03: Supply Chain, LLM06: Excessive Agency | Required | Policy Document, Assessment Report | Annual | 4 |
| Continuous Improvement | `continuous-improvement` | LLM04: Data and Model Poisoning, LLM09: Misinformation | Expected | Assessment Report, Incident Report | Quarterly | 3 |
| Targeted Communication | `targeted-communication` | LLM01: Prompt Injection, LLM02: Sensitive Information Disclosure | Required | Communication Artifact, Training Record, Curriculum Document | Continuous | 4 |
| Active Participation | `active-participation` | LLM01: Prompt Injection, LLM07: System Prompt Leakage | Expected | Incident Report, Feedback Survey | Continuous | 4 |
| Feedback Responsiveness | `feedback-responsiveness` | LLM05: Improper Output Handling | Expected | Feedback Survey, Incident Report | As Needed | 3 |
| Performance Measurement | `performance-measurement` | LLM01: Prompt Injection, LLM06: Excessive Agency | Required | Metric Report, Assessment Report | Quarterly | 4 |
| Risk Driven Assessment | `risk-driven-assessment` | LLM06: Excessive Agency, LLM01: Prompt Injection | Required | Assessment Report, Policy Document | Semi-Annual | 5 |
| Behavioral Impact | `behavioral-impact` | LLM09: Misinformation | Expected | Simulation Results, Incident Report | Quarterly | 4 |
| Relevant Tailored Training | `relevant-tailored-training` | LLM01: Prompt Injection, LLM02: Sensitive Information Disclosure | Required | Curriculum Document, Training Record, Assessment Report | Annual | 5 |
| Effective Learning Methods | `effective-learning-methods` | LLM01: Prompt Injection, LLM05: Improper Output Handling | Expected | Training Record, Simulation Results, Feedback Survey | As Needed | 4 |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | LLM02: Sensitive Information Disclosure, LLM06: Excessive Agency | Expected | Training Record | Onboarding | 4 |

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