---
type: dataset
project: GRID
position: 1
status: pilot
---

# Data Dictionary

Command: `/operationalize`, `/dataset`. Sources: [[Measurement Research Design]], [[Refined Measurement Framework]] §8 (canonical variable architecture — supersedes earlier informal variable names), [[Data Sources]] (real IDMC/World Bank displacement data received 2026-09-27). Scope: **pilot only** — humanitarian-assistance domain, Burundi/Iraq/Colombia case-study countries. Structure follows AGENT.md §10: CONCEPT → DIMENSION → INDICATOR → VARIABLE → CODING RULE → EVIDENCE.

## Identification Variables

| Variable | Description | Status |
|---|---|---|
| `country` | Country in the finalized GRID cross-national dataset. | ✓ scope defined (all GRID countries) for the full tier; real data currently on hand covers Burundi/Iraq/Colombia only — see [[Data Sources]] |
| `year` | Calendar year, 1989 through the latest year in the finalized GRID dataset. | ✓ scope defined; real IDMC coverage on hand is 2008–2025 |
| `episode_id` | Identifier for the displacement episode to which alignment and response are attributed. | ✓ **Partially resolved for Burundi/Iraq/Colombia**: real IDMC `event_id` values (from `*_idmc_idu_events.csv` and the `associated-with-disasters_*.csv` files) provide genuine candidate episode identifiers, each with a start/end date, location, and a Conflict/Disaster category — see [[Data Sources]]. General episode-boundary rule for countries without event-level IDMC data ⚠ still open. |
| `displacement_cause` | Conflict vs. Disaster, per the IDMC `category`/`displacement_type` field. | ✓ directly available from real data for the three case countries; operationalizes the researcher's safeguard to distinguish state-caused from other-caused displacement (conflict ≠ state-caused, but it is the closer of the two categories) |
| `domain` | Policy domain being coded. Pilot value: `humanitarian_assistance`. Other illustrative values (not yet coded): `public_services`, `rights_legal_guarantees`, `mobility_territorial_control`, others pending finalized GRID framework. | ✓ pilot domain fixed |

## Political Alignment Variables

Per [[Refined Measurement Framework]] §1–3, §8.

| Variable | Level | Concept | Coding | Evidence |
|---|---|---|---|---|
| `align_NG_local` | Dyad | National government ↔ local authority (NG–L) | 2 = aligned / 1 = cross-cutting-ambiguous / 0 = opposed / NA = insufficient evidence | Partisan/coalitional affiliation, electoral alignment, formal alliances, documented conflict/cooperation |
| `align_NG_IDP` | Dyad | National government ↔ displaced population (NG–D) | 2 / 1 / 0 / NA (as above) | Political affiliation/coalition, electoral evidence where available, documented alliances or exclusion, evidence on politically salient group identity |
| `align_local_IDP` | Dyad | Local authority ↔ displaced population (L–D) | 2 / 1 / 0 / NA (as above) | Local political affiliation, electoral evidence, documented relationships, alliances, conflict, or exclusion |
| `alignment_configuration` | Episode | Full three-dyad vector, e.g. (2,2,2), (2,2,1), (2,0,2) | Derived: (`align_NG_local`, `align_NG_IDP`, `align_local_IDP`) | — |
| `alignment_structure` | Episode | Derived categorical summary | shared alignment / predominantly aligned / fragmented / shared opposition / indeterminate — see [[Political Alignment]] for the derivation table | Derived from `alignment_configuration` |
| `alignment_confidence` | Dyad | Evidence quality for each dyadic score (analytically separate from the score itself) | High / Medium / Low / Insufficient | See [[Evidence Standards]] for the 3-tier evidence hierarchy |
| `alignment_evidence_coverage` | Episode | How many of the 3 dyads are actually observed | 0–3 | Derived: count of non-NA dyads |
| `align_timing` | Episode | Measurement window | Must be pre-displacement/onset-period, per [[Political Alignment]] | Same sources as above, dated to that window |

