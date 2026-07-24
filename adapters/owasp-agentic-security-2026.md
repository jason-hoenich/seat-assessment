# OWASP Top 10 for Agentic Applications 2026

**Version:** 2026
**Last Updated:** 2026-06-16
**Official Reference:** https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/

Mapping of SEAT outcomes to the OWASP Top 10 for Agentic Applications (ASI) 2026 risk categories, extending security awareness program maturity to the oversight, identity, and governance of AI agents.

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
| strategic-alignment | ASI01:2026 - Agent Goal Hijack, ASI10:2026 - Rogue Agents | Expected | Policy Document, Assessment Report | 5 | Program strategy defines the approved objectives, autonomy boundaries, and guardrails for deployed agents, reducing the room for goal hijack and behavioral drift that produces rogue agents. Cadence: Annual. |
| governance-documentation | ASI03:2026 - Agent Identity & Privilege Abuse, ASI04:2026 - Agentic Supply Chain Compromise | Required | Policy Document, Assessment Report | 5 | Documented policy for agent identity, permission scoping, and approved tools and registries establishes the control baseline that limits privilege abuse and dynamic supply chain compromise. Cadence: Annual. |
| executive-support | ASI08:2026 - Cascading Agent Failures, ASI10:2026 - Rogue Agents | Required | Board Minutes, Policy Document | 5 | Leadership commitment funds the human-oversight checkpoints, segmentation, and emergency-shutdown mandates that contain cascading failures and rogue autonomous behavior. Cadence: Semi-Annual. |
| continuous-improvement | ASI06:2026 - Memory & Context Poisoning, ASI08:2026 - Cascading Agent Failures | Expected | Assessment Report, Incident Report | 4 | A continuous-improvement loop drives periodic memory integrity audits and post-incident hardening so that poisoned context and propagating failures are caught and designed out over time. Cadence: Quarterly. |
| targeted-communication | ASI09:2026 - Human-Agent Trust Exploitation | Required | Communication Artifact, Training Record, Curriculum Document | 5 | Role-targeted communication directly counters automation bias and authority misrepresentation by teaching staff when not to trust an agent's confident but unverified output. Cadence: Continuous. |
| cultural-relevance | ASI09:2026 - Human-Agent Trust Exploitation | Recommended | Communication Artifact, Feedback Survey | 2 | Messaging that resonates across roles and contexts makes the warning against over-reliance on agents land, reducing uncritical acceptance of misleading agent explanations. Cadence: Continuous. |
| active-participation | ASI01:2026 - Agent Goal Hijack, ASI09:2026 - Human-Agent Trust Exploitation | Expected | Incident Report, Feedback Survey | 4 | A workforce that actively reports anomalous or off-objective agent behavior provides early human detection of goal hijack and trust exploitation that automated monitoring can miss. Cadence: Continuous. |
| feedback-responsiveness | ASI02:2026 - Tool Misuse & Exploitation, ASI08:2026 - Cascading Agent Failures | Expected | Feedback Survey, Incident Report | 3 | Responsive feedback channels surface tool-misuse patterns and early failure signals so they can be contained before they cascade through connected tools and agents. Cadence: As Needed. |
| performance-measurement | ASI02:2026 - Tool Misuse & Exploitation, ASI10:2026 - Rogue Agents | Required | Metric Report, Assessment Report | 4 | Continuous measurement of agent tool usage and goal alignment is the detection layer for unsafe tool composition and gradual goal drift toward rogue behavior. Cadence: Quarterly. |
| risk-driven-assessment | ASI01:2026 - Agent Goal Hijack, ASI03:2026 - Agent Identity & Privilege Abuse | Required | Assessment Report, Policy Document | 5 | Risk-driven triage by blast radius decides which agents (those with the most privilege and the widest goal scope) receive the deepest adversarial testing for hijack and privilege abuse. Cadence: Semi-Annual. |
| behavioral-impact | ASI09:2026 - Human-Agent Trust Exploitation, ASI10:2026 - Rogue Agents | Expected | Simulation Results, Incident Report | 4 | Measuring whether people critically evaluate agent recommendations, via adversarial simulations, quantifies real resistance to trust exploitation rather than assumed vigilance. Cadence: Quarterly. |
| behavioral-impact-assessment | ASI06:2026 - Memory & Context Poisoning, ASI10:2026 - Rogue Agents | Recommended | Simulation Results, Incident Report | 3 | Repeated behavioral assessment over time detects gradual goal drift and the downstream effects of memory poisoning that a point-in-time check would miss. Cadence: Quarterly. |
| relevant-tailored-training | ASI01:2026 - Agent Goal Hijack, ASI09:2026 - Human-Agent Trust Exploitation | Required | Curriculum Document, Training Record, Assessment Report | 5 | Role-specific training on prompt and instruction injection and on agent over-reliance equips the people who build and supervise agents to recognize hijack attempts and resist trust exploitation. Cadence: Annual. |
| effective-learning-methods | ASI02:2026 - Tool Misuse & Exploitation, ASI09:2026 - Human-Agent Trust Exploitation | Expected | Training Record, Simulation Results, Feedback Survey | 4 | Hands-on, scenario-based methods (live adversarial exercises against real agents) teach recognition of tool misuse and misleading agent explanations far better than static content. Cadence: As Needed. |
| accessible-inclusive-training | ASI09:2026 - Human-Agent Trust Exploitation | Expected | Communication Artifact | 3 | Making agent-literacy training understandable to all personnel, not just builders, broadens the base of users who can spot automation bias and unwarranted agent confidence. Cadence: Continuous. |
| flexible-effective-delivery | ASI04:2026 - Agentic Supply Chain Compromise, ASI07:2026 - Insecure Inter-Agent Communication | Expected | Training Record | 4 | Flexible, rapidly updatable delivery keeps guidance current with fast-moving agent threats such as compromised tool registries and spoofed inter-agent messages. Cadence: As Needed. |
| integrated-training-lifecycle | ASI03:2026 - Agent Identity & Privilege Abuse, ASI10:2026 - Rogue Agents | Expected | Training Record | 4 | Embedding agent identity hygiene and autonomy-boundary expectations from onboarding onward builds durable habits that limit privilege abuse and runaway autonomy across the agent lifecycle. Cadence: Onboarding. |
