# OWASP Top 10 for Agentic Applications 2026

Mapping of SEAT outcomes to the OWASP Top 10 for Agentic Applications (ASI) 2026 risk categories, extending security awareness program maturity to the oversight, identity, and governance of AI agents.

**Version:** 2026  
**Adapter last updated:** 2026-06-16  
**Official reference:** https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/  
**Adapter id:** `owasp-asi-2026`

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
| Strategic Alignment | `strategic-alignment` | ASI01:2026 - Agent Goal Hijack, ASI10:2026 - Rogue Agents | Expected | Policy Document, Assessment Report | Annual | 5 | Yes |
| Governance Documentation | `governance-documentation` | ASI03:2026 - Agent Identity & Privilege Abuse, ASI04:2026 - Agentic Supply Chain Compromise | Required | Policy Document, Assessment Report | Annual | 5 | Yes |
| Executive Support | `executive-support` | ASI08:2026 - Cascading Agent Failures, ASI10:2026 - Rogue Agents | Required | Board Minutes, Policy Document | Semi-Annual | 5 | Yes |
| Continuous Improvement | `continuous-improvement` | ASI06:2026 - Memory & Context Poisoning, ASI08:2026 - Cascading Agent Failures | Expected | Assessment Report, Incident Report | Quarterly | 4 | Yes |
| Targeted Communication | `targeted-communication` | ASI09:2026 - Human-Agent Trust Exploitation | Required | Communication Artifact, Training Record, Curriculum Document | Continuous | 5 | Yes |
| Cultural Relevance | `cultural-relevance` | ASI09:2026 - Human-Agent Trust Exploitation | Recommended | Communication Artifact, Feedback Survey | Continuous | 2 | Yes |
| Active Participation | `active-participation` | ASI01:2026 - Agent Goal Hijack, ASI09:2026 - Human-Agent Trust Exploitation | Expected | Incident Report, Feedback Survey | Continuous | 4 | Yes |
| Feedback Responsiveness | `feedback-responsiveness` | ASI02:2026 - Tool Misuse & Exploitation, ASI08:2026 - Cascading Agent Failures | Expected | Feedback Survey, Incident Report | As Needed | 3 | Yes |
| Performance Measurement | `performance-measurement` | ASI02:2026 - Tool Misuse & Exploitation, ASI10:2026 - Rogue Agents | Required | Metric Report, Assessment Report | Quarterly | 4 | Yes |
| Risk Driven Assessment | `risk-driven-assessment` | ASI01:2026 - Agent Goal Hijack, ASI03:2026 - Agent Identity & Privilege Abuse | Required | Assessment Report, Policy Document | Semi-Annual | 5 | Yes |
| Behavioral Impact | `behavioral-impact` | ASI09:2026 - Human-Agent Trust Exploitation, ASI10:2026 - Rogue Agents | Expected | Simulation Results, Incident Report | Quarterly | 4 | **Not assessed** |
| Behavioral Impact Assessment | `behavioral-impact-assessment` | ASI06:2026 - Memory & Context Poisoning, ASI10:2026 - Rogue Agents | Recommended | Simulation Results, Incident Report | Quarterly | 3 | **Not assessed** |
| Relevant Tailored Training | `relevant-tailored-training` | ASI01:2026 - Agent Goal Hijack, ASI09:2026 - Human-Agent Trust Exploitation | Required | Curriculum Document, Training Record, Assessment Report | Annual | 5 | Yes |
| Effective Learning Methods | `effective-learning-methods` | ASI02:2026 - Tool Misuse & Exploitation, ASI09:2026 - Human-Agent Trust Exploitation | Expected | Training Record, Simulation Results, Feedback Survey | As Needed | 4 | Yes |
| Accessible Inclusive Training | `accessible-inclusive-training` | ASI09:2026 - Human-Agent Trust Exploitation | Expected | Communication Artifact | Continuous | 3 | Yes |
| Flexible Effective Delivery | `flexible-effective-delivery` | ASI04:2026 - Agentic Supply Chain Compromise, ASI07:2026 - Insecure Inter-Agent Communication | Expected | Training Record | As Needed | 4 | Yes |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | ASI03:2026 - Agent Identity & Privilege Abuse, ASI10:2026 - Rogue Agents | Expected | Training Record | Onboarding | 4 | Yes |

## Mapping notes

