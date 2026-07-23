# SEAT Security Awareness Maturity Framework

**Version 1.0 | 2026**

**Published by HumanRisk**

---

## About This Document

The SEAT (Security Education Assessment Toolkit) Security Awareness Maturity Framework is a vendor-neutral, open methodology for evaluating the maturity of organizational security awareness programs. It provides a structured approach to assessing program effectiveness across four domains, with explicit mappings to major compliance and regulatory frameworks.

This framework is published under Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0). Organizations may freely use, reference, and build upon this framework for non-commercial purposes with attribution.

**Suggested citation:** HumanRisk. (2026). SEAT Security Awareness Maturity Framework, Version 1.0. Retrieved from https://humanrisk.com/framework

---

## Table of Contents

1. [Purpose and Scope](#1-purpose-and-scope)
2. [The Problem This Framework Solves](#2-the-problem-this-framework-solves)
3. [Key Definitions](#3-key-definitions)
4. [Framework Overview](#4-framework-overview)
5. [Maturity Model](#5-maturity-model)
6. [Assessment Domains](#6-assessment-domains)
7. [Domain 1: Strategy and Governance](#7-domain-1-strategy-and-governance)
8. [Domain 2: Engagement and Culture](#8-domain-2-engagement-and-culture)
9. [Domain 3: Assessment and Metrics](#9-domain-3-assessment-and-metrics)
10. [Domain 4: Training and Development](#10-domain-4-training-and-development)
11. [Scoring Methodology](#11-scoring-methodology)
12. [SEAT Outcomes Model](#12-seat-outcomes-model)
13. [Regulatory and Compliance Framework Mappings](#13-regulatory-and-compliance-framework-mappings)
14. [Evidence Requirements](#14-evidence-requirements)
15. [Assessment Process](#15-assessment-process)
16. [Using SEAT Ratings for Compliance](#16-using-seat-ratings-for-compliance)
17. [Framework Governance and Versioning](#17-framework-governance-and-versioning)
18. [Appendix A: Framework Mapping Reference](#appendix-a-framework-mapping-reference)
19. [Appendix B: Sample Assessment Report Structure](#appendix-b-sample-assessment-report-structure)
20. [Appendix C: Glossary](#appendix-c-glossary)

---

## 1. Purpose and Scope

### Purpose

This framework provides a standardized methodology for evaluating the maturity of security awareness programs within organizations of any size and industry. It enables:

- **Program owners** to objectively assess their current state and identify gaps
- **CISOs and security leaders** to benchmark program performance and justify investment
- **Auditors and assessors** to evaluate security awareness program controls against regulatory requirements
- **Boards and executives** to understand organizational human risk posture through a consistent rating system

### Scope

The SEAT framework evaluates the *program* that manages security awareness within an organization. It does not evaluate:

- Individual employee knowledge or behavior (that is the program's job)
- Specific vendor tools or platforms (the framework is vendor-neutral)
- Technical security controls (covered by other frameworks like NIST CSF broadly)

The framework assesses how well an organization designs, delivers, measures, and improves its security awareness program as a function of risk management.

### Intended Audience

- Security awareness program managers and owners
- Chief Information Security Officers (CISOs) and security leadership
- Governance, Risk, and Compliance (GRC) teams
- Internal and external auditors
- Consultants and managed security service providers (MSSPs)

---

## 2. The Problem This Framework Solves

Organizations invest significantly in security awareness training, phishing simulations, and related tools. Yet there is no widely adopted standard for evaluating whether these investments produce meaningful outcomes.

Current challenges:

- **No standard measurement.** Each vendor defines "good" differently, typically in terms that favor their own product.
- **Compliance checkbox mentality.** Many programs exist solely to satisfy audit requirements rather than reduce risk.
- **Fragmented guidance.** Regulatory frameworks (NIST, ISO, NIS2, DORA, CMMC) each address security awareness differently, with varying levels of specificity. Program owners must reconcile these independently.
- **Vendor lock-in as a proxy for quality.** Organizations often equate "having a tool" with "having a program," when tool deployment is only one component of program maturity.

The SEAT framework addresses these gaps by providing a unified, vendor-neutral maturity model that maps to all major regulatory frameworks and measures program effectiveness based on outcomes, not tool adoption.

---

## 3. Key Definitions

| Term | Definition |
|------|-----------|
| **Security Awareness Program** | The organized, ongoing effort to educate an organization's workforce about security threats, policies, and behaviors. Encompasses training, communications, simulations, measurement, and culture-building activities. |
| **Program Maturity** | The degree to which a security awareness program is formalized, measured, integrated with organizational risk management, and continuously improved. |
| **SEAT Assessment** | A structured evaluation of an organization's security awareness program using this framework's methodology, resulting in a maturity rating. |
| **SEAT Rating** | The overall maturity level (1-5) assigned to an organization's security awareness program following a SEAT Assessment. |
| **Domain** | One of four primary areas of program evaluation: Strategy and Governance, Engagement and Culture, Assessment and Metrics, Training and Development. |
| **Outcome** | A specific, measurable result that indicates program effectiveness within a domain. The framework defines 16 canonical outcomes. |
| **Assessor** | An individual qualified to conduct SEAT Assessments, either as a self-assessment by the program owner or as a facilitated assessment by a certified assessor. |

---

## 4. Framework Overview

The SEAT framework is structured as a maturity model with three layers:

```
Layer 1: Maturity Levels (1-5)
    What stage is the program at?

Layer 2: Assessment Domains (4 domains, 16 outcomes)
    What specific capabilities are being evaluated?

Layer 3: Compliance Mappings (10 frameworks)
    How does the maturity rating satisfy regulatory requirements?
```

### Design Principles

1. **Vendor-neutral.** The framework evaluates program design and effectiveness, not specific tools or platforms.
2. **Outcome-driven.** Maturity is measured by what the program achieves, not what it deploys.
3. **Mapping-first.** Every assessment outcome maps directly to one or more regulatory framework controls.
4. **Practitioner-informed.** The framework was developed with input from security awareness practitioners across multiple industries and organization sizes.
5. **Accessible.** The framework is free to use and designed to be understandable without specialized training, while supporting rigorous professional assessment.

---

## 5. Maturity Model

The SEAT maturity model defines five levels of program maturity. Each level builds on the previous, representing increasing formalization, measurement, integration, and optimization.

### Level 1: Minimal

The organization has no formal security awareness program, or existing activities are entirely ad hoc.

**Characteristics:**
- No documented strategy or program plan
- Training occurs only when required by a specific compliance event
- No dedicated program owner or budget
- No metrics tracked beyond basic completion rates, if any
- Security awareness is treated as an IT task, not a risk management function

**Typical indicators:**
- Annual compliance-only training (one module, same content each year)
- No phishing simulations
- No executive visibility or sponsorship
- No communication strategy

### Level 2: Emerging

Some security awareness activities exist but lack consistency, documentation, and measurement.

**Characteristics:**
- Basic activities exist (training, occasional phishing simulations) but are informal
- A program owner may exist but without dedicated budget or authority
- Some metrics are tracked but not reported consistently
- Content is generic, not tailored to organizational risks
- Limited executive awareness of program existence

**Typical indicators:**
- Quarterly or annual training with off-the-shelf content
- Phishing simulations run occasionally without consistent methodology
- Basic completion tracking in a spreadsheet or LMS
- No formal communication strategy

### Level 3: Established

The program is documented, structured, and operating with defined processes and regular measurement.

**Characteristics:**
- Written program strategy with defined goals and objectives
- Dedicated program owner with budget allocation
- Regular training cadence with content aligned to organizational risks
- Phishing simulations conducted on a consistent schedule with tracking
- Metrics reported to security leadership on a regular cadence
- Communication strategy exists and is executed

**Typical indicators:**
- Monthly or quarterly training with role-based content variations
- Regular phishing simulations with difficulty progression
- Dashboard or reporting mechanism for program metrics
- Annual program review and planning cycle
- Some integration with incident response processes

### Level 4: Advanced

The program is mature, well-integrated with organizational risk management, and demonstrates measurable behavior change.

**Characteristics:**
- Program strategy explicitly tied to enterprise risk register
- Comprehensive, role-based training with personalization
- Phishing simulations integrated with training (educational, not punitive)
- Behavioral metrics tracked alongside completion metrics
- Regular board-level or executive reporting on human risk posture
- Feedback mechanisms drive continuous content improvement
- Multi-channel communication strategy (not just email)
- Incident response integration (employees know how to report, and do)

**Typical indicators:**
- Behavior change metrics (reporting rates, repeat click rates, time-to-report)
- Risk-based training prioritization (high-risk roles get more attention)
- Program effectiveness tied to security incident trends
- Active executive sponsor with regular engagement
- Cross-functional collaboration (security, HR, communications, IT)

### Level 5: Optimized

The program is industry-leading, deeply embedded in organizational culture, and continuously optimized through data-driven decision making.

**Characteristics:**
- Security awareness is part of organizational identity, not a compliance function
- Predictive analytics inform program priorities
- Employees are active participants in security culture, not passive training recipients
- Program benchmarked against external peers
- Innovation in delivery methods and engagement approaches
- Recognized externally as a model program
- Full lifecycle integration (hiring, onboarding, ongoing, role transitions, offboarding)

**Typical indicators:**
- Employee-driven security initiatives (security champions programs, peer reporting)
- Program metrics influence organizational risk ratings
- Demonstrated reduction in human-factor security incidents over time
- External recognition or case study publication
- Continuous improvement cycle with measurable iteration

---

## 6. Assessment Domains

The SEAT framework evaluates programs across four domains. Each domain represents a critical area of program capability.

| Domain | Focus | Questions | Outcomes |
|--------|-------|-----------|----------|
| Strategy and Governance | Is the program designed as a risk management function with executive support? | 6 | 4 |
| Engagement and Culture | Does the program reach the right people with relevant, culturally appropriate content? | 5 | 4 |
| Assessment and Metrics | Does the program measure what matters and demonstrate impact? | 5 | 3 |
| Training and Development | Is training effective, accessible, and integrated with the employee lifecycle? | 5 | 5 |

Each domain is scored independently, producing a domain-level maturity rating. The overall SEAT Rating is a weighted composite of all four domains.

**Domain weighting:**

Strategy and Governance carries the heaviest weight in the overall score. Without executive support, budget, and strategic alignment, the other three domains cannot sustain maturity. An organization with advanced training but minimal governance will not receive a high overall rating. This is intentional.

---

## 7. Domain 1: Strategy and Governance

This domain evaluates the strategic foundation of the security awareness program. It answers: *Is the program designed and managed as a risk management function, or is it an afterthought?*

### Outcomes Evaluated

**SG-1: Strategic Alignment**
The program is explicitly aligned with the organization's risk management strategy and compliance requirements. Program priorities are informed by the enterprise risk register, threat landscape, and regulatory obligations.

*Evidence types:* Program strategy document, risk register references, board minutes, compliance mapping documentation

**SG-2: Governance Documentation**
The program has formal documentation including a charter, policy alignment, and defined roles and responsibilities. Documentation is reviewed and updated on a regular cadence.

*Evidence types:* Program charter, policy documents, RACI matrix, review logs

**SG-3: Executive Support**
The program has active executive sponsorship with dedicated budget, regular leadership engagement, and visibility at the board or C-suite level.

*Evidence types:* Budget allocation records, board presentation materials, executive communications, meeting minutes

**SG-4: Continuous Improvement**
The program includes a formal assessment and improvement cycle. Performance is reviewed against objectives, and findings drive program changes.

*Evidence types:* Assessment reports, improvement plans, year-over-year trend analysis, program review documentation

### Framework Mapping (Strategy and Governance)

| Framework | Relevant Controls |
|-----------|------------------|
| NIST CSF 2.0 | GV.RM-03, GV.PO-01 |
| ISO 27001:2022 | 5.1, 5.2, 6.1, A.5.1, A.6.3 |
| NIS2 | Article 20(1), Article 20(2) |
| DORA | Article 5(1), Article 13(6) |
| CMMC | CA.L2-3.12.1, AT.L2-3.2.1 |
| PCI DSS 4.0 | 12.1, 12.3, 12.4.1 |
| SOC 2 | CC1.1, CC1.4, CC2.2 |

---

## 8. Domain 2: Engagement and Culture

This domain evaluates how the program connects with its audience. It answers: *Does the program reach the right people with content that is relevant, accessible, and culturally appropriate?*

### Outcomes Evaluated

**EC-1: Targeted Communication**
The program uses role-based, risk-informed communication strategies. Different audiences receive different messaging based on their risk profile and job function.

*Evidence types:* Communication plans, audience segmentation documentation, role-based content examples

**EC-2: Cultural Relevance**
Program content is adapted for the organization's cultural context, including language, regional considerations, and organizational values.

*Evidence types:* Localized content examples, language support documentation, cultural adaptation records

**EC-3: Active Participation**
The program includes mechanisms to move employees from passive recipients to active participants. Incentive programs, recognition, and gamification may be used.

*Evidence types:* Participation metrics, incentive program documentation, recognition records, engagement surveys

**EC-4: Feedback Responsiveness**
The program collects and acts on employee feedback. Content and delivery methods evolve based on audience input.

*Evidence types:* Feedback collection mechanisms, content revision logs, survey results, change documentation

### Framework Mapping (Engagement and Culture)

| Framework | Relevant Controls |
|-----------|------------------|
| NIST CSF 2.0 | PR.AT-01, PR.AT-02 |
| ISO 27001:2022 | A.6.3, 7.3, 7.4 |
| NIS2 | Article 20(2) |
| DORA | Article 13(6) |
| CMMC | AT.L2-3.2.2 |
| PCI DSS 4.0 | 12.6.1, 12.6.2 |
| SOC 2 | CC1.4, CC2.2, CC2.3 |
| GDPR | Article 39(1)(b), Article 47(2)(n) |

---

## 9. Domain 3: Assessment and Metrics

This domain evaluates how the program measures effectiveness and demonstrates impact. It answers: *Does the program know if it is working, and can it prove it?*

### Outcomes Evaluated

**AM-1: Performance Measurement**
The program tracks meaningful metrics beyond basic completion rates. KPIs are defined, reported regularly, and tied to program objectives.

*Evidence types:* KPI definitions, metric dashboards, reporting cadence documentation, trend reports

**AM-2: Risk-Driven Assessment**
The program uses risk-based prioritization to focus assessment efforts. High-risk populations, behaviors, and threat vectors receive additional measurement attention.

*Evidence types:* Risk-based assessment methodology, population segmentation, threat-aligned simulation records

**AM-3: Behavioral Impact Assessment**
The program measures actual behavior change, not just knowledge acquisition. Metrics include reporting rates, simulation performance trends, and incident correlation.

*Evidence types:* Behavioral trend analysis, simulation results over time, incident report correlation, time-to-report metrics

### Framework Mapping (Assessment and Metrics)

| Framework | Relevant Controls |
|-----------|------------------|
| NIST CSF 2.0 | ID.RA-01, PR.AT-01 |
| ISO 27001:2022 | 9.1, 9.3, A.6.3 |
| NIS2 | Article 20(1) |
| DORA | Article 13(6) |
| CMMC | AT.L2-3.2.3 |
| PCI DSS 4.0 | 12.6.3 |
| SOC 2 | CC4.1, CC4.2 |

---

## 10. Domain 4: Training and Development

This domain evaluates the design and delivery of training and educational content. It answers: *Is training effective, accessible, appropriately delivered, and integrated with the employee lifecycle?*

### Outcomes Evaluated

**TD-1: Relevant, Tailored Training**
Training content is aligned to organizational risks and tailored to different roles, departments, or risk profiles.

*Evidence types:* Training curriculum, role-based content matrix, risk-to-training mapping documentation

**TD-2: Effective Learning Methods**
The program uses varied, evidence-based learning methods. Phishing simulations are used as educational tools, not purely punitive mechanisms.

*Evidence types:* Learning methodology documentation, simulation-to-training integration records, content format variety

**TD-3: Accessible, Inclusive Training**
Training is accessible to all employees regardless of role, location, language, or ability. Accommodations are documented and maintained.

*Evidence types:* Accessibility compliance records, language availability, accommodation documentation

**TD-4: Flexible, Effective Delivery**
Training is delivered on an appropriate cadence with consideration for employee workload, role requirements, and learning retention principles.

*Evidence types:* Training calendar, delivery schedule, completion and engagement analytics

**TD-5: Integrated Training Lifecycle**
Training is integrated with the employee lifecycle from onboarding through role transitions and offboarding. Security awareness is part of professional development, not a standalone obligation.

*Evidence types:* Onboarding program documentation, role-transition training records, career development integration

### Framework Mapping (Training and Development)

| Framework | Relevant Controls |
|-----------|------------------|
| NIST CSF 2.0 | PR.AT-01, PR.AT-02 |
| ISO 27001:2022 | A.6.3, 7.2, 7.3 |
| NIS2 | Article 20(2) |
| DORA | Article 13(6) |
| CMMC | AT.L2-3.2.1, AT.L2-3.2.2, AT.L2-3.2.3 |
| PCI DSS 4.0 | 12.6.1, 12.6.2, 12.6.3, 12.6.3.1 |
| SOC 2 | CC1.4, CC2.2 |
| GDPR | Article 39(1)(b) |

---

## 11. Scoring Methodology

### Per-Question Scoring

Each assessment question is scored on a 1-5 scale corresponding to the maturity levels defined in Section 5. A response of N/A (0) is excluded from the scoring calculation.

### Domain Score Calculation

Each domain score is calculated as the average of all applicable question scores within that domain:

```
Domain Score = Sum of applicable question scores / Number of applicable questions
```

The resulting score maps to a maturity level:

| Score Range | Maturity Level |
|-------------|---------------|
| 1.0 - 1.5 | Level 1: Minimal |
| 1.6 - 2.5 | Level 2: Emerging |
| 2.6 - 3.5 | Level 3: Established |
| 3.6 - 4.5 | Level 4: Advanced |
| 4.6 - 5.0 | Level 5: Optimized |

### Overall SEAT Rating

The overall SEAT Rating is the weighted average of all four domain scores:

| Domain | Weight |
|--------|--------|
| Strategy and Governance | 30% |
| Engagement and Culture | 25% |
| Assessment and Metrics | 25% |
| Training and Development | 20% |

Strategy and Governance is weighted most heavily because executive support and strategic alignment are prerequisites for sustained maturity in all other domains.

The overall weighted score maps to the same maturity level scale, producing a single SEAT Rating (Level 1 through Level 5) for the organization.

### Rating Validity

A SEAT Rating is valid for 12 months from the date of assessment. Organizations may re-assess at any time to update their rating.

---

## 12. SEAT Outcomes Model

The framework defines 16 canonical outcomes across the four domains. These outcomes represent the specific, measurable capabilities that a mature security awareness program should demonstrate.

### Outcomes by Domain

**Strategy and Governance**
| ID | Outcome | Description |
|----|---------|-------------|
| SG-1 | Strategic Alignment | Program priorities driven by enterprise risk and compliance requirements |
| SG-2 | Governance Documentation | Formal program charter, policies, and defined roles |
| SG-3 | Executive Support | Active sponsorship, dedicated budget, leadership visibility |
| SG-4 | Continuous Improvement | Regular assessment and data-driven program iteration |

**Engagement and Culture**
| ID | Outcome | Description |
|----|---------|-------------|
| EC-1 | Targeted Communication | Role-based, risk-informed messaging strategies |
| EC-2 | Cultural Relevance | Content adapted for organizational and regional context |
| EC-3 | Active Participation | Employees engaged as active participants, not passive recipients |
| EC-4 | Feedback Responsiveness | Program evolves based on audience input |

**Assessment and Metrics**
| ID | Outcome | Description |
|----|---------|-------------|
| AM-1 | Performance Measurement | Meaningful KPIs tracked and reported regularly |
| AM-2 | Risk-Driven Assessment | Measurement prioritized by risk profile |
| AM-3 | Behavioral Impact Assessment | Actual behavior change measured, not just knowledge |

**Training and Development**
| ID | Outcome | Description |
|----|---------|-------------|
| TD-1 | Relevant, Tailored Training | Content aligned to risks and tailored by role |
| TD-2 | Effective Learning Methods | Varied, evidence-based approaches including simulation |
| TD-3 | Accessible, Inclusive Training | Available to all employees regardless of context |
| TD-4 | Flexible, Effective Delivery | Appropriate cadence and delivery methods |
| TD-5 | Integrated Training Lifecycle | Embedded in employee lifecycle from onboarding forward |

### Using Outcomes for Gap Analysis

Each outcome can be evaluated independently, allowing organizations to identify specific strengths and gaps within a domain. An organization may score Level 4 overall in Training and Development but Level 2 on TD-3 (Accessible, Inclusive Training), indicating a specific gap that requires attention.

This granularity enables targeted improvement planning rather than broad, unfocused remediation.

---

## 13. Regulatory and Compliance Framework Mappings

The SEAT framework maps its 16 outcomes to controls and requirements across 10 major regulatory and industry frameworks. These mappings enable organizations to use their SEAT assessment results as evidence of compliance activity.

### Supported Frameworks

| Framework | Version | Applicability |
|-----------|---------|---------------|
| NIST CSF | 2.0 | All organizations (voluntary, widely adopted) |
| ISO 27001 | 2022 | Organizations seeking/maintaining ISO certification |
| NIS2 | 2022/2555 | EU essential and important entities |
| DORA | 2022/2554 | EU financial sector entities |
| CMMC | 2.0 | US Department of Defense contractors |
| PCI DSS | 4.0 | Organizations processing payment card data |
| SOC 2 | Current | Service organizations (trust services criteria) |
| GDPR | 2016/679 | Organizations processing EU personal data |
| MITRE ATT&CK | Current | Threat-informed program design |
| CRI Profile | Current | Financial services cyber risk baseline |

### Mapping Methodology

Each mapping includes:

- **SEAT Outcome ID:** Which program outcome addresses the control
- **Framework Reference:** The specific control, article, or requirement
- **Assurance Level:** Whether the control is Required, Expected, or Recommended by the framework
- **Evidence Types:** What documentation or artifacts demonstrate compliance
- **Cadence:** How frequently the evidence should be updated (Annual, Quarterly, Continuous)

Detailed mapping tables are provided in Appendix A.

### Important Limitations

SEAT assessment results do not constitute certification or formal compliance determination for any regulatory framework. They provide structured evidence of security awareness program activities and maturity that support an organization's broader compliance posture.

Organizations should consult qualified auditors for formal compliance determinations.

---

## 14. Evidence Requirements

Each SEAT outcome can be substantiated with specific evidence types. During a SEAT Assessment, the assessor evaluates both the program owner's self-reported maturity and the availability of supporting evidence.

### Evidence Categories

| Category | Examples |
|----------|---------|
| Policy Document | Program charter, security awareness policy, acceptable use policy |
| Communication Artifact | Newsletter samples, awareness campaign materials, executive communications |
| Training Record | LMS completion data, attendance logs, curriculum documentation |
| Metric Report | KPI dashboards, quarterly reports, trend analysis |
| Board Minutes | Executive briefing slides, board meeting records, risk committee minutes |
| Incident Report | Security incident records showing employee reporting behavior |
| Assessment Report | Prior SEAT assessments, internal program reviews, audit findings |
| Curriculum Document | Training content inventory, role-based content matrix |
| Simulation Results | Phishing simulation data, click/report rates, difficulty progression |
| Feedback Survey | Employee feedback data, program satisfaction surveys, focus group records |

### Evidence Maturity

The quality and completeness of evidence contributes to the maturity rating:

- **Level 1-2:** Little to no formal evidence exists
- **Level 3:** Evidence exists but may be inconsistent or incomplete
- **Level 4:** Comprehensive evidence maintained on a regular cadence
- **Level 5:** Evidence is systematically managed, version-controlled, and readily available for audit

---

## 15. Assessment Process

### Assessment Types

**Self-Assessment**
The program owner evaluates their own program using the SEAT framework. Suitable for internal planning, gap identification, and improvement tracking. Self-assessments can be conducted at any time using the SEAT platform.

**Facilitated Assessment**
A SEAT-certified assessor guides the program owner through the assessment, providing calibration and objectivity. Suitable for organizations seeking a validated rating for compliance or stakeholder reporting.

**Enterprise Assessment**
A comprehensive, multi-session assessment for large or complex organizations. Includes stakeholder interviews, evidence review, and a detailed findings report. Results in a formal SEAT Rating with compliance evidence package.

### Assessment Cadence

| Assessment Type | Recommended Frequency |
|----------------|----------------------|
| Self-Assessment | Quarterly or as needed |
| Facilitated Assessment | Annually |
| Enterprise Assessment | Annually with quarterly surveillance |

### Assessment Workflow

1. **Scoping:** Define organizational boundaries, business units, and regulatory context
2. **Data Gathering:** Program owner completes the 21-question assessment instrument
3. **Evidence Review:** Assessor (or self) evaluates available evidence for each outcome
4. **Scoring:** Domain and overall maturity scores calculated per Section 11
5. **Gap Analysis:** Specific gaps identified by outcome and mapped to framework requirements
6. **Reporting:** Assessment report generated with findings, rating, and recommendations
7. **Improvement Planning:** Prioritized roadmap based on gap analysis and organizational priorities

---

## 16. Using SEAT Ratings for Compliance

### Audit Evidence

A completed SEAT Assessment produces artifacts that support audit and compliance activities:

- **SEAT Assessment Report:** Detailed findings by domain and outcome
- **Maturity Rating Certificate:** Date-stamped rating with validity period
- **Compliance Mapping Report:** SEAT results mapped to specific framework controls
- **Gap Analysis:** Identified deficiencies with remediation recommendations
- **Evidence Inventory:** Catalog of supporting documentation reviewed during assessment

### Communicating to Auditors

When presenting SEAT results to auditors, organizations should:

1. Reference the specific framework controls addressed (using the mapping tables)
2. Provide the SEAT Assessment Report alongside supporting evidence
3. Note the assessment date and rating validity period
4. Identify any gaps and associated remediation plans

### Communicating to Boards and Executives

The SEAT Rating provides a simple, consistent metric for executive communication:

- Single number (Level 1-5) with clear definitions
- Domain-level breakdown showing relative strengths and gaps
- Trend over time (comparing sequential assessments)
- Peer context (when available through SEAT benchmark programs)

---

## 17. Framework Governance and Versioning

### Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026 | Initial publication |

### Update Process

The SEAT framework is maintained by HumanRisk and updated based on:

- Changes to mapped regulatory frameworks (new versions, new requirements)
- Practitioner feedback from SEAT Assessment users and certified assessors
- Emerging threats and trends that impact security awareness program design
- Research and industry developments in human risk management

Updates follow semantic versioning:
- **Minor updates (1.x):** Clarifications, additional mappings, expanded guidance. Assessment methodology unchanged.
- **Major updates (x.0):** Changes to domains, scoring methodology, or maturity definitions. May require re-assessment.

### Feedback

Feedback on this framework is welcome and encouraged. Contact framework@humanrisk.com or submit through the SEAT platform.

---

## Appendix A: Framework Mapping Reference

*Detailed control-by-control mapping tables for all 10 supported frameworks will be published as a companion document. Each mapping specifies the SEAT outcome, framework control reference, assurance level, required evidence types, and assessment cadence.*

*The companion mapping document is available at humanrisk.com/framework/mappings*

---

## Appendix B: Sample Assessment Report Structure

A SEAT Assessment Report includes the following sections:

1. **Executive Summary**
   - Overall SEAT Rating
   - Assessment date and validity
   - Key findings (3-5 bullet points)
   - Top recommendations

2. **Organization Profile**
   - Industry and size
   - Regulatory environment
   - Assessment scope and boundaries

3. **Domain Results**
   - Score and maturity level per domain
   - Strengths and gaps per outcome
   - Evidence summary

4. **Compliance Mapping**
   - Framework-by-framework control status
   - Satisfied, partially satisfied, and gap controls

5. **Gap Analysis**
   - Prioritized list of gaps by impact and effort
   - Recommended remediation activities
   - Suggested timeline

6. **Improvement Roadmap**
   - 90-day, 6-month, and 12-month priorities
   - Target maturity levels by domain
   - Recommended re-assessment date

---

## Appendix C: Glossary

| Term | Definition |
|------|-----------|
| Behavioral Metric | A measurement of actual employee security behavior (e.g., phishing report rate) as opposed to knowledge or completion |
| Compliance Mapping | The association between SEAT outcomes and specific regulatory framework controls |
| Domain | One of four primary assessment areas in the SEAT framework |
| Evidence | Documentation or artifacts that substantiate a maturity rating |
| Maturity Level | A defined stage (1-5) of program development and effectiveness |
| Outcome | A specific program capability evaluated within a domain (16 total) |
| Program Owner | The individual or team responsible for managing the security awareness program |
| SEAT Assessment | A structured evaluation using this framework's methodology |
| SEAT Rating | The overall maturity level assigned after assessment |
| Self-Assessment | An assessment conducted by the program owner without external facilitation |
| Surveillance | A periodic check between full assessments to verify continued compliance |

---

**SEAT Security Awareness Maturity Framework v1.0**
**Published by HumanRisk | humanrisk.com/framework**
**Licensed under CC BY-NC 4.0**
