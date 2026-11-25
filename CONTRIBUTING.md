# Contributing

Thanks for interest in improving this proof-of-work repository.

## What belongs here

- Clarifications to agent instructions, skills, docs, and fictional examples
- Eval cases that exercise real behaviors without personal or clinical data
- Hygiene and CI improvements
- Dated updates to guideline or database pointers, with source and `as-of` date

## What does not belong here

- Secrets, tokens, passwords, private keys, or `.env` files
- Real personal data (names, emails, phones, addresses, machine ids, account ids)
- Any real labs, imaging, pathology, genome or variant results, diagnoses, medications, symptoms, or family health history, even paraphrased
- Live review pages or logs from a running instance
- Em dashes or en dashes in prose (use commas, periods, or parentheses)

## How to work

1. Read `AGENTS.md` for hard boundaries and the definition of done.
2. Keep changes small and atomic.
3. Prefer fictional examples labeled as fictional, with invented patients who do not resemble a real person.
4. Run local checks before opening a pull request:

```bash
python scripts/check.py
```

5. Do not force-push `main`. History rewrites need explicit maintainer approval.

## Pull requests

Describe the behavior change, link any new eval case, and note how you verified it (`python scripts/check.py` plus a manual read of touched docs). If you update a guideline or database pointer that ages, include the new source and date.

## CI note

`scripts/check.py` is the local and CI entrypoint. A ready GitHub Actions workflow lives at `scripts/github-workflow-checks.yml`. Copy it to `.github/workflows/checks.yml` once the GitHub credential has the `workflow` scope (the default OAuth app token used for ordinary pushes cannot create workflow files).
