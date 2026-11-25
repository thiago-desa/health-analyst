# AGENTS.md

Short, high-signal instructions for coding agents working in `health-analyst`.

## What this repo is

A sanitized proof-of-work snapshot of a health analyst Grok Bot. Markdown skills, a knowledge-graph framework, evals, and docs are the product. There is no service binary to compile.

## Layout

| Path | Role |
|------|------|
| `agents/` | Sanitized bot definition |
| `skills/` | Prefixed skills that match the published template, including the operating framework |
| `graphs/` | Longer dated framework overlay and graph schema |
| `docs/` | Architecture, workflow, failure modes, sources |
| `evals/` | Golden set of fictional review and safety cases |
| `examples/` | Fictional review only |
| `scripts/check.py` | Hygiene CI entrypoint |

## Commands

```bash
python scripts/check.py
```

## Hard boundaries

- Not medical advice. Never diagnose, prescribe, change a medication, or tell someone to skip a clinician.
- Never invent lab values, imaging findings, variant classifications, guideline grades, capabilities, or a track record. If a source is down or stale, say so.
- Never commit secrets, personal data, or any real labs, imaging, genome, diagnoses, medications, symptoms, or other health data, even paraphrased.
- Examples and evals must stay clearly fictional patients and clearly fictional results.
- Urgent red flags: tell the person to seek care now. Do not soften that into a wait-and-see plan.
- No em dashes or en dashes in prose.
- Do not claim capabilities the source bot does not have (no packed reminder routine, no live clinical database, no completed public case archive in this snapshot).
- Leave dated guidelines and database records with a provenance date. Re-check aging facts before treating them as current.
- Keep skill filenames prefixed (`health-...`). The shared Grok Bot skill library requires unique names.
- Skills must not point at repo-only paths. The packed skill has to work inside a Grok Bot that does not have this repository.

## Definition of done

- New analysis behavior is reflected in the matching `skills/health-*.md` file and has a golden-set case (Must / Must-not).
- Offline, stale-data, urgent-escalation, and quiet paths stay documented in `docs/failure-modes.md` and `evals/golden-set.md`.
- `python scripts/check.py` passes. README import link is the published `https://x.ai/bot/...` URL once the owner pastes it, or an explicit placeholder until then.
- Template parity holds: skill names, no packed routine, and the memories listed in the README still match the template.
- No advice, diagnosis, or prescription language slipped into examples or skills.
- No real health data is present, even paraphrased.

## Ownership

Maintained by Thiago De Sa. Irreversible git / GitHub actions (new public repo, first push, force-push, delete, visibility change) need the owner's explicit approval even when an agent stages the work. Normal pushes of small improvements to this existing repo are fine once it is public.
