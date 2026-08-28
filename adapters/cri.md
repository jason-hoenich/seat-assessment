# Cyber Resilience Initiative (CRI)

Comprehensive mapping of SEAT outcomes to CRI Profile v2.1 requirements for financial institutions focusing on operational resilience and cyber risk management.

**Version:** 2.1  
**Adapter last updated:** 2025-01-27  
**Official reference:** https://www.cisa.gov/cross-sector-cybersecurity-performance-goals  
**Adapter id:** `cri`

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
| Strategic Alignment | `strategic-alignment` | GV.OC-01.01 | Required | Policy Document, Board Minutes, Assessment Report | Annual | 5 |
| Cultural Relevance | `cultural-relevance` | GV.OC-02.01 | Required | Policy Document, Assessment Report, Training Record, Feedback Survey | Continuous | 4 |
| Strategic Alignment | `strategic-alignment` | GV.OC-02.02 | Required | Policy Document, Board Minutes, Assessment Report | Annual | 5 |
| Strategic Alignment | `strategic-alignment` | GV.OC-02.03 | Required | Policy Document, Assessment Report | Annual | 5 |
| Governance Documentation | `governance-documentation` | GV.OC-03.01 | Required | Policy Document, Board Minutes, Assessment Report | Annual | 5 |
| Governance Documentation | `governance-documentation` | GV.OC-03.02 | Required | Policy Document | Annual | 4 |
| Risk Driven Assessment | `risk-driven-assessment` | GV.OC-04.01 | Required | Assessment Report | Continuous | 4 |
| Risk Driven Assessment | `risk-driven-assessment` | GV.OC-04.02 | Required | Policy Document | Annual | 4 |
| Continuous Improvement | `continuous-improvement` | GV.OC-04.03 | Required | Policy Document, Assessment Report | Continuous | 4 |
| Risk Driven Assessment | `risk-driven-assessment` | GV.OC-04.04 | Required | Policy Document, Assessment Report | Continuous | 5 |
| Risk Driven Assessment | `risk-driven-assessment` | GV.OC-05.01 | Required | Assessment Report | Continuous | 4 |
| Risk Driven Assessment | `risk-driven-assessment` | GV.OC-05.02 | Required | Assessment Report | Continuous | 5 |
| Strategic Alignment | `strategic-alignment` | GV.OC-05.03 | Required | Policy Document, Assessment Report | Annual | 5 |
| Governance Documentation | `governance-documentation` | GV.OC-05.04 | Required | Policy Document | Annual | 4 |
| Strategic Alignment | `strategic-alignment` | GV.RM-01.01 | Required | Policy Document, Board Minutes, Assessment Report | Annual | 5 |
| Governance Documentation | `governance-documentation` | GV.RM-01.02 | Required | Policy Document, Assessment Report | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.RM-01.03 | Required | Policy Document, Assessment Report | Annual | 4 |
| Performance Measurement | `performance-measurement` | GV.RM-01.04 | Required | Assessment Report, Metric Report | Quarterly | 4 |
| Strategic Alignment | `strategic-alignment` | GV.RM-01.05 | Required | Policy Document | Annual | 5 |
| Executive Support | `executive-support` | GV.RM-02.01 | Required | Policy Document, Board Minutes | Annual | 5 |
| Governance Documentation | `governance-documentation` | GV.RM-02.02 | Required | Policy Document, Assessment Report | Annual | 4 |
| Strategic Alignment | `strategic-alignment` | GV.RM-02.03 | Required | Policy Document | Annual | 5 |
| Strategic Alignment | `strategic-alignment` | GV.RM-03.01 | Required | Policy Document, Assessment Report | Annual | 5 |
| Strategic Alignment | `strategic-alignment` | GV.RM-03.02 | Required | Policy Document, Assessment Report | Annual | 5 |
| Risk Driven Assessment | `risk-driven-assessment` | GV.RM-03.03 | Required | Policy Document, Assessment Report | Annual | 5 |
| Cultural Relevance | `cultural-relevance` | GV.RM-03.04 | Required | Policy Document, Training Record, Communication Artifact | Continuous | 4 |
| Executive Support | `executive-support` | GV.RM-04.01 | Required | Policy Document, Board Minutes | Annual | 5 |
| Risk Driven Assessment | `risk-driven-assessment` | GV.RM-05.01 | Required | Policy Document, Assessment Report | Continuous | 4 |
| Governance Documentation | `governance-documentation` | GV.RM-05.02 | Required | Policy Document | Annual | 4 |
| Continuous Improvement | `continuous-improvement` | GV.RM-06.01 | Required | Policy Document, Assessment Report | Annual | 4 |
| Strategic Alignment | `strategic-alignment` | GV.RM-07.01 | Required | Assessment Report, Policy Document | Annual | 5 |
| Risk Driven Assessment | `risk-driven-assessment` | GV.RM-08.01 | Required | Assessment Report, Policy Document | Continuous | 4 |
| Governance Documentation | `governance-documentation` | GV.RM-08.02 | Required | Policy Document | Continuous | 4 |
| Governance Documentation | `governance-documentation` | GV.RM-08.03 | Required | Policy Document | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.RM-08.04 | Required | Policy Document | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.RM-08.05 | Required | Policy Document | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.RM-08.06 | Required | Policy Document | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.RM-08.07 | Required | Policy Document | Annual | 4 |
| Strategic Alignment | `strategic-alignment` | GV.RM-09.01 | Required | Policy Document, Assessment Report | Annual | 5 |
| Continuous Improvement | `continuous-improvement` | GV.RM-09.02 | Required | Policy Document | Continuous | 4 |
| Executive Support | `executive-support` | GV.RR-01.01 | Required | Board Minutes, Policy Document | Annual | 5 |
| Executive Support | `executive-support` | GV.RR-01.02 | Required | Board Minutes, Policy Document | Annual | 5 |
| Executive Support | `executive-support` | GV.RR-01.03 | Required | Board Minutes, Policy Document | Annual | 5 |
| Executive Support | `executive-support` | GV.RR-01.04 | Required | Policy Document, Board Minutes | Annual | 5 |
| Executive Support | `executive-support` | GV.RR-01.05 | Required | Policy Document | Annual | 5 |
| Governance Documentation | `governance-documentation` | GV.RR-02.01 | Required | Policy Document, Training Record | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.RR-02.02 | Required | Policy Document | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.RR-02.03 | Required | Policy Document | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.RR-02.04 | Required | Policy Document | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.RR-02.05 | Required | Policy Document, Training Record | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.RR-02.06 | Required | Policy Document | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.RR-02.07 | Required | Policy Document | Annual | 4 |
| Executive Support | `executive-support` | GV.RR-03.01 | Required | Policy Document | Annual | 5 |
| Executive Support | `executive-support` | GV.RR-03.02 | Required | Policy Document | Annual | 5 |
| Executive Support | `executive-support` | GV.RR-03.03 | Required | Policy Document | Annual | 5 |
| Governance Documentation | `governance-documentation` | GV.RR-04.01 | Required | Policy Document | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.RR-04.02 | Required | Policy Document | Annual | 4 |
| Risk Driven Assessment | `risk-driven-assessment` | GV.RR-04.03 | Required | Policy Document, Training Record | Continuous | 4 |
| Governance Documentation | `governance-documentation` | GV.PO-01.01 | Required | Policy Document, Board Minutes | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.PO-01.02 | Required | Board Minutes | Annual | 4 |
| Cultural Relevance | `cultural-relevance` | GV.PO-01.03 | Required | Policy Document, Training Record | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.PO-01.04 | Required | Policy Document, Training Record | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.PO-01.05 | Required | Policy Document | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.PO-01.06 | Required | Policy Document | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.PO-01.07 | Required | Policy Document, Board Minutes | Annual | 4 |
| Governance Documentation | `governance-documentation` | GV.PO-01.08 | Required | Policy Document, Board Minutes | Annual | 4 |
| Continuous Improvement | `continuous-improvement` | GV.PO-02.01 | Required | Policy Document, Board Minutes | Annual | 4 |
| Executive Support | `executive-support` | GV.OV-01.01 | Required | Board Minutes | Annual | 5 |
| Executive Support | `executive-support` | GV.OV-01.02 | Required | Board Minutes | Quarterly | 5 |
| Executive Support | `executive-support` | GV.OV-01.03 | Required | Board Minutes | Quarterly | 5 |
| Risk Driven Assessment | `risk-driven-assessment` | GV.OV-02.01 | Required | Policy Document, Assessment Report | Annual | 5 |
| Governance Documentation | `governance-documentation` | GV.OV-02.02 | Required | Policy Document | Annual | 4 |
| Performance Measurement | `performance-measurement` | GV.OV-03.01 | Required | Metric Report | Quarterly | 4 |
| Performance Measurement | `performance-measurement` | GV.OV-03.02 | Required | Metric Report | Quarterly | 4 |
| Relevant Tailored Training | `relevant-tailored-training` | PR.AT-01.01 | Required | Training Record, Policy Document | Continuous | 5 |
| Relevant Tailored Training | `relevant-tailored-training` | PR.AT-01.02 | Required | Curriculum Document, Training Record, Policy Document | Annual | 5 |
| Continuous Improvement | `continuous-improvement` | PR.AT-01.03 | Required | Training Record, Policy Document | Continuous | 4 |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | PR.AT-01.04 | Required | Training Record, Policy Document | As Needed | 4 |
| Effective Learning Methods | `effective-learning-methods` | PR.AT-02.01 | Required | Training Record, Policy Document | Continuous | 4 |
| Relevant Tailored Training | `relevant-tailored-training` | PR.AT-02.02 | Required | Training Record | Annual | 5 |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | PR.AT-02.03 | Required | Training Record, Policy Document | Continuous | 4 |
| Effective Learning Methods | `effective-learning-methods` | PR.AT-02.04 | Required | Training Record, Assessment Report | Continuous | 4 |
| Accessible Inclusive Training | `accessible-inclusive-training` | PR.AT-02.05 | Required | Training Record | Continuous | 3 |
| Targeted Communication | `targeted-communication` | PR.AT-02.06 | Required | Communication Artifact | Continuous | 4 |
| Executive Support | `executive-support` | PR.AT-02.07 | Required | Training Record, Board Minutes | Annual | 5 |
| Executive Support | `executive-support` | PR.AT-02.08 | Required | Board Minutes, Policy Document | Annual | 5 |
| Performance Measurement | `performance-measurement` | ID.IM-01.02 | Required | Metric Report, Assessment Report | Quarterly | 4 |
| Continuous Improvement | `continuous-improvement` | ID.IM-01.03 | Required | Assessment Report, Metric Report | Quarterly | 4 |
| Continuous Improvement | `continuous-improvement` | ID.IM-01.04 | Required | Assessment Report, Policy Document | Continuous | 4 |
| Risk Driven Assessment | `risk-driven-assessment` | ID.RA-01.01 | Required | Assessment Report, Policy Document | Annual | 5 |
| Performance Measurement | `performance-measurement` | ID.RA-06.01 | Required | Assessment Report, Metric Report | Annual | 4 |
| Active Participation | `active-participation` | RS.CO-02.01, RS.CO-02.02 | Required | Incident Report, Communication Artifact | Continuous | 4 |
| Behavioral Impact | `behavioral-impact` | DE.AE-02.01, DE.AE-04.01 | Required | Simulation Results, Incident Report | Quarterly | 4 |
| Feedback Responsiveness | `feedback-responsiveness` | ID.IM-03.01, ID.IM-03.02 | Expected | Assessment Report, Incident Report | Quarterly | 3 |

