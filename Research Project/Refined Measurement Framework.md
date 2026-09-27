---
type: source
project: GRID
position: 1
status: pilot
source_file: GRID_Position_1_Refined_Measurement_Framework.docx
ingested: 2026-09-27
supersedes: partial refinement of Measurement Research Design.md
---

# GRID Position 1: Refining the Measurement Framework

> Markdown transcription of `Refined Measurement Framework.docx`, provided by the researcher on 2026-09-27. RESEARCHER MATERIAL. Consolidates decisions on three previously open items: alignment aggregation, evidence confidence, and authority locus. Supersedes the corresponding open questions in [[Measurement Research Design]] without contradicting its other content.

**Subtitle**: Aggregation of political alignment, evidence confidence, and authority locus

**Purpose**: This memo consolidates the methodological decisions and refinements concerning three open questions: (1) how to aggregate the three dyadic political-alignment scores; (2) how to assess confidence in the evidence underlying those scores; and (3) how to operationalize the institutional locus of authority.

## 1. Aggregating the three dyadic scores

The three dyadic relationships are coded separately:

| Dyad | Relationship |
|---|---|
| NG–L | National government ↔ local authority |
| NG–D | National government ↔ displaced population |
| L–D | Local authority ↔ displaced population |

Each dyad receives: 2 = aligned; 1 = cross-cutting/ambiguous; 0 = opposed; NA = insufficient evidence.

The recommended approach is **not** to calculate a single scalar alignment index — the three-way configuration contains theoretically meaningful information that would be lost through simple averaging.

**Recommended derived typology (`alignment_structure`):**

| Configuration | NG–L | NG–D | L–D | Interpretation |
|---|---|---|---|---|
| Shared alignment | 2 | 2 | 2 | All three relationships are aligned. |
| Predominantly aligned | 2/1 | 2/1 | 2/1 | No observed opposition, but at least one relationship is cross-cutting/ambiguous. |
| Fragmented | mixed | mixed | mixed | At least one dyad is opposed and the configuration is non-uniform. |
| Shared opposition | 0 | 0 | 0 | All three relationships are opposed. |
| Indeterminate | NA-heavy | NA-heavy | NA-heavy | Insufficient evidence to classify the configuration. |

**Primary rule**: shared alignment requires all three dyads coded 2. Fragmented alignment requires at least one dyad coded 0, provided there is sufficient evidence to establish a non-uniform configuration.

Configurations should not be treated as equivalent simply because they produce the same numerical average — e.g., (2,2,1) and (2,0,2) represent substantively different political structures.

## 2. Preserve the full configuration in the dataset

Two variables should be retained:

| Variable | Purpose |
|---|---|
| `alignment_configuration` | Stores the full three-dyad vector, e.g. (2,2,2), (2,2,1), or (2,0,2). |
| `alignment_structure` | Derived categorical summary: shared alignment / predominantly aligned / fragmented / shared opposition / indeterminate. |

The full configuration should be the primary explanatory measure; the categorical variable can be used where a more parsimonious specification is theoretically appropriate.

**Treatment of missing dyads:**
- 3/3 dyads observed: classify normally.
- 2/3 dyads observed: classify only when the observed relationships are sufficient to establish the configuration.
- 1/3 dyads observed: generally classify as indeterminate.
- 0/3 dyads observed: indeterminate.

NA should never be converted into 1 or another substantive score. A separate variable, `alignment_evidence_coverage`, records how many dyads are actually observed (0–3).

## 3. Evidence-confidence scheme

Confidence should be kept analytically separate from the substantive alignment score. Weak evidence does not mean the relationship itself is ambiguous — a relationship can be coded 0 with high confidence.

| Confidence | Proposed rule |
|---|---|
| High | Direct, explicit evidence from a primary or authoritative source, ideally corroborated by an independent source. |
| Medium | One credible direct source, or multiple consistent indirect sources. |
| Low | Indirect, incomplete, or weakly corroborated evidence permitting only a tentative classification. |
| Insufficient | Evidence absent, contradictory, or too weak to justify substantive coding; code as NA. |

**Recommended evidence hierarchy:**
- **Tier 1**: direct political evidence — party/coalition membership, formal coalition agreements, electoral endorsement, documented political alliances, official political affiliation.
- **Tier 2**: observable political relationships — electoral support patterns, documented cooperation, political appointments, public alliances, documented exclusion/conflict.
- **Tier 3**: indirect contextual evidence — historical relationships or contextual associations.

Tier 3 evidence should **not** by itself be sufficient for a high-confidence classification. In particular, ethnic, religious, geographic, or historical proximity should not automatically be treated as evidence of political alignment.

**Recommended analytical treatment**: High- and Medium-confidence observations can constitute the principal analytical sample. Low-confidence observations should remain in the dataset but be flagged for sensitivity analysis. Insufficient evidence should be coded NA.

