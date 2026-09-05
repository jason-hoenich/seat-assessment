# Harmonic Security AI Usage Index 2026

Observed AI-session minutes across six tools, classified as personal or business use, mapped to the SEAT outcomes the pattern puts pressure on.

**Publisher:** Harmonic Security
**Coverage window:** Trailing seven weeks ending April 2026, a panel of enterprise organizations on Harmonic's own monitoring
**Published:** 2026-05-20
**Source last updated:** 2026-09-05
**Official reference:** https://www.harmonic.security/resources/ai-usage-index-report-2026
**Source id:** `harmonic-2026-aui`
**Source type:** Usage telemetry (observed AI sessions from one vendor's instrumented customer base; not survey data, not threat or incident data)

## How an assistant applies this source

You need the respondent's per-question scores (1-5) and their outcome scores, produced by the flow in `AGENTS.md` and `adapters/outcomes.md`. Then:

1. **Compute outcome scores first.** Every finding below is anchored to one or more SEAT outcomes by outcome id. Score those outcomes the normal way before you use anything in this file.
2. **Findings are evidence, never scores.** Nothing in this file changes a respondent's score, adds a requirement, or creates a gap. A research source explains what a given score exposes the program to. Compliance status comes only from `adapters/`.
3. **Only use figures that appear in this file.** Do not supply numbers from your own knowledge of this report or any other, and do not update, round, or extrapolate the figures here. If the respondent asks about something this file does not cover, say so.
4. **Attribute every figure** with the publisher and the coverage window, and say what the figure is a share of. Every rate in this file names its base because the same percentage means different things against different denominators.
5. **The respondent's data wins.** If the respondent has their own AI usage telemetry, or their own tenant reporting, that is better evidence about their organization than this file. Say the benchmark did not match rather than arguing.
6. **This is where work happens, not how a workforce behaves.** Use this source to argue about coverage: which accounts, tools, and departments a program's AI guidance and governance actually reach. Do not use it to claim an incident rate, a rate of policy violation, or a general truth about employees. See the provenance section.
7. **Do not use this file to generate fear.** Tie every finding to a specific outcome score and a specific action the respondent could take.

## Findings mapped to SEAT outcomes

| Finding | Figure | SEAT outcome | Outcome id | What a low score here exposes |
|---|---|---|---|---|
| Personal-tier accounts carry business work | 64.5% of classified minutes on personal and free-tier plans are business use (ambiguous minutes excluded) | Risk Driven Assessment | `risk-driven-assessment` | A risk picture drawn from the enterprise tenant's own logs misses most of the AI activity that is actually work |
| It holds on every plan the report checked | Share of each personal-tier plan's classified minutes that is business use: Copilot Free 80.2%, Claude Pro 75.5%, ChatGPT Plus 71.2%, Claude Free 67.2%, ChatGPT Free 60.6%, Gemini Free 40.5% | Relevant Tailored Training | `relevant-tailored-training` | An AI lesson that ends at "use the approved tool" never addresses the account that is already open when the work question arrives |
| Personal use lives on enterprise plans | Of all personal-use minutes, 45.6% are on enterprise-licensed plans, 29.9% on paid consumer plans, 15.5% on free or guest accounts | Governance Documentation | `governance-documentation` | Acceptable-use rules keyed to account tier misclassify in both directions: the free account doing contract review and the enterprise seat drafting a personal email |
| AI use is mostly work | Of 1,935,247 classified minutes, 74.6% are business use, 13.3% personal, 12.1% ambiguous | Strategic Alignment | `strategic-alignment` | An AI pillar built as a prohibition campaign is aimed at the 13.3% and positions the program against the business rather than inside it |
| The work mix does not depend on the tool | Across 11,569 classified business hours: efficiency and automation 47%, risk and compliance 20%, decision support 20%, revenue and growth 7%, innovation and creation 6%, with the same hierarchy on all six tools | Relevant Tailored Training | `relevant-tailored-training` | Content organized by tool ages the moment a team switches tools, and never teaches the task, which is what determines what gets pasted |
| Compliance work is itself done in AI | Risk and compliance is 20% of classified business hours | Governance Documentation | `governance-documentation` | The function writing the AI policy is doing its own work in the tool, and the program has no stated position on that |
| Legal is the heaviest user | Legal and Governance is 19.5% of all AI hours, ahead of Go to Market at 17.7%, Design and Development at 13.3%, Strategy at 11.9% | Risk Driven Assessment | `risk-driven-assessment` | A risk register that files AI under engineering or under "everyone" has the most sensitive use, contracts and litigation and regulatory work, in the wrong row |
| Coverage runs opposite to the unmanaged work | Legal is 32.3% of enterprise-plan AI hours and barely present on free accounts; Go to Market is 28.6% of free-account AI hours, the largest category there, against 10.1% of enterprise-plan hours | Targeted Communication | `targeted-communication` | Role targeting derived from the enterprise tenant reaches the population already covered and misses Sales and Marketing, where the unmanaged use concentrates |
| Functions use AI differently | Average minutes per AI task: Design and Development 9.6, Strategy 8.6, Finance 7.6, Legal and Governance 6.4 at the highest volume, Operations and Customer Experience 4.9 | Relevant Tailored Training | `relevant-tailored-training` | One AI module for everyone describes a session most of the audience never has, deep and iterative for some functions, quick lookups for others |
| Session depth varies by an order of magnitude | Perplexity Enterprise 11.8 minutes per task, Claude Enterprise 10.4, ChatGPT Free 4.8, ChatGPT Guest 2.0; Claude sessions average 10 minutes 12 seconds against 5 minutes 53 seconds for ChatGPT, 73% longer | Performance Measurement | `performance-measurement` | Counting AI events, seats, or policy acknowledgements treats a two-minute lookup and a twelve-minute contract review as the same unit of exposure |
| The context leaves with the person | Publisher's stated consequence of the 64.5% figure, not a measurement: when an employee leaves, the business context in their personal AI account leaves with them | Integrated Training Lifecycle | `integrated-training-lifecycle` | Onboarding covers AI acceptable use; offboarding never asks where the work lived |

## Notes by outcome

**Targeted Communication (`targeted-communication`).** This is the finding most likely to break something a program currently does. Legal has largely moved onto enterprise plans, so it is visible, governed, and reachable through the tenant. Go to Market is running on free accounts the employer cannot see, so it is absent from the tenant data that role targeting is usually built from. A program that targets AI guidance by what its own reporting shows is aiming at the people already covered. When you report on this outcome, ask the respondent which departments their AI guidance was built for and where that list came from. If the answer is "the enterprise AI admin console," this finding applies directly.

**Risk Driven Assessment (`risk-driven-assessment`).** Two findings land here. The first is the 64.5% figure: most of what happens on personal-tier accounts is work, so a risk assessment fed only by the enterprise tenant is assessing a minority of the activity. The second is Legal at 19.5% of all AI hours. Most program risk registers, where they mention AI at all, attach it to engineering or to the whole workforce. The heaviest and most sensitive use sits in a function the register rarely names.

**Relevant Tailored Training (`relevant-tailored-training`).** Three findings, one lesson. The per-plan business shares say the behavior is not tool-specific. The constant work mix says the task is what matters, not the application. The department depth figures say a session in Design and Development and a session in Customer Experience are different activities. Together they argue for AI content built around the task the employee is doing, for the function doing it, rather than a single module about approved tools. The publisher's own explanation for the per-plan figures is worth passing on as interpretation rather than data: the free account is already logged in, already has history, already has extensions, and is what is open when the question arrives. Training that adds knowledge without changing which account is open is competing with friction, and friction usually wins.

**Performance Measurement (`performance-measurement`).** Session depth is the one variable in this report that behaves like a measurement a program could adopt. Seats, tokens, monthly active users, and acknowledgement counts measure adoption. Depth per task is at least a proxy for how much context goes into a session. Treat the publisher's claim that depth correlates with the amount of content shared as their assertion; the report states it and does not show the data behind it. Even so, a program that has no measure of AI exposure beyond a completion rate on an AI policy module scores low here for a reason this report makes concrete.

**Governance Documentation (`governance-documentation`).** Nearly half of personal use is on enterprise plans and nearly two thirds of personal-tier use is business, so a policy that defines acceptable use by which account someone is logged into misdescribes both. The 20% of business hours spent on risk and compliance work is a separate point: the people who write the AI policy are among its heaviest users, and most policies have nothing to say about that.

**Integrated Training Lifecycle (`integrated-training-lifecycle`).** The departure point is the publisher's inference, not a measured figure, and it is included because it names a lifecycle moment programs consistently skip. Onboarding gets the AI acceptable-use briefing. Offboarding gets a device return checklist. Nobody asks which personal accounts the work lived in.

## Provenance and limits

This is usage telemetry from one vendor's instrumented customer base. Harmonic observes AI sessions through browser-level monitoring on managed devices or devices with its agent installed, and classifies each session as personal, business, or ambiguous with a large-language-model classifier. Plan tiers come from account metadata. The panel is enterprise organizations that bought AI governance tooling, which skews toward organizations already concerned about AI use and toward the managed devices inside them. Unmanaged devices and anything outside the browser are not in the data.

What it can support: claims about where AI work happens (which accounts, plans, tools, and departments), and about what a governance or awareness approach keyed to the enterprise tenant fails to reach.

What it cannot support: claims about how a workforce behaves in general, rates of policy violation, incident or breach rates, or the amount of sensitive data actually exposed. Minutes measure time in a session, not what was pasted. The classifier's error rate is not published, and 12.1% of minutes were ambiguous. Percentages by department and plan are shares of hours in this panel, not of any population of employees. One plan-level figure is flagged by the publisher itself: Gemini Free at 40.5% business use is probably inflated toward personal by Chrome's AI Mode capturing ambient browsing, so treat it as an outlier rather than a finding.

Harmonic sells AI governance tooling and this report is marketing for it. That does not disqualify the data, and it does constrain the claims. The recommendations section of the report argues for the kind of monitoring Harmonic provides. Take the observations; leave the prescriptions to the respondent.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) research sources. CC BY-ND 4.0.
