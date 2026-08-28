# NIST AI Risk Management Framework (AI RMF 1.0)

Mapping of SEAT outcomes to the NIST AI RMF 1.0 GOVERN, MAP, MEASURE, and MANAGE subcategories, with Generative AI Profile (NIST-AI-600-1) context where it sharpens the mapping. Extends security awareness program maturity to organizational AI risk governance and workforce AI literacy.

**Version:** 1.0  
**Adapter last updated:** 2026-07-08  
**Official reference:** https://www.nist.gov/itl/ai-risk-management-framework  
**Adapter id:** `nist-ai-rmf`

## How an assistant applies this adapter

You need the respondent's per-question scores (1-5) from `assessment/questions.md`, produced by the flow in `AGENTS.md`. Then:

1. **Compute each outcome score.** Every outcome is scored from the questions listed for it in `adapters/outcomes.md`. Average those question scores, skipping any answered N/A, and round to one decimal.
2. **Decide met or gap, per assurance level.** The threshold depends on the row's assurance level, not a single global number:
   - Required: outcome score >= 4.5
   - Expected: outcome score >= 2.5
   - Recommended: outcome score >= 1.5
   At or above the row's threshold is **met**. Below it is a **gap**. There is no partial state; the platform scores this as met or not met, and this export matches it.
3. **Rows marked "Not assessed".** Some requirements map to a SEAT outcome that no core question feeds. Report these as **not assessed**, never as a gap, and leave them out of the overall score entirely. A gap means the program was measured and fell short. Not assessed means the 21-question core instrument does not cover it. Say so plainly, list the evidence the framework expects so the respondent knows what it would take, and note that the hosted assessment at https://app.humanrisk.com asks the additional framework-specific questions that score these outcomes.
4. **List missing evidence.** For any row that is a gap at Required or Expected assurance, report that row's evidence types as missing evidence together with its framework reference.
5. **Compute the overall alignment score.** Using only the scored rows: the effective score is the outcome score when met, and `(outcome score / 5) * threshold * 0.5` when it is a gap, which is the penalty the platform applies. Multiply each effective score by the row weight, sum, and divide by the total weight of the scored rows. Round to one decimal. The result is on a 0 to 5 scale, not a percentage.

Report the overall score, met/gap per requirement, any not-assessed requirements, and missing evidence for each gap. Do not invent requirements that are not in the table below, and never answer the assessment questions on the respondent's behalf.

## Mapping table

