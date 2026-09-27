---
type: method
project: GRID
position: 1
status: pilot
---

# Unit of Analysis

Command: `/design`. Sources: [[Project]], [[Measurement Research Design]] §7, [[Refined Measurement Framework]] §8, [[Data Dictionary]]. RESEARCHER MATERIAL unless marked otherwise.

## Per-Tier Units (as established across sources)

| Tier | Unit | Status |
|---|---|---|
| Cross-national | **Country-year**, or possibly **country-year-displacement-episode** | ⚠ OPEN — explicitly left undecided by the researcher pending inspection of the finalized GRID dataset structure |
| Colombia (subnational, proposed candidate case) | **Municipality-year** | ✓ specified in [[Project]]; not a fixed requirement per [[Measurement Research Design]] §1 ("proposed candidate case rather than a predetermined requirement") |
| Iraq (case-study context) | **Location-level** (displacement/return data) | ✓ specified in [[Project]] |
| Burundi (case-study context) | Case-based; limited quantitative measures | ✓ specified in [[Project]] |

## The Open Question: Country-Year vs. Country-Year-Episode

This is the single most consequential undecided design choice, because the alignment and response variables in [[Data Dictionary]] are explicitly keyed to an `episode_id`, not to calendar year alone. Two candidate resolutions:

1. **Country-year**: one observation per country per year, aggregating across any displacement episodes active that year. Simpler, matches conventional panel-data structure, compatible with the researcher's proposed fixed-effects/event-study estimators (see [[Project Brief]]).
2. **Country-year-displacement-episode**: one observation per episode per year, allowing multiple episodes within the same country-year to be coded separately (relevant if a country has concurrent or sequential displacement episodes with different politically salient populations and different alignment configurations).

The researcher's own memo explicitly declines to resolve this before inspecting the finalized GRID dataset ("the final unit and estimator should be specified only after inspecting the finalized dataset" — [[Measurement Research Design]] §7). This repository does not resolve it for the full cross-national tier either.

### Empirical Evidence Favoring Country-Year-Episode (2026-09-27)

Real IDMC displacement data for Burundi, Iraq, and Colombia (see [[Data Sources]]) shows multiple, distinct, dated displacement events routinely co-occurring within a single country-year — e.g., Colombia's event-level records show dozens of separate conflict and disaster events in a single year, each with its own start/end date, location, and (for conflict events) potentially a different politically salient displaced population. Collapsing these to one country-year observation would force a single alignment configuration onto events that may have genuinely different political alignments (e.g., a conflict displacement in one department vs. a flood displacement in another, in the same year). This is empirical, not theoretical, support for **country-year-episode** as the more information-preserving default for the three case-study countries — it can always be aggregated up to country-year later, but the reverse is not possible. This does not resolve the question for the full cross-national tier (all GRID countries), which still depends on the finalized GRID dataset's own structure.

## Implication for Variable Coding

- `align_NG_local`, `align_NG_IDP`, `align_local_IDP`, `alignment_configuration`, `alignment_structure` are coded at the **episode** level (per [[Data Dictionary]]).
- `authority_formal/budget/admin/actual/locus` are coded at the **domain** level, within an episode/period.
- `response_de_jure`, `response_de_facto` are coded at the **domain** level.

If the final cross-national unit is country-year (not country-year-episode), a rule will be needed for collapsing episode-level alignment/response codes into a single country-year observation when multiple episodes coexist. ⚠ OPERATIONALIZATION OPEN — no such rule exists yet.

## Related

[[Comparative Strategy]] · [[Case Selection]] · [[Temporal Scope]] · [[Data Dictionary]] · [[Scope & Limitations]] · [[Data Sources]]
