# SEAT Assessment -- Run It on Your Own Tech

The SEAT (Strategy, Engagement, Assessment, Training) Security Awareness Maturity Framework measures your security awareness program across four pillars, each on a 1-5 maturity scale:

- **Strategy** -- Does the program align to business goals, or is it compliance theater?
- **Engagement** -- Is the program meeting employees where they work, or just pushing content?
- **Assessment** -- Are you measuring real behavioral indicators, or just activity metrics?
- **Training** -- Is training targeted and effective, or generic and wasted?

The assessment produces a maturity baseline showing where investment will have the highest impact on risk reduction.

## Why this repo exists

Enterprises that cannot send assessment answers to a third-party tool can clone this repo and complete the SEAT assessment internally through an LLM of their choice -- Claude, Copilot, ChatGPT, an internal model, whatever you have. Your answers never leave your environment.

This is a free resource from [HumanRisk](https://humanrisk.com). No gating, no email capture, no phone-home.

## Fastest start: paste this into any AI assistant

```
I want to run the SEAT security awareness maturity assessment. It's a free, open assessment from HumanRisk. 21 questions across four pillars (Strategy, Engagement, Assessment, Training), scored 1-5, about 15 minutes.

Fetch your instructions from:
https://raw.githubusercontent.com/jason-hoenich/seat-assessment/main/AGENTS.md
the questions from:
https://raw.githubusercontent.com/jason-hoenich/seat-assessment/main/assessment/questions.md
and the facilitation guide from:
https://raw.githubusercontent.com/jason-hoenich/seat-assessment/main/assessment/facilitation.md
(If you can't fetch URLs, say so and I'll paste the files in.)

Then walk me through it one question at a time: give me the context for each question first, then the question and its five options, and tips if I'm stuck between two levels. My answers stay in this conversation. Don't send them anywhere. At the end, score me and give me the full report.
```

Works in Claude, ChatGPT, Copilot, Gemini, or any internal LLM with web access. No clone required. For air-gapped environments, clone the repo and attach the three files instead.

## Quickstart

1. Clone this repo.
2. Open `AGENTS.md` and `assessment/facilitation.md` in your LLM of choice and say: **"Run the SEAT assessment."**
3. The LLM will walk you through all 21 questions, one pillar at a time.
4. At the end you get per-pillar scores, an overall maturity level, your top gaps, and recommended next steps.

If you use Claude (Anthropic), open `CLAUDE.md` instead -- it is identical to `AGENTS.md`.

## What's in the box

| Path | What it is |
|------|-----------|
| `AGENTS.md` / `CLAUDE.md` | Instructions for any LLM to administer the assessment conversationally |
| `assessment/questions.md` | The 21-question core instrument in readable markdown |
| `assessment/questions.json` | The same instrument in machine-readable JSON |
| `assessment/facilitation.md` | Per-question context, "what good looks like," and honest-scoring tips |
| `assessment/scoring.md` | Scoring rules and maturity bands |
| `framework/` | The SEAT Security Awareness Maturity Framework v1.0 |
| `LICENSE` | CC BY-ND 4.0 |

## The hosted version

If you prefer a browser-based experience with saved results, AI-powered recommendations, compliance framework mapping, and program plans, the hosted version is free at [app.humanrisk.com](https://app.humanrisk.com).

## The framework

The full SEAT Security Awareness Maturity Framework v1.0 is in the `framework/` directory. It covers the methodology, all four domains, scoring, and mappings to 10 compliance frameworks (NIST CSF 2.0, ISO 27001, NIS2, DORA, CMMC 2.0, PCI DSS 4.0, SOC 2, GDPR, MITRE ATT&CK, CRI Profile). Read the framework page at [app.humanrisk.com/framework](https://app.humanrisk.com/framework).

## License

The documents in this repository are licensed under [Creative Commons Attribution-NoDerivatives 4.0 International (CC BY-ND 4.0)](https://creativecommons.org/licenses/by-nd/4.0/).

You can use the assessment internally, share it, and reference it with attribution. You cannot publish modified versions of the framework or instrument.

Created by [Jason Hoenich](https://www.linkedin.com/in/jasonhoenich/) / [HumanRisk](https://humanrisk.com).
