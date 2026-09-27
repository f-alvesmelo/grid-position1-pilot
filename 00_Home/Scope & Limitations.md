---
type: project
project: GRID
position: 1
status: pilot
---

# Scope & Limitations

> Source: [[Project]]. RESEARCHER MATERIAL unless marked otherwise.

## Pilot Scope Decisions (2026-09-27)

> Recorded in [[Changelog]]. RESEARCHER decisions, not agent proposals.

- **Domain**: the pilot operationalizes and codes **humanitarian assistance** only. The three tiers below (cross-national, Colombia, Iraq/Burundi) all narrow to this domain for pilot purposes; other domains (housing, documentation, freedom of movement, security, etc.) are out of scope for the pilot but remain part of the long-run project design.
- **Response structure**: within the humanitarian-assistance domain, responses are coded as **de jure** (formal policy) and **de facto** (observed implementation) separately, not as a single composite score.

## Comparative Scope

Nested, mixed-method design (Lieberman, 2005) combining three tiers, treated as **asymmetric** rather than statistically equivalent:

1. **Cross-national tier** — GRID's cross-national dataset of government responses to internal displacement. Per [[Measurement Research Design]] §7: **all countries** in the finalized GRID dataset (Colombia/Burundi/Iraq are case-study contexts, not the country universe); temporal scope **1989 through the latest year in the finalized dataset**. Exact statistical unit (country-year vs. country-year-displacement-episode) [TO VERIFY] pending inspection of the finalized dataset.
2. **Subnational quantitative tier — Colombia** (principal case) — municipality-year dataset linking the Registro Único de Víctimas with municipal electoral/political data and conflict indicators.
3. **Comparative qualitative/mixed tier — Iraq and Burundi** (complementary, not equivalent):
   - **Iraq** — location-level displacement/return data; variation in territorial/institutional authority.
   - **Burundi** — contrasting political context; "comparable quantitative measures of alignment are more limited," so evidence relies more on qualitative process tracing.

The researcher explicitly frames Iraq/Burundi as following "the logic of nested analysis rather than treating data availability as a substitute for theoretical case selection" (Lieberman, 2005).

## Temporal Scope

- Institutional timeline: four-year PhD, GRID project, University of Amsterdam (2026–2031) — see the Gantt chart embedded in [[Project]] and summarized in [[Project Brief]].
- ✓ **RESOLVED, per [[Measurement Research Design]] §7**: substantive temporal scope of the cross-national tier is **1989 through the latest year covered by the finalized GRID dataset**. The end year is deliberately described as a moving target (tied to the finalized dataset) rather than fixed in advance, per the researcher's own memo.
- Colombia/Iraq/Burundi tiers: temporal scope not yet specified beyond "electoral turnover" as a possible source of variation in Colombia (see [[Project Brief]]).

## Case Selection Logic

- **Colombia**: selected as the principal subnational case because it allows linking individual-level victim registry data (Registro Único de Víctimas) with municipal electoral/political and conflict data, and because electoral turnover offers a plausible source of temporal variation. The project explicitly contrasts its own focus (political determinants of government responses *after* displacement) with existing Colombia scholarship on how political alignments contributed to the *production* of displacement (Steele, 2011; Steele, 2017).
- **Iraq and Burundi**: selected as complementary comparative cases to test whether mechanisms identified statistically "carry over across different institutional configurations," not as a matched pair or a representative sample.

## Explicit Identification / Endogeneity Concerns (as stated by the researcher)

- Political alignment may affect not only government responses but also the **production and composition of displacement itself** — a potential source of reverse causality/confounding.
- Mitigations proposed: distinguishing pre-displacement alignment from subsequent responses; distinguishing displacement caused by the responding state from displacement it did not cause; lagged measures; alternative operationalisations; theoretically justified covariates; robustness/sensitivity analyses.
- **Measurement validity** is flagged as a central methodological concern because political alignment "can take different institutional forms across contexts" (Adcock & Collier, 2001).

## Known Data Availability Constraints (as stated by the researcher)

- Burundi: quantitative measures of political alignment are comparatively limited, requiring greater reliance on qualitative evidence.
- The cross-national GRID dataset's exact coverage (response categories, missing-data patterns) beyond country universe and start year is still pending the finalized codebook. [TO VERIFY].

## Limitations Not Yet Addressed (flagged, not resolved)

- No explicit discussion of missing-data strategy for the cross-national panel.
- No explicit discussion of external validity / generalizability beyond the three qualitative cases and the single pilot domain (humanitarian assistance).
- Exact evidence thresholds for dyadic alignment coding (2/1/0/NA) are explicitly deferred by the researcher to a pilot + intercoder reliability check — not yet run.
- **Unit of analysis undecided**: country-year vs. country-year-displacement-episode for the cross-national tier — explicitly deferred by the researcher pending inspection of the finalized GRID dataset. See [[Unit of Analysis]].
- Evidence-confidence scheme not yet extended beyond political alignment to authority-locus indicators or response variables.
- ~~No explicit list of policy domains to be compared.~~ — **Resolved for the pilot**: humanitarian assistance; full illustrative list now known (see Pilot Scope Decisions above).
- ~~De jure vs. de facto response divergence... not yet built into coding strategy.~~ — **Resolved**: de jure and de facto are coded separately, with explicit definitions and a 2×2 consistency matrix. See [[Coding Protocol]] and [[Data Dictionary]].
- ~~How is "displaced population alignment" measured?~~ — **Resolved**: identify the politically salient displaced population tied to the displacement episode, measured pre-displacement/onset. See [[Political Alignment]].
- ~~Cross-national country/time scope unspecified.~~ — **Resolved**: all GRID countries, 1989–latest finalized year (see Temporal Scope above).
- ~~A general evidence-confidence scheme has not been defined.~~ — **Resolved**: High/Medium/Low/Insufficient, with a 3-tier evidence hierarchy. See [[Evidence Standards]].
- ~~No aggregation rule for combining the three dyadic alignment scores.~~ — **Resolved**: `alignment_configuration` (full vector) and `alignment_structure` (5-category typology). See [[Political Alignment]].

## Comparative Design (Formalized)

Full detail now lives in `03_Comparative Design/`: [[Unit of Analysis]] · [[Comparative Strategy]] · [[Case Selection]] · [[Temporal Scope]]. The sections above remain as a scope summary; those files are the canonical, detailed versions.

## Real Data Received (2026-09-27)

Real IDMC/World Bank displacement data for Burundi, Iraq, and Colombia (2008–2025) plus a global country-year workbook (all countries) is now on hand — see [[Data Sources]]. **This grounds the displacement/episode side of the pilot only.** It contains no political-alignment, authority-locus, or government-response information, so the core DV/IV of this project (per [[Data Dictionary]]) remain uncoded. Do not read progress on this data as progress on the substantive coding task.

## Synthetic Data Notice

No synthetic or demonstration data exists yet in this repository. If/when a demonstration dataset is created under `02_Data/demo/`, it will carry an explicit **SYNTHETIC DATA — DEMONSTRATION ONLY** label and must never be used to support substantive claims about real countries, governments, or populations (per AGENT.md §13).

## Related

[[Project Brief]] · [[Research Questions]] · [[GRID Position 1 Alignment]] · [[Research Design Audit]] · [[Changelog]] · [[Measurement Research Design]]
