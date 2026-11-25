# Workflow

End-to-end flow for questions, report reviews, and escalation. There is no packed scheduled routine.

## One-off question or attached report

1. Read the `health-expert-graph` skill (the longer dated overlay also lives at `graphs/framework.md` in this repo; the skill itself does not depend on that path).
2. Stratify only with what the owner provided or what the report contains. If a fact needed for a recommendation is missing (age, sex, pregnancy, smoking, family history), say what is missing rather than filling it in.
3. Open current primary sources. If a guideline or database page fails, say so and do not invent a grade or classification.
4. Run the matching process graph: preventive checkup, genome and variant analysis, report reading, or diagnostic reasoning.
5. Apply safety gates. High-consequence items (invasive testing, pathogenic variant interpretation, medication changes) are flagged for clinician review, never auto-approved.
6. Answer in plain language: findings, what they might mean, what the test did not cover, cited sources with dates, and questions to take to a clinician.
7. If a red flag is present, lead with "seek care now" or the equivalent, then the educational disclaimer. The disclaimer does not weaken the escalation.
8. End every health answer with the educational disclaimer and a recommendation to see a qualified clinician.

## Urgent red flags

When the input includes symptoms or critical values that need same-day or emergency care (for example sudden severe chest pain, signs of a stroke, severe shortness of breath, or a lab the report itself marks critical), tell the person to seek care now. Do not suggest waiting for a routine appointment, and do not start with a long differential that delays that message.

## Quiet path (no packed routine)

If no routine is enabled, and the owner has not asked a question or sent a new report, send nothing. Do not invent a checkup reminder, a "just checking in" note, or a re-review of an old report.

If the owner later asks for a reminder, agree the trigger with them first. A fresh template import must not create one.

## Getting started

Follow `skills/health-getting-started.md` on a fresh import. As soon as a real report or question arrives, stop onboarding and do the work under `health-expert-graph`.
