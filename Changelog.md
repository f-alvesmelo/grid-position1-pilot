---
type: project
project: GRID
position: 1
status: pilot
---

# Changelog

## 2026-09-27

### Change
Researcher resolved three of the five priority open items identified in [[Research Design Audit]]:
1. "Response composition" is **multi-domain**, not scalar.
2. De jure and de facto responses will be **coded separately**.
3. The pilot's first policy domain will be **humanitarian assistance**.

### Reason
Direct researcher decision, given in response to the agent's open questions following `/ingest-project`, `/audit`, and `/grid`.

### Status
Accepted

### Impact
- [[Research Questions]] — dependent variable section updated to reflect multi-domain composition and separate de jure/de facto coding; humanitarian assistance recorded as the first (pilot) domain, with other domains left open for later expansion.
- [[Scope & Limitations]] — de jure/de facto item removed from "not yet addressed"; pilot domain scope now bounded to humanitarian assistance for this repository, with the multi-domain ambition noted as a future-expansion item.
- [[Research Design Audit]] — priority items 1–3 marked resolved; items 4 (mechanism chain) and 5 (evidence-confidence scheme) remain open, to be addressed under `/theory` and `/operationalize`.
- [[GRID Position 1 Alignment]] — de jure/de facto distinction (Position 1's own core distinction) now reflected as an accepted design decision, not just a development opportunity.

These are RESEARCHER decisions, not AGENT proposals. No new data, sources, or findings were introduced.

## 2026-09-27 (2)

### Change
Researcher supplied a detailed methodological memo, "[[Measurement Research Design]]" (`GRID_Position_1_Measurement_Research_Design.docx`), resolving most of the remaining open operationalization items:
- Political alignment measurement instrument: relational/dyadic coding (aligned=2 / cross-cutting-ambiguous=1 / opposed=0 / NA=insufficient evidence) across three dyads (national government↔local authority; national government↔displaced population; local authority↔displaced population).
- Full illustrative domain list beyond humanitarian assistance: public services, rights and legal guarantees, mobility and territorial control, plus other domains pending the finalized GRID framework.
- De jure/de facto definitions and a 2×2 consistency matrix (consistent protection / protective-inconsistent / repressive-inconsistent / consistent repression-restriction).
- Displaced-population alignment operationalization: identify the politically salient displaced population per displacement episode, measured pre-displacement/onset-period.
- Temporal scope: cross-national tier begins 1989, extends to the latest year in the finalized GRID dataset.
- Country scope: all countries in the finalized GRID dataset — Colombia/Burundi/Iraq are case-study contexts, not the full country universe.
- A one-sentence conceptual model (mechanism): pre-displacement alignment configuration → political incentives/relationships → domain-specific response, conditioned by institutional location of authority.
- An explicit proposed empirical sequence (6 steps) and 8 methodological safeguards.

### Reason
Researcher-authored working design memo, provided directly to the agent for ingestion into the pilot repository.

### Status
Accepted (as a working methodological design — the memo itself notes the finalized GRID codebook may still alter final variables, unit of analysis, and available years)

### Impact
- [[Research Questions]], [[Scope & Limitations]], [[GRID Position 1 Alignment]], [[Research Design Audit]] — updated to reflect the resolved items above.
- New `01_Theory/` module created (`/theory`), populated from this memo's conceptual model and Project.md's theoretical argument.
- New `02_Data/` module created (`/operationalize`), populated from this memo's coding scheme, variable definitions, and evidence structure.
- Evidence-confidence scheme (Research Design Audit priority item 5) is still **not** fully resolved: the memo defines a substantive coding scale (2/1/0/NA) for alignment itself, but not a general evidence-quality confidence scheme (HIGH/MEDIUM/LOW/UNRESOLVED per AGENT.md §12) for use across variables. Flagged as remaining open work in [[Evidence Standards]].

This is RESEARCHER MATERIAL. No sources, data, or findings were added by the agent; the memo's own explicit caveats (working design, pending finalized codebook) are preserved rather than treated as settled fact.

## 2026-09-27 (3)

### Change
Researcher supplied a second methodological memo, "[[Refined Measurement Framework]]" (`GRID_Position_1_Refined_Measurement_Framework.docx`), resolving the three items left open after the previous entry:
- **Alignment aggregation**: the three dyadic scores are combined into `alignment_configuration` (full 3-dyad vector, primary measure — not a scalar average) and `alignment_structure` (shared alignment / predominantly aligned / fragmented / shared opposition / indeterminate), with explicit classification rules and missing-dyad handling (`alignment_evidence_coverage`).
- **Evidence-confidence scheme**: High / Medium / Low / Insufficient, kept analytically separate from the substantive alignment score, with a 3-tier evidence hierarchy (direct political evidence > observable political relationships > indirect contextual evidence) and explicit analytical treatment (High/Medium = principal sample; Low = sensitivity analysis; Insufficient = NA). This **replaces** the agent-proposed scheme drafted in the prior version of [[Evidence Standards]].
- **`authority_locus`**: corrected from an implied country-level characteristic to a **domain- and episode/period-specific** variable, derived from four separately-recorded indicators (`authority_formal`, `authority_budget`, `authority_admin`, `authority_actual`), each N/L/S/D/U.
- A canonical **final variable architecture** (14 variables) that supersedes the informal variable names used in the prior iteration of `02_Data/` (e.g., `align_natl_local` → `align_NG_local`; `hum_dejure`/`hum_defacto` → generic `response_de_jure`/`response_de_facto` keyed by a `domain` field).

### Reason
Researcher-authored refinement memo, provided directly to the agent, explicitly framed as consolidating decisions on the three open questions flagged in the prior changelog entry.

### Status
Accepted (as a working methodological specification — the memo's own status note flags that exact thresholds for `alignment_structure` and `authority_locus` still require pilot validation)

### Impact
- [[Political Alignment]], [[Concepts]], [[Mechanisms]], [[Observable Implications]] (all in `01_Theory/`) — updated with the aggregation typology, domain-specific authority locus, and the refined conceptual-architecture table.
- [[Data Dictionary]], [[Variables]], [[Coding Protocol]] (all in `02_Data/`) — rebuilt around the canonical variable names and added the aggregation/authority-derivation/confidence-assessment steps.
- [[Evidence Standards]] — the agent's previously-proposed confidence scheme is now **replaced** by the researcher's actual scheme; this fully resolves Research Design Audit priority item 5.
- [[Research Design Audit]] — all 5 priority items now resolved; new open items surfaced (Delegated-authority mechanism, confidence scheme not yet extended beyond alignment, `episode_id` boundary, authority-derivation rule still provisional).
- [[GRID Position 1 Alignment]] — authority-locus refinement flagged as the single most Position-1-relevant addition, since it operationalizes the "institutional location of authority" conditioning factor central to H3.

This is RESEARCHER MATERIAL. Where the agent had previously proposed a scheme (evidence confidence) pending researcher confirmation, that proposal is now retired in favor of the researcher's own decision, and the changelog preserves both versions for traceability rather than erasing the earlier proposal from history.

## 2026-09-27 (4)

### Change
Ran `/design`, consolidating comparative-design material (previously scattered across [[Project Brief]] and [[Scope & Limitations]]) into a new `03_Comparative Design/` module: [[Unit of Analysis]], [[Comparative Strategy]], [[Case Selection]], [[Temporal Scope]].

### Reason
Sequencing decision: with `/theory` and `/operationalize` substantially resolved by the two researcher memos, `/design` was run before `/dataset` per AGENT.md §28's default ordering, since the dataset schema depends on a settled (or at least explicitly flagged) unit of analysis.

### Status
Accepted (agent-executed consolidation of existing researcher material; no new substantive claims introduced)

### Impact
- New module `03_Comparative Design/` created.
- [[Scope & Limitations]] updated: evidence-confidence resolution note (missed in the prior pass) now correctly reflects [[Refined Measurement Framework]]; new pointer section added to the canonical `03_Comparative Design/` files.
- Surfaced explicitly as the clearest remaining blocker for `/dataset`: the **country-year vs. country-year-episode** unit-of-analysis decision, which the researcher has twice deferred pending inspection of the finalized GRID dataset. See [[Unit of Analysis]].

## 2026-09-27 (5)

### Change
Researcher supplied 10 real data files for Burundi, Iraq, and Colombia (IDMC Internal Displacement Updates event microdata, IDMC disaster/conflict country-year series, the IDMC global `1_Displacement_data`/`2_Context_Displacement_data`/`3_IDPs_SADD_estimates` workbook covering all countries 2008–2025, and a World Bank IDP-stock indicator file), described by the researcher as "the data to build the dataset based on." Ran `/dataset` against this material.

### Reason
Researcher-supplied empirical data, provided to ground the pilot dataset in real displacement statistics rather than only a schema.

### Status
Accepted, with an important scope correction: this data is **displacement-magnitude and event data (EMPIRICAL EVIDENCE)**, not political-alignment or government-response data. It grounds the `country`, `year`, `episode_id`, and `displacement_cause` columns; it does **not** and cannot populate `align_*`, `authority_*`, or `response_de_jure`/`response_de_facto`, which still require a separate coding pass against documentary/political evidence per [[Coding Protocol]]. This distinction is made explicit throughout the affected files to prevent the displacement data from being mistaken for, or silently standing in for, the uncoded political/response variables.

### Impact
- New file [[Data Sources]] — documents all 10 files, their real provenance, coverage, and (critically) what they can and cannot support.
- New file `pilot_country_year_displacement.csv` — a real country-year panel (Burundi/Iraq/Colombia, 2008–2025) extracted from the IDMC global workbook.
- **Data-quality catch during extraction**: an initial XML-parsing pass read spreadsheet cells by position-of-appearance rather than by column letter, which silently misaligned values whenever a country-year had a sparse (omitted) middle column — e.g., shifting Colombia's disaster figures into conflict-flow fields, since Colombia has no reported conflict-flow value in the source data at all. This was caught before the CSV was finalized and the extraction was redone keyed to actual column letters. Documented in [[Data Sources]] as a cautionary note, since it is exactly the kind of silent measurement error the researcher's own safeguards warn against.
- [[Unit of Analysis]] — added empirical support (from real, dated, co-occurring displacement events) for country-year-episode over country-year as the more information-preserving default for the three case-study countries; does not resolve the question for the full cross-national tier.
- [[Data Dictionary]] — `episode_id` and new `displacement_cause` (Conflict/Disaster) marked partially resolved for Burundi/Iraq/Colombia via real IDMC `event_id`s; added an explicit warning against inferring response values from displacement magnitude.
- [[Coding Protocol]] — Step 1 updated to point coders to the real event data for the three case countries.
- Identified gap: no Colombia conflict-driven country-year series was provided (only Burundi and Iraq have that specific file); Colombia's conflict/IDP series is only available via the global workbook and raw event files.
- Identified gap: the World Bank `.xls` file could not be machine-parsed in this environment (legacy binary format, no `.xls`-capable library available) — flagged rather than guessed at.

## 2026-09-27 (6)

### Change
Ran `/literature`, building the `05_Literature/` module ([[Literature Map]], [[Internal Displacement]], [[Government Responses]], [[Protection and Repression]], [[Political Alignment]] (literature), [[Research Gaps]]) entirely from the 14 citations already present in [[Project]]'s reference list.

### Reason
Agent's own choice of next step: a real pilot coding pass was the other option offered, but it would require documentary/political evidence (coalition agreements, electoral records, government policy documents) that has not been supplied and cannot be fabricated. `/literature` was the lower-risk, immediately executable option that also matches AGENT.md §28's default ordering.

### Status
Accepted (agent-executed organization of existing citations; no new bibliographic information introduced)

### Impact
- New module `05_Literature/` created.
- Explicitly flagged rather than papered over: the protection–repression continuum rests on a single citation (the GRID framing paper itself); the three-actor alignment configuration is the researcher's own synthesis, not a direct restatement of any one cited source; several citations (Lichtenheld & Steele 2025, Steele 2011/2017, Weihmayer 2024) have method/data/finding details the project text does not specify, marked [TO VERIFY] rather than invented.

## 2026-09-27 (7)

### Change
Ran `/analysis`, building `06_Analysis/` ([[Descriptive Analysis]], [[Comparative Analysis]], [[Pilot Findings]], [[Limitations]], [[Next Steps]]). Computed real descriptive statistics (totals, trend comparisons, peak years) directly from [[pilot_country_year_displacement.csv]] using awk.

### Reason
Agent's own choice, again picking the practical option: real data was on hand from the `/dataset` stage, making a genuine (if descriptive-only) analysis possible without fabrication, unlike a coding pass or `/reproduce` (which is pure documentation of already-decided workflow).

### Status
Accepted — labeled explicitly throughout as descriptive analysis of **displacement magnitude**, not a test of H1–H3

### Impact
- New module `06_Analysis/` created with real computed results: e.g., Colombia's conflict-driven IDP stock rose from 3.0M (2008) to a 2024 peak of 7.265M and remains near that peak in 2025, while Burundi's fell from a 2009 peak of 157,000 to 6,800 by 2025, and Iraq's peaked in 2015 (3.29M, the ISIS-conflict period) before declining to 997,000 by 2025.
- [[Pilot Findings]] states explicitly and prominently: **zero observations exist for `align_*`, `authority_*`, or `response_de_jure`/`response_de_facto`** — the displacement-magnitude findings above are real but say nothing about H1–H3, and must not be read as such.
- [[Next Steps]] separates what requires the researcher (real-world evidence gathering for pilot coding) from what the agent can continue doing (reproducibility docs, vault/GitHub polish).

## 2026-09-27 (8)

### Change
Ran `/reproduce`, building `07_Reproducibility/` ([[Research Workflow]], [[Data Provenance]], [[Reproducibility Guide]]).

### Reason
Continuing the default workflow (`/analysis` → `/reproduce`) at the user's request ("continue"); this is documentation of already-built material rather than new empirical or theoretical content.

### Status
Accepted

### Impact
- [[Research Workflow]] — full PROJECT→VARIABLES→DATA→CODING→ANALYSIS→OUTPUT chain diagrammed, with a worked example tracing the "Colombia conflict stock peaked at 7,265,000 in 2024" figure back to its exact source cell.
- [[Data Provenance]] — full file-by-file provenance table, including the 8 real data files received but not yet transformed into a repository artifact (event-level and disaster CSVs, read/inspected but not yet built into an `episode_id` table), and the unparsed World Bank `.xls`.
- [[Reproducibility Guide]] — step-by-step re-derivation instructions for `pilot_country_year_displacement.csv` and the `06_Analysis/` figures, explicit environment notes (no Python/R/LibreOffice available this session), and the prerequisites still missing before any H1–H3-relevant number could be reproducible.

## 2026-09-27 (9)

### Change
Ran `/github` at the user's request. Created `README.md`, `CITATION.cff`, and `.gitignore` at the repository root.

### Reason
User explicitly requested this stage next.

### Status
Accepted, with one item deliberately left undone: **no LICENSE file was created.** License choice affects reuse rights and is a substantive decision for the researcher, not a default the agent should impose — flagged in the README's new "License" section instead. `CITATION.cff` similarly uses placeholder author/affiliation fields rather than guessing the researcher's identity from session context.

### Impact
- `README.md` — full structure per AGENT.md §19, distinguishing researcher's proposed research / pilot infrastructure / empirical evidence throughout; explicitly states the pilot is not a completed GRID dataset and that political-alignment/response coding is at zero observations.
- `CITATION.cff` — placeholder citation metadata; author name/affiliation left blank for the researcher to fill in rather than inferred.
- `.gitignore` — standard Obsidian/OS/editor excludes, plus `*.exe`, which will keep `Research Project/Git-2.55.0.5-64-bit.exe` (a ~65MB installer that happens to sit in the vault) out of any future git commit.

## Related

[[Research Design Audit]] · [[Project Ingestion Report]] · [[Measurement Research Design]] · [[Refined Measurement Framework]] · [[Data Sources]] · [[Literature Map]] · [[Pilot Findings]] · [[Research Workflow]]