**Rule**: NA is never converted into 1 or another substantive score. Missing-dyad handling for `alignment_structure`: 3/3 observed → classify normally; 2/3 → classify only if sufficient to establish the configuration; 1/3 or 0/3 → indeterminate.

## Institutional Authority Variables

Per [[Refined Measurement Framework]] §4–6, §8. Coded **per domain and period/episode**, not at the country level.

| Variable | Level | Indicator | Coding | Evidence |
|---|---|---|---|---|
| `authority_formal` | Domain | A. Formal legal allocation — who is legally responsible? | N / L / S / D / U | Constitution, legislation, executive decrees, regulations, administrative statutes, official policy frameworks |
| `authority_budget` | Domain | B. Budgetary authority — who controls the relevant resources? | N / L / S / D / U | National/municipal budgets, programme financing, intergovernmental transfers, earmarked funds, procurement authority |
| `authority_admin` | Domain | C. Administrative/implementation authority — which institution formally implements? | N / L / S / D / U | Administrative mandates, programme manuals, agency structures, implementation guidelines, official records |
| `authority_actual` | Domain | D. Observed decision-making — who actually authorized/restricted/distributed/withdrew the response? | N / L / S / D / U | Administrative decisions, government orders, programme records, court documents, official correspondence, humanitarian documentation, interviews |
| `authority_locus` | Domain | Derived final category | N (National) / L (Local) / S (Shared) / D (Delegated) / U (Unclear) | Derived from the four indicators above — see [[Coding Protocol]] for illustrative derivation rules |

**Note**: formal responsibility, fiscal control, implementation authority, and actual decision-making may not all point to the same level — recording all four separately (rather than only the final `authority_locus`) preserves this and prevents formal assignment from being conflated with actual power.

## Government Response Variables

Per [[Measurement Research Design]] §3, §6 and [[Refined Measurement Framework]] §8. Coded **per domain**; pilot domain is `humanitarian_assistance`.

| Variable | Level | Coding | Evidence |
|---|---|---|---|
| `response_de_jure` | Domain | Protective / restrictive-repressive / absent (no formal response) | Formal entitlement, programme, allocation, responsibility, or restriction |
| `response_de_facto` | Domain | Protective / restrictive-repressive / absent (no meaningful state action) | Actual provision, facilitation, restriction, exclusion, diversion, withdrawal, or administrative/security barriers affecting access |
| `response_consistency` | Domain (derived) | consistent_protection / protective_inconsistent / repressive_inconsistent / consistent_repression | Derived from `response_de_jure` × `response_de_facto` — see [[Coding Protocol]] |

**Key rule** (applies to both layers independently): absence of a de jure policy must not be auto-coded as absence of a de facto response, and absence of a formal response must not be auto-coded as repression. "Absent" is a distinct third value, not a synonym for repression.

**Critical gap**: no data received so far — including the real IDMC/World Bank files in [[Data Sources]] — contains any `response_de_jure` or `response_de_facto` values. These displacement datasets record *that displacement occurred and from what cause*, not *what the government did in response*. Populating these two columns requires a separate coding pass against documentary/administrative evidence (see [[Coding Protocol]] Step 6), which has not been done. Do not infer response values from displacement magnitude (e.g., high displacement ≠ repressive response) — that would be exactly the kind of unsupported inference the non-fabrication rule prohibits.

## Not Yet in the Dictionary (Beyond Pilot Scope)

- Response variables for domains other than humanitarian assistance (`public_services`, `rights_legal_guarantees`, `mobility_territorial_control`) — same `response_de_jure`/`response_de_facto`/`response_consistency` structure applies once `domain` takes those values, but they are not yet coded.
- Colombia/Iraq/Burundi case-level variables (municipality-year, location-level) — not yet specified beyond the units named in [[Scope & Limitations]].
- General `episode_id` boundary rule for countries beyond the three with real IDMC event-level data on hand.

## Related

[[Variables]] · [[Coding Protocol]] · [[Evidence Standards]] · [[Political Alignment]] · [[Protection]] · [[Repression]] · [[Refined Measurement Framework]] · [[Data Sources]] · [[pilot_country_year_displacement.csv]]