## Mapping notes

**Strategic Alignment (GV.OC-01.01).** Technology and cybersecurity strategies, architectures, and programs are formally governed to align with and support the organization's mission, objectives, priorities, tactical initiatives, and risk profile.

**Cultural Relevance (GV.OC-02.01).** The organization's obligation to its customers, employees, and stakeholders to maintain safety and soundness is reflected in risk management strategy and risk-aware culture.

**Strategic Alignment (GV.OC-02.02).** Technology and cybersecurity risk management strategies identify and communicate the organization's role within the financial services sector as a component of critical infrastructure.

**Strategic Alignment (GV.OC-02.03).** Technology and cybersecurity risk management strategies identify and communicate the organization's role as it relates to other critical infrastructure sectors outside of the financial services sector and the interdependency risks.

**Governance Documentation (GV.OC-03.01).** The organization's technology and cybersecurity strategy, framework, and policies align with legal, statutory, contractual, and regulatory obligations with unambiguously assigned compliance responsibilities.

**Governance Documentation (GV.OC-03.02).** The organization implements and maintains a documented policy or policies that address customer data privacy that is approved by a designated officer or the organization's appropriate governing body.

**Risk Driven Assessment (GV.OC-04.01).** The organization maintains an inventory of key internal assets, business functions, and external dependencies that includes mappings to other assets, business functions, and information flows.

