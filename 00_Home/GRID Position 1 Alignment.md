---
type: project
project: GRID
position: 1
status: pilot
---

# GRID Position 1 Alignment

Command executed: `/grid`

GRID Position 1 direction (as given to this agent): *comparative cross-national research involving development and analysis of the GRID dataset, with possible qualitative fieldwork*, investigating government responses to internal displacement along the **protection–repression** continuum and how political alignment shapes those responses.

## How the Project Connects to Position 1

The researcher's project is, on its face, a close match to Position 1:

- It is explicitly **cross-national**, with the GRID dataset as the first analytical tier.
- It is explicitly organized around **government responses to internal displacement**, using the same **protection–repression continuum** language as the GRID project itself, and cites the GRID project's own framing paper directly (Steele, Schwartz, & Lichtenheld, 2024).
- It centers **political alignment** as the explanatory variable, which is the specific mechanism Position 1 is meant to investigate.
- It proposes **qualitative fieldwork/process tracing** (Iraq, Burundi) as a complement to the quantitative tiers, matching Position 1's "possible qualitative fieldwork" scope.
- It engages **temporal variation** (event-study designs around changes in alignment) and **cross-country variation** (panel models with country fixed effects).

## Elements Directly Relevant to Position 1

- Cross-national comparison → cross-national GRID dataset tier.
- Government responses / protection / repression → the core dependent variable.
- Political alignment → the core independent variable and the project's central theoretical contribution.
- Dataset development → the project proposes to *extend* GRID's cross-national dataset with subnational (Colombia) data, which is dataset-development work in the Position 1 sense.
- Comparative analysis → the nested cross-national/subnational/qualitative design.

## Elements That Require Further Development for a Position 1 Pilot

- **De jure vs. de facto responses**: Position 1 explicitly distinguishes these. As of 2026-09-27, [[Measurement Research Design]] fully operationalizes this — explicit definitions, per-domain coding categories, and a 2×2 consistency matrix (consistent protection / protective-inconsistent / repressive-inconsistent / consistent repression-restriction). ✓ Now operationalized, not just decided.
- **Pilot domain scope**: bounded to **humanitarian assistance**, with the full illustrative domain set (public services, rights and legal guarantees, mobility and territorial control, others pending the finalized GRID framework) now documented.
- **Measurement/coding of political alignment**: ✓ Now operationalized — relational/dyadic coding across three actor-level pairs (2=aligned / 1=cross-cutting-ambiguous / 0=opposed / NA=insufficient evidence), with the displaced population treated as episode-specific and measured pre-displacement to avoid post-treatment bias.
- **Temporal and country scope**: ✓ Now specified — all countries in the finalized GRID dataset, 1989 through the latest finalized year. Exact statistical unit (country-year vs. country-year-episode) remains open pending inspection of the finalized dataset.
- **Alignment aggregation**: ✓ Now operationalized, per [[Refined Measurement Framework]] — the three dyadic scores combine into `alignment_configuration` (full vector, primary measure) and `alignment_structure` (shared alignment / predominantly aligned / fragmented / shared opposition / indeterminate), with explicit rules for classification and missing-dyad handling.
- **Evidence-confidence scheme**: ✓ Now operationalized — High/Medium/Low/Insufficient, with a 3-tier evidence hierarchy (direct political evidence > observable political relationships > indirect contextual evidence), kept analytically separate from the substantive alignment score. Not yet extended to authority-locus or response variables.
- **Authority locus**: ✓ Now fully operationalized, and explicitly corrected to be **domain- and episode-specific rather than country-level** — a state can be National authority over one domain and Delegated/Local over another. Derived from four separately-recorded indicators (formal legal, budgetary, administrative, observed decision-making), which is a more rigorous instrument than the memo's own first pass. This is arguably the single most Position-1-relevant refinement, since it operationalizes exactly the "institutional location of authority" conditioning factor central to H3.
- **Remaining gap**: the mechanism for `authority_locus` = Delegated is explicitly unsettled (see [[Mechanisms]]); intercoder reliability thresholds are still deferred to a future pilot.

## What the Pilot Demonstrates

Given the non-fabrication rule and the current state of the project, a Position 1 pilot built from this material can demonstrate:

- the researcher's ability to move from a comparative theoretical argument to an explicit, falsifiable set of hypotheses (H1–H3);
- awareness of multilevel-governance and measurement-validity concerns specific to cross-national comparative work;
- a defensible, non-naïve nested case-selection logic (Colombia as principal quantitative case; Iraq/Burundi as asymmetric qualitative complements);
- **a fully specified measurement instrument** for both political alignment (relational/dyadic) and government response (multi-domain, de jure/de facto) — this is now a genuine operationalization, not just a stated ambition;
- a reproducible quantitative workflow design (R-based pipeline).

It cannot yet demonstrate a populated dataset, actual comparative findings, or validated intercoder reliability — these require running the pilot coding exercise the researcher's own memo calls for. Per AGENT.md §26, this remains flagged as future work rather than simulated by the agent.

## Related

[[Project Brief]] · [[Research Questions]] · [[Scope & Limitations]] · [[Research Design Audit]] · [[Project Ingestion Report]] · [[Changelog]] · [[Measurement Research Design]] · [[Refined Measurement Framework]]
