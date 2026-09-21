# WHO Medicines Prequalification Analytics

**Independent portfolio project** analysing WHO's public medicines
prequalification data to understand global patterns in therapeutic area
coverage, manufacturer concentration, and prequalification activity over
time.

## Business context
WHO's Prequalification Programme assesses medicines against international
quality, safety, and efficacy standards so that UN agencies and
procurement bodies can purchase from a trusted list of manufacturers.
Understanding *what* gets prequalified, *by whom*, and *when* is directly
relevant to regulatory-performance monitoring work — the kind of analysis
a body like the African Medicines Agency (AMA) would use to track its own
regulatory throughput.

## Objective
Turn a real WHO public dataset into a structured, KPI-driven analysis that
demonstrates: data cleaning, KPI definition, trend analysis, and
translating findings into decision-relevant insight — not just chart-making.

## Dataset
- Source: WHO Prequalification of Medical Products — Finished
  Pharmaceutical Products / Biotherapeutic Products list
  (https://extranet.who.int/prequal/medicines/prequalified/finished-pharmaceutical-products)
- This project uses a 248-record sample pulled directly from the WHO
  export, covering every therapeutic area in the full ~667-record list.
  See `data_cleaning_notes.md` for exactly what was cleaned and why.

## KPIs tracked
| KPI | Value (sample) |
|---|---|
| Total prequalified products | 248 |
| Therapeutic areas represented | 15 |
| Distinct applicants/manufacturers | 60+ |
| Prequalification period | 2002–2026 |
| Full vs Abridged vs Alternative Listing | 119 / 65 / 56 |

## Structure
```
WHO-Medicines-Prequalification-Analysis/
├── README.md
├── WHO_prequalified_medicines_sample.csv    # cleaned dataset
├── data_cleaning_notes.md                   # what was cleaned and why
└── key_findings.md                          # analysis & insights
```

## Findings
See `key_findings.md` for the full write-up. Headlines:
- HIV/AIDS accounts for 54% of prequalified products in the sample
- Two manufacturers (Aurobindo, Macleods) account for ~20% of listings
- Prequalification activity spikes around global health events (2020,
  2022) rather than growing steadily — a finding directly relevant to how
  KPIs should be interpreted on a regulatory-performance dashboard

## Tools
Python (pandas) for cleaning and KPI calculation. Tableau Public
dashboard: *[link to be added]*.

## Status
This project is part of an active portfolio build. A Tableau dashboard
visualising these KPIs interactively is in progress — this README will be
updated with the published Tableau Public link once complete.
