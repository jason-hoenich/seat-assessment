# SEAT Outcomes

The canonical SEAT outcomes that every framework adapter maps to. Outcome scores are the bridge between the 21 assessment questions and any compliance framework: score the questions, average them into outcomes, then read the outcomes against an adapter in this directory.

## Question to outcome map

| Question | SEAT outcome | Outcome id |
|---|---|---|
| Q1 | Strategic Alignment | `strategic-alignment` |
| Q2 | Governance Documentation | `governance-documentation` |
| Q3 | Executive Support | `executive-support` |
| Q4 | Continuous Improvement | `continuous-improvement` |
| Q5 | Performance Measurement | `performance-measurement` |
| Q6 | Strategic Alignment | `strategic-alignment` |
| Q7 | Strategic Alignment | `strategic-alignment` |
| Q8 | Continuous Improvement | `continuous-improvement` |
| Q9 | Targeted Communication | `targeted-communication` |
| Q10 | Active Participation | `active-participation` |
| Q11 | Targeted Communication | `targeted-communication` |
| Q12 | Cultural Relevance | `cultural-relevance` |
| Q13 | Feedback Responsiveness | `feedback-responsiveness` |
| Q14 | Continuous Improvement | `continuous-improvement` |
| Q15 | Risk Driven Assessment | `risk-driven-assessment` |
| Q16 | Performance Measurement | `performance-measurement` |
| Q17 | Relevant Tailored Training | `relevant-tailored-training` |
| Q18 | Effective Learning Methods | `effective-learning-methods` |
| Q19 | Accessible Inclusive Training | `accessible-inclusive-training` |
| Q20 | Flexible Effective Delivery | `flexible-effective-delivery` |
| Q21 | Integrated Training Lifecycle | `integrated-training-lifecycle` |

To score an outcome, average the scores of every question mapped to it, skipping N/A answers, and round to one decimal.

## Outcome definitions

### Strategy & Governance

- **Strategic Alignment** (`strategic-alignment`) -- scored from Q1, Q6, Q7
- **Governance Documentation** (`governance-documentation`) -- scored from Q2
- **Executive Support** (`executive-support`) -- scored from Q3
- **Continuous Improvement** (`continuous-improvement`) -- scored from Q4, Q8, Q14

### Engagement & Culture

- **Targeted Communication** (`targeted-communication`) -- scored from Q9, Q11
- **Cultural Relevance** (`cultural-relevance`) -- scored from Q12
- **Active Participation** (`active-participation`) -- scored from Q10
- **Feedback Responsiveness** (`feedback-responsiveness`) -- scored from Q13

### Assessment & Metrics

- **Performance Measurement** (`performance-measurement`) -- scored from Q5, Q16
- **Risk Driven Assessment** (`risk-driven-assessment`) -- scored from Q15
- **Behavioral Impact** (`behavioral-impact`) -- **not scored by the core instrument**; see the note below
- **Behavioral Impact Assessment** (`behavioral-impact-assessment`) -- **not scored by the core instrument**; see the note below

### Training & Development

- **Relevant Tailored Training** (`relevant-tailored-training`) -- scored from Q17
- **Effective Learning Methods** (`effective-learning-methods`) -- scored from Q18
- **Accessible Inclusive Training** (`accessible-inclusive-training`) -- scored from Q19
- **Flexible Effective Delivery** (`flexible-effective-delivery`) -- scored from Q20
- **Integrated Training Lifecycle** (`integrated-training-lifecycle`) -- scored from Q21

## Outcomes the core instrument does not score

Two outcomes, `behavioral-impact` and `behavioral-impact-assessment`, are referenced by adapters but are not scored by any of the 21 core questions. In the hosted assessment they are scored by additional framework-specific questions that are outside this core instrument. Here, any requirement mapped to them is reported as **not assessed** rather than as a gap, and is excluded from the overall alignment score. Reporting them as gaps would mark every program as failing a requirement it was never asked about, and would drag every score down by a fixed amount. If you need those outcomes scored, the hosted assessment at https://app.humanrisk.com asks the additional questions.

The two ids also overlap in meaning. Both are load-bearing across the adapters, so both are retained here exactly as published and are not merged in this export.

## A known overlap, documented honestly

If an adapter references one and your scoring covers the other, treat them as the same outcome.

---

Part of the [SEAT Assessment](https://github.com/jason-hoenich/seat-assessment) framework adapters. CC BY-ND 4.0.