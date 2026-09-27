---
type: method
project: GRID
position: 1
status: pilot
---

# Coding Protocol

Command: `/operationalize`. Sources: [[Measurement Research Design]], [[Refined Measurement Framework]]. Purpose (per AGENT.md §10): explain how a researcher would reach the *same* coding decision when encountering comparable evidence in another country or year.

## Scope

This protocol currently covers **one policy domain: humanitarian assistance** (`domain` = `humanitarian_assistance`), plus the **political alignment** and **authority locus** instruments, which are designed to generalize to other domains once those are coded.

## Step 1 — Identify the Displacement Episode and Politically Salient Displaced Population

Before coding alignment, identify:
1. The displacement episode (`episode_id`): country, approximate onset date.
2. The **politically salient displaced population or group** associated with that episode — not assumed homogeneous; may vary by episode even within the same country.

**For Burundi, Iraq, and Colombia**: real IDMC event records (`event_id`, event name, start/end date, Conflict/Disaster category) are available in [[Data Sources]] and can be used directly as `episode_id` candidates, prioritizing Conflict-category events as the closer match to "state-caused displacement." Disaster-category events are still valid episodes for the humanitarian-assistance domain but sit outside the political-alignment mechanism's core logic (a flood is not caused by political alignment, though the *response* to it still can be).

⚠ For any country without event-level IDMC data on hand, the exact rule for delimiting an episode boundary is not yet specified — flag ambiguous cases as `episode_boundary_unclear` rather than guessing.

## Step 2 — Code Political Alignment (Pre-Displacement / Onset Period)

For each of the three dyads, ask the dyad's primary question (see [[Political Alignment]]) using evidence dated to the **pre-displacement or onset period**:

| Variable | Dyad |
|---|---|
| `align_NG_local` | National government ↔ local authority |
| `align_NG_IDP` | National government ↔ displaced population |
| `align_local_IDP` | Local authority ↔ displaced population |

Coding values: **2 = aligned**, **1 = cross-cutting/ambiguous**, **0 = opposed**, **NA = insufficient evidence**.

**Rule**: if evidence is genuinely ambiguous/conflicting, code 1. If evidence is simply absent, code NA. Never convert NA into 1 or any other substantive score.

## Step 3 — Assess Evidence Confidence for Each Dyadic Score

Independently of the substantive score, rate `alignment_confidence` for each dyad using the evidence-tier hierarchy in [[Evidence Standards]]:

| Confidence | Rule |
|---|---|
| High | Direct, explicit evidence from a primary/authoritative source, ideally corroborated independently. |
| Medium | One credible direct source, or multiple consistent indirect sources. |
| Low | Indirect, incomplete, or weakly corroborated evidence — tentative classification only. |
| Insufficient | Evidence absent, contradictory, or too weak — code the dyad NA. |

**Rule**: Tier-3 evidence (historical/contextual association; ethnic, religious, or geographic proximity) is never sufficient alone for a High rating, and must not be treated as evidence of political alignment by default.

## Step 4 — Derive Configuration and Structure

1. Assemble `alignment_configuration` = (`align_NG_local`, `align_NG_IDP`, `align_local_IDP`).
2. Count `alignment_evidence_coverage` = number of non-NA dyads (0–3).
3. Derive `alignment_structure`:

| Configuration | All 3 dyads | Rule |
|---|---|---|
| Shared alignment | 2, 2, 2 | All three coded 2. |
| Predominantly aligned | 2/1, 2/1, 2/1 | No dyad coded 0; at least one coded 1. |
| Fragmented | mixed, incl. ≥1 zero | At least one dyad = 0 and the configuration is non-uniform, with sufficient evidence (coverage ≥ 2) to establish non-uniformity. |
| Shared opposition | 0, 0, 0 | All three coded 0. |
| Indeterminate | — | Coverage ≤ 1, or otherwise insufficient to classify. |

Do not treat configurations with the same numerical average (e.g., (2,2,1) vs. (2,0,2)) as equivalent — always classify from the full vector, not a mean.

