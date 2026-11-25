# Graph schema

A compact map of the nodes and edges in `graphs/framework.md` and the packed `health-expert-graph` skill. This is a reasoning schema, not a live patient database.

## Node types

| Type | What it represents | Notes |
|------|--------------------|-------|
| Person | Age, sex, ancestry, family history, lifestyle, medications, prior diagnoses, as provided | Store only what the owner or the report provided. Never invent a missing field |
| ScreeningRecommendation | Grade, age range, risk modifiers, interval | Must carry source, version, and as-of date |
| LabResult | Analyte, value, units, reference range, method, flag | Prefer the report's own range and units |
| ImagingFinding | Modality, region, description, lexicon score (BI-RADS, LI-RADS, and similar) when present | Correlate clinically. Do not diagnose from a single image description |
| PathologyReport | Specimen, descriptive findings, grade, margins, biomarkers | Separate description from a definitive clinical diagnosis |
| Gene | HGNC symbol, transcript, disease associations | ClinGen validity when available |
| Variant | HGVS, coordinates, transcript, classification, evidence codes | Never invent a class. Follow ACMG/AMP plus VCEP rules |
| Phenotype | HPO terms or plain-language findings | Used to match, not to force, a genotype explanation |
| Disease | OMIM or MONDO id, inheritance, penetrance | Educational context only |
| Source | Database or guideline, version, date | Required on graded or classified claims |

## Edge types

| Edge | From | To | Meaning |
|------|------|----|---------|
| has_risk_factor | Person | a risk factor node | Only if the fact was provided |
| should_receive | Person | ScreeningRecommendation | After guideline and risk-modifier checks |
| classified_as | Variant | Pathogenic, Likely pathogenic, VUS, Likely benign, or Benign | ACMG/AMP five-tier, with evidence codes |
| has_evidence | Variant | ACMGCriterion | PVS1, PS1-4, PM1-6, PP1-5, BA1, BS1-4, BP1-6 |
| observed_in | Variant | Population | gnomAD or similar allele frequency, with ancestry when given |
| associated_with | Gene | Disease | ClinGen validity when available |
| abnormal_in_context_of | LabResult | a condition or pattern | A consistency note, not a diagnosis |
| supports, contradicts, or is_consistent_with | Finding | a hypothesis | Keep both supporting and contradicting edges |

## Walking a query

1. Bind the question to one process lane: preventive, genomic, report reading, or diagnostic reasoning.
2. Stratify the person with provided facts only.
3. Attach sources opened this run. Drop any hop you cannot support.
4. Apply safety gates before high-consequence language (medication changes, pathogenic calls, invasive testing).
5. If a red flag is present, escalate first.
6. If no question and no new report arrived, stay silent.

## What this schema is not

It is not a stored medical record, a live graph database, or a diagnostic device. Persistence in a live bot is memory plus the framework document, and only for facts the owner chose to share. This public repository does not hold those facts.
