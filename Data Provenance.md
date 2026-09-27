---
type: method
project: GRID
position: 1
status: pilot
---

# Data Provenance

Command: `/reproduce`. Full provenance chain for every data file in this repository, per AGENT.md §18.

## Primary Research Documents

| File | Origin | Date Received |
|---|---|---|
| `Research Project/Project.md` | Researcher's original project proposal | Pre-existing at agent activation |
| `Research Project/Measurement Research Design.docx`/`.md` | Researcher-authored memo | 2026-09-27 |
| `Research Project/Refined Measurement Framework.docx`/`.md` | Researcher-authored memo | 2026-09-27 |

## Empirical Data Files

| File | Publisher | Original Filename | Date Received | Processing Applied |
|---|---|---|---|---|
| `02_Data/pilot_country_year_displacement.csv` | IDMC (Internal Displacement Monitoring Centre) | `IDMC_Internal_Displacement_Conflict-Violence_Disasters.xlsx`, sheet `1_Displacement_data` | 2026-09-27 | Unzipped (xlsx = zip archive); `xl/worksheets/sheet1.xml` parsed with a `perl` script keyed to column letters; filtered to ISO3 ∈ {BDI, IRQ, COL}; written to CSV. No values altered, aggregated, or estimated — every cell is a direct transcription of the source XML. Blank = not reported in source, not zero. |

## Empirical Data Files Received But Not Yet Processed Into a Repository Artifact

| File | Publisher | Coverage | Status |
|---|---|---|---|
| `bdi_idmc_idu_events.csv` | IDMC (IDU) | Burundi, ~570 event-location records | Read/inspected (partial); not yet transformed into a repository `episode_id` table |
| `irq_idmc_idu_events.csv` | IDMC (IDU) | Iraq, 4 recent event-location records | Read/inspected (full); not yet transformed |
| `col_idmc_idu_events.csv` | IDMC (IDU) | Colombia, ~199 event-location records | Read/inspected (partial); not yet transformed |
| `internal-displacements-new-displacements-associated-with-disasters_bdi.csv` | IDMC | Burundi, 724 disaster events, 2008–2022+ | Read/inspected (partial, 228 of 725 lines); not yet transformed |
| `internal-displacements-new-displacements-associated-with-disasters_irq.csv` | IDMC | Iraq, 53 disaster events, 2008–2025 | Read/inspected (full) |
| `internal-displacements-new-displacements-associated-with-disasters_col.csv` | IDMC | Colombia, ~1,059 disaster events | Read/inspected (partial, 255 of 1,060 lines); not yet transformed |
| `internal-displacements-new-displacements-idps_bdi.csv` | IDMC | Burundi, country-year, 2009–2025 | Read/inspected (full); cross-checked against the xlsx (see discrepancy note in [[Data Sources]]) |
| `internal-displacements-new-displacements-idps_irq.csv` | IDMC | Iraq, country-year, 2009–2025 | Read/inspected (full) |
| `API_SM.POP.IDPC_DS2_en_excel_v2_430765.xls` | World Bank (World Development Indicators) | All countries, indicator SM.POP.IDPC | **Not parsed** — legacy binary `.xls` format, no compatible library in this environment. Presence of Burundi/Colombia/Iraq confirmed via raw string scan only. |

All of the above remain in the user's Downloads folder at the paths originally provided; none have been copied into the repository, since they were not yet transformed into a citable repository artifact. If any of these are processed in a future session, this table should be updated with the resulting artifact's location and the processing method used.

## Data Vintage Note

The IDMC global xlsx's per-figure methodology notes (sheet `2_Context_Displacement_data`) reference "the 2026 edition" with revisions to prior years' figures. The standalone country-year files may reflect an earlier edition. Where the two disagree (see [[Data Sources]] cross-check note), this is normal for an evolving statistical series, not a data error — but any published output should state which edition's figures it used.

## Chain of Custody for Derived Files

- [[pilot_country_year_displacement.csv]] — derived solely from `IDMC_Internal_Displacement_Conflict-Violence_Disasters.xlsx`. No other file contributed values to it.
- All `06_Analysis/` figures — derived solely from `pilot_country_year_displacement.csv`, via `awk` (see [[Research Workflow]] for the worked example).
- No synthetic or placeholder values appear anywhere in `02_Data/` or `06_Analysis/` as of this entry — everything currently populated is real, sourced data. (This will change if/when a synthetic demonstration file is created per AGENT.md §13 — any such file will be labeled **SYNTHETIC DATA — DEMONSTRATION ONLY** and listed separately here.)

## Related

[[Research Workflow]] · [[Reproducibility Guide]] · [[Data Sources]] · [[Changelog]]
