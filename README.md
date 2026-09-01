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

## Quickstart

1. Clone this repo.
2. Open `AGENTS.md` in your LLM of choice and say: **"Run the SEAT assessment."**
3. The LLM will walk you through all 21 questions, one pillar at a time.
4. At the end you get per-pillar scores, an overall maturity level, your top gaps, and recommended next steps.
5. When it offers, pick a compliance framework and it will map your results against that framework locally.
6. When it offers, pick a research source and it will read your weakest outcomes against published threat and benchmark data, locally.

If you use Claude (Anthropic), open `CLAUDE.md` instead -- it is identical to `AGENTS.md`.

Not sure what to ask for beyond the assessment itself? [Run the Framework With Any AI](https://app.humanrisk.com/framework/llm) has fourteen copy-paste prompts built on these files: running a single pillar, mapping your results to a compliance framework, building the staffing business case, reading your results against published research, and turning your gaps into a 90-day plan.

Working from URLs instead of a clone? Point your assistant at `AGENTS.md`, `assessment/questions.md`, and `adapters/outcomes.md`, and let it fetch individual adapter files on demand. Cloning is the safer default, because an assistant fetching live URLs picks up whatever those files say at that moment. If you are running this against sensitive results, review the files once and then reference them pinned to that commit SHA rather than to `main`. `SECURITY.md` shows the URL form and explains why.

## What's in the box

| Path | What it is |
| --- | --- |
| `AGENTS.md` / `CLAUDE.md` | Instructions for any LLM to administer the assessment conversationally |
| `assessment/questions.md` | The 21-question core instrument in readable markdown |
| `assessment/questions.json` | The same instrument in machine-readable JSON |
| `assessment/scoring.md` | Scoring rules and maturity bands |
| `assessment/facilitation.md` | Per-question context: why each question exists, what strong looks like, and the trap that inflates scores |
| `adapters/` | 16 compliance and AI governance framework mappings, applied locally by your assistant |
| `adapters/outcomes.md` | The SEAT outcome definitions and the question-to-outcome map |
| `adapters/index.json` | All mappings in machine-readable form |
| `research/` | Published research sources, mapped to SEAT outcomes and applied locally |
| `research/sources.md` | What a research source may and may not do, and how an assistant applies one |
| `research/index.json` | All research sources in machine-readable form |
| `framework/` | The SEAT Security Awareness Maturity Framework v1.0 |
| `SECURITY.md` | Canonical sources, tamper guidance, and how to pin a commit |
| `LICENSE` | CC BY-ND 4.0 |

## Compliance mapping, run locally

The `adapters/` directory carries the same outcome-to-requirement mappings the hosted platform uses, so framework mapping runs entirely in your own environment. Each adapter file contains the full mapping table, the evidence each requirement expects, and the rules your assistant applies to decide met vs. gap.

Compliance: NIST CSF 2.0, ISO 27001, NIS2, DORA, CMMC, PCI DSS 4.0, SOC 2, GDPR, MITRE ATT&CK, CRI Profile.

AI governance: EU AI Act, NIST AI RMF, ISO 42001, OWASP LLM Top 10, OWASP ASI 2026, MITRE ATLAS.

Scoring uses per-assurance-level thresholds rather than one global cutoff: Required at 4.5 or above, Expected at 2.5, Recommended at 1.5. The overall alignment score is weighted and reported on a 0 to 5 scale. The exact rules are in every adapter file and in `adapters/index.json`.

## Research context, run locally

A maturity score tells you where a program is weak. It does not tell you what that weakness costs. The `research/` directory carries published research mapped to the same SEAT outcomes the adapters use, so your assistant can read your weakest outcomes against external evidence without sending anything anywhere.

Current sources: the CrowdStrike 2026 Threat Hunting Report for observed attacker tradecraft, the SANS 2026 Security Awareness and Culture Report for practitioner staffing benchmarks, CybSafe's Oh, Behave! 2025-2026 for workforce behavior, and the Fable Security AI Behavior Index for measured AI behavior broken out by role.

Research explains exposure. It never changes a score, never creates a gap, and never determines compliance status, which is what the adapters are for. `research/sources.md` states those limits and explains which kind of evidence supports which kind of argument, since a practitioner survey and threat telemetry cannot prove the same things. Every figure lives in its source file, and your assistant is instructed not to supply numbers from its own memory, which is what keeps a reading reproducible rather than improvised.

These are summaries of published third-party research, presented with attribution and a link to each original. They are not a substitute for reading the source reports.

## The hosted version

If you prefer a browser-based experience with saved results, AI-powered recommendations, compliance framework mapping, and program plans, the hosted version is free at [app.humanrisk.com](https://app.humanrisk.com).

## The framework

The full SEAT Security Awareness Maturity Framework v1.0 is in the `framework/` directory. It covers the methodology, all four domains, scoring, and the framework mappings. Read the framework page at [app.humanrisk.com/framework](https://app.humanrisk.com/framework).

## License

The documents in this repository are licensed under [Creative Commons Attribution-NoDerivatives 4.0 International (CC BY-ND 4.0)](https://creativecommons.org/licenses/by-nd/4.0/).

You can use the assessment internally, share it, and reference it with attribution. You cannot publish modified versions of the framework or instrument.

Created by [Jason Hoenich](https://www.linkedin.com/in/jasonhoenich/) / [HumanRisk](https://humanrisk.com).
