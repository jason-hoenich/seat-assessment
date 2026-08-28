# MITRE ATT&CK Framework

Mapping of SEAT outcomes to MITRE ATT&CK tactics and techniques for adversary behavior analysis and defense planning.

**Version:** v14.1  
**Adapter last updated:** 2025-01-27  
**Official reference:** https://attack.mitre.org/  
**Adapter id:** `mitre-attack`

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
| Strategic Alignment | `strategic-alignment` | TA0043 - Reconnaissance, TA0042 - Resource Development | Expected | Assessment Report, Policy Document | Annual | 4 | Yes |
| Governance Documentation | `governance-documentation` | TA0040 - Impact, TA0010 - Exfiltration | Required | Policy Document, Other | Annual | 3 | Yes |
| Executive Support | `executive-support` | TA0001 - Initial Access, TA0003 - Persistence | Required | Board Minutes, Policy Document | Annual | 5 | Yes |
| Continuous Improvement | `continuous-improvement` | TA0011 - Command and Control, TA0009 - Collection | Expected | Assessment Report, Incident Report | Continuous | 4 | Yes |
| Targeted Communication | `targeted-communication` | T1566 - Phishing, T1204 - User Execution | Required | Communication Artifact, Training Record, Curriculum Document | Continuous | 5 | Yes |
| Cultural Relevance | `cultural-relevance` | T1534 - Internal Spearphishing, T1192 - Spearphishing Link | Expected | Communication Artifact, Feedback Survey | Continuous | 3 | Yes |
| Active Participation | `active-participation` | T1078 - Valid Accounts, T1110 - Brute Force | Required | Incident Report, Feedback Survey | Continuous | 4 | Yes |
| Feedback Responsiveness | `feedback-responsiveness` | T1190 - Exploit Public-Facing Application, T1133 - External Remote Services | Expected | Feedback Survey, Incident Report | As Needed | 3 | Yes |
| Performance Measurement | `performance-measurement` | T1059 - Command and Scripting Interpreter, T1105 - Ingress Tool Transfer | Required | Metric Report, Assessment Report | Quarterly | 4 | Yes |
| Risk Driven Assessment | `risk-driven-assessment` | T1021 - Remote Services, T1055 - Process Injection | Required | Assessment Report, Policy Document, Curriculum Document | Semi-Annual | 5 | Yes |
| Behavioral Impact | `behavioral-impact` | T1036 - Masquerading, T1027 - Obfuscated Files or Information | Expected | Simulation Results, Incident Report | Quarterly | 4 | **Not assessed** |
| Behavioral Impact Assessment | `behavioral-impact-assessment` | T1547 - Boot or Logon Autostart Execution, T1053 - Scheduled Task/Job | Expected | Simulation Results, Incident Report | Quarterly | 3 | **Not assessed** |
| Relevant Tailored Training | `relevant-tailored-training` | T1566.001 - Spearphishing Attachment, T1566.002 - Spearphishing Link | Required | Curriculum Document, Training Record | Annual | 5 | Yes |
| Effective Learning Methods | `effective-learning-methods` | T1598 - Phishing for Information, T1593 - Search Open Websites/Domains | Expected | Training Record, Simulation Results, Feedback Survey | As Needed | 4 | Yes |
| Accessible Inclusive Training | `accessible-inclusive-training` | T1589 - Gather Victim Identity Information, T1591 - Gather Victim Org Information | Expected | Communication Artifact | Continuous | 3 | Yes |
| Flexible Effective Delivery | `flexible-effective-delivery` | T1195 - Supply Chain Compromise, T1199 - Trusted Relationship | Expected | Training Record | As Needed | 4 | Yes |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | T1200 - Hardware Additions, T1091 - Replication Through Removable Media | Expected | Training Record | Onboarding | 3 | Yes |

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