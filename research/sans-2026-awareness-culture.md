# SANS 2026 Security Awareness and Culture Report

Practitioner benchmark data on program staffing, maturity drivers, and barriers, mapped to the SEAT outcomes it informs.

**Publisher:** SANS Institute
**Coverage:** 11th annual report, 1,700+ practitioner respondents
**Published:** 2026-08-28
**Source last updated:** 2026-08-31
**Official reference:** https://www.sans.org/security-awareness-training/resources/reports/
**Source id:** `sans-2026`
**Source type:** Practitioner survey

## How an assistant applies this source

You need the respondent's per-question scores (1-5) and their outcome scores, produced by the flow in `AGENTS.md` and `adapters/outcomes.md`. Then:

1. **Compute outcome scores first.** Every finding below is anchored to SEAT outcomes by outcome id. Score those outcomes the normal way before you use anything in this file.
2. **Findings are evidence, never scores.** Nothing here changes a score, adds a requirement, or creates a gap. Compliance status comes only from `adapters/`.
3. **Only use figures that appear in this file.** Do not supply numbers from your own knowledge of this report or any other, and do not update or extrapolate the figures here.
4. **Attribute every figure,** naming the publisher and that it is survey data from practitioners rather than measured outcomes.
5. **The respondent's data wins.** If the respondent says their situation differs, take their word for it and say the benchmark did not match.
6. **This is the source for resourcing arguments.** The staffing figures below are the strongest available external anchor for a headcount case. Use them when the respondent is building one, and do not pad them with invented ROI numbers.

## Findings mapped to SEAT outcomes

| Finding | Figure | SEAT outcome | Outcome id | What a low score here exposes |
|---|---|---|---|---|
| Staffing drives maturity | Culture change requires at least 4.3 dedicated FTEs; behavior change at least 3 | Strategic Alignment | `strategic-alignment` | A program expected to change culture on a fraction of one person's time |
| Program age drives maturity | The most mature programs run 6+ FTEs over 10+ years | Continuous Improvement | `continuous-improvement` | Restarting the program every reorg, so maturity never compounds |
| Time is the top barrier | Lack of time has been the number one program barrier for the fifth-plus consecutive year | Executive Support | `executive-support` | Sponsorship that approves tools but not the hours to run the program |
| Social engineering leads human risk | Ranked the number one human risk by 77% of respondents | Risk Driven Assessment | `risk-driven-assessment` | Risk register that does not name the top-ranked human risk |
| AI risk rising fast | AI moved from the number four human risk to number two in two years | Relevant Tailored Training | `relevant-tailored-training` | Curriculum with no AI content, or AI content limited to policy |
| Practitioners now use AI themselves | 75% of security awareness teams use AI, mostly for content creation | Effective Learning Methods | `effective-learning-methods` | Manual content production consuming the hours the top barrier already limits |
| Compensation benchmark | Average practitioner salary is $123,624 | Executive Support | `executive-support` | A headcount ask with no cost anchor attached |

## Notes by outcome

**Strategic Alignment (`strategic-alignment`).** The 3 and 4.3 FTE figures are the most quotable numbers in this file, because they convert a maturity score into a headcount argument. A respondent scoring low here who also has less than one dedicated FTE is not running an underperforming program, they are running an under-resourced one. Say that plainly. The distinction changes who the recommendation is addressed to.

**Executive Support (`executive-support`).** Pair the time barrier with the salary benchmark when building a case. The persistent finding is that programs stall on hours rather than on knowledge, which means the ask is for capacity, not for tooling. Ask the respondent what leadership currently cares about before framing it.

**Continuous Improvement (`continuous-improvement`).** The 10+ year finding matters for expectation setting. Maturity compounds, so a program two years in that scores as Developing is on track rather than failing. Use this to prevent a respondent from reading a mid-range score as a verdict.

**Risk Driven Assessment (`risk-driven-assessment`) and Relevant Tailored Training (`relevant-tailored-training`).** Social engineering at 77% and AI's climb to number two set the two topics a current curriculum has to cover. If the respondent's training content addresses neither, that is a concrete finding rather than a general observation.

## Provenance and limits

Self-reported practitioner survey data. Respondents are people who work in security awareness and chose to answer a SANS survey, which skews toward practitioners engaged enough with the discipline to participate. Rankings reflect practitioner perception of risk, not measured incident data.

The staffing figures are correlational. Programs with more FTEs score as more mature, which does not by itself establish that adding FTEs produces maturity. It remains the best available external benchmark for the argument, and should be presented as a benchmark rather than as a causal guarantee.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) research sources. CC BY-ND 4.0.