**Risk Driven Assessment (GV.OC-04.02).** The organization documents the business processes that are critical for the delivery of services and the functioning of the organization, and the impacts to the business if those processes are degraded or not functioning.

**Continuous Improvement (GV.OC-04.03).** Resilience requirements to support the delivery of critical services are established for all operating states (e.g., under duress/attack, during recovery, and normal operations).

**Risk Driven Assessment (GV.OC-04.04).** The organization prioritizes the resilience design, planning, testing, and monitoring of systems and other key internal and external dependencies according to their criticality to the supported business functions, enterprise mission, and to the financial services sector.

**Risk Driven Assessment (GV.OC-05.01).** The organization identifies, assesses, and documents the key dependencies, interdependencies, and potential points of failure to support the delivery of critical services.

**Risk Driven Assessment (GV.OC-05.02).** The organization has prioritized its external dependencies according to their criticality to the supported enterprise mission, business functions, and to the financial services sector.

**Strategic Alignment (GV.OC-05.03).** The organization defines objectives (e.g., Recovery Time Objective, Maximum Tolerable Downtime, Impact Tolerance) for the resumption of critical operations in alignment with business imperatives, stakeholder obligations, and critical infrastructure dependencies.

**Governance Documentation (GV.OC-05.04).** Recovery point objectives to support data integrity are consistent with the organization's recovery time objectives, information flow dependencies between systems, and business obligations.

