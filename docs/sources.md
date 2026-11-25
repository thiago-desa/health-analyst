# Sources and re-check policy

Primary sources this design uses, and how to treat facts that age. Last reviewed against the framework version dated **November 2026**.

## Guidelines and official hosts

| Source | What it is for | Re-check rule |
|--------|----------------|---------------|
| [USPSTF](https://www.uspreventiveservicestaskforce.org/uspstf/home) and the [A and B list](https://www.uspreventiveservicestaskforce.org/uspstf/recommendation-topics/uspstf-a-and-b-recommendations) | Preventive screening grades, age ranges, and intervals | Open the current recommendation page before stating a grade or age range. Never reuse a remembered grade as if it were live |
| [Canadian Task Force on Preventive Health Care](https://canadiantaskforce.ca/) and the person's other local or provincial programs | Local preventive and immunization guidance | Check the local source when the owner has a jurisdiction. Do not assume one country's grade applies everywhere |
| [AAFP clinical recommendations](https://www.aafp.org/family-physician/patient-care/clinical-recommendations/all-clinical-recommendations/uspstf.html) | Family-medicine view of USPSTF and related guidance | Use as a complement, not a replacement for the primary task-force page |
| [ACMG](https://www.acmg.net/) and the [2015 ACMG/AMP variant paper](https://www.nature.com/articles/gim201530) | Five-tier classification framework | Follow current ClinGen refinements when a VCEP spec exists. Do not invent evidence codes |

## Genomics and variant databases

| Source | What it is for | Re-check rule |
|--------|----------------|---------------|
| [ClinVar](https://www.ncbi.nlm.nih.gov/clinvar/) | Submitted classifications and review status | Open the record this run. Note review status and conflicts |
| [gnomAD](https://gnomad.broadinstitute.org/) | Population allele frequencies | Use the build and ancestry groupings the page actually shows |
| [ClinGen](https://clinicalgenome.org/), [curation](https://curation.clinicalgenome.org/), and [CSPEC](https://cspec.genome.network/) | Gene-disease validity and gene-specific rules | Prefer a VCEP specification over a generic ACMG walk when one exists |
| [OMIM](https://www.omim.org/) and [GeneReviews](https://www.ncbi.nlm.nih.gov/books/NBK1116/) | Disease-gene summaries | Cite the page and date. These are educational, not a diagnosis |
| [DECIPHER](https://www.deciphergenomics.org/), [LitVar2](https://www.ncbi.nlm.nih.gov/research/litvar2/), [Mutalyzer](https://www.mutalyzer.nl/) | Phenotype, literature, and HGVS checks | Supporting evidence only unless the primary guideline says otherwise |

Other public browsers and tools the framework may use: [UCSC](https://genome.ucsc.edu/), [Ensembl](https://ensembl.org/), [IGV](https://igv.org/), and Mastermind. HGMD, LOVD, and dbSNP are used with caution about clinical validity.

## Laboratory, radiology, and pathology references

- [Mayo Clinic Laboratories test catalog](https://www.mayocliniclabs.com/test-catalog)
- [Radiopaedia](https://radiopaedia.org/) and the relevant reporting lexicon (BI-RADS, LI-RADS, PI-RADS, Lung-RADS) when it applies
- [mypathologyreport.ca](https://www.mypathologyreport.ca/)
- [CAP](https://www.cap.org/), testing.com, ADLM, and CDC laboratory training resources

The report's own reference ranges, units, and method still come first.

## Facts that must not be treated as timeless

Recorded in `graphs/framework.md` and summarized in the `health-expert-graph` skill as of November 2026, and to be re-checked:

- USPSTF and local task-force screening ages, intervals, and grades
- Immunization schedules
- ClinVar review status and ClinGen VCEP specifications
- Lab method changes that alter reference ranges
- ACMG/AMP refinements after the 2015 standard

When you reuse one of these, either confirm it against a current primary source and add today's date, or quote it as a November 2026 framework pointer.

## What not to use as a source

- The owner's or a family's real health records in this public repository
- Invented or remembered lab values, grades, or variant classes
- Login-walled pages you could not open
- Computational predictors presented as a standalone classification
- Anonymous forums presented as guidelines
