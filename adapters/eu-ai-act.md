# EU AI Act

**Version:** 2024/1689 (Digital Omnibus, June 2026)
**Last Updated:** 2026-07-08
**Official Reference:** https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689

Mapping of SEAT outcomes to EU AI Act obligations for providers and deployers, centered on the Article 4 AI literacy duty as amended by the Digital Omnibus on AI (June 2026).

Art. 4 (AI literacy) is a direct legal duty, in force, softened by the Omnibus from "ensure" AI literacy to "take measures to support the development of" AI literacy. Measures-based framing makes documented program evidence the natural compliance artifact. Art. 50 (transparency) applies from 2 August 2026; staff who operate or publish output from AI systems need to understand disclosure obligations. Art. 26 (deployer obligations, including human oversight competence) is noted where relevant, but high-risk obligations are deferred (Annex III stand-alone systems to 2 Dec 2027, Annex I product-embedded to 2 Aug 2028). Extraterritorial like GDPR: US organizations placing AI systems on the EU market or whose system output is used in the EU are in scope.

## How an assistant applies this adapter

Given per-question maturity scores (1-5), compute outcome scores by averaging the scores of all questions that map to each SEAT outcome (see outcomes.md for the mapping). Then for each requirement below:

- **Met:** outcome score >= threshold for that requirement's assurance level
- **Partial:** outcome score > 0 but below threshold
- **Gap:** outcome score is 0 or no questions answered for that outcome

Thresholds by assurance level:
- Required: >= 4.5
- Expected: >= 2.5
- Recommended: >= 1.5

For gaps and partial results on Required or Expected requirements, list the missing evidence types.

## Outcome-to-Requirement Mapping

| SEAT Outcome | Framework Reference | Assurance | Evidence Required | Weight | Notes |
|---|---|---|---|---|---|
| strategic-alignment | Art. 4 | Expected | Policy Document, Assessment Report | 4 | Art. 4 measures must account for the context in which AI systems are used and the persons they are used on. An AI literacy program disconnected from how the organization actually deploys AI does not satisfy the duty. Program strategy should inventory AI use cases and align literacy measures to them. Cadence: Annual. |
| governance-documentation | Art. 4 | Required | Policy Document, Training Record, Assessment Report | 5 | The Omnibus reframed Art. 4 from an outcome guarantee to demonstrable measures. That makes documentation the compliance artifact: what measures were taken, for whom, on what basis, reviewed when. An undocumented literacy effort is legally indistinguishable from no effort. Cadence: Annual. |
| executive-support | Art. 4 | Expected | Board Minutes, Training Record | 3 | Art. 4 applies to staff and other persons dealing with the operation and use of AI systems on the organization's behalf, which includes decision-makers who approve AI deployments. Management that mandates AI adoption without understanding its failure modes undermines the duty. Cadence: Annual. |
| continuous-improvement | Art. 4, Art. 50 | Expected | Assessment Report, Policy Document | 3 | AI systems, use cases, and obligations change faster than annual training cycles. Art. 50 transparency obligations apply from 2 August 2026 with watermarking for already-marketed systems grace-perioded to 2 December 2026; literacy measures need a review loop that tracks these dates and new deployments. Cadence: Continuous. |
| targeted-communication | Art. 4 | Required | Communication Artifact, Curriculum Document, Training Record | 5 | Art. 4 explicitly requires measures to take into account technical knowledge, experience, education and training of staff, and the context of use. A single generic AI awareness module for the whole workforce fails this on its face. Persona-targeted delivery is written into the article. Cadence: Continuous. |
| active-participation | Art. 4, Art. 50 | Recommended | Feedback Survey, Incident Report | 3 | Shadow AI use is the practical failure mode of AI literacy. A program where employees disclose AI use and report AI-related concerns produces the behavioral evidence that literacy measures are working; a program where AI use stays hidden produces none. Cadence: Continuous. |
| performance-measurement | Art. 4 | Expected | Metric Report, Assessment Report | 4 | Art. 4 does not mandate effectiveness measurement the way NIS2 Art. 21(2)(f) does; completion of a literacy course can technically count as a measure. But "appropriate" measures invite the question of appropriateness, and measured programs are far easier to defend to a market surveillance authority than certificate binders. Cadence: Annual. |
| risk-driven-assessment | Art. 4 | Expected | Assessment Report, Policy Document | 4 | Appropriate measures scale with the risk of the AI systems in use. Literacy measures for staff operating consequential systems should be deeper than for casual chatbot users. A risk-tiered training map is the natural evidence that proportionality was considered. Cadence: Annual. |
| relevant-tailored-training | Art. 4 | Required | Curriculum Document, Training Record | 5 | The core of the duty. AI literacy training tailored to role, prior knowledge, and the specific systems in use, covering both operating AI competently and recognizing its risks (hallucination, over-reliance, data leakage, deepfakes). Generic AI 101 content for everyone is the compliance-theater version. Cadence: Annual. |
| accessible-inclusive-training | Art. 4 | Required | Training Record, Metric Report | 4 | Art. 4 covers staff and other persons operating or using AI systems on the organization's behalf, which reaches contractors and third parties, not just employees. Coverage reporting across the full population in scope is the evidence. Cadence: Continuous. |
| integrated-training-lifecycle | Art. 4, Art. 26 | Expected | Training Record, Curriculum Document | 3 | Literacy needs change when a person's AI exposure changes: onboarding, new tool rollouts, role changes into AI-operating positions. Art. 26 human oversight competence requirements for high-risk deployers (deferred to Dec 2027 / Aug 2028) will raise the bar for specific roles; building the lifecycle now avoids retrofitting later. Cadence: Onboarding. |
