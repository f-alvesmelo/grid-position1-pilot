---
type: method
project: GRID
position: 1
status: pilot
---

# Comparative Strategy

Command: `/design`. Sources: [[Project]], [[Measurement Research Design]]. RESEARCHER MATERIAL.

## What Varies?

The dependent variable — government response, decomposed by domain and by de jure/de facto layer (see [[Data Dictionary]]) — is expected to vary:

- **Across countries** (cross-national tier)
- **Across time** (temporal variation, including around identifiable changes in political alignment)
- **Across subnational units** (municipality-year in Colombia; location-level in Iraq)
- **Across policy domains** (humanitarian assistance vs. other domains, pilot restricted to the former)
- **Within a domain, across the de jure/de facto layers** (consistency vs. inconsistency)

## Why Should It Vary? (Theoretical Driver)

Per [[Core Argument]]: variation in government response is explained by variation in **political alignment configuration** (`alignment_structure`), conditioned by **institutional location of authority** (`authority_locus`). See [[Mechanisms]] for the full CONCEPT→MECHANISM chain per hypothesis.

## Nested, Asymmetric, Mixed-Method Design (Lieberman, 2005)

Three tiers, explicitly **not** treated as statistically equivalent:

1. **Cross-national statistical analysis** — GRID dataset, all countries, 1989–latest finalized year (see [[Temporal Scope]]). Panel models with country/temporal fixed effects; event-study specifications around identifiable changes in alignment. R-based pipeline: harmonisation → estimation → clustered inference → reproducible visualisation.
2. **Subnational quantitative analysis — Colombia** (proposed candidate case, not a fixed requirement) — municipality-year, linking the Registro Único de Víctimas with municipal electoral/political and conflict data. Electoral turnover as a potential source of temporal variation for event-study analysis.
3. **Comparative qualitative/mixed evidence — Iraq and Burundi** — asymmetric, complementary cases (not a matched pair or representative sample), tested via process tracing to see whether mechanisms identified statistically "carry over across different institutional configurations."

## What Comparisons Are Theoretically Meaningful?

- **Within-country, across-domain**: does the same country-year show different response profiles across humanitarian assistance vs. other domains? (Tests the multidimensionality claim directly — see [[Concepts]].)
- **Within-domain, across `alignment_structure` categories**: do shared-alignment cases differ systematically from fragmented cases in response consistency? (H1/H2)
- **Within `alignment_structure`, across `authority_locus`**: does the same alignment configuration produce different responses depending on who holds authority over the domain? (H3 — the moderation test)
- **Cross-tier**: do mechanisms found in the cross-national statistical tier replicate in the Colombia subnational tier and in Iraq/Burundi process tracing?

## Alternative Explanations to Rule Out

Named explicitly in [[Project Brief]] for the qualitative/process-tracing tier: (i) administrative capacity, (ii) conflict intensity, (iii) territorial control. ⚠ Not yet built as codeable covariates for the cross-national/pilot tier (see [[Variables]], "Variable Roles Not Yet Defined").

## Related

[[Unit of Analysis]] · [[Case Selection]] · [[Temporal Scope]] · [[Mechanisms]] · [[Research Questions]]