**Strategic Alignment (GV.RM-01.01).** Technology and cybersecurity risk management strategies and frameworks are approved by the governing authority and incorporated into the overall business strategy and enterprise risk management framework.

**Governance Documentation (GV.RM-01.02).** Technology and cybersecurity risk management strategies and frameworks are informed by applicable international, national, and financial services industry standards and guidelines.

**Governance Documentation (GV.RM-01.03).** The organization has established, and maintains, technology and cybersecurity programs designed to protect the confidentiality, integrity and availability of its information and operational systems, commensurate with the organization's risk appetite and business needs.

**Performance Measurement (GV.RM-01.04).** Technology and cybersecurity risk management programs incorporate risk identification, measurement, monitoring, and reporting.

**Strategic Alignment (GV.RM-01.05).** The organization's technology, cybersecurity, resilience, and third-party risk management programs, policies, resources, and priorities are aligned and mutually supporting.

**Executive Support (GV.RM-02.01).** The governing authority endorses and regularly reviews technology and cybersecurity risk appetite and is regularly informed about the status of, and material changes to, the organization's inherent risk profile.

**Governance Documentation (GV.RM-02.02).** The organization has established statements of technology and cybersecurity risk tolerance consistent with its risk appetite, and has integrated them into technology, cybersecurity, operational, and enterprise risk management practices.

**Strategic Alignment (GV.RM-02.03).** Determination of the organization's risk appetite and tolerance includes consideration of the organization's stakeholder obligations, role in critical infrastructure, and sector-specific risk analysis.

**Strategic Alignment (GV.RM-03.01).** Technology and cybersecurity risk management frameworks and programs are integrated into the enterprise risk management framework.

**Strategic Alignment (GV.RM-03.02).** The organization's business continuity and resilience strategy and program align with and support the overall enterprise risk management framework.

**Risk Driven Assessment (GV.RM-03.03).** Technology and cybersecurity risk management and risk assessment processes are consistent with the organization's enterprise risk management policies, procedures, and methodologies and include criteria for the evaluation and categorization of enterprise-specific risks and threats.

**Cultural Relevance (GV.RM-03.04).** Technology and cybersecurity risk management considerations are integrated into daily operations, cultural norms, management discussions, and management decision-making.