## 4. `authority_locus`: make it domain-specific

The strongest revision is to avoid treating `authority_locus` as a country-level characteristic. Authority should be coded for each relevant government-response domain and period/episode.

The same state may have national authority over legal status, local authority over shelter allocation, shared authority over education, and delegated implementation of humanitarian assistance. A single national/local value would obscure the institutional structure the theory seeks to examine.

| Code | authority_locus | Meaning |
|---|---|---|
| N | National | National government has primary decision-making authority. |
| L | Local/subnational | Local authority has primary decision-making authority. |
| S | Shared/concurrent | National and local authorities both possess meaningful decision-making authority. |
| D | Delegated | Authority formally originates at a higher level but implementation or decision authority is delegated downward or to another actor. |
| U | Unclear | Evidence is insufficient to determine the institutional locus. |

Delegated should be treated as an institutional relationship rather than simply another geographical level.

## 5. Evidencing authority locus

The authority instrument should combine four indicators, making `authority_locus` empirically observable rather than an impressionistic assessment:

| Indicator | Question | Possible evidence |
|---|---|---|
| A. Formal legal allocation | Who is legally responsible for the policy domain? | Constitution, legislation, executive decrees, regulations, administrative statutes, official policy frameworks. |
| B. Budgetary authority | Who controls the relevant resources? | National/municipal budgets, programme financing, intergovernmental transfers, earmarked funds, procurement authority. |
| C. Administrative/implementation authority | Which institution is formally responsible for implementing the policy? | Administrative mandates, programme manuals, agency structures, implementation guidelines, official records. |
| D. Observed decision-making | Who actually authorized, restricted, distributed, or withdrew the response? | Administrative decisions, government orders, programme records, court documents, official correspondence, humanitarian documentation, appropriate interviews. |

## 6. Deriving `authority_locus`

The four indicators should be recorded separately before deriving the final authority-locus category, preventing a formal legal assignment from being treated as identical to actual decision-making power.

**Illustrative derivation rules:**
- National legal responsibility + national budget + national implementation → **N** (national).
- National legal framework + meaningful municipal authority and implementation → potentially **S** (shared), where both levels possess substantive decision-making power.
- National government retains formal responsibility but formally assigns implementation to municipalities → **D** (delegated), if the institutional arrangement meets the delegation criterion.
- Municipality has legally assigned responsibility, controls relevant resources, and makes the decisions → **L** (local).

The exact derivation rule should be finalized after piloting, because formal responsibility, fiscal control, implementation authority, and actual decision-making may not always point to the same level.

## 7. Revised conceptual architecture

The three constructs remain analytically distinct:

| Construct | Core question |
|---|---|
| Political alignment configuration | Who is politically related to whom? |
| Authority locus | Who has institutional power over the relevant response domain? |
| Government response | What did the state formally and actually do? |

> Pre-displacement political alignment configuration → political incentives and relationships → domain-specific government response, with institutional location of authority conditioning where and through whom those incentives can translate into policy and practice.

## 8. Recommended final variable architecture

| Variable | Level | Coding |
|---|---|---|
| `align_NG_local` | Dyad | 2 / 1 / 0 / NA |
| `align_NG_IDP` | Dyad | 2 / 1 / 0 / NA |
| `align_local_IDP` | Dyad | 2 / 1 / 0 / NA |
| `alignment_configuration` | Episode | Full three-dyad vector |
| `alignment_structure` | Episode | Shared / predominantly aligned / fragmented / shared opposition / indeterminate |
| `alignment_confidence` | Dyad | High / medium / low / insufficient |
| `alignment_evidence_coverage` | Episode | 0–3 observed dyads |
| `authority_formal` | Domain | N / L / S / D / U |
| `authority_budget` | Domain | N / L / S / D / U |
| `authority_admin` | Domain | N / L / S / D / U |
| `authority_actual` | Domain | N / L / S / D / U |
| `authority_locus` | Domain | N / L / S / D / U |
| `response_de_jure` | Domain | Protective / restrictive-repressive / absent |
| `response_de_facto` | Domain | Protective / restrictive-repressive / absent |

## 9. Methodological implication

The resulting design avoids three major measurement problems: reducing relational political structure to a single index; conflating uncertainty with substantive ambiguity; and treating institutional authority as a fixed national attribute. It creates a transparent audit trail from source evidence to dyadic coding, from dyadic coding to political configuration, and from institutional indicators to domain-specific authority.

**Status**: Working methodological specification. The precise thresholds for deriving `alignment_structure` and `authority_locus` should be validated through a pilot coding exercise before full-scale analysis.

## Related

[[Measurement Research Design]] · [[Project]] · [[AGENT]]
