---
type: project
project: GRID
position: 1
status: pilot
---

# Research Design Audit

Command executed: `/audit`
Perspective: cross-national comparative research (per AGENT.md §4). No numerical scores are used, per instruction.

## Research Question

- STRENGTH — The question is explicitly comparative and explicitly multilevel: it asks how *configurations* of alignment across three actor levels shape response *composition* across territories and domains. This is a well-posed comparative question with clear variation to explain (composition of protection/repression) and a clear proposed source of variation (alignment configuration).
- STRENGTH — The unit of analysis is at least partially specified per tier (country-year implied for cross-national; municipality-year for Colombia; location-level for Iraq).
- GAP — "Policy domain" is invoked in the research question itself but no domains are named anywhere in the project text.
- OPEN QUESTION — Is the outcome a single scalar (degree of protection vs. repression) or a genuinely multi-category "composition" (e.g., a vector across domains)? The wording ("composition") suggests the latter, which is analytically more demanding and needs to be resolved before operationalization.

## Theory

- STRENGTH — The core theoretical move (alignment as multilevel/non-scalar, conditioned by institutional location of authority) is explicit and non-trivial; it directly motivates H3 as a moderation hypothesis rather than treating H1/H2 as universal laws.
- GAP — The causal mechanism connecting "alignment configuration" to "response composition" is asserted but not walked through step by step (e.g., what specifically changes in a government's incentives or capacity when alignment is fragmented vs. shared?).
- RISK — Without an explicit mechanism, H1–H3 risk being tested as correlational patterns without a clear falsification path for the *mechanism* itself (as opposed to the pattern).
- DEVELOPMENT OPPORTUNITY — A `/theory` pass could make the CONCEPT → MECHANISM → EXPECTED RELATIONSHIP → OBSERVABLE IMPLICATION chain explicit for each hypothesis.

## Measurement

- GAP — No operational definition of "political alignment" is given for any of the three actor levels (national government, local authority, displaced population). The IDP level is particularly undertheorized as a measurable political actor.
- GAP — No operational definition of "protection" and "repression" as a composition is given; GRID's own existing coding scheme is referenced only implicitly (via the project's own name and framing), not reproduced or cited with a specific source.
- RISK — Measurement validity is explicitly flagged by the researcher as a concern (Adcock & Collier, 2001) because alignment "can take different institutional forms across contexts" — this is a real risk for cross-national comparability of the alignment measure specifically.
- OPEN QUESTION — Will de jure and de facto responses be coded and analyzed separately, or collapsed into a single protection/repression score? The project's own framing ("formal policies... but implementation varies... informal practices may diverge") suggests they should be distinguished, but no decision is stated.

## Dataset

- STRENGTH — The nested design gives each tier a plausible observation unit (country-year; municipality-year; location-level).
- GAP — Temporal dimension (start/end years) is unspecified for every tier.
- GAP — Geographical/country dimension for the cross-national tier (which countries, how many) is unspecified.
- OPEN QUESTION — Level of government: the design mentions "national" and "local" but does not specify how many subnational tiers exist within each case (e.g., is there a regional tier between national and municipal in Colombia?).

## Evidence

- STRENGTH — For the qualitative tier, the researcher already names concrete evidence types (government/administrative documents, policy records, humanitarian sources, interviews) and named alternative explanations to rule out (administrative capacity, conflict intensity, territorial control) — this is an unusually well-specified process-tracing design for a proposal stage.
- GAP — No evidence standard or confidence scheme (e.g., HIGH/MEDIUM/LOW/UNRESOLVED) is yet defined for how quantitative alignment codings will be documented.
- DEVELOPMENT OPPORTUNITY — Building `02_Data/Evidence Standards.md` and `02_Data/Coding Protocol.md` before any pilot coding, per AGENT.md §12.

## Comparative Inference

