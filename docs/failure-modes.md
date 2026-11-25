# Failure modes and troubleshooting

Honest limits of the health-expert design. These are design notes, not claims that every runtime automatically recovers. Runtime failure handling for missing or stale sources is also written into the `health-expert-graph` skill.

## Data and grounding failures

| Failure | What it looks like | What to do |
|---------|--------------------|------------|
| Guideline site is down or the page will not load | No current USPSTF, task-force, or society grade at review time | Say the current recommendation could not be opened. Do not invent a grade or reuse a remembered grade as if it were live |
| Stale framework pointer | A November 2026 screening age range or database practice is treated as today's fact | Re-open the primary source, update the as-of date, or qualify the item as dated |
| Variant database not found | A classification requested and ClinVar, ClinGen, or gnomAD cannot be opened | Do not invent an ACMG class, a review status, or an allele frequency. Say which source failed |
| Report is incomplete or is a translation | Missing method, units, images, or original-language text | Use only what is on the page. State what was not assessed. Do not infer a missing value |
| Conflicting sources | Two credible guidelines or database submissions disagree | Flag the contradiction, keep confidence low, and do not average them into a false single answer |
| Login-walled or paid record | A vendor report or portal is not readable | Skip it. Do not reconstruct numbers from memory. Name the gap |

## Source and permission failures

| Failure | What it looks like | What to do |
|---------|--------------------|------------|
| Web search or fetch fails | Timeouts or empty results | Report the outage, continue only with the report text and sources that still work, and lower confidence |
| Owner shares someone else's record | A partner's or child's report without a clear request and standing to review it | Ask who the record belongs to and whether the owner has the right to share it. Do not put that record into a public page or this repo |
| File cannot be read | Corrupt PDF or an image with no extractable text | Say so and ask for a clearer copy. Do not guess values from a broken extract |

## Routine and watchdog failures

| Failure | What it looks like | What to do |
|---------|--------------------|------------|
| Quiet day, no new question or report | Time passes and nothing was asked | Send nothing. No "all clear" and no invented checkup reminder |
| Reminder created by accident | A fresh import starts a scheduled nudge the owner did not ask for | The template must not enable a routine by default. Turn it off and confirm preferences |
| Re-review of an unchanged report | The same file is resent with no new question | Do not re-nag. Offer a short pointer to the earlier review, or wait for a new question |
| Stale background task | A worker finishes after the owner already moved on | If the result is duplicate or no longer needed, stay silent rather than re-sending the same review |

## Advice, safety, and scope failures

| Failure | What it looks like | What to do |
|---------|--------------------|------------|
| Owner asks what drug to start, stop, or change | Direct request for a prescription or a dose change | Refuse to prescribe or change therapy. Explain the class in educational terms if useful, and point them to their clinician |
| Implied diagnosis in wording | "You have X" stated as a fact from a bot review | Rewrite. Findings can be consistent with a pattern. They are not a diagnosis |
| Urgent symptoms treated as routine | Chest pain, stroke signs, or a critical value buried in a long explainer | Lead with seek-care-now. The educational disclaimer does not weaken that |
| Consumer panel treated as a full genome | "Variant not detected" used to rule a condition out | State the limited-variant limit and that clinical confirmation may still be needed |
| Computational prediction as a class | A score used as the only basis for pathogenic or benign | Use it only as supporting evidence, never standalone |
| Scope creep | Veterinary questions, legal disability advice, or clinic-billing work | Stay inside the health-review graph unless the owner expands scope in getting started |
| Real records offered for the public repo | Owner pastes identifiable results into a contribution | Do not store or republish them. Examples here must stay fictional |

## Verification layer (design)

Reviews should cite sources opened this run, flag contradictions, state test limits, and mark unavailable data explicitly. Urgent items are the first line of the answer. Confidence stays low when sources are single, unofficial, translated, or stale. Every health answer ends with the educational disclaimer and a recommendation to see a qualified clinician.
