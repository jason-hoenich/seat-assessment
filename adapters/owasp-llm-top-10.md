# OWASP Top 10 for LLM Applications 2025

**Version:** 2025
**Last Updated:** 2026-07-22
**Official Reference:** https://genai.owasp.org/llm-top-10/

Mapping of SEAT outcomes to the OWASP Top 10 for LLM Applications (2025) risk categories, extending security awareness to the people who build and operate LLM-powered features.

Application-layer risks for LLM-powered software, from the OWASP GenAI Security Project. This adapter maps SEAT outcomes to the risks that are as much a workforce problem as a technical one: the people building and using LLM features are the control surface for prompt injection, sensitive-information disclosure, over-reliance on misinformation, and excessive agency. Risk IDs follow the 2025 list (LLM01-LLM10). It is an awareness and testing reference, not a regulation, so there are no direct penalties; its value is the shared vocabulary for training builders on what to test for.

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
| strategic-alignment | LLM06: Excessive Agency | Expected | Policy Document, Assessment Report | 4 | LLM06 is about giving an LLM feature more autonomy, permissions, or tools than its function needs. Program strategy defines what LLM features are allowed to do and where a human stays in the loop, which is the governance boundary that keeps agency in check. Cadence: Annual. |
| governance-documentation | LLM03: Supply Chain, LLM06: Excessive Agency | Required | Policy Document, Assessment Report | 4 | Documented policy on approved models, plugins, and the permission scope of LLM features is the baseline that limits supply-chain exposure (LLM03) and unchecked agency (LLM06). Without it there is no standard to test a new LLM feature against. Cadence: Annual. |
| continuous-improvement | LLM04: Data and Model Poisoning, LLM09: Misinformation | Expected | Assessment Report, Incident Report | 3 | LLM threats move fast. A continuous-improvement loop that folds new poisoning and misinformation patterns into guidance and tests is what keeps LLM defenses from ossifying around last year's attack set. Cadence: Quarterly. |
| targeted-communication | LLM01: Prompt Injection, LLM02: Sensitive Information Disclosure | Required | Communication Artifact, Training Record, Curriculum Document | 4 | Role-targeted communication teaches builders to treat all model input as untrusted (LLM01) and teaches every user not to paste secrets or regulated data into prompts (LLM02). These are behaviors, and behavior is changed by relevant messaging, not a generic banner. Cadence: Continuous. |
| active-participation | LLM01: Prompt Injection, LLM07: System Prompt Leakage | Expected | Incident Report, Feedback Survey | 4 | A workforce that reports odd LLM behavior, suspected injection, or a leaked system prompt gives early human detection of attacks that pass automated filters. Participation turns users into a sensor layer for LLM01 and LLM07. Cadence: Continuous. |
| feedback-responsiveness | LLM05: Improper Output Handling | Expected | Feedback Survey, Incident Report | 3 | LLM05 covers treating model output as trusted downstream. Responsive feedback channels surface where output is being consumed unsafely so it can be fixed before it reaches a browser, shell, or database. Cadence: As Needed. |
| performance-measurement | LLM01: Prompt Injection, LLM06: Excessive Agency | Required | Metric Report, Assessment Report | 4 | Measuring how the organization's LLM features hold up against injection attempts and how well they stay within their intended agency is the detection layer for LLM01 and LLM06. Point-in-time review misses drift as features gain new tools. Cadence: Quarterly. |
| risk-driven-assessment | LLM06: Excessive Agency, LLM01: Prompt Injection | Required | Assessment Report, Policy Document | 5 | Risk-driven testing sends the deepest adversarial effort at the LLM features with the widest agency and the most sensitive reach, where a successful injection does the most damage. Blast radius, not feature count, sets the priority. Cadence: Semi-Annual. |
| behavioral-impact | LLM09: Misinformation | Expected | Simulation Results, Incident Report | 4 | LLM09 is amplified by users who accept confident but wrong output. Measuring whether people actually verify LLM answers, through realistic scenarios, quantifies real resistance to misinformation rather than assumed skepticism. Cadence: Quarterly. |
| relevant-tailored-training | LLM01: Prompt Injection, LLM02: Sensitive Information Disclosure | Required | Curriculum Document, Training Record, Assessment Report | 5 | Developers who build LLM features need training on injection defense and on keeping secrets and regulated data out of prompts and logs. General staff need the lighter version. Tailoring the depth to the role is what makes the training land. Cadence: Annual. |
| effective-learning-methods | LLM01: Prompt Injection, LLM05: Improper Output Handling | Expected | Training Record, Simulation Results, Feedback Survey | 4 | Hands-on exercises where people try to break a real LLM feature teach recognition of injection and unsafe output handling far better than slides. The skill is pattern recognition, and pattern recognition is built by doing. Cadence: As Needed. |
| integrated-training-lifecycle | LLM02: Sensitive Information Disclosure, LLM06: Excessive Agency | Expected | Training Record | 4 | Embedding LLM secure-use habits from developer onboarding, and refreshing them when someone starts building agentic features, builds durable defaults against disclosure and over-permissioning rather than relying on a one-time course. Cadence: Onboarding. |