**Executive Support (GV.RM-04.01).** The governing authority and senior management provide guidance, direction, and credible challenge in the design and implementation of risk management strategies, assessment of identified risks against risk appetite and risk tolerance, and in the selection of risk treatment approaches.

**Risk Driven Assessment (GV.RM-05.01).** The organization has a process for monitoring its technology, cybersecurity, and third-party risks, including escalating those risks that exceed risk appetite to management and identifying risks with the potential to impact multiple operating units.

**Governance Documentation (GV.RM-05.02).** The organization establishes minimum requirements for its third-parties that include how the organizations will communicate and coordinate in times of emergency.

**Continuous Improvement (GV.RM-06.01).** Technology and cybersecurity risk management and risk assessment processes and methodologies are documented and regularly reviewed and updated to address changes in the risk profile and risk appetite, the evolving threat environment, and new technologies, products, services, and interdependencies.

**Strategic Alignment (GV.RM-07.01).** The organization has mechanisms in place to ensure that strategies, initiatives, opportunities, and emerging technologies are evaluated both in terms of risks and uncertainties that are potentially detrimental to the organization, as well as potentially advantageous to the organization (i.e., positive risks).

**Risk Driven Assessment (GV.RM-08.01).** Technology and cybersecurity risk management frameworks are applied to, and are adapted as needed by, the organization's innovations in technology use and adoption of emerging technologies.

**Governance Documentation (GV.RM-08.02).** Technology and cybersecurity risk management frameworks are applied to all technology projects and procurements to ensure that security requirements are addressed consistently from project onset.

**Governance Documentation (GV.RM-08.03).** The organization defines, maintains, and uses technical security standards, architectures, processes or practices to ensure the security of its applications and infrastructure.

**Governance Documentation (GV.RM-08.04).** The organization integrates the use of technology architecture in its governance processes to support consistent approaches to security and technology design, integration of third party services, consideration and adoption of new technologies, and investment and procurement decisioning.

**Governance Documentation (GV.RM-08.05).** The technology architecture and associated management processes should be comprehensive and designed to achieve security and resilience commensurate with business needs.

**Governance Documentation (GV.RM-08.06).** Technology programs and projects are formally governed and stakeholder engagement is managed to facilitate effective communication, awareness, credible challenge, and decision-making.

**Governance Documentation (GV.RM-08.07).** Technology projects follow an established project management methodology to manage delivery and delivery risks, produce consistent quality, and achieve business objectives and value.

**Strategic Alignment (GV.RM-09.01).** The organization has an enterprise-wide resilience strategy and program, including architecture, cyber resilience, business continuity, disaster recovery, and incident response, which support its mission, stakeholder obligations, critical infrastructure role, and risk appetite.

**Continuous Improvement (GV.RM-09.02).** The resilience program ensures that the organization can continue operating critical business functions and deliver services to stakeholders, to include critical infrastructure partners, during adverse incidents and cyber attacks.

**Executive Support (GV.RR-01.01).** The governing authority oversees and holds senior management accountable for implementing the organization's technology and cybersecurity risk management strategies and frameworks.

**Executive Support (GV.RR-01.02).** The governing authority regularly reviews, oversees, and holds senior management accountable for implementing the organization's third-party risk management strategy and program.

**Executive Support (GV.RR-01.03).** The governing authority regularly reviews, oversees, and holds senior management accountable for implementing the organization's resilience strategy and program.

**Executive Support (GV.RR-01.04).** The organization has designated a qualified Cybersecurity Officer (e.g., CISO) who is responsible and accountable for developing a cybersecurity strategy, overseeing and implementing its cybersecurity program, and enforcing its cybersecurity policy.

**Executive Support (GV.RR-01.05).** The organization designates a qualified Technology Officer (e.g., CIO or CTO) who is responsible and accountable for developing technology strategy, overseeing and implementing its technology program, and enforcing its technology policy.

**Governance Documentation (GV.RR-02.01).** The roles, responsibilities, qualifications, and skill requirements for personnel that implement, manage, and oversee the technology, cybersecurity, and resilience programs are defined, aligned, coordinated, and holistically managed.

