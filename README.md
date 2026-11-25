# health-expert

Health expert Grok Bot that reads checkups, labs, imaging, pathology, and consumer genetics through an evidence graph, cites current guidelines, and is not medical advice.

**Not medical advice.** This bot does not diagnose, treat, prescribe, or replace a qualified clinician. Outputs are educational information and structured analysis only. Genetic findings must be interpreted by a clinical geneticist or genetic counsellor. If something looks urgent, the bot should tell the person to seek care now. Always go over results with a clinician.

## Problem it solves

Lab PDFs, imaging reports, and consumer genetics summaries are hard to read together. A useful review has to use the report's own units and ranges, say what a test did not cover, cite the current guideline or database record with a date, and keep high-consequence steps (medication changes, pathogenic variant calls, invasive testing) for a clinician. This design leads with that evidence graph, never invents a missing value or classification, and stays quiet when no one asked and nothing new arrived.

## How to use with Grok Bot

1. The easiest path is to copy the published template (see Import below).
2. Or create a new Grok Bot (suggested name: `health expert`) and paste the contents of `agents/health-expert.md` (the **Description / system instructions** section) into the bot description / instructions.
3. Pack the two skills in `skills/`. Their `health-` prefixes exist because the Grok Bot skill library is shared.
4. On first run, follow `skills/health-getting-started.md`: confirm whose health is in scope, which jurisdiction's guidelines to prefer, how they want reviews delivered, and the not-medical-advice, no-invention, and no em dash writing rules.
5. Do not enable a scheduled routine unless the owner asks for one. The live design has no packed routine.

## Import into Grok Bot

The template import link will be added here once the owner pastes the published share URL.

Placeholder: `https://x.ai/bot/<template-id>`

## Template parity

The published template should pack:

- **Skills:** `health-getting-started` (the getting-started skill) and `health-expert-graph` (the operating framework, evidence hierarchy, safety gates, and canonical sources).
- **Routine:** none. Do not invent a checkup reminder or a watch. Offer a reminder only if the owner asks.
- **Memories:** not medical advice, and tell the person to see a clinician; never invent lab values, variant classifications, guideline grades, or a track record; genetic findings need a clinical geneticist or genetic counsellor for clinical interpretation; urgent red flags mean seek care now; no em dashes; read the `health-expert-graph` skill first; never republish real health records.

`graphs/framework.md` is the longer, dated public overlay behind the packed `health-expert-graph` skill. Keep the two aligned when guideline versions change.

## Disclaimer

Nothing in this repository, its skills, examples, or any review produced from this design is medical advice, a diagnosis, or a treatment plan. It is not a substitute for a licensed clinician, a clinical laboratory, or a genetics service. Examples are clearly fictional and must not be read as real patients or real results. Guideline grades, database records, and lab methods age quickly and must be re-checked against primary sources, with the date of the check shown. If you have symptoms that worry you, or a result marked critical, contact a clinician or emergency services rather than waiting on a bot.

## Key files

| Path | What it is |
|------|------------|
| `agents/health-expert.md` | Full sanitized agent definition |
| `skills/health-getting-started.md` | First-conversation setup (getting-started skill) |
| `skills/health-expert-graph.md` | Operating framework packed in the template |
| `graphs/framework.md` | Longer dated knowledge overlay (November 2026) |
| `graphs/schema.md` | Nodes, edges, and how a query walks the graph |
| `docs/architecture.md` | Design: evidence graph, safety gates, verification, no packed routine |
| `docs/workflow.md` | Intake, analysis, and escalation flow |
| `docs/failure-modes.md` | Offline, stale sources, quiet path, and no-advice paths |
| `docs/sources.md` | Primary sources and re-check policy |
| `examples/fictional-health-review.md` | Fully fictional checkup and consumer-genetics review |
| `ATTRIBUTION.md` | Design influences and research citations |
| `LICENSE` | MIT |
| `AGENTS.md` | Short agent instructions, boundaries, definition of done |
| `CONTRIBUTING.md` | How to propose changes safely |
| `evals/` | Golden-set behavioral regressions |
| `scripts/check.py` | Secrets / PII / em dash / link hygiene checks |
| `scripts/github-workflow-checks.yml` | GitHub Actions workflow (copy to `.github/workflows/checks.yml` when the token has `workflow` scope) |

## Proof-of-work notes

This repository is a cleaned public snapshot of a working Grok Bot design, staged a few days after the live bot was created in November 2026:

- A health-expert operating graph is the core overlay: an evidence hierarchy, safety gates, preventive-care lanes, ACMG/AMP variant interpretation rules, report reading for labs, imaging, and pathology, and structured diagnostic reasoning. The template packs this as the `health-expert-graph` skill.
- In the first working session the bot used that graph to read a checkup report together with a consumer genetics summary, integrate the two, cite current guidelines, state what the tests did not cover, and flag symptoms that would need same-day or emergency care.
- Follow-up questions were answered as educational explainers (a medication class, a common inherited lab pattern, a recessive carrier result), always with a see-a-clinician close and no invented values.
- There is no packed routine. If the owner has not asked a question and no new report has arrived, the bot stays silent rather than inventing a checkup reminder.

The snapshot does not include any real reports, results, or a clinical track record. Do not invent one.

## Review findings

This snapshot applies the portfolio review notes from the start: [docs/review-2026-11-09.md in repo-operational-head](https://github.com/thiago-desa/repo-operational-head/blob/main/docs/review-2026-11-09.md).

## License and attribution

MIT License. Copyright (c) 2026 Thiago De Sa.

Design influences and research citations are listed in `ATTRIBUTION.md`.