## Step 5 — Code Authority Locus for the Domain

For the domain being coded (pilot: `humanitarian_assistance`), record each of the four indicators separately, each N/L/S/D/U:

| Variable | Question |
|---|---|
| `authority_formal` | Who is legally responsible for this domain? |
| `authority_budget` | Who controls the relevant resources? |
| `authority_admin` | Which institution formally implements the policy? |
| `authority_actual` | Who actually authorized/restricted/distributed/withdrew the response? |

Then derive `authority_locus` using the illustrative rules below (to be finalized after piloting):
- National legal responsibility + national budget + national implementation → **N**.
- National legal framework + meaningful municipal authority and implementation → potentially **S**, where both levels hold substantive decision-making power.
- National government retains formal responsibility but formally assigns implementation to municipalities → **D**, if the arrangement meets the delegation criterion.
- Municipality has legal responsibility, controls resources, and makes the decisions → **L**.
- If the four indicators do not point to a consistent level and no derivation rule resolves them → **U**.

## Step 6 — Code Humanitarian-Assistance Response (De Jure and De Facto, Separately)

Answer, in order:
1. What formal entitlement, programme, allocation, institutional responsibility, or restriction exists? → codes `response_de_jure`.
2. What assistance is actually provided, facilitated, restricted, selectively withheld, or withdrawn? → codes `response_de_facto`.
3. Is the response protective, restrictive-repressive, or absent? → the classification applied to steps 1 and 2.
4. Does the de facto response correspond to or diverge from the de jure response? → derives `response_consistency` (Step 7).

**Key rule** (apply to both layers independently): absence of a de jure policy must **not** automatically be coded as absence of a de facto response, and absence of a formal response must **not** automatically be treated as repression. "Absent" is a distinct third value.

## Step 7 — Derive Response Consistency

Cross-tabulate `response_de_jure` × `response_de_facto`:

| | De facto protective | De facto restrictive-repressive |
|---|---|---|
| **De jure protective** | Consistent protection | Protective-inconsistent response |
| **De jure restrictive-repressive** | Repressive-inconsistent response | Consistent repression/restriction |

(Cases involving "absent" on either layer fall outside this 2×2 and should be flagged separately — ⚠ OPERATIONALIZATION OPEN: exact treatment of "absent" combinations not yet specified.)

## Step 8 — Document Every Coding Decision

For each observation, record (per AGENT.md §12's observation → variable → coding decision → evidence → source → confidence chain):

| Observation | Variable | Code | Evidence | Source | Confidence | Notes |
|---|---|---|---|---|---|---|
| e.g. Episode X, 2005 | `align_NG_IDP` | 0 | ... | ... | High/Medium/Low/Insufficient | ... |

## Methodological Safeguards (verbatim from the researcher's memos)

- Do not collapse multidimensional responses into a single protection–repression score unless the evidence justifies a specific aggregation rule.
- Do not treat missing evidence as moderate alignment.
- Measure political alignment before, or as close as possible to, the onset of the relevant displacement episode.
- Distinguish state-caused displacement from displacement caused by other actors where the data permit.
- Separate political choice from capacity constraints, territorial control, conflict intensity, and humanitarian access.
- Do not promise a particular estimator before inspecting the final GRID data structure.
- Pilot the coding rules on a small set of cases and assess intercoder agreement before scaling up.
- Treat Colombia as a potential in-depth component, not a requirement to reproduce all three GRID country studies.
- Do not calculate a single scalar alignment index — the configuration carries information a mean would destroy.
- Tier-3 evidence alone is never sufficient for high-confidence alignment coding.
- `authority_locus` is coded per domain and episode/period, never assumed constant for a country.

## Status

This protocol has **not yet been piloted**. Per the researcher's own memos, exact thresholds for `alignment_structure` and `authority_locus`, and intercoder reliability, should be established through a small pilot before full cross-national coding begins.

## Related

[[Data Dictionary]] · [[Variables]] · [[Evidence Standards]] · [[Political Alignment]] · [[Protection]] · [[Repression]] · [[Refined Measurement Framework]]
