# Business and economic studies on life expectancy: A bibliometric review

Reproducibility materials for the bibliometric review of life expectancy research
in the business and economics domain (Baraheem & Merigó), analysing 2,506
publications indexed in the Web of Science Core Collection, 1943–2024.

## Contents

- `LifeExpectancy_bibliometric_WoS_query_sensitivity_validation.ipynb` — query sensitivity analysis
- `LifeExpectancy_bibliometric_WoS_Scopus_coverage_analysis.ipynb` — database coverage analysis
- `sample100_to_screen.csv` — random sample of 100 added records used for relevance screening
- `scopus_only_records.csv` — the 1,295 records retrieved only by the Scopus search

## Database definition

- **Database:** Web of Science Core Collection (searched February 2025)
- **Query:** Topic (TS) = `"Life* Expectanc*"`
- **Filters:** Articles and Review Articles; publication years ≤ 2024; Early Access,
  expressions of concern, and retracted publications excluded; Research Area:
  Business Economics
- **Result:** 2,506 documents

## Search validation (August 2026)

**Query sensitivity.** The base query was compared against broader variants under
identical filters:

| Query | Records |
|---|---|
| `"life expectanc*"` (base) | 2,580 |
| + `"life span"`, `"length of life"` | 3,011 (+16.7%) |
| + `"longevity"`, `"lifespan"`, `"life span"` | 5,447 (+111.1%) |

The 2,867 records added by the broad variant were retrieved with
`TS=("longevity" OR "lifespan" OR "life span") NOT TS=("life expectanc*")` and a
random sample of 100 was screened: **40%** (Wilson 95% CI 31–50%) concerned human
life expectancy; the majority concerned firm/organisational longevity, life-span
workplace psychology, or product and asset lifespans.

**Database coverage.** An equivalent Scopus search
(`TITLE-ABS-KEY("life expectanc*") AND PUBYEAR < 2025`, final-stage articles and
reviews, BUSI + ECON subject areas) returned 2,712 records; 1,417 are common to
both corpora (52.2% of Scopus; 54.8% of WoS). 86% of Scopus-only records come from
journals absent from the WoS Business Economics research area, while the WoS-only
records are concentrated in the field's core health-economics journals, which
Scopus classifies under Medicine.

## Reproducing the analyses

Each notebook runs in Google Colab. The database export files are **not
redistributed here** because Web of Science and Scopus licence terms prohibit
sharing full records. To reproduce: re-run the documented queries (institutional
access required), export (WoS → Excel "Full Record" in 1,000-record batches;
Scopus → CSV with DOI), and upload the exports when the notebook prompts. The
random sample uses a fixed seed (`random_state=42`) and is identical across runs.

## Software

Python 3 · pandas · xlrd. Bibliometric mapping in the paper uses
[VOSviewer](https://www.vosviewer.com/); descriptive analysis uses Microsoft Excel.

## Citation

If you use these materials, please cite the paper (reference to be added upon
publication).
