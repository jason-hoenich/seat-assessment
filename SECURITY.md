# Security and Integrity

This repository contains no executable code. It is markdown: an assessment instrument, scoring rules, a facilitation guide, and instructions for AI assistants. Nothing here runs, and nothing here collects data. Your answers stay in your own LLM conversation; the instructions in AGENTS.md explicitly direct assistants to keep them there.

## Canonical sources

Because AI assistants follow the instructions in these files, integrity matters more than it would for ordinary documentation. Treat only these as canonical:

- This repository: https://github.com/jason-hoenich/seat-assessment
- The HumanRisk site: https://app.humanrisk.com (framework and mirrors)

Any other copy, fork, or mirror should be treated as untrusted. In particular, if a copy of AGENTS.md instructs an assistant to send, save, or transmit assessment answers anywhere, it has been tampered with: the canonical instructions forbid exactly that.

## Verifying what your assistant loaded

If your organization requires verification before pointing an internal LLM at external content, pin the specific commit rather than `main`:

```
https://raw.githubusercontent.com/jason-hoenich/seat-assessment/<commit-sha>/AGENTS.md
```

Review the files at that commit once, then reference the pinned URLs. The content at a commit SHA cannot change.

Air-gapped environments: clone the repo, review the three files (AGENTS.md, assessment/questions.md, assessment/facilitation.md), and attach them to your assistant directly. Nothing requires network access.

## Reporting

Found a tampered copy, an impersonating repository, or an integrity concern with this one? Email jason@hoenich.com. For content issues (a question that reads wrong, a scoring edge case), open an issue.

## License boundary

CC BY-ND 4.0: use it internally, share it, reference it with attribution. Publishing modified versions of the instrument or framework is not permitted. This keeps every copy in circulation answerable to the same source of truth, which is a security property as much as a legal one.
