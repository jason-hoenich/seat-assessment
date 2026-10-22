# CybSafe Oh, Behave! 2026-2027

Population-level data on what people actually do, mapped to the SEAT outcomes it informs. Supersedes the 2025-2026 edition (`cybsafe-2026`).

**Publisher:** CybSafe and the National Cybersecurity Alliance, with Dr. Suzie Dobrontei, Dr. Jason R.C. Nurse, and survey design input from Dr. Lorrie Faith Cranor's team at Carnegie Mellon University CyLab
**Coverage:** 5,000 adults (age 18+), 1,000 each in the US, UK, India, Brazil, and Singapore, balanced for age and gender. 3,269 were employed. Fieldwork April 28 to May 19, 2026
**Published:** 2026-10-22
**Source last updated:** 2026-10-22
**Official reference:** https://www.cybsafe.com/research/
**Source id:** `cybsafe-2026-27`
**Source type:** Population behavior and attitude survey

## How an assistant applies this source

You need the respondent's per-question scores (1-5) and their outcome scores, produced by the flow in `AGENTS.md` and `adapters/outcomes.md`. Then:

1. **Compute outcome scores first.** Every finding below is anchored to SEAT outcomes by outcome id.
2. **Findings are evidence, never scores.** Nothing here changes a score, adds a requirement, or creates a gap. Compliance status comes only from `adapters/`.
3. **Only use figures that appear in this file.** Do not supply numbers from your own knowledge of this report or any other.
4. **Attribute every figure,** naming the publisher and that it is self-reported behavior from a general population, not from the respondent's own workforce.
5. **State the base.** Most figures here describe a subgroup: people who use AI at work, people who attended training, people who do not report phishing. The base is in the table. A rate cited without it will mislead.
6. **Do not build trends against the 2025-2026 edition.** The country mix changed (Germany, Australia, and Mexico out; Singapore in) and the questions were redesigned with Carnegie Mellon CyLab. A figure that moved between editions may reflect the sample, not behavior. Cite only the year-over-year changes the publisher prints, and say they are the publisher's comparison.
7. **The respondent's data wins.** If the respondent has their own behavioral data, that data is better than this benchmark for their organization. Say so.
8. **This is the source for knowing-versus-doing arguments.** Use it when the respondent needs to show that awareness, confidence, and stated satisfaction with training do not translate into behavior.

## Findings mapped to SEAT outcomes

