---
type: concept
project: GRID
position: 1
status: pilot
---

# Political Alignment

Command: `/theory`. Sources: [[Measurement Research Design]] §4–5, [[Refined Measurement Framework]] §1–2. RESEARCHER MATERIAL.

## Definition

Political alignment is the configuration of political relationships among three actor levels — **national government, local authority, and displaced population** — rather than a single scalar quantity. "A single scalar alignment score is not recommended because it would obscure the configuration of relationships" (researcher's memo).

## Measured Relationally, by Dyad

Alignment is assessed separately for each of three dyads (canonical variable names per [[Refined Measurement Framework]] §8):

| Dyad | Variable | Primary question | Possible evidence |
|---|---|---|---|
| National government ↔ local authority (NG–L) | `align_NG_local` | Are the governing coalitions politically congruent, cross-cutting, or opposed? | Partisan/coalitional affiliation, electoral alignment, formal alliances, documented conflict or cooperation. |
| National government ↔ displaced population (NG–D) | `align_NG_IDP` | Is the politically salient displaced population aligned with, cross-cutting relative to, or opposed to the national governing coalition? | Political affiliation/coalition, electoral evidence where available, documented alliances or exclusion, evidence on politically salient group identity. |
| Local authority ↔ displaced population (L–D) | `align_local_IDP` | Is the relevant local governing coalition aligned with, cross-cutting relative to, or opposed to the displaced population? | Local political affiliation, electoral evidence, documented relationships, alliances, conflict, or exclusion. |

## Coding Scale

- **2** = aligned
- **1** = cross-cutting / ambiguous
- **0** = opposed
- **NA** = insufficient evidence

**Rule**: unknown/insufficient evidence must remain missing (NA) — it must **not** be coded as moderate alignment (1). This preserves the distinction between "genuinely ambiguous/cross-cutting" and "we don't know."

## Configuration (Combining the Three Dyads)

✓ **RESOLVED, per [[Refined Measurement Framework]] §1–2.** The recommended approach is **not** to calculate a single scalar alignment index — averaging would lose theoretically meaningful information (e.g., (2,2,1) and (2,0,2) average similarly but represent substantively different political structures).

Two variables are retained:
- **`alignment_configuration`** — the full three-dyad vector, e.g. (2,2,2), (2,2,1), (2,0,2). This is the **primary explanatory measure**.
- **`alignment_structure`** — a derived categorical summary, used where a more parsimonious specification is theoretically appropriate:

| Configuration | NG–L | NG–D | L–D | Interpretation |
|---|---|---|---|---|
| Shared alignment | 2 | 2 | 2 | All three relationships are aligned. |
| Predominantly aligned | 2/1 | 2/1 | 2/1 | No observed opposition, but at least one relationship is cross-cutting/ambiguous. |
| Fragmented | mixed | mixed | mixed | At least one dyad is opposed and the configuration is non-uniform. |
| Shared opposition | 0 | 0 | 0 | All three relationships are opposed. |
| Indeterminate | NA-heavy | NA-heavy | NA-heavy | Insufficient evidence to classify the configuration. |

**Primary rule**: shared alignment requires all three dyads coded 2; fragmented alignment requires at least one dyad coded 0 with sufficient evidence to establish a non-uniform configuration.

**Missing-dyad handling**: 3/3 observed → classify normally; 2/3 observed → classify only if sufficient to establish the configuration; 1/3 or 0/3 observed → indeterminate. A separate variable, `alignment_evidence_coverage` (0–3), records how many dyads were actually observed. NA is never converted into 1 or another substantive score.

This directly refines H1 ("shared alignment") and H2 ("fragmented alignment") from loose descriptive terms into the precise categories above — see [[Research Questions]] and [[Mechanisms]].

## The Displaced Population as a Political Actor

The displaced population is **not assumed to be politically homogeneous**. For cross-national coding, the analyst must first identify the **politically salient displaced population or group** associated with the specific displacement episode being coded.

## Temporal Ordering (Avoiding Post-Treatment Bias)

Alignment must be measured **before or as close as possible to the onset of the relevant displacement episode**:

1. Pre-displacement or onset-period political alignment
2. Displacement episode
3. Subsequent government response

Rationale (researcher's own words): "This reduces the risk of measuring alignment after it has itself been altered by government protection, repression, displacement, or selection into displacement." This directly operationalizes the identification concern already flagged in [[Project Brief]] (alignment may affect the production of displacement itself).

## Reliability and Confidence

✓ **RESOLVED, per [[Refined Measurement Framework]] §3.** Confidence in the evidence underlying each dyadic score (`alignment_confidence`: High / Medium / Low / Insufficient) is tracked **separately** from the substantive score itself — a relationship can be coded 0 with high confidence. See [[Evidence Standards]] for the full scheme and evidence-tier hierarchy. Exact thresholds for deriving `alignment_structure` should still be validated through a pilot coding exercise (per the memo's own status note).

## Related

[[Core Argument]] · [[Concepts]] · [[Mechanisms]] · [[Coding Protocol]] · [[Data Dictionary]] · [[Refined Measurement Framework]]
