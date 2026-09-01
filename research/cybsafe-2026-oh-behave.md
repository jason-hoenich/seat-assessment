# CybSafe Oh, Behave! 2025-2026

Population-level data on what people actually do, mapped to the SEAT outcomes it informs.

**Publisher:** CybSafe, with Dr. Suzie Dobrontei and Dr. Jason R.C. Nurse
**Coverage:** Annual cybersecurity attitudes and behaviors study
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
| AI use is mainstream | 65% of workers use AI | Relevant Tailored Training | `relevant-tailored-training` | Curriculum that treats AI as an emerging topic rather than a current one |
| Sensitive data goes into unapproved tools | 43% share sensitive data through unapproved AI tools | Risk Driven Assessment | `risk-driven-assessment` | Risk picture that assumes policy prohibition equals workforce behavior |
| Personal experience of cybercrime is common | 44% were victims of cybercrime | Cultural Relevance | `cultural-relevance` | Content pitched at corporate risk that never connects to what people have lived through |
| Deepfake contact is already routine | 34% experienced deepfake scam calls | Effective Learning Methods | `effective-learning-methods` | Training that teaches people to trust a familiar voice or face |

## Notes by outcome

**Risk Driven Assessment (`risk-driven-assessment`).** The 43% figure is the most useful single number here, because it directly measures the gap between a stated policy and actual behavior. A respondent whose AI risk control is an acceptable-use policy, with no measurement of whether it is followed, has an assumption where they need a finding. Use this to argue for measurement rather than for a stricter policy.

**Relevant Tailored Training (`relevant-tailored-training`) and Cultural Relevance (`cultural-relevance`).** The 65% and 44% figures set the audience. Two thirds of the workforce is already using AI, and close to half have personally been hit by cybercrime. Content that addresses neither is speaking to a workforce that does not exist. When a respondent scores low on cultural relevance, this is the evidence that generic content is a measurable miss rather than a stylistic preference.

**Effective Learning Methods (`effective-learning-methods`).** A third of people have already received a deepfake scam call. Verification training that rests on recognizing a familiar voice is teaching a heuristic that has already failed at population scale. The replacement behavior is out-of-band verification, which is specific and testable.

## Provenance and limits

Self-reported survey data from a general population, not from any single organization's workforce. People are unreliable narrators of their own security behavior, and self-report typically understates risky behavior because respondents know what the correct answer sounds like. Treat these figures as a conservative floor.

Because this is population data rather than workplace telemetry, it describes the people an organization hires rather than how they behave inside a given control environment. If the respondent has their own behavioral measurement, prefer it.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) research sources. CC BY-ND 4.0.
