# CrowdStrike 2026 Threat Hunting Report

Frontline adversary tradecraft observed by CrowdStrike OverWatch, mapped to the SEAT outcomes it puts pressure on.

**Publisher:** CrowdStrike Counter Adversary Operations (OverWatch)
**Coverage window:** July 1, 2025 to June 30, 2026
**Source last updated:** 2026-08-31
**Official reference:** https://www.crowdstrike.com/en-us/resources/reports/threat-hunting-report/
**Source id:** `crowdstrike-2026-thr`
**Source type:** Threat telemetry (observed intrusions, not survey data)

## How an assistant applies this source

You need the respondent's per-question scores (1-5) and their outcome scores, produced by the flow in `AGENTS.md` and `adapters/outcomes.md`. Then:

1. **Compute outcome scores first.** Every finding below is anchored to one or more SEAT outcomes by outcome id. Score those outcomes the normal way before you use anything in this file.
2. **Findings are evidence, never scores.** Nothing in this file changes a respondent's score, adds a requirement, or creates a gap. A research source explains what a given score exposes the program to. Compliance status comes only from `adapters/`.
3. **Only use figures that appear in this file.** Do not supply numbers from your own knowledge of this report or any other, and do not update, round, or extrapolate the figures here. If the respondent asks about something this file does not cover, say so.
4. **Attribute every figure.** Name the publisher and the coverage window when you cite one, so the respondent can tell benchmark data from their own data.
5. **The respondent's data wins.** If the respondent tells you their own environment contradicts a finding, take their word for it and say the benchmark did not match. This is external evidence, not ground truth about their organization.
6. **Threat data ages.** State the coverage window whenever you present a finding as current. If today is more than roughly a year past the window above, tell the respondent the source may be stale before you reason from it.
7. **Do not use this file to generate fear.** Tie every finding to a specific outcome score and a specific action the respondent could take. A finding the respondent can do nothing about does not belong in the report.

## Findings mapped to SEAT outcomes

| Finding | Figure | SEAT outcome | Outcome id | What a low score here exposes |
|---|---|---|---|---|
| Vishing as initial access | Vishing intrusions doubled in H1 2026 vs H2 2025, following a 134% rise 2024 to 2025 | Relevant Tailored Training | `relevant-tailored-training` | Curriculum built around email leaves the fastest-growing vector untaught |
| IT impersonation pretext | Standard pretext is an attacker posing as IT staff resolving a trivial support issue, often calling a personal mobile | Targeted Communication | `targeted-communication` | No stated position on what IT will never ask by phone leaves employees to guess |
| No channel to report a call | Vishing calls cannot be detected in isolation; defenders depend on contextual activity around the call | Feedback Responsiveness | `feedback-responsiveness` | A report-phish button with no equivalent for calls produces zero telemetry on the top vector |
| Device code phishing | 15x increase in monthly attempts over six months, driven by commodity phishing-as-a-service kits | Effective Learning Methods | `effective-learning-methods` | Training that teaches URL inspection fails against an attack that uses a genuine login page |
| MFA completes and access is still lost | Victim authenticates legitimately and passes MFA; attacker takes the resulting session token | Relevant Tailored Training | `relevant-tailored-training` | "MFA will protect you" is taught as an endpoint rather than a control with known bypasses |
| Identity is the attack surface | In most observed identity intrusions the attacker never touches a managed endpoint | Risk Driven Assessment | `risk-driven-assessment` | Program risk picture built on endpoint and email data misses where intrusions now occur |
| Unmanaged personal devices in the attack path | Victims are routed to adversary-in-the-middle pages on personal phones, outside security visibility | Accessible Inclusive Training | `accessible-inclusive-training` | Training that assumes a managed corporate device does not reach the device being attacked |
| Attacker-registered MFA devices | Attackers enroll their own devices, including Android emulators and QEMU instances, for persistence | Performance Measurement | `performance-measurement` | No visibility into enrollment events means no metric on the step that establishes persistence |
| Speed from takeover to theft | One intrusion moved from account takeover to data exfiltration in under five minutes | Performance Measurement | `performance-measurement` | Quarterly click rate and annual completion describe a cadence attackers have left behind |
| Speed of detection as the differentiator | In a disrupted intrusion, malicious MFA enrollment was caught at four minutes and sessions revoked at nineteen | Continuous Improvement | `continuous-improvement` | Without a measured report-to-response time there is no way to tell whether the program would have helped |
| Developers targeted directly | An employee was approached over LinkedIn and compromised during a video call, yielding a malicious dependency across 131 packages | Relevant Tailored Training | `relevant-tailored-training` | Exempting engineering from training leaves the population with the largest blast radius uncovered |
| Maintainer credentials as the seed | Self-propagating malware from one set of stolen credentials reached more than 300 dependencies in a single day | Strategic Alignment | `strategic-alignment` | Awareness scoped to employees rather than to identities that control production |
| Package registry as the vector | npm accounted for 87% of malicious software registry threats in H1 2026 | Integrated Training Lifecycle | `integrated-training-lifecycle` | No role-triggered training when someone gains publish or pipeline rights |
| CI/CD pipeline compromise | A poisoned public CI/CD component caused every downstream pipeline that pulled it to run a credential stealer | Governance Documentation | `governance-documentation` | Third-party scope defined as named vendors rather than as inherited code |
| Close access against travelers | Backdoors installed via bootable USB on laptops left unattended, defeating phishing training, password policy, and MFA together | Flexible Effective Delivery | `flexible-effective-delivery` | No travel content and no way to demonstrate travel-risk coverage |
| Timing of physical compromise | Conference-week compromises occurred at 19:52 and 21:57 local time, matching dinner service | Cultural Relevance | `cultural-relevance` | Generic content that never addresses the specific situations employees are actually in |
| Executives and specialists as named targets | Targeting mapped to state collection priorities, with sustained focus on media personnel and strategically named sectors | Executive Support | `executive-support` | Leadership treated only as a funding source, never as a targeted population needing its own briefing |
| Vulnerability weaponization speed | 88% of observed exploitation of vulnerabilities with a public proof of concept occurred within 48 hours of release | Continuous Improvement | `continuous-improvement` | Annual program review cycles against a threat environment that turns over in days |
| AI-enabled adversary activity | Adversaries use generative AI for payloads, reconnaissance, and fake infrastructure, and target AI systems directly | Relevant Tailored Training | `relevant-tailored-training` | AI content limited to acceptable-use policy rather than the risks employees actually encounter |
| Corporate LLM access abused | One campaign sent nearly 200,000 API requests in a two-minute flood against a victim's own model access | Risk Driven Assessment | `risk-driven-assessment` | AI risk assessed as a data-leakage question only, missing credential and cost exposure |