**Governance Documentation (GV.RR-02.02).** The organization has established and assigned roles and responsibilities for systematic cybersecurity threat identification, monitoring, detection, and event reporting processes.

**Governance Documentation (GV.RR-02.03).** Resilience program roles and responsibilities are assigned to management across the organization to ensure risk assessment, planning, testing, and execution coverage for all critical business functions.

**Governance Documentation (GV.RR-02.04).** Roles and responsibilities for the Third-Party Risk Management Program and for each third-party engagement are defined and assigned.

**Governance Documentation (GV.RR-02.05).** Personnel who fulfill the organization's physical security and cybersecurity objectives understand their roles and responsibilities.

**Governance Documentation (GV.RR-02.06).** Roles and responsibilities for the inventory, ownership, and custodianship of applications, data and other technology assets are established and maintained.

**Governance Documentation (GV.RR-02.07).** Technology and cybersecurity risk management frameworks provide for segregation of duties between policy development, implementation, and oversight.

**Executive Support (GV.RR-03.01).** The organization's budgeting and resourcing processes identify, prioritize, and address resource needs to manage identified technology and cybersecurity risks.

**Executive Support (GV.RR-03.02).** The organization regularly assesses its skill and resource level requirements against its current personnel complement to determine gaps in resource need.

**Executive Support (GV.RR-03.03).** The organization provides adequate resources, appropriate authority, and access to the governing authority for the designated Cybersecurity Officer (e.g., CISO).

**Governance Documentation (GV.RR-04.01).** The organization conducts background/screening checks on all personnel upon hire/retention, at regular intervals throughout employment, and upon a change in role commensurate with their access to critical data and systems.

**Governance Documentation (GV.RR-04.02).** The organization establishes processes and controls to mitigate cyber risks related to employment termination, as permitted by law, to include the return or disposition of all organizational assets.

**Risk Driven Assessment (GV.RR-04.03).** The organization integrates insider threat considerations into its human resource, risk management, and control programs to address the potential for malicious or unintentional harm by trusted employees or third parties.

**Governance Documentation (GV.PO-01.01).** Technology and cybersecurity policies are documented, maintained and approved by the governing authority or a designated executive.

**Governance Documentation (GV.PO-01.02).** The accountable governing body, and applicable cybersecurity program and policies, for any given organizational unit, affiliate, or merged entity are clearly established, applied, and communicated.

**Cultural Relevance (GV.PO-01.03).** The organization's incentive programs are consistent with cyber risk management objectives, and technology and cybersecurity policies integrate with an employee accountability policy.

**Governance Documentation (GV.PO-01.04).** All personnel consent to policies addressing acceptable technology use, social media use, personal device use, confidentiality, and/or other security-related policies and agreements.

**Governance Documentation (GV.PO-01.05).** Technology and cybersecurity processes, procedures, and controls are established in alignment with cybersecurity policy.

**Governance Documentation (GV.PO-01.06).** Physical and environmental security policies are implemented and managed.

**Governance Documentation (GV.PO-01.07).** The organization maintains documented business continuity and resilience program policies and procedures approved by the governing authority.

**Governance Documentation (GV.PO-01.08).** The organization maintains documented third-party risk management program policies and procedures approved by the governing authority.

**Continuous Improvement (GV.PO-02.01).** The cybersecurity policy is regularly reviewed, revised, and communicated under the leadership of a designated Cybersecurity Officer to address changes in the risk profile and risk appetite, the evolving threat environment, and new technologies.

**Executive Support (GV.OV-01.01).** The governing authority regularly reviews and evaluates the organization's ability to manage its technology, cybersecurity, third-party, and resilience risks.

**Executive Support (GV.OV-01.02).** The designated Cybersecurity Officer periodically reports to the appropriate governing authority on the status of cybersecurity within the organization.

**Executive Support (GV.OV-01.03).** The designated Technology Officer regularly reports to the governing authority on the status of technology use and risks within the organization.

**Risk Driven Assessment (GV.OV-02.01).** The organization regularly assesses its inherent technology and cybersecurity risks and ensures that changes to the business and threat environment lead to updates to the organization's strategies, programs, risk appetite and risk tolerance.

