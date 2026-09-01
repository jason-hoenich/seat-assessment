# Fable Security AI Behavior Index, Vol. 1

Measured security detections across AI-using employees, mapped to the SEAT outcomes it informs.

**Publisher:** Fable Security
**Coverage:** 90 days of client security detections across roughly 290,000 employees in 30+ organizations
**Published:** 2026-06-01
**Source last updated:** 2026-08-31
**Official reference:** https://www.fablesecurity.com/research
**Source id:** `fable-abi-2026`
**Source type:** Security detection telemetry (measured behavior, not survey)

## How an assistant applies this source

You need the respondent's per-question scores (1-5) and their outcome scores, produced by the flow in `AGENTS.md` and `adapters/outcomes.md`. Then:

1. **Compute outcome scores first.** Every finding below is anchored to SEAT outcomes by outcome id.
2. **Findings are evidence, never scores.** Nothing here changes a score, adds a requirement, or creates a gap. Compliance status comes only from `adapters/`.
3. **Only use figures that appear in this file.** Do not supply numbers from your own knowledge of this report or any other.
4. **Attribute every figure,** and state that it is measured detection data rather than survey data, since that is what makes it unusual.
5. **Carry the causation caveat.** The publisher frames these findings as correlation, not causation. Do not let a respondent walk away believing AI use causes the behavior differences reported here.
6. **This is the source for role-based targeting arguments.** Its most useful property is that it breaks risk down by job function, which is exactly the evidence a respondent needs when arguing against uniform delivery.

## Findings mapped to SEAT outcomes

| Finding | Figure | SEAT outcome | Outcome id | What a low score here exposes |
|---|---|---|---|---|
| Most AI use is invisible to tooling | 34% of employees had a detectable standalone AI app, but over 91% are in at least one app with embedded AI | Risk Driven Assessment | `risk-driven-assessment` | AI risk scoped to the tools security can see, which is a third of the real surface |
| AI users are better at set-once controls | 36% less likely to be missing MFA, 43% less likely to trigger a new DLP alert | Performance Measurement | `performance-measurement` | Metrics that treat AI users as a uniformly risky population rather than a mixed one |
| AI users are worse at repeated choices | 3.2x more likely to browse unsafely, 3.7x more likely to be overdue on required training | Effective Learning Methods | `effective-learning-methods` | Program design that assumes a one-time control fixes a recurring behavior |
| Risk is concentrated by role | Administration and Governance staff are 24x more likely than other AI users to be risky phishing-link clickers | Targeted Communication | `targeted-communication` | Identical content to every role, when risk varies by more than an order of magnitude |
| The policy authors are the riskiest cohort | The group that writes AI acceptable-use policy has the highest AI file-upload rate at 79.6% and the worst MFA gap at 11.97% | Governance Documentation | `governance-documentation` | Policy written by a population that is not itself measured against it |
| Technical staff carry a distinct risk | Technology staff are 3.3x more likely to trigger a new credential-theft alert | Relevant Tailored Training | `relevant-tailored-training` | Engineering exempted from training, or given the same module as everyone else |
| Role differences survive controls | AI-enabled Administration and Governance staff are still 23.5x more likely to be risky clickers than same-role peers | Risk Driven Assessment | `risk-driven-assessment` | Segmentation by department alone, without accounting for tool usage within the department |
| Erosion is not inevitable | Finance has one of the highest AI adoption rates at 52.3% file-upload and the lowest training-overdue rate at 0.85% | Active Participation | `active-participation` | Fatalism about AI risk, when at least one function demonstrates high adoption with strong behavior |

## Notes by outcome

**Risk Driven Assessment (`risk-driven-assessment`).** The 34% versus 91% gap is the headline. Any AI risk assessment built on discoverable AI logins is measuring roughly a third of actual exposure, because embedded AI features inside already-approved applications do not show up as AI use. A respondent scoring low here who tells you they have AI covered because they blocked certain tools has a visibility problem rather than a control problem.

**Targeted Communication (`targeted-communication`) and Active Participation (`active-participation`).** The role breakdown is the strongest argument in this file against uniform delivery, because the variance is measured rather than assumed. The Finance finding matters just as much as the Administration and Governance one: it demonstrates that high AI adoption and strong security behavior coexist, which prevents the whole file from being read as an argument to restrict AI.

**Effective Learning Methods (`effective-learning-methods`).** The split between set-once controls and repeated discretionary behavior is a design insight, not just a statistic. It suggests that where a behavior can be converted into a one-time configuration it should be, and that training effort should concentrate on the behaviors that genuinely recur. Use this when a respondent is deciding where to spend limited hours.

**Governance Documentation (`governance-documentation`).** The finding that legal, compliance, risk, and HR are the riskiest AI-enabled cohort is uncomfortable and worth stating plainly, because those functions typically author the AI policy and typically exempt themselves from the measurement. Frame it as a scope question rather than as a criticism of those teams.

## Provenance and limits

Measured detection data rather than self-report, which makes it stronger than survey evidence on behavior. It is drawn from one vendor's client base of 30+ organizations, so it is not a census and skews toward organizations that deploy behavioral security tooling.

The publisher frames the findings as correlation, not causation, and describes them as a behavioral floor rather than a ceiling. The reason is important and worth passing on: undetected embedded AI use gets counted in the non-AI comparison group, which means the real differences between AI users and non-users are probably understated rather than overstated.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) research sources. CC BY-ND 4.0.