| Finding | Figure | SEAT outcome | Outcome id | What a low score here exposes |
|---|---|---|---|---|
| AI is now a majority behavior | 80% of all participants use AI tools; 44% use them at both home and work; 50% of all participants use AI at work (base 5,000) | Relevant Tailored Training | `relevant-tailored-training` | A curriculum that still treats AI as an emerging topic while half the population uses it on the job |
| Employers are driving AI adoption | Of those using AI at work (n=2,481), 20% were required by their employer and 24% encouraged, against 41% who started on their own initiative | Risk Driven Assessment | `risk-driven-assessment` | A risk picture that treats unsanctioned AI use as rogue behavior when the organization pushed people into the tools |
| Unsanctioned sharing is routine | 32% of those using AI at work (n=2,481) shared sensitive work information with AI tools without their employer's knowledge; a further 4% were not sure | Risk Driven Assessment | `risk-driven-assessment` | Assuming an acceptable-use policy describes behavior without ever measuring it |
| Guidance is missing or unclear | Of those using AI at work (n=2,481), 54% say their employer clearly communicated what can and cannot be shared with AI; 19% got guidance that was not very clear and 24% got none | Governance Documentation | `governance-documentation` | Documentation that exists but was never tested for whether employees understood it |
| AI risk training is absent | 56% of AI users (n=3,981) have received no training on the security and privacy risks of AI tools; 52% of employed AI users have not | Effective Learning Methods | `effective-learning-methods` | Treating unsanctioned AI sharing as a discipline problem when most of it is a coverage problem |
| What gets pasted in | Among those who shared without employer knowledge (n=791): internal company documents 50%, customer or client data 50%, financial data 47%, business strategies 41%, proprietary code 39%, employee or HR information 30% | Relevant Tailored Training | `relevant-tailored-training` | Generic AI warnings that never name the specific data types people are actually sharing |
| Sharing skews young | Unsanctioned sharing among those using AI at work (n=2,481): Gen Z 40%, Millennials 35%, Gen X 22%, Baby Boomers 17% | Targeted Communication | `targeted-communication` | One AI message to a workforce where the behavior varies more than twofold by cohort |
| Sharing varies by sector | Unsanctioned sharing among those using AI at work: marketing, advertising and PR 46%, finance and insurance 42%, construction 40%, IT and telecommunications 39%, government and public administration 19% (sectors with 50+ respondents only) | Targeted Communication | `targeted-communication` | Benchmarking AI exposure against an all-industry average when the respondent's own sector sits well above or below it |
| Most people have been hit personally | 50% of all participants have been victims of cybercrime (base 5,000). By generation: Gen Z 64%, Millennials 57%, Baby Boomers 33% lost money or data to a scam | Cultural Relevance | `cultural-relevance` | Content pitched at corporate risk that never connects to what half the audience has already lived through |
| Deepfake calls cost money | 36% of all participants received a deepfake phone or video call, and 40% of those lost money or data as a result. Millennials 48% and Gen Z 42% were targeted | Effective Learning Methods | `effective-learning-methods` | Verification training that still teaches people to trust a familiar voice or face |
| Confidence outruns checking | 64% are confident they can identify a phishing email, 71% a scam text; 61% regularly check messages for warning signs (base 5,000) | Performance Measurement | `performance-measurement` | Measuring confidence or knowledge and reporting it as behavior |
| Most people do not report | 41% report phishing messages always or very often; 21% rarely or never; 10% do not know how or have never seen a way to report (base 5,000) | Active Participation | `active-participation` | A reporting metric built on a button many people never use or cannot find |
| Non-reporters want a closed loop | Among non-reporters (n=1,049), would report if: they understood how 60%, they trusted the reporting process 58%, something would happen when they report 57%, there were some benefit to them 49% | Feedback Responsiveness | `feedback-responsiveness` | Reports that disappear without acknowledgement, which teaches people to stop reporting |
| Training coverage is half | 50% of all participants have no access to cybersecurity training; among employed participants, 47% are required to complete training and 48% are not | Accessible Inclusive Training | `accessible-inclusive-training` | Coverage assumed from an LMS assignment count rather than measured across the workforce, including contractors and part-time staff |
| Cadence is onboarding plus annual | Among those required to train (n=1,543): 48% at onboarding, 46% once a year, 30% more than once a year, 11% only when something goes wrong | Integrated Training Lifecycle | `integrated-training-lifecycle` | A program whose only touchpoints are day one and the annual compliance window |
| Delivery lags preference | 34% prefer short, bite-sized information delivered when relevant (base 5,000), while 29% of those required to train (n=1,543) receive it; video is preferred by 50% and gamified activities by 17% | Flexible Effective Delivery | `flexible-effective-delivery` | Delivery chosen by what the platform does well rather than how the workforce wants to learn |
| Why people skip training | Among those with access who did not attend (n=638): no time 21%, already know enough 19%, do not think training reduces their risk 17%, cybersecurity is not important to them 17%. Gen Z is the most likely generation to have access and skip it (21%) | Relevant Tailored Training | `relevant-tailored-training` | Training that has never shown the audience it reduces their own risk |
| Useful is not the same as adopted | Among those who attended training (n=1,844), 88% found it useful; 54% got better at recognizing and reporting phishing, 49% started using MFA, 46% began using a password manager. The publisher notes most key behaviors were adopted by fewer than half of attendees | Performance Measurement | `performance-measurement` | Satisfaction and completion reported as impact |
| Leaders get credit, colleagues get blamed | Among employed participants (n=3,269), 60% say senior leaders visibly champion cybersecurity, 64% say good practices are embedded in how work gets done, and 48% see people inside their organization as a significant risk | Executive Support | `executive-support` | Leadership visibility counted as culture while half the workforce still sees its own colleagues as the threat |
| Fatalism undercuts motivation | 35% see no point in protecting themselves further because their information is already online; 39% consider having personal data stolen, and 33% losing money, an unavoidable cost of being online (base 5,000) | Targeted Communication | `targeted-communication` | Fear-based messaging aimed at people who have already decided their effort makes no difference |
| Knowing without doing | 21% know how to use MFA but have stopped or do not use it; 53% do not use MFA regularly; 70% are at least somewhat familiar with passkeys and 39% use them (base 5,000) | Behavioral Impact (not scored by the core 21) | `behavioral-impact` | Programs that stop at capability and never address opportunity or motivation |