**Governance Documentation (GV.OV-02.02).** The organization determines and articulates how it intends to maintain an acceptable level of residual technology and cybersecurity risk as set by the governing authority.

**Performance Measurement (GV.OV-03.01).** The organization develops, implements, and reports to management and the governing body key technology and cybersecurity risk and performance indicators and metrics.

**Performance Measurement (GV.OV-03.02).** Resilience program performance is measured and regularly reported to senior executives and the governing authority.

**Relevant Tailored Training (PR.AT-01.01).** All personnel receive cybersecurity awareness training upon hire and on a regular basis.

**Relevant Tailored Training (PR.AT-01.02).** Cybersecurity awareness training includes awareness of and competencies for data protection, personal data handling, compliance obligations, working with third parties, detecting cyber risks, and incident reporting.

**Continuous Improvement (PR.AT-01.03).** Cybersecurity awareness training is updated regularly to reflect risks and threats identified by the organization, security policies and standards, applicable laws and regulations, and changes in individual responsibilities.

**Integrated Training Lifecycle (PR.AT-01.04).** As new technology is deployed or undergoes change that requires changes in practices, all impacted personnel are trained on the new system and any accompanying technology and cybersecurity risks.

**Effective Learning Methods (PR.AT-02.01).** Mechanisms are in place to ensure that personnel working with cybersecurity and technology maintain current knowledge and skills related to changing threats, countermeasures, new tools, best practices, and job responsibilities.

**Relevant Tailored Training (PR.AT-02.02).** High-risk groups, such as those with elevated privileges or in sensitive business functions, receive cybersecurity situational awareness training for their roles and responsibilities.

**Integrated Training Lifecycle (PR.AT-02.03).** All personnel are made aware of and are trained for their role and operational steps in response and recovery plans.

**Effective Learning Methods (PR.AT-02.04).** The organization maintains and enhances the skills and knowledge of in-house staff performing incident management and forensic investigation activities.

**Accessible Inclusive Training (PR.AT-02.05).** All third party staff receive cybersecurity awareness and job training sufficient for them to perform their duties and maintain organizational security.

**Targeted Communication (PR.AT-02.06).** The organization has established and maintains a cybersecurity awareness program through which customers are kept aware of new threats and vulnerabilities, basic cybersecurity hygiene practices, and their role in cybersecurity.

**Executive Support (PR.AT-02.07).** The organization's governing body and senior management receive cybersecurity situational awareness training to evaluate and manage cyber risks, promote culture, and lead by example.

**Executive Support (PR.AT-02.08).** Where the governing authority does not have adequate cybersecurity expertise, they have direct access to the senior officer responsible for cybersecurity and independent sources of expertise.

**Performance Measurement (ID.IM-01.02).** The organization implements a regular process to collect, store, report, benchmark, and assess trends in actionable performance indicators and risk metrics.

**Continuous Improvement (ID.IM-01.03).** The organization establishes specific objectives, performance criteria, benchmarks, and tolerance limits to identify areas that have improved or are in need of improvement over time.

**Continuous Improvement (ID.IM-01.04).** Technology and cybersecurity programs include elements designed to assess, manage, and continually improve the quality of program delivery in addressing stakeholder requirements and risk reduction.

**Risk Driven Assessment (ID.RA-01.01).** The organization identifies, assesses, and documents risks and potential vulnerabilities associated with assets, to include workforce, data, technology, facilities, services, and connections.

**Performance Measurement (ID.RA-06.01).** Technology and cybersecurity risk management programs and risk assessment processes produce actionable recommendations that the organization uses to select, design, prioritize, implement, maintain, evaluate, and modify cybersecurity and technology controls.

**Active Participation (RS.CO-02.01, RS.CO-02.02).** Incident response program includes defined escalation protocols and notification procedures for impacted stakeholders including government bodies and supervisory agencies.

**Behavioral Impact (DE.AE-02.01, DE.AE-04.01).** The organization performs timely collection and analysis of event data and has documented processes to analyze and triage incidents to assess root cause, technical impact, and business impact.

**Feedback Responsiveness (ID.IM-03.01, ID.IM-03.02).** Formal processes improve protection controls and monitoring/detection processes by integrating recommendations, findings, and lessons learned from exercises, testing, audits, assessments, and incidents.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.