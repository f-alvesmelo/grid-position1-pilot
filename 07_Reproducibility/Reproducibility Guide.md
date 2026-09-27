---
type: method
project: GRID
position: 1
status: pilot
---

# Reproducibility Guide

Command: `/reproduce`. Practical guide for reproducing every computed number currently in this repository.

## Reproducing `pilot_country_year_displacement.csv`

1. Obtain `IDMC_Internal_Displacement_Conflict-Violence_Disasters.xlsx` from IDMC.
2. Unzip it (it is a standard `.xlsx`/zip archive): `unzip IDMC_Internal_Displacement_Conflict-Violence_Disasters.xlsx -d unpacked/`.
3. Open `unpacked/xl/worksheets/sheet1.xml`. Cells are stored sparse (a cell is entirely omitted, not left empty, when unreported) and as inline strings (`t="inlineStr"`) or numbers (`t="n"`).
4. Parse each `<row>`, keying every `<c r="COLUMN_LETTER...">` value to its **column letter**, not its position in the row — sparse rows will have fewer `<c>` elements than the full column set, and reading by position silently misaligns values (this was caught once already in this project; see [[Data Sources]]).
5. Filter to the rows of interest (here: ISO3 ∈ {BDI, IRQ, COL}) and write to CSV with the header: `iso3,country,year,conflict_stock_displacement,conflict_stock_displacement_raw,conflict_new_displacement,conflict_new_displacement_raw,disaster_new_displacement,disaster_new_displacement_raw,disaster_stock_displacement,disaster_stock_displacement_raw` (columns D–K of the source sheet, in that order).

## Reproducing `06_Analysis/Descriptive Analysis.md` and `Comparative Analysis.md`

All figures are simple, auditable operations on `pilot_country_year_displacement.csv`:

- **2008 vs. 2025 snapshot values**: direct row lookup for `year=2008` and `year=2025` per country.
- **Peak year**: for each country, the year with the maximum `conflict_stock_displacement`.
- **Cumulative sums**: sum of `conflict_new_displacement` and `disaster_new_displacement` across all non-blank years per country.

Any spreadsheet tool, or a one-line `awk`/`pandas`/R script grouping by `iso3` and applying `max()`/`sum()`, will reproduce these exactly. No smoothing, interpolation, or estimation was applied.

## Migrating to the Researcher's Planned R Pipeline

The project's own design specifies an R-based pipeline: data harmonisation → model estimation → clustered inference → reproducible visualisation (see [[Project Brief]]). The `awk`-based computations in `06_Analysis/` are a pilot-stage stand-in, not a substitute for this — when the researcher's R environment is available, `pilot_country_year_displacement.csv` can be read directly (`read.csv()`) and the same operations above reproduced with `dplyr::group_by(iso3) %>% summarise(...)` or equivalent, extended to proper panel visualization (e.g., `ggplot2`).

## Prerequisites for Reproducing Any Future Coding Work

Before `align_*`, `authority_*`, or `response_*` values can be populated (and therefore before any H1–H3 test is reproducible), the following must exist and be documented here:

1. A finalized list of coded episodes (real `episode_id` values, sourced per [[Coding Protocol]] Step 1).
2. The documentary evidence base for each (political/coalition sources, government policy/administrative records) — currently absent from this repository.
3. Coder identity and date for each coding decision, per the evidence table template in [[Evidence Standards]].

Until then, this guide only covers what is actually reproducible: the displacement-magnitude descriptive statistics.

## Environment Notes

This pilot's data processing was done with only `bash`/`awk`/`perl` (no Python, R, or LibreOffice available in the working environment) — see [[Data Sources]]'s "Known Limitation" note on the unparsed `.xls` file. A full research environment with Python/pandas or R would simplify re-deriving these tables considerably and is recommended before scaling beyond the pilot.

## Related

[[Research Workflow]] · [[Data Provenance]] · [[Data Sources]] · [[Descriptive Analysis]] · [[Coding Protocol]]
