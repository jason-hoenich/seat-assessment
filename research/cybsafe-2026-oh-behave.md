# CybSafe Oh, Behave! 2025-2026

Population-level data on what people actually do, mapped to the SEAT outcomes it informs.

**Publisher:** CybSafe, with Dr. Suzie Dobrontei and Dr. Jason R.C. Nurse
**Coverage:** 4,573 participants across US, UK, Germany, Australia, India, Brazil, Mexico. Fieldwork May 2 to May 27, 2025
**Published:** 2025-09-29
**Source last updated:** 2026-08-31
**Official reference:** https://www.cybsafe.com/research/
**Source id:** `cybsafe-2026`
**Source type:** Population behavior and attitude survey

## How an assistant applies this source

You need the respondent's per-question scores (1-5) and their outcome scores, produced by the flow in `AGENTS.md` and `adapters/outcomes.md`. Then:

1. **Compute outcome scores first.** Every finding below is anchored to SEAT outcomes by outcome id.
2. **Findings are evidence, never scores.** Nothing here changes a score, adds a requirement, or creates a gap. Compliance status comes only from `adapters/`.
3. **Only use figures that appear in this file.** Do not supply numbers from your own knowledge of this report or any other.
4. **Attribute every figure,** naming the publisher and that it is self-reported behavior from a general population, not from the respondent's own workforce.
5. **The respondent's data wins.** If the respondent has their own behavioral data, that data is better than this benchmark for their organization. Say so.
6. **This is the source for behavior-versus-awareness arguments.** Use it when the respondent needs to show that knowing and doing are different problems, which is the case most awareness programs are built to answer and most metrics fail to make.

## Findings mapped to SEAT outcomes

| Finding | Figure | SEAT outcome | Outcome id | What a low score here exposes |
|---|---|---|---|---|
| AI use flipped in one year | 65% of participants now use AI tools, exactly inverting last year's 65% who used none. 28% use them both at home and work, 29% at home only | Relevant Tailored Training | `relevant-tailored-training` | Curriculum that treats AI as an emerging topic rather than a current one |
| Shadow AI is the norm at work | Among employed participants using AI at work (N=2521), 43% admitted sharing sensitive work information with AI tools without their employer's knowledge, a 5% increase | Risk Driven Assessment | `risk-driven-assessment` | Risk picture that assumes policy prohibition equals workforce behavior |
| The sharing is untrained, not defiant | 58% of AI users received no training on the security and privacy risks of these tools; 52% of employed participants have never received any | Effective Learning Methods | `effective-learning-methods` | Treating shadow AI as a discipline problem when it is a coverage problem |
| What actually gets pasted in | Among those who shared, financial data 42%, confidential business strategies or plans 40%, proprietary code 34%, employee or HR information 30% | Cultural Relevance | `cultural-relevance` | Generic AI warnings that never name the specific data types at risk |
| Sharing skews young | 48% of Gen Z and Millennials shared sensitive work information with AI tools, against 30% of Gen X and 20% of Baby Boomers | Targeted Communication | `targeted-communication` | One message to a workforce where the behavior varies more than twofold by cohort |
| Personal experience of cybercrime is common | 44% of participants had been victims of cybercrime, a 9% increase in one year | Cultural Relevance | `cultural-relevance` | Content pitched at corporate risk that never connects to what people have lived through |
| Deepfake contact is already routine | Over a third (34%) of participants have experienced deepfake scam calls | Effective Learning Methods | `effective-learning-methods` | Training that teaches people to trust a familiar voice or face |

## Notes by outcome

**Risk Driven Assessment (`risk-driven-assessment`).** The 43% figure is the most useful single number here, because it directly measures the gap between a stated policy and actual behavior. State the base when you cite it: it is 43% of employed participants who use AI at work, not 43% of everyone. A respondent whose AI risk control is an acceptable-use policy, with no measurement of whether it is followed, has an assumption where they need a finding. Use this to argue for measurement rather than for a stricter policy.

**Relevant Tailored Training (`relevant-tailored-training`) and Cultural Relevance (`cultural-relevance`).** The 65% and 44% figures set the audience. Note that the 65% covers AI use anywhere, and much of it is personal: 29% use AI at home only, and 28% at both home and work. The workplace-relevant slice is smaller than the headline, so do not present 65% as a workplace adoption rate. Close to half of participants have personally been hit by cybercrime. Content that addresses neither is speaking to a workforce that does not exist.

**Effective Learning Methods (`effective-learning-methods`), on coverage.** The 58% of AI users who received no training on AI risks is the finding that reframes shadow AI. People pasting financial data and proprietary code into AI tools have mostly never been told not to. That makes it a program coverage gap rather than a compliance failure, which changes both the recommendation and who owns it.

**Effective Learning Methods (`effective-learning-methods`), on verification.** A third of people have already received a deepfake scam call. Verification training that rests on recognizing a familiar voice is teaching a heuristic that has already failed at population scale. The replacement behavior is out-of-band verification, which is specific and testable.

## Provenance and limits

Self-reported survey data from a general population, not from any single organization's workforce. People are unreliable narrators of their own security behavior, and self-report typically understates risky behavior because respondents know what the correct answer sounds like. Treat these figures as a conservative floor.

Because this is population data rather than workplace telemetry, it describes the people an organization hires rather than how they behave inside a given control environment. If the respondent has their own behavioral measurement, prefer it.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) research sources. CC BY-ND 4.0.
