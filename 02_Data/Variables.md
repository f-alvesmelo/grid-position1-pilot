---
type: variable
project: GRID
position: 1
status: pilot
---

# Variables

Command: `/operationalize`. Companion to [[Data Dictionary]] — organizes the same variables by theoretical role (IV / DV / moderator) rather than by table. Sources: [[Measurement Research Design]], [[Refined Measurement Framework]].

## Independent Variable: Political Alignment Configuration

- **Dyadic scores**: `align_NG_local`, `align_NG_IDP`, `align_local_IDP` — each 2/1/0/NA.
- **Primary explanatory measure**: `alignment_configuration` (full three-dyad vector). Not reduced to a scalar average, since e.g. (2,2,1) and (2,0,2) are substantively different configurations that would average similarly.
- **Parsimonious derived measure**: `alignment_structure` (shared alignment / predominantly aligned / fragmented / shared opposition / indeterminate) — use where a simpler specification is theoretically appropriate.
- **Evidence quality** (separate from the score): `alignment_confidence` (High/Medium/Low/Insufficient) and `alignment_evidence_coverage` (0–3 dyads observed).
- **Timing**: `align_timing` — measured pre-displacement/onset-period, to avoid post-treatment bias.
- **Actor requiring special care**: the displaced-population side of two dyads (`align_NG_IDP`, `align_local_IDP`) requires first identifying the *politically salient displaced population or group* tied to the specific displacement episode — the population is not assumed homogeneous.

## Moderator: Institutional Authority Locus

- **Four indicators**, each domain-level: `authority_formal`, `authority_budget`, `authority_admin`, `authority_actual` (each N/L/S/D/U).
- **Derived final variable**: `authority_locus` (N/L/S/D/U), combining the four indicators — see [[Coding Protocol]] for derivation logic.
- **Theoretical role**: per H3, determines which alignment dyad should be most predictive of the domain's response. The Delegated (D) case is the least theoretically settled — see [[Mechanisms]].
- **Design principle**: coded per **domain and episode/period**, not as a country-level constant, because the same state can have different authority arrangements across domains (e.g., national legal status vs. delegated humanitarian implementation).

## Dependent Variable: Government Response

- **Structure**: two layers coded separately per domain — `response_de_jure`, `response_de_facto`, each three-valued (protective / restrictive-repressive / absent).
- **Derived construct**: `response_consistency`, a 2×2 cross-tabulation of the two layers (see [[Coding Protocol]]).
- **Pilot domain**: `domain` = `humanitarian_assistance` only. Same variable structure applies, in principle, to other domains once `domain` takes those values — not yet coded.

## Variable Roles Not Yet Defined

- Domain-level covariates (administrative capacity, conflict intensity, territorial control) — named in [[Project Brief]] as *alternative explanations* to distinguish from political alignment during process tracing, but not yet built as codeable variables.
- Displacement-cause variable (state-caused vs. other-caused) — named as a methodological safeguard, not yet built as a variable.
- `episode_id` boundary rule.

## Related

[[Data Dictionary]] · [[Coding Protocol]] · [[Evidence Standards]] · [[Research Questions]] · [[Mechanisms]] · [[Refined Measurement Framework]]