| SEAT outcome | Outcome id | Framework reference | Assurance | Evidence expected | Cadence | Weight | Scored |
|---|---|---|---|---|---|---|---|
| Strategic Alignment | `strategic-alignment` | GOVERN 1.1, GOVERN 1.2 | Required | Policy Document, Assessment Report | Annual | 5 | Yes |
| Governance Documentation | `governance-documentation` | GOVERN 1.2, GOVERN 2.1 | Required | Policy Document, Assessment Report | Annual | 5 | Yes |
| Executive Support | `executive-support` | GOVERN 2.3 | Required | Board Minutes, Policy Document | Semi-Annual | 5 | Yes |
| Continuous Improvement | `continuous-improvement` | GOVERN 1.5, MANAGE 4.2 | Expected | Assessment Report, Incident Report | Quarterly | 4 | Yes |
| Targeted Communication | `targeted-communication` | GOVERN 4.1; NIST-AI-600-1 GOVERN 4.1 actions | Required | Communication Artifact, Training Record, Curriculum Document | Continuous | 5 | Yes |
| Cultural Relevance | `cultural-relevance` | GOVERN 4.1, MAP 5.2 | Recommended | Communication Artifact, Feedback Survey | Continuous | 2 | Yes |
| Active Participation | `active-participation` | GOVERN 4.3, MANAGE 4.3 | Expected | Incident Report, Feedback Survey | Continuous | 4 | Yes |
| Feedback Responsiveness | `feedback-responsiveness` | MEASURE 3.3, MANAGE 4.1 | Expected | Feedback Survey, Incident Report | As Needed | 3 | Yes |
| Performance Measurement | `performance-measurement` | MEASURE 2.13 | Required | Metric Report, Assessment Report | Quarterly | 5 | Yes |
| Risk Driven Assessment | `risk-driven-assessment` | MAP 5.1, MEASURE 1.1 | Required | Assessment Report, Policy Document | Semi-Annual | 5 | Yes |
| Behavioral Impact | `behavioral-impact` | MEASURE 2.5; NIST-AI-600-1 MEASURE 2.5 actions | Expected | Simulation Results, Incident Report | Quarterly | 4 | **Not assessed** |
| Behavioral Impact Assessment | `behavioral-impact-assessment` | MEASURE 4.2; NIST-AI-600-1 MEASURE 4.2 actions | Recommended | Simulation Results, Incident Report | Quarterly | 3 | **Not assessed** |
| Relevant Tailored Training | `relevant-tailored-training` | GOVERN 2.2, MAP 3.4 | Required | Curriculum Document, Training Record, Assessment Report | Annual | 5 | Yes |
| Effective Learning Methods | `effective-learning-methods` | GOVERN 2.2, MEASURE 2.13 | Expected | Training Record, Simulation Results, Feedback Survey | As Needed | 4 | Yes |
| Accessible Inclusive Training | `accessible-inclusive-training` | GOVERN 2.2, GOVERN 3.1 | Expected | Communication Artifact, Training Record | Continuous | 3 | Yes |
| Flexible Effective Delivery | `flexible-effective-delivery` | GOVERN 2.2, MANAGE 4.1 | Expected | Training Record | As Needed | 4 | Yes |
| Integrated Training Lifecycle | `integrated-training-lifecycle` | GOVERN 2.2, MANAGE 2.4 | Expected | Training Record | Onboarding | 4 | Yes |

## Mapping notes

**Strategic Alignment (GOVERN 1.1, GOVERN 1.2).** GOVERN 1.1 asks whether legal and regulatory requirements around AI are understood and managed; GOVERN 1.2 asks whether trustworthy-AI characteristics are written into organizational policy. A program strategy that names the AI risks the business carries, rather than reciting generic awareness goals, is the working evidence for both.

**Governance Documentation (GOVERN 1.2, GOVERN 2.1).** GOVERN 2.1 wants roles, responsibilities, and lines of communication for AI risk documented. If nobody can point to the page that says who owns AI acceptable use, who approves new tools, and who trains the workforce, the function is not implemented no matter how good the intentions are.

**Executive Support (GOVERN 2.3).** GOVERN 2.3 places responsibility for AI risk decisions with executive leadership. Board minutes showing leadership reviewed AI risk posture, and funded the program that manages the human side of it, are exactly the artifact an assessor asks for first.

**Continuous Improvement (GOVERN 1.5, MANAGE 4.2).** GOVERN 1.5 requires ongoing monitoring and periodic review of the risk management process itself; MANAGE 4.2 folds measurable improvement into system updates. A program that revises its AI guidance on a schedule, and after incidents, is doing both. One that shipped a policy in 2024 and has not touched it since is doing neither.

**Targeted Communication (GOVERN 4.1; NIST-AI-600-1 GOVERN 4.1 actions).** GOVERN 4.1 asks for organizational practices that foster critical thinking and a safety-first mindset. The GAI Profile sharpens this around the human-AI configuration risk: people over-trusting confident model output. Role-targeted communication teaching staff when to verify AI output is the direct countermeasure. GAI Profile reference is at the subcategory level, not a specific action ID.

**Cultural Relevance (GOVERN 4.1, MAP 5.2).** MAP 5.2 covers practices and personnel for regular engagement with the people the AI affects. Messaging about AI risk that lands with a claims adjuster and a data scientist alike, rather than one generic memo, is what makes the safety-first culture GOVERN 4.1 describes real rather than aspirational.

