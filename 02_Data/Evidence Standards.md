---
type: method
project: GRID
position: 1
status: pilot
---

# Evidence Standards

Command: `/operationalize`. Per AGENT.md §12, this file defines evidence-confidence categories before they are used in coding. ✓ **Resolved 2026-09-27** by [[Refined Measurement Framework]] §3 — this supersedes the agent-proposed scheme drafted in the prior iteration of this file (see [[Changelog]]).

## Confidence Categories (RESEARCHER MATERIAL, per [[Refined Measurement Framework]] §3)

Confidence is kept **analytically separate** from the substantive alignment score — weak evidence does not mean the relationship itself is ambiguous. A relationship can be coded 0 (opposed) with high confidence.

| Confidence | Rule |
|---|---|
| **High** | Direct, explicit evidence from a primary or authoritative source, ideally corroborated by an independent source. |
| **Medium** | One credible direct source, or multiple consistent indirect sources. |
| **Low** | Indirect, incomplete, or weakly corroborated evidence permitting only a tentative classification. |
| **Insufficient** | Evidence absent, contradictory, or too weak to justify substantive coding; code the underlying variable NA. |

## Evidence Hierarchy (RESEARCHER MATERIAL)

| Tier | Evidence type | Examples |
|---|---|---|
| **Tier 1** | Direct political evidence | Party/coalition membership, formal coalition agreements, electoral endorsement, documented political alliances, official political affiliation. |
| **Tier 2** | Observable political relationships | Electoral support patterns, documented cooperation, political appointments, public alliances, documented exclusion/conflict. |
| **Tier 3** | Indirect contextual evidence | Historical relationships or contextual associations. |

**Rule**: Tier 3 evidence alone is never sufficient for a High-confidence classification. In particular, ethnic, religious, geographic, or historical proximity must **not** be automatically treated as evidence of political alignment.

## Analytical Treatment of Confidence Levels (RESEARCHER MATERIAL)

- **High and Medium** confidence observations: constitute the principal analytical sample.
- **Low** confidence observations: remain in the dataset but are flagged for sensitivity analysis (not used in the principal specification).
- **Insufficient** evidence: coded NA on the underlying variable; excluded from substantive coding.

## Applies To

Currently specified for **political alignment** dyads (`align_NG_local`, `align_NG_IDP`, `align_local_IDP` → `alignment_confidence`). The researcher's memo does not yet extend an explicit confidence scale to the authority-locus indicators (`authority_formal`/`budget`/`admin`/`actual`) or to the response variables (`response_de_jure`/`response_de_facto`) — ⚠ OPERATIONALIZATION OPEN whether the same High/Medium/Low/Insufficient scale should be reused there or a domain-specific scheme is needed.

## Evidence Table Template (per AGENT.md §12)

| Observation | Variable | Code | Evidence | Source | Confidence | Notes |
|---|---|---|---|---|---|---|
| | | | | | | |

## What Remains for the Researcher to Decide

- Whether/how to extend the confidence scheme to `authority_locus` indicators and response variables.
- Exact thresholds distinguishing High vs. Medium vs. Low in edge cases — explicitly deferred to a pilot coding exercise with intercoder reliability checks.
- Intercoder reliability procedure and acceptable agreement threshold — not yet specified.

## Related

[[Coding Protocol]] · [[Data Dictionary]] · [[Variables]] · [[Political Alignment]] · [[Research Design Audit]] · [[Refined Measurement Framework]]
