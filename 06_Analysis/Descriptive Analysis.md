---
type: analysis
project: GRID
position: 1
status: pilot
---

# Descriptive Analysis

Command: `/analysis`. **REAL DATA ANALYSIS** (not synthetic) — computed directly from [[pilot_country_year_displacement.csv]], itself extracted from the IDMC Global Internal Displacement Database (see [[Data Sources]]). Per AGENT.md §15, every analysis below states its population, unit of analysis, time period, variables, method, data source, and limitations up front.

**Scope warning**: this is a descriptive analysis of **displacement magnitude**, not of political alignment or government response. It says nothing about H1–H3. See [[Pilot Findings]] for why.

| Element | Value |
|---|---|
| Population | Burundi, Iraq, Colombia (the project's three case-study countries) |
| Unit of analysis | Country-year |
| Time period | 2008–2025 |
| Variables | `conflict_stock_displacement`, `conflict_new_displacement`, `disaster_new_displacement`, `disaster_stock_displacement` |
| Method | Descriptive statistics (sums, trend comparison of endpoint years, peak-year identification) computed via shell/awk directly on the CSV |
| Data source | IDMC Global Internal Displacement Database, `1_Displacement_data` sheet (see [[Data Sources]]) |
| Limitations | See dedicated section below and [[Limitations]] |

## 1. Conflict-Driven Displacement Stock: 2008 vs. 2025

| Country | 2008 stock | 2025 stock | Change |
|---|---|---|---|
| Burundi | 100,000 | 6,800 | −93,200 (−93%) |
| Iraq | 2,647,000 | 997,000 | −1,650,000 (−62%) |
| Colombia | 3,000,000 | 7,211,000 | +4,211,000 (+140%) |

**Observation**: Burundi and Iraq show large declines in conflict-driven IDP stock over the period, consistent with displacement episodes resolving (returns, local integration) faster than new conflict displacement occurs. Colombia shows the opposite pattern — its conflict-driven IDP stock more than doubled over the same period, consistent with Colombia's long-documented status as one of the world's largest and most protracted internal displacement situations.

## 2. Conflict Stock Peak Year

| Country | Peak conflict stock | Year |
|---|---|---|
| Burundi | 157,000 | 2009 |
| Iraq | 3,290,000 | 2015 |
| Colombia | 7,265,000 | 2024 |

**Observation**: Iraq's peak (2015) aligns with the well-documented 2014–2017 conflict period; Burundi's peak is earliest in the series (2009); Colombia's peak is the most recent (2024) — its conflict displacement stock has not yet turned a corner within the observed window.

## 3. Cumulative New Displacement by Cause, 2008–2025 (sum of reported years)

| Country | Conflict new displacement (sum) | Disaster new displacement (sum) |
|---|---|---|
| Burundi | 61,224 | 382,400 |
| Iraq | 6,546,000 | 406,200 |
| Colombia | 4,023,000 | 4,295,500 |

**Observation**: For Burundi, cumulative disaster-driven new displacement (382,400) considerably exceeds conflict-driven new displacement (61,224) over this period — despite Burundi's much larger conflict-driven *stock* (a legacy of displacement predating 2008, per [[Scope & Limitations]]'s note on the 2008–2025 window). Colombia shows disaster-driven and conflict-driven new displacement of roughly the same order of magnitude, both in the millions — a reminder that Colombia's displacement profile is not purely conflict-driven, which matters for scoping the humanitarian-assistance pilot domain (see [[Case Selection]]).

## 4. Disaster Stock, Most Recent Reported Year

| Country | Disaster stock | Year |
|---|---|---|
| Burundi | 82,000 | 2025 |
| Iraq | 186,000 | 2025 |
| Colombia | 35,000 | 2022 (no 2023–2025 value reported) |

## Limitations of This Analysis

- These figures describe **displacement magnitude only**. They do not measure, and should not be read as proxying for, government protection or repression — a country with a large declining conflict stock is not thereby "more protective," since returns can result from many causes (conflict resolution, host-country conditions, external assistance) unrelated to the responding government's own conduct.
- "Sum of reported years" for new displacement undercounts true cumulative displacement wherever a year has no reported figure (blank cells in the source data, not zeros).
- Data vintage: figures come from IDMC's most recent (2026 edition) global workbook and may revise the standalone country files' historical figures — see the cross-check note in [[Data Sources]].
- No cross-national (all-GRID-countries) analysis is included here — this file covers only the three case-study countries.

## Related

[[pilot_country_year_displacement.csv]] · [[Data Sources]] · [[Comparative Analysis]] · [[Pilot Findings]] · [[Limitations]]
