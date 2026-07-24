# MITRE ATT&CK Framework

**Version:** v14.1
**Last Updated:** 2025-01-27
**Official Reference:** https://attack.mitre.org/

Mapping of SEAT outcomes to MITRE ATT&CK tactics and techniques for adversary behavior analysis and defense planning.

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
| strategic-alignment | TA0043 - Reconnaissance, TA0042 - Resource Development | Expected | Assessment Report, Policy Document | 4 | Strategic alignment helps defend against reconnaissance and resource development phases by ensuring awareness programs address threat actor methodologies and organizational attack surface. Cadence: Annual. |
| governance-documentation | TA0040 - Impact, TA0010 - Exfiltration | Required | Policy Document | 3 | Comprehensive documentation supports incident response and helps prevent impact and exfiltration by establishing clear procedures and responsibilities. Cadence: Annual. |
| executive-support | TA0001 - Initial Access, TA0003 - Persistence | Required | Board Minutes, Policy Document | 5 | Executive support is crucial for defending against initial access and persistence tactics, as leadership commitment drives consistent security practices across the organization. Cadence: Annual. |
| continuous-improvement | TA0011 - Command and Control, TA0009 - Collection | Expected | Assessment Report, Incident Report | 4 | Continuous improvement helps adapt defenses against evolving command and control and collection techniques by incorporating threat intelligence and lessons learned. Cadence: Continuous. |
| targeted-communication | T1566 - Phishing, T1204 - User Execution | Required | Communication Artifact, Training Record, Curriculum Document | 5 | Targeted communication directly counters phishing and user execution techniques by educating users about specific threats relevant to their roles and responsibilities. Cadence: Continuous. |
| cultural-relevance | T1534 - Internal Spearphishing, T1192 - Spearphishing Link | Expected | Communication Artifact, Feedback Survey | 3 | Cultural relevance helps defend against targeted spearphishing attacks by ensuring security messages resonate with diverse workforce segments and cultural contexts. Cadence: Continuous. |
| active-participation | T1078 - Valid Accounts, T1110 - Brute Force | Required | Incident Report, Feedback Survey | 4 | Active participation helps detect and prevent valid account abuse and brute force attacks through user reporting of suspicious activities and adherence to security practices. Cadence: Continuous. |
| feedback-responsiveness | T1190 - Exploit Public-Facing Application, T1133 - External Remote Services | Expected | Feedback Survey, Incident Report | 3 | Responsive feedback mechanisms help identify and address vulnerabilities in public-facing applications and remote services through user observations and reports. Cadence: As Needed. |
| performance-measurement | T1059 - Command and Scripting Interpreter, T1105 - Ingress Tool Transfer | Required | Metric Report, Assessment Report | 4 | Performance measurement helps detect command and scripting interpreter abuse and ingress tool transfer by tracking user behavior patterns and security awareness effectiveness. Cadence: Quarterly. |
| risk-driven-assessment | T1021 - Remote Services, T1055 - Process Injection | Required | Assessment Report, Policy Document, Curriculum Document | 5 | Risk-driven assessments inform awareness priorities about remote services abuse and process injection techniques based on organizational threat landscape and attack patterns. Cadence: Semi-Annual. |
| behavioral-impact | T1036 - Masquerading, T1027 - Obfuscated Files or Information | Expected | Simulation Results, Incident Report | 4 | Behavioral impact assessment measures user ability to identify masquerading and obfuscated threats through simulations and real-world incident response. Cadence: Quarterly. |
| behavioral-impact-assessment | T1547 - Boot or Logon Autostart Execution, T1053 - Scheduled Task/Job | Expected | Simulation Results, Incident Report | 3 | Assessment of behavioral changes helps detect persistence mechanisms like autostart execution and scheduled tasks through improved user awareness and reporting. Cadence: Quarterly. |
| relevant-tailored-training | T1566.001 - Spearphishing Attachment, T1566.002 - Spearphishing Link | Required | Curriculum Document, Training Record | 5 | Tailored training directly addresses spearphishing attachment and link techniques by providing role-specific scenarios and threat examples relevant to user responsibilities. Cadence: Annual. |
| effective-learning-methods | T1598 - Phishing for Information, T1593 - Search Open Websites/Domains | Expected | Training Record, Simulation Results, Feedback Survey | 4 | Effective learning methods help users recognize phishing for information and open source intelligence gathering attempts through interactive and engaging training approaches. Cadence: As Needed. |
| accessible-inclusive-training | T1589 - Gather Victim Identity Information, T1591 - Gather Victim Org Information | Expected | Communication Artifact | 3 | Accessible training ensures all personnel understand how attackers gather victim identity and organizational information, promoting consistent security practices across diverse workforce. Cadence: Continuous. |
| flexible-effective-delivery | T1195 - Supply Chain Compromise, T1199 - Trusted Relationship | Expected | Training Record | 4 | Flexible delivery methods help address complex threats like supply chain compromise and trusted relationship abuse through varied training formats and timely updates. Cadence: As Needed. |
| integrated-training-lifecycle | T1200 - Hardware Additions, T1091 - Replication Through Removable Media | Expected | Training Record | 3 | Integrated training lifecycle ensures consistent awareness of physical security threats like hardware additions and removable media attacks from onboarding through career development. Cadence: Onboarding. |