## Notes by outcome

**Risk Driven Assessment (`risk-driven-assessment`) and Governance Documentation (`governance-documentation`).** The AI findings read as one chain. Employers pushed adoption (44% required or encouraged), 43% of those using AI at work got unclear guidance or none, and 32% shared sensitive work information without their employer knowing. State the base every time: these are people who use AI at work (n=2,481), not all employees. A respondent whose AI control is a policy acknowledgement has an assumption where they need a measurement. Use this to argue for testing comprehension of the policy and measuring the behavior, not for a stricter policy. The 32% is lower than the 43% in the 2025-2026 edition, but the sample and questions changed, and the publisher does not present it as a decline. Do not either.

**Feedback Responsiveness (`feedback-responsiveness`) and Active Participation (`active-participation`).** Fewer than half report phishing regularly, and the conditions non-reporters set are design conditions: know how (60%), trust the process (58%), see something happen (57%). A respondent who scores low on feedback responsiveness and tracks report rate as a headline metric is measuring the output of a loop they have not built. The first move is acknowledging every report and telling reporters what happened.

**Performance Measurement (`performance-measurement`).** This is the strongest proof-over-promise material in the file. 88% of attendees said training was useful, while each specific behavior was adopted by fewer than half. Confidence in spotting phishing (64% for email) runs ahead of the habit of checking (61%) and well ahead of reporting (41%). Satisfaction, confidence, and completion all measure something other than behavior. The respondent's metrics should include at least one observed behavior.

**Targeted Communication (`targeted-communication`).** Two splits matter. Unsanctioned AI sharing runs from 17% (Baby Boomers) to 40% (Gen Z), and from 19% (government) to 46% (marketing, advertising and PR). The youngest cohorts also report the highest confidence and the highest victimization, which the publisher frames as overconfidence. Separately, a third of people believe their effort makes no difference, so fear appeals work against the program. The publisher recommends proof that protective actions work over further threat statistics.

**Integrated Training Lifecycle (`integrated-training-lifecycle`) and Flexible Effective Delivery (`flexible-effective-delivery`).** Among those required to train, onboarding (48%) and annual (46%) dominate, and 11% are trained only after an incident. Preference for bite-sized, in-the-moment content (34%) now exceeds what employers deliver (29%). Gamified activities are the least preferred format (17%), which is worth knowing before a respondent buys a program built around them.

## Provenance and limits

Self-reported survey data from a general population across five countries, not from any single organization's workforce. People are unreliable narrators of their own security behavior, and self-report typically understates risky behavior because respondents know what the correct answer sounds like. Treat these figures as a conservative floor.

The training-impact figures are the attendees' own account of how training changed their behavior. They are evidence of perceived impact, not measured impact, and they come from people who chose to attend.

The sample is not comparable to the 2025-2026 edition: three countries changed, and the survey was redesigned with Carnegie Mellon CyLab, including moving some single-answer questions to multi-select. Year-over-year deltas printed by the publisher are its own comparison; treat them with the same caution.

Because this is population data rather than workplace telemetry, it describes the people an organization hires rather than how they behave inside a given control environment. If the respondent has their own behavioral measurement, prefer it.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) research sources. CC BY-ND 4.0.
