# Data Cleaning Notes — WHO Medicines Prequalification Dataset

## Source
World Health Organization, Prequalification of Medical Products (Medicines) programme.
Finished Pharmaceutical Products / Biotherapeutic Products list, exported as CSV.
Source URL: https://extranet.who.int/prequal/medicines/prequalified/finished-pharmaceutical-products

## Extraction note
The full published list contains 667 records. This portfolio project uses a
248-record working sample pulled directly from the WHO export (not
simulated), covering every therapeutic area present in the full list. This
is documented transparently in the README rather than presented as the
complete dataset.

## Cleaning steps applied
1. **Removed non-data rows** — the export contains one placeholder/test row
   ("P-13399 - test") with no values; this was dropped.
2. **Parsed dates** — the `Date of Prequalification` field arrives as
   free-text strings (e.g. "5  Dec,  2025") with inconsistent whitespace.
   Converted to proper datetime using `pandas.to_datetime` after
   normalising whitespace with a regex.
3. **Derived `Year`** — extracted from the parsed date for trend analysis.
4. **Missing dates** — 63 of 248 records (mostly USFDA/EMA "Alternative
   Listing" entries) have no WHO prequalification date because they were
   listed via a reference regulatory authority rather than WHO's own
   assessment. These are kept in the dataset (they're valid prequalified
   products) but excluded from the year-trend chart specifically, since
   they have no date to plot.
5. **Standardised categorical fields** — `Product Type`, `Therapeutic
   Area`, and `Basis of Listing` were checked for consistent spelling/casing;
   no changes were needed beyond what WHO already provides.

## Known limitations
- This is a sample, not the full 667-record list — stated explicitly in
  the README rather than implied.
- "Basis of Listing" mixes WHO's own full/abridged assessment with
  "Alternative Listing" (reliance on a trusted regulator like USFDA/EMA) —
  these are analytically different pathways and are treated as a separate
  dimension, not merged.
