---
type: dataset
project: GRID
position: 1
status: pilot
---

# Data Sources

Command: `/dataset`. Documents the 10 real data files the researcher provided on 2026-09-27 for building the pilot dataset. This is **EMPIRICAL EVIDENCE** (IDMC and World Bank published statistics), not synthetic data — but it is displacement-magnitude/event data, **not** political-alignment or government-response data. See "What This Data Can and Cannot Support" below before using it in analysis.

## Files Received

| File | Source | Coverage | Content |
|---|---|---|---|
| `bdi_idmc_idu_events.csv` | IDMC (Internal Displacement Monitoring Centre), Internal Displacement Updates (IDU) | Burundi, 570 event-location records, dates mostly 2025–2026 | Event-level displacement records: id, lat/long, role (Recommended figure / Triangulation), displacement_type (Conflict/Disaster), figure (persons displaced), displacement dates, event_id, event_name, category/subcategory/type/subtype (hazard or conflict type), sources, locations, description |
| `irq_idmc_idu_events.csv` | IDMC IDU | Iraq, 4 event-location records, 2026 only | Same schema as above — this file is a small/recent extract, not a historical series |
| `col_idmc_idu_events.csv` | IDMC IDU | Colombia, ~199 event-location records, 2025–2026 | Same schema — includes both Conflict (NIAC/IAC) and Disaster events |
| `internal-displacements-new-displacements-associated-with-disasters_bdi.csv` | IDMC | Burundi, 724 disaster events, 2008–2022 (partial view read; file continues) | Disaster event records: iso3, year, start/end date (+accuracy), event_name, hazard_category/type/subtype, new_displacement (+rounded), total_displacement (+rounded), event_codes |
| `internal-displacements-new-displacements-associated-with-disasters_irq.csv` | IDMC | Iraq, 53 disaster events, 2008–2025 | Same schema as above |
| `internal-displacements-new-displacements-associated-with-disasters_col.csv` | IDMC | Colombia, ~1059 disaster events, 2008–2014+ (partial view read; file continues) | Same schema as above |
| `internal-displacements-new-displacements-idps_bdi.csv` | IDMC | Burundi, country-year, 2009–2025 | Country-year aggregate: new_displacement (+rounded), total_displacement (+rounded) — appears to be the **conflict-driven** IDP series (IDMC's "new displacements — IDPs" product) |
| `internal-displacements-new-displacements-idps_irq.csv` | IDMC | Iraq, country-year, 2009–2025 | Same schema as above |
| `IDMC_Internal_Displacement_Conflict-Violence_Disasters.xlsx` | IDMC, IDMC Global Internal Displacement Database | **All countries**, 2008–2025 (~2,500 country-year rows across 4 sheets) | Sheet `1_Displacement_data`: ISO3, Name, Year, Conflict Stock Displacement (+Raw), Conflict Internal Displacements/flow (+Raw), Disaster Internal Displacements/flow (+Raw), Disaster Stock Displacement (+Raw). Sheet `2_Context_Displacement_data`: per-figure methodology/caveat notes (free text). Sheet `3_IDPs_SADD_estimates`: sex/age-disaggregated IDP estimates by country-year-cause. Sheet `README`. |
| `API_SM.POP.IDPC_DS2_en_excel_v2_430765.xls` | World Bank, World Development Indicators | All countries (confirmed present: Burundi, Colombia, Iraq) | Indicator SM.POP.IDPC — "Internally displaced people (IDPs) by country or territory of asylum." Legacy binary `.xls` format; **not machine-parsed in this pass** (no `.xls`-capable library available in this environment — see "Known Limitation" below). Same substantive family as the IDMC stock figures. |

**No Colombia conflict-driven country-year "new-displacements-idps" file was provided** (only Burundi and Iraq have this file). Colombia's conflict/IDP country-year series is only available via the IDMC global xlsx (`1_Displacement_data` sheet, "Conflict" columns) and the raw event-level `col_idmc_idu_events.csv` / disaster CSV.

## Extracted Pilot Table

[`pilot_country_year_displacement.csv`](pilot_country_year_displacement.csv) — a country-year panel for Burundi, Iraq, and Colombia, 2008–2025, extracted directly from the IDMC global xlsx (`1_Displacement_data` sheet). Columns: `conflict_stock_displacement(_raw)`, `conflict_new_displacement(_raw)`, `disaster_new_displacement(_raw)`, `disaster_stock_displacement(_raw)`.

**Extraction method**: the xlsx stores sparse rows — a cell is omitted entirely (not just blank) when a country-year has no reported value for that column. An early extraction pass read cells by position-of-appearance rather than by column letter, which silently shifted values into the wrong fields whenever a row had a missing middle column (e.g., Colombia has no "Conflict Internal Displacements" flow value in any year, which shifted disaster figures into the conflict-flow field). This was caught and corrected before writing the CSV — the final extraction keys every value to its actual spreadsheet column letter (A–K), not its position in the row. Flagging this here because it is exactly the kind of silent data error the researcher's own methodological safeguards (§9 of [[Refined Measurement Framework]]) warn against, and because anyone re-deriving this table from the source xlsx should key on column letters, not positional order.

Blank cells in the CSV mean "not reported that year," not zero.

## Cross-Check Note: Minor Discrepancies Between Files

The standalone `internal-displacements-new-displacements-idps_bdi.csv` and the IDMC global xlsx do not always agree exactly on the same country-year (e.g., Burundi 2015 total_displacement = 100,000/99,300 in the standalone file vs. conflict_stock_displacement_raw = 100,518 in the xlsx). This most likely reflects different data-vintage/edition snapshots (the xlsx's per-figure notes reference "the 2026 edition" with revisions to prior years) rather than an extraction error. Treat these as two dated snapshots of an evolving statistical series, not as contradictory ground truth — the coding protocol should record **which vintage/edition** a figure was drawn from (`source`, `coding_notes`).

## What This Data Can and Cannot Support

### Can support
- **Displacement magnitude and timing** (`new_displacement`, `total_displacement`, stock vs. flow) for Burundi, Iraq, Colombia, 2008–2025, and — via the global xlsx — for all countries, which is directly relevant to bounding the **cross-national tier's** country/year scope (see [[Scope & Limitations]], [[Temporal Scope]]).
- **Real candidate displacement episodes** for the three case-study countries: the event-level files (`*_idmc_idu_events.csv`, `associated-with-disasters_*.csv`) each carry a real `event_id`/event name, start/end dates, and a **category** distinguishing Conflict (NIAC/IAC) from Disaster (weather/geophysical) causes. This directly operationalizes the researcher's own safeguard to "distinguish state-caused displacement from displacement caused by other actors where the data permit" ([[Refined Measurement Framework]] §9) — conflict-category events are the natural candidates for `episode_id` in the political-alignment framework; disaster-category events are still legitimate humanitarian-assistance-response episodes but sit outside the "state-caused displacement" logic.
- **Grounding the unit-of-analysis debate**: because real episodes here have explicit start/end dates and can co-occur within a country-year (e.g., Colombia had dozens of distinct conflict and disaster events in some years), this data empirically confirms that **country-year-episode** is the more information-preserving unit — collapsing to country-year would blend distinct episodes with potentially different alignment configurations. See [[Unit of Analysis]].

### Cannot support (still requires separate coding per [[Coding Protocol]])
- **Political alignment** (`align_NG_local`, `align_NG_IDP`, `align_local_IDP`) — none of these files contain any political, partisan, or electoral information. Alignment coding requires the documentary/political evidence types listed in [[Political Alignment]] and [[Evidence Standards]] (coalition agreements, electoral results, documented alliances), which is a completely different evidence base.
- **Authority locus** (`authority_formal/budget/admin/actual/locus`) — none of these files contain legal, budgetary, or administrative-responsibility information.
- **Government response** (`response_de_jure`, `response_de_facto`) — none of these files record government policy, humanitarian-assistance provision, or restriction. They record *how many people were displaced and why*, not *what the government did about it*.

**In short: this data answers "did a displacement episode occur, when, where, and from what proximate cause" — it does not answer "was the government's response to that episode protective or repressive, de jure or de facto, and was that response conditioned by political alignment."** Populating the latter requires a separate coding pass using the [[Coding Protocol]] and genuinely political/administrative sources, which is future work, not something derivable from this data.

## Known Limitation

`API_SM.POP.IDPC_DS2_en_excel_v2_430765.xls` is a legacy binary Excel format (BIFF/CDFV2), not the zip-based `.xlsx` format the other file uses. This environment has no `.xls`-capable parsing library (no Python/pandas, no LibreOffice) — only `unzip`, `perl`, and text tools, which cannot read binary BIFF cell records. String scanning confirmed Burundi, Colombia, and Iraq are present and the indicator is SM.POP.IDPC (IDP stock), but the actual numeric time series was **not extracted**. Since this indicator substantially overlaps the already-extracted IDMC stock figures, this is a low-priority gap — flagged rather than worked around with a guess.

## Related

[[pilot_country_year_displacement.csv]] · [[Unit of Analysis]] · [[Data Dictionary]] · [[Coding Protocol]] · [[Scope & Limitations]]