## Notes by outcome

**Relevant Tailored Training (`relevant-tailored-training`).** This is the outcome this source pressures hardest. Three separate findings land on it: the channel shift toward voice, the token-theft techniques that survive correct MFA use, and the direct targeting of developers. A program scoring at or below 3 here is very likely teaching a threat model narrower than the one in use. When you report on this outcome, name which of the three gaps applies rather than recommending "more tailored training."

**Performance Measurement (`performance-measurement`).** The five-minute and four-minute figures reframe what this outcome should measure. Latency metrics, specifically mean time to report and time from report to session revocation, map to whether an intrusion succeeds. Completion and click rate do not. If the respondent scores low here, the highest-value single change is instrumenting one latency metric rather than adding another activity metric.

**Feedback Responsiveness (`feedback-responsiveness`).** Reporting culture is only as wide as the channels provided. Most programs have a one-click path for email and nothing for a phone call, which means the fastest-growing vector generates no reports, no coaching moments, and no evidence of coverage. This is usually the cheapest gap in this file to close.

**Risk Driven Assessment (`risk-driven-assessment`).** Two findings apply: intrusions that never touch a managed endpoint, and AI risk that extends past data leakage into credential theft and cost harvesting. Both suggest the same failure, which is a risk picture inherited from the tooling that happens to be deployed rather than built from where attacks actually land.

**Accessible Inclusive Training (`accessible-inclusive-training`) and Flexible Effective Delivery (`flexible-effective-delivery`).** These two carry the coverage gaps: the unmanaged personal phone in the attack path, and personnel traveling with company devices. Both are populations or contexts a standard delivery model does not reach. Neither is solved by more content in the existing channel.

**Governance Documentation (`governance-documentation`) and Strategic Alignment (`strategic-alignment`).** The supply chain findings push scope questions upward. If awareness is scoped to employees, and third-party risk is scoped to contracted vendors, then the identities that control production code and the dependencies pulled into the build sit outside both. That is a governance boundary question, not a training question.

## Provenance and limits

This is observed intrusion telemetry from one vendor's customer base, drawn from 7 trillion daily events across endpoint, identity, cloud, and SIEM. It is not a survey and not a census. It reflects what one platform saw in environments that deploy it, which skews toward larger organizations with mature tooling.

The report also expanded its own scope this year to include automated attacks alongside interactive intrusions, so year-over-year volume comparisons within it are not like for like. The publisher reports roughly 4% growth in overall intrusion activity against 27% the prior year and attributes the flattening to adversary maturation rather than reduced risk. Treat that as the publisher's interpretation, not as a finding.

Nothing here establishes that a given organization faces these techniques. It establishes that they are in active use. The bridge from one to the other is the respondent's own outcome scores.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) research sources. CC BY-ND 4.0.
