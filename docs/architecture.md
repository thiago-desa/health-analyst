# Architecture

health-analyst is a health analyst Grok Bot. The design is a dated evidence graph plus a verification layer and explicit safety gates. There is no packed reminder or watch routine.

## Goals

When the owner asks a health question or shares a report:

1. Stratify the person only with facts they provided or that appear in the report
2. Walk the matching process graph (preventive, genomic, report reading, or diagnostic reasoning)
3. Cite current primary sources with a date, and state uncertainty and test limits
4. Escalate urgent red flags to in-person care now
5. Never present the output as medical advice, a diagnosis, or a treatment plan

## Super-agent characteristics (where they fit)

- **Continuous:** one persistent analyst identity that re-reads the `health-expert-graph` skill before analysis.
- **Verification:** a produce, check, correct loop on every major review. Claims need a source and a strength-of-evidence note.
- **Persistent:** memories and the framework skill can carry consented, owner-provided context across days. This public repo never stores that context.
- **Not claimed here:** a packed checkup reminder, a multi-worker clinical desk, a live patient graph database, or a public case archive. This snapshot is a single conversational bot.

## Two loops

### Conversational loop

The owner asks a question or attaches a report. The bot loads the `health-expert-graph` skill, gathers current guideline and database pages, walks the matching process graph, and answers in plain language with citations, limitations, and the educational disclaimer.

### Scheduled loops

None are packed. If the owner later asks for a reminder (for example, "nudge me when a repeat lab is due"), set it up only after they agree, and keep it out of a fresh template import. If no question was asked and no new report arrived, send nothing.

## Grounding and verification

- Primary guidelines and curated databases are first-class sources.
- The report's own units, method, and reference ranges beat a remembered typical range.
- Consumer genetics panels are selected-variant tests. A "variant not detected" result does not rule a condition out.
- Contradictions are surfaced, not averaged away.
- Aging guideline grades and database records carry a November 2026 review date and a re-check rule (`docs/sources.md`).

## Context budget

Keep the person-specific facts they just provided, the findings under review, the sources opened this run, and the safety-gate outcome. Do not paste the entire framework into a review. Retrieve a lane (preventive, genomic, report, or diagnostic) when that lane is needed.

## Tools

- Web search and fetch of public guideline and database pages (USPSTF, ClinVar, gnomAD, ClinGen, local task-force pages, lab catalogs).
- File reading for reports the owner attaches in the chat.
- The packed skills. This repo also keeps the longer overlay in `graphs/`.

No electronic health record hookup, no clinical laboratory API, and no prescribing system are part of this design.

## What this repo is

A public-ready snapshot of the agent definition, framework, skills, evals, and a fictional review, kept in parity with the published Grok Bot template once the share link is added. It is not a clinic, not a medical-device software package, and not an archive of real reviews.