**Active Participation (GOVERN 4.3, MANAGE 4.3).** GOVERN 4.3 asks for practices that enable AI incident identification and information sharing; MANAGE 4.3 requires incidents and errors to be communicated to the people affected. A workforce that reports odd model behavior, suspected shadow AI, or a deepfake voicemail without fear is the incident-reporting culture both subcategories assume exists.

**Feedback Responsiveness (MEASURE 3.3, MANAGE 4.1).** MEASURE 3.3 requires feedback processes so end users can report problems; MANAGE 4.1 requires post-deployment monitoring that captures and evaluates user input. If employees flag AI problems and nothing visibly changes, the feedback channel exists on paper and the reports stop coming. Closing the loop is the control.

**Performance Measurement (MEASURE 2.13).** MEASURE 2.13 evaluates whether the measurement processes themselves are effective. Read plainly, MEASURE is an effectiveness mandate: it asks whether your controls demonstrably work, not whether they exist. It is the AI-governance analogue of NIS2 Art. 21(2)(f), and completion rates do not answer it. Maturity scoring over time does.

**Risk Driven Assessment (MAP 5.1, MEASURE 1.1).** MAP 5.1 characterizes likely impacts; MEASURE 1.1 selects metrics for the most significant risks identified in MAP. Assessment effort should follow the risk: the teams wiring AI into payment flows and customer data deserve deeper scrutiny than the ones drafting marketing copy with it.

**Behavioral Impact (MEASURE 2.5; NIST-AI-600-1 MEASURE 2.5 actions).** MEASURE 2.5 demonstrates validity and reliability in deployment conditions. The GAI Profile names confabulation as a headline risk here: models asserting false things fluently. Whether people catch and question plausible-but-wrong AI output, measured through realistic exercises rather than assumed, is the human half of that validity question. GAI Profile reference is at the subcategory level, not a specific action ID.

**Behavioral Impact Assessment (MEASURE 4.2; NIST-AI-600-1 MEASURE 4.2 actions).** MEASURE 4.2 tracks trustworthiness in the deployment context using input from domain experts and AI actors over time. The GAI Profile frames the information integrity risk this serves: repeated behavioral measurement shows whether the workforce is getting better or worse at spotting synthetic and manipulated content, which a point-in-time check cannot. GAI Profile reference is at the subcategory level, not a specific action ID.

**Relevant Tailored Training (GOVERN 2.2, MAP 3.4).** GOVERN 2.2 is where workforce AI literacy lives in the framework: personnel and partners receive AI risk management training. MAP 3.4 adds operator and practitioner proficiency requirements. Together they mandate training scoped to what each role does with AI, not one generic module for everyone.

**Effective Learning Methods (GOVERN 2.2, MEASURE 2.13).** GOVERN 2.2 training only counts if it changes what people do, and MEASURE 2.13 obligates you to check. Hands-on methods, like exercises against real model output and deepfake samples, teach recognition in a way slideware does not, and they generate the effectiveness evidence MEASURE asks for as a byproduct.

**Accessible Inclusive Training (GOVERN 2.2, GOVERN 3.1).** GOVERN 3.1 values diverse perspectives in AI risk decisions, and GOVERN 2.2 does not scope literacy to the engineering org. AI risk shows up wherever AI is used, which is now everywhere, so literacy material has to be understandable to the whole workforce, not just the people who ship models.

**Flexible Effective Delivery (GOVERN 2.2, MANAGE 4.1).** AI risks move faster than annual training cycles; MANAGE 4.1 post-deployment monitoring will keep surfacing new failure modes. Delivery that can push updated guidance within days of a new threat pattern, a jailbreak technique or a fresh deepfake scam, keeps GOVERN 2.2 literacy current instead of historical.

**Integrated Training Lifecycle (GOVERN 2.2, MANAGE 2.4).** MANAGE 2.4 requires mechanisms to supersede, disengage, or deactivate AI systems behaving outside intent. That human-oversight mechanism only works if the people near the system know it exists and when to pull it. Embedding AI oversight expectations from onboarding onward, and refreshing them at role changes, makes the kill switch a practiced habit rather than a document.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.