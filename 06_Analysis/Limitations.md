---
type: analysis
project: GRID
position: 1
status: pilot
---

# Limitations

Command: `/analysis`. Consolidates analysis-stage limitations. See [[Scope & Limitations]] for project-wide design limitations and [[Research Design Audit]] for the full audit.

## Data Limitations

- Real displacement data covers only three countries (Burundi, Iraq, Colombia) and 2008–2025 — not the full cross-national GRID scope (all countries, 1989–latest).
- No Colombia conflict-driven country-year series was directly provided (see [[Data Sources]]); Colombia's conflict figures here come from the global IDMC workbook only.
- Blank cells in [[pilot_country_year_displacement.csv]] mean "not reported," not zero — sums in [[Descriptive Analysis]] undercount true totals in years with missing reports.
- Data vintage differences exist between the standalone country files and the global workbook (different edition snapshots) — see the cross-check note in [[Data Sources]].
- The World Bank IDP-stock file could not be parsed in this environment (legacy binary format) — not incorporated into any analysis.

## Analytical Limitations

- **No political alignment, authority-locus, or government-response data has been coded** — the analyses in `06_Analysis/` are descriptive analyses of displacement magnitude, not tests of H1–H3. See [[Pilot Findings]] for the explicit statement of what is and is not known.
- Displacement-trajectory differences across countries (declining vs. rising stock) reflect many possible causes (conflict resolution, humanitarian intervention, host-community capacity) that have not been disentangled — per the researcher's own safeguard to separate political choice from capacity constraints, conflict intensity, and territorial control ([[Refined Measurement Framework]] §9).
- No inferential statistics (regression, event-study, clustered inference) have been run — only descriptive sums, trend comparisons, and peak-year identification, computed via shell tools rather than the researcher's planned R pipeline (see [[Project Brief]]).

## Reproducibility Limitations

- Statistics in [[Descriptive Analysis]] were computed with `awk` directly on the CSV for this pilot; they have not yet been reproduced in the R-based pipeline the researcher's own design specifies (harmonisation → estimation → clustered inference → reproducible visualisation). See `07_Reproducibility/` (to be built under `/reproduce`).

## Related

[[Descriptive Analysis]] · [[Comparative Analysis]] · [[Pilot Findings]] · [[Scope & Limitations]] · [[Research Design Audit]] · [[Next Steps]]