**Strategic Alignment (ASI01:2026 - Agent Goal Hijack, ASI10:2026 - Rogue Agents).** Program strategy defines the approved objectives, autonomy boundaries, and guardrails for deployed agents, reducing the room for goal hijack and behavioral drift that produces rogue agents.

**Governance Documentation (ASI03:2026 - Agent Identity & Privilege Abuse, ASI04:2026 - Agentic Supply Chain Compromise).** Documented policy for agent identity, permission scoping, and approved tools and registries establishes the control baseline that limits privilege abuse and dynamic supply chain compromise.

**Executive Support (ASI08:2026 - Cascading Agent Failures, ASI10:2026 - Rogue Agents).** Leadership commitment funds the human-oversight checkpoints, segmentation, and emergency-shutdown mandates that contain cascading failures and rogue autonomous behavior.

**Continuous Improvement (ASI06:2026 - Memory & Context Poisoning, ASI08:2026 - Cascading Agent Failures).** A continuous-improvement loop drives periodic memory integrity audits and post-incident hardening so that poisoned context and propagating failures are caught and designed out over time.

**Targeted Communication (ASI09:2026 - Human-Agent Trust Exploitation).** Role-targeted communication directly counters automation bias and authority misrepresentation by teaching staff when not to trust an agent's confident but unverified output.

**Cultural Relevance (ASI09:2026 - Human-Agent Trust Exploitation).** Messaging that resonates across roles and contexts makes the warning against over-reliance on agents land, reducing uncritical acceptance of misleading agent explanations.

**Active Participation (ASI01:2026 - Agent Goal Hijack, ASI09:2026 - Human-Agent Trust Exploitation).** A workforce that actively reports anomalous or off-objective agent behavior provides early human detection of goal hijack and trust exploitation that automated monitoring can miss.

**Feedback Responsiveness (ASI02:2026 - Tool Misuse & Exploitation, ASI08:2026 - Cascading Agent Failures).** Responsive feedback channels surface tool-misuse patterns and early failure signals so they can be contained before they cascade through connected tools and agents.

**Performance Measurement (ASI02:2026 - Tool Misuse & Exploitation, ASI10:2026 - Rogue Agents).** Continuous measurement of agent tool usage and goal alignment is the detection layer for unsafe tool composition and gradual goal drift toward rogue behavior.

**Risk Driven Assessment (ASI01:2026 - Agent Goal Hijack, ASI03:2026 - Agent Identity & Privilege Abuse).** Risk-driven triage by blast radius decides which agents (those with the most privilege and the widest goal scope) receive the deepest adversarial testing for hijack and privilege abuse.

**Behavioral Impact (ASI09:2026 - Human-Agent Trust Exploitation, ASI10:2026 - Rogue Agents).** Measuring whether people critically evaluate agent recommendations, via adversarial simulations, quantifies real resistance to trust exploitation rather than assumed vigilance.

**Behavioral Impact Assessment (ASI06:2026 - Memory & Context Poisoning, ASI10:2026 - Rogue Agents).** Repeated behavioral assessment over time detects gradual goal drift and the downstream effects of memory poisoning that a point-in-time check would miss.

**Relevant Tailored Training (ASI01:2026 - Agent Goal Hijack, ASI09:2026 - Human-Agent Trust Exploitation).** Role-specific training on prompt and instruction injection and on agent over-reliance equips the people who build and supervise agents to recognize hijack attempts and resist trust exploitation.

**Effective Learning Methods (ASI02:2026 - Tool Misuse & Exploitation, ASI09:2026 - Human-Agent Trust Exploitation).** Hands-on, scenario-based methods (live adversarial exercises against real agents) teach recognition of tool misuse and misleading agent explanations far better than static content.

**Accessible Inclusive Training (ASI09:2026 - Human-Agent Trust Exploitation).** Making agent-literacy training understandable to all personnel, not just builders, broadens the base of users who can spot automation bias and unwarranted agent confidence.

**Flexible Effective Delivery (ASI04:2026 - Agentic Supply Chain Compromise, ASI07:2026 - Insecure Inter-Agent Communication).** Flexible, rapidly updatable delivery keeps guidance current with fast-moving agent threats such as compromised tool registries and spoofed inter-agent messages.

**Integrated Training Lifecycle (ASI03:2026 - Agent Identity & Privilege Abuse, ASI10:2026 - Rogue Agents).** Embedding agent identity hygiene and autonomy-boundary expectations from onboarding onward builds durable habits that limit privilege abuse and runaway autonomy across the agent lifecycle.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.