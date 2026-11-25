# Attribution

This proof-of-work repository documents a Grok Bot health analyst design by Thiago De Sa (2026).

## Design influences (ideas, not code)

- Graph-style clinical reasoning: nodes (person, finding, gene, variant, disease, source), edges (supports, contradicts, classified as, associated with), and gates for high-consequence steps.
- Super-agent harness ideas: a produce-check-correct loop, evidence-based verification, and a quiet path when no new question or report has arrived.
- Andrew Ng's AI Engineering skills framing: grounding, evaluation, and production hygiene.
- Agent-repo practice: short `AGENTS.md`, golden Must / Must-not evals, documented failure modes, and a hygiene check from the first commit.

## Research citations in the framework

The November 2026 knowledge overlay in `graphs/framework.md`, and the packed `health-expert-graph` skill, point at publicly available guidelines and databases. None of the following are copied as proprietary text or code. Grades, records, and methods taken from them are dated and must be re-checked:

- U.S. Preventive Services Task Force (USPSTF) recommendation topics, including the A and B list.
- Canadian Task Force on Preventive Health Care, plus the person's local national or provincial programs when those apply.
- ACMG/AMP 2015 variant interpretation standards and ClinGen Sequence Variant Interpretation and VCEP specifications.
- ClinVar, gnomAD, ClinGen gene-disease validity, OMIM, GeneReviews, DECIPHER, and related public genomics resources.
- College of American Pathologists (CAP), CDC laboratory training resources, Mayo Clinic Laboratories test catalog, Radiopaedia, and mypathologyreport.ca as report-reading references.

If a citation in the framework is wrong or outdated, fix it with a new primary source and an `as-of` date rather than leaving a stale claim.

## License

MIT License. Copyright (c) 2026 Thiago De Sa. See `LICENSE`.
