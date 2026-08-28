# MITRE ATT&CK Framework

Mapping of SEAT outcomes to MITRE ATT&CK tactics and techniques for adversary behavior analysis and defense planning.

**Version:** v14.1  
**Adapter last updated:** 2025-01-27  
**Official reference:** https://attack.mitre.org/  
**Adapter id:** `mitre-attack`

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
| Strategic Alignment | `strategic-alignment` | TA0043 - Reconnaissance, TA0042 - Resource Development | Expected | Assessment Report, Policy Document | Annual | 4 |
| Governance Documentation | `governance-documentation` | TA0040 - Impact, TA0010 - Exfiltration | Required | Policy Document, Other | Annual | 3 |
| Executive Support | `executive-support` | TA0001 - Initial Access, TA0003 - Persistence | Required | Board Minutes, Policy Document | Annual | 5 |
| Continuous Improvement | `continuous-improvement` | TA0011 - Command and Control, TA0009 - Collection | Expected | Assessment Report, Incident Report | Continuous | 4 |
| Targeted Communication | `targeted-communication` | T1566 - Phishing, T1204 - User Execution | Required | Communication Artifact, Training Record, Curriculum Document | Continuous | 5 |
| Cultural Relevance | `cultural-relevance` | T1534 - Internal Spearphishing, T1192 - Spearphishing Link | Expected | Communication Artifact, Feedback Survey | Continuous | 3 |
| Active Participation | `active-participation` | T1078 - Valid Accounts, T1110 - Brute Force | Required | Incident Report, Feedback Survey | Continuous | 4 |
| Feedback Responsiveness | `feedback-responsiveness` | T1190 - Exploit Public-Facing Application, T1133 - External Remote Services | Expected | Feedback Survey, Incident Report | As Needed | 3 |
| Performance Measurement | `performance-measurement` | T1059 - Command and Scripting Interpreter, T1105 - Ingress Tool Transfer | Required | Metric Report, Assessment Report | Quarterly | 4 |
| Risk Driven Assessment | `risk-driven-assessment` | T1021 - Remote Services, T1055 - Process Injection | Required | Assessment Report, Policy Document, Curriculum Document | Semi-Annual | 5 |
| Behavioral Impact | `behavioral-impact` | T1036 - Masquerading, T1027 - Obfuscated Files or Information | Expected | Simulation Results, Incident Report | Quarterly | 4 |
| Behavioral Impact Assessment | `behavioral-impact-assessment` | T1547 - Boot or Logon Autostart Execution, T1053 - Scheduled Task/Job | Expected | Simulation Results, Incident Report | Quarterly | 3 |
| Relevant Tailored Training | `relevant-tailored-training` | T1566.001 - Spearphishing Attachment, T1566.002 - Spearphishing Link | Required | Curriculum Document, Training Record | Annual | 5 |
| Effective Learning Methods | `effective-learning-methods` | T1598 - Phishing for Information, T1593 - Search Open Websites/Domains | Expected | Training Record, Simulation Results, Feedback Survey | As Needed | 4 |
| Accessible Inclusive Training | `accessible-inclusive-training` | T1589 - Gather Victim Identity Information, T1591 - Gather Victim Org Information | Expected | Communication Artifact | Continuous | 3 |
| Flexible Effective Delivery | `flexible-effective-delivery` | T1195 - Supply Chain Compromise, T1199 - Trusted Relationship | Expected | Training Record | As Needed | 4 |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | T1200 - Hardware Additions, T1091 - Replication Through Removable Media | Expected | Training Record | Onboarding | 3 |

## Mapping notes

**Strategic Alignment (TA0043 - Reconnaissance, TA0042 - Resource Development).** Strategic alignment helps defend against reconnaissance and resource development phases by ensuring awareness programs address threat actor methodologies and organizational attack surface.

**Governance Documentation (TA0040 - Impact, TA0010 - Exfiltration).** Comprehensive documentation supports incident response and helps prevent impact and exfiltration by establishing clear procedures and responsibilities.

**Executive Support (TA0001 - Initial Access, TA0003 - Persistence).** Executive support is crucial for defending against initial access and persistence tactics, as leadership commitment drives consistent security practices across the organization.

**Continuous Improvement (TA0011 - Command and Control, TA0009 - Collection).** Continuous improvement helps adapt defenses against evolving command and control and collection techniques by incorporating threat intelligence and lessons learned.

**Targeted Communication (T1566 - Phishing, T1204 - User Execution).** Targeted communication directly counters phishing and user execution techniques by educating users about specific threats relevant to their roles and responsibilities.

**Cultural Relevance (T1534 - Internal Spearphishing, T1192 - Spearphishing Link).** Cultural relevance helps defend against targeted spearphishing attacks by ensuring security messages resonate with diverse workforce segments and cultural contexts.

**Active Participation (T1078 - Valid Accounts, T1110 - Brute Force).** Active participation helps detect and prevent valid account abuse and brute force attacks through user reporting of suspicious activities and adherence to security practices.

**Feedback Responsiveness (T1190 - Exploit Public-Facing Application, T1133 - External Remote Services).** Responsive feedback mechanisms help identify and address vulnerabilities in public-facing applications and remote services through user observations and reports.

**Performance Measurement (T1059 - Command and Scripting Interpreter, T1105 - Ingress Tool Transfer).** Performance measurement helps detect command and scripting interpreter abuse and ingress tool transfer by tracking user behavior patterns and security awareness effectiveness.

**Risk Driven Assessment (T1021 - Remote Services, T1055 - Process Injection).** Risk-driven assessments inform awareness priorities about remote services abuse and process injection techniques based on organizational threat landscape and attack patterns.

**Behavioral Impact (T1036 - Masquerading, T1027 - Obfuscated Files or Information).** Behavioral impact assessment measures user ability to identify masquerading and obfuscated threats through simulations and real-world incident response.

**Behavioral Impact Assessment (T1547 - Boot or Logon Autostart Execution, T1053 - Scheduled Task/Job).** Assessment of behavioral changes helps detect persistence mechanisms like autostart execution and scheduled tasks through improved user awareness and reporting.

**Relevant Tailored Training (T1566.001 - Spearphishing Attachment, T1566.002 - Spearphishing Link).** Tailored training directly addresses spearphishing attachment and link techniques by providing role-specific scenarios and threat examples relevant to user responsibilities.

**Effective Learning Methods (T1598 - Phishing for Information, T1593 - Search Open Websites/Domains).** Effective learning methods help users recognize phishing for information and open source intelligence gathering attempts through interactive and engaging training approaches.

**Accessible Inclusive Training (T1589 - Gather Victim Identity Information, T1591 - Gather Victim Org Information).** Accessible training ensures all personnel understand how attackers gather victim identity and organizational information, promoting consistent security practices across diverse workforce.

**Flexible Effective Delivery (T1195 - Supply Chain Compromise, T1199 - Trusted Relationship).** Flexible delivery methods help address complex threats like supply chain compromise and trusted relationship abuse through varied training formats and timely updates.

**Integrated Training Lifecycle (T1200 - Hardware Additions, T1091 - Replication Through Removable Media).** Integrated training lifecycle ensures consistent awareness of physical security threats like hardware additions and removable media attacks from onboarding through career development.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.