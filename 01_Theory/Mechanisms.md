---
type: mechanism
project: GRID
position: 1
status: pilot
---

# Mechanisms

Command: `/theory`. Per AGENT.md §9: CONCEPT → MECHANISM → EXPECTED RELATIONSHIP → OBSERVABLE IMPLICATION → EMPIRICAL EVIDENCE, for each theoretical claim. Sections marked RESEARCHER MATERIAL restate the project/memo directly; sections marked AGENT PROPOSAL are structural scaffolding added to make the chain explicit and require researcher confirmation.

## Conceptual Model (RESEARCHER MATERIAL)

> "Pre-displacement political alignment configuration → political incentives and relationships → domain-specific government response, with institutional location of authority conditioning where and through whom those incentives can translate into policy and practice."

— [[Measurement Research Design]] §10, restated with a refinement from [[Refined Measurement Framework]] §7 (authority conditions *where and through whom* incentives translate into response, not merely *whether* they do).

The three constructs are analytically distinct (per [[Refined Measurement Framework]] §7):

| Construct | Core question |
|---|---|
| Political alignment configuration | Who is politically related to whom? |
| Authority locus | Who has institutional power over the relevant response domain? |
| Government response | What did the state formally and actually do? |

This is the only mechanism statement given directly by the researcher. Everything below elaborates its structure without adding new causal content; where elaboration is the agent's organizational proposal rather than a researcher claim, it is marked AGENT PROPOSAL.

## H1 — Shared Alignment → More Protective Responses

| Step | Content | Source |
|---|---|---|
| CONCEPT | Political alignment configuration = **shared alignment** (`alignment_structure` = shared alignment, i.e., all three dyads = 2) | RESEARCHER MATERIAL, now precisely defined per [[Refined Measurement Framework]] §1 |
| MECHANISM | Shared alignment → aligned political incentives across levels → fewer political costs to extending protection | AGENT PROPOSAL (elaborates the conceptual model; the specific claim "fewer political costs" is inferred, not stated verbatim, and should be confirmed by the researcher) |
| EXPECTED RELATIONSHIP | H1: greater alignment (shared > predominantly aligned > fragmented/shared opposition) → more protective response profiles | RESEARCHER MATERIAL |
| OBSERVABLE IMPLICATION | In the humanitarian-assistance pilot domain: cases with `alignment_structure` = shared alignment should show a higher rate of `response_de_jure`/`response_de_facto` = "consistent protection" than cases coded fragmented or shared opposition. Restrict to High/Medium `alignment_confidence` observations for the principal test; treat Low-confidence cases as a sensitivity check (per [[Evidence Standards]]). | AGENT PROPOSAL — a candidate empirical test, not yet run |
| EMPIRICAL EVIDENCE | [EVIDENCE NEEDED] — requires pilot coding of both alignment and response variables. | — |

## H2 — Fragmented Alignment → Heterogeneous (Mixed) Responses

| Step | Content | Source |
|---|---|---|
| CONCEPT | Political alignment configuration = **fragmented** (`alignment_structure` = fragmented, i.e., at least one dyad = 0 in a non-uniform configuration) | RESEARCHER MATERIAL, now precisely defined per [[Refined Measurement Framework]] §1 |
| MECHANISM | Fragmentation → different actors face different incentives depending on which level holds authority over the domain → response reflects whichever actor's incentives dominate for that domain, producing inconsistency across domains/layers rather than uniform repression | AGENT PROPOSAL (elaborates the conceptual model's authority-conditioning clause) |
| EXPECTED RELATIONSHIP | H2: fragmented alignment → more heterogeneous combinations of protective and repressive responses | RESEARCHER MATERIAL |
| OBSERVABLE IMPLICATION | Cases with `alignment_structure` = fragmented should show higher rates of `response_de_jure`/`response_de_facto` divergence ("protective-inconsistent" / "repressive-inconsistent") than cases coded shared alignment or shared opposition. | AGENT PROPOSAL |
| EMPIRICAL EVIDENCE | [EVIDENCE NEEDED] | — |

## H3 — Institutional Location of Authority Moderates H1/H2

| Step | Content | Source |
|---|---|---|
| CONCEPT | `authority_locus` over the policy domain: National (N) / Local (L) / Shared (S) / Delegated (D) / Unclear (U), derived from four indicators (formal legal, budgetary, administrative, observed decision-making) | RESEARCHER MATERIAL, now fully operationalized per [[Refined Measurement Framework]] §4–6 |
| MECHANISM | The alignment dyad that matters most for a domain's response is the dyad involving the actor that actually holds authority over that domain — e.g., if `authority_locus` = L (local), `align_local_IDP` should predict response better than `align_NG_IDP`. For `authority_locus` = D (delegated), the mechanism is more complex: formal responsibility sits with one actor while implementation sits with another, so *both* the delegating and delegated actors' alignment may matter. | AGENT PROPOSAL — the delegated case in particular is not yet worked out by the researcher and is flagged as a genuine open modeling question |
| EXPECTED RELATIONSHIP | H3: the alignment–response relationship varies by `authority_locus` (moderation) | RESEARCHER MATERIAL |
| OBSERVABLE IMPLICATION | In domains coded `authority_locus` = L, `align_local_IDP` should predict `response_de_jure`/`response_de_facto` better than `align_NG_IDP`; the reverse should hold for `authority_locus` = N. Domains coded S (shared) should show both dyads mattering; domains coded D (delegated) are the least theoretically settled case (see Mechanism column). | AGENT PROPOSAL |
| EMPIRICAL EVIDENCE | [EVIDENCE NEEDED] — `authority_locus` is now a defined, codeable variable (see [[Data Dictionary]]), but no cases have been coded yet. | — |

## What Remains Open

- The mechanism connecting alignment to "political incentives and relationships" is asserted at a high level; it does not yet specify *why* aligned actors face lower costs of protection (electoral accountability? shared identity? resource dependence?). This is a genuine gap the researcher may want to address before process tracing (Iraq/Burundi) is designed, since process tracing needs competing mechanism-level predictions to adjudicate between.
- The mechanism for `authority_locus` = **Delegated (D)** is explicitly the least settled case (see H3 above) — worth resolving before coding delegated-authority domains.
- ~~No aggregation rule for the alignment typology.~~ — **Resolved**: `alignment_configuration` / `alignment_structure` (see [[Political Alignment]]).
- ~~Institutional location of authority not yet coded as a variable.~~ — **Resolved**: `authority_locus`, derived from four indicators (see [[Data Dictionary]], [[Coding Protocol]]).

## Related

[[Core Argument]] · [[Political Alignment]] · [[Observable Implications]] · [[Research Questions]] · [[Coding Protocol]] · [[Refined Measurement Framework]]