- STRENGTH — The researcher explicitly rejects treating Iraq and Burundi as "statistically equivalent cases" and frames them instead through nested-analysis logic (Lieberman, 2005) — this is methodologically sound and avoids a common comparative-design error (false symmetry between cases with very different data availability).
- STRENGTH — The Colombia case is explicitly positioned against existing literature (Steele 2011; Steele 2017) with a clear statement of what is different about this project's angle (responses *after* displacement, not the *production* of displacement) — this shows awareness of how the case contributes beyond replication.
- OPEN QUESTION — What alternative explanations, beyond administrative capacity/conflict intensity/territorial control (named for the qualitative tier), will be considered for the cross-national statistical tier?

## Reproducibility

- STRENGTH — The quantitative pipeline is already specified at a useful level of concreteness (R; harmonisation → estimation → clustered inference → reproducible visualisation).
- GAP — No data provenance or reproducibility documentation exists yet (expected under `07_Reproducibility/`, to be built via `/reproduce`).
- RISK — Because the GRID cross-national dataset is an external/shared resource, reproducibility for this pilot will depend on documenting exactly which GRID dataset version/vintage is used — this is not yet addressed.

## Summary of Priority Items

1. ~~Resolve whether "response composition" is scalar or multi-category (affects everything downstream).~~ — **Resolved 2026-09-27: multi-domain.**
2. ~~Decide whether de jure/de facto responses are coded separately.~~ — **Resolved 2026-09-27: yes, coded separately, with explicit definitions and a 2×2 consistency matrix ([[Measurement Research Design]] §3, §6).**
3. ~~Specify at least one policy domain to make the pilot demonstrable.~~ — **Resolved 2026-09-27: humanitarian assistance; full illustrative domain list also now known.**
4. ~~Draft an explicit mechanism chain for H1–H3.~~ — **Resolved 2026-09-27** (structurally): a full CONCEPT → MECHANISM → EXPECTED RELATIONSHIP → OBSERVABLE IMPLICATION table exists per hypothesis in [[Mechanisms]], now referencing the precise `alignment_structure` and `authority_locus` categories. The *mechanism* content itself (why aligned actors face lower costs of protection; the delegated-authority case) remains partly AGENT PROPOSAL pending researcher confirmation — see [[Mechanisms]] "What Remains Open".
5. ~~Define an evidence-confidence scheme before any coding.~~ — **Resolved 2026-09-27**: [[Refined Measurement Framework]] §3 supplies a High/Medium/Low/Insufficient scheme with a 3-tier evidence hierarchy, replacing the agent's earlier draft proposal. See [[Evidence Standards]]. Not yet extended to authority-locus or response variables — ⚠ open.

## Researcher Decisions (2026-09-27)

See [[Changelog]] for the full record. This audit's original text above is left unchanged (per AGENT.md §25, substantive changes are recorded in the changelog rather than silently rewritten into prior analysis). Two subsequent changelog entries (2026-09-27) resolve all five priority items via two researcher-supplied memos: [[Measurement Research Design]] (items 1–3, partial 4) and [[Refined Measurement Framework]] (items 4 refinement, 5, plus the aggregation and authority-locus operationalizations that item 4/5 depended on).

## New Items Surfaced by the Refined Framework (2026-09-27)

- The mechanism for `authority_locus` = Delegated (D) is explicitly unsettled — worth resolving before coding delegated-authority domains (see [[Mechanisms]]).
- Evidence-confidence scheme is not yet extended beyond political alignment to authority-locus indicators or response variables.
- `episode_id` boundary rule still undefined.
- Derivation rule from the four authority indicators to final `authority_locus` is explicitly provisional pending a pilot (per the memo's own status note).

## Related

[[Project Ingestion Report]] · [[Project Brief]] · [[Research Questions]] · [[Scope & Limitations]] · [[GRID Position 1 Alignment]] · [[Changelog]] · [[Measurement Research Design]] · [[Refined Measurement Framework]]
