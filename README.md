# GRID Position 1 Research Pilot

A small, rigorous, reproducible research pilot demonstrating preparation for **GRID Position 1** — comparative cross-national research on government responses to internal displacement, developed and analyzed against the GRID (Protect and Repress) framework.

> **This repository is a pilot, not a completed GRID dataset or a finished empirical study.** It demonstrates research design, operationalization, and reproducible workflow. It does not yet contain coded political-alignment or government-response data, and it makes no empirical claims about any country's protection or repression record. See [Limitations](#limitations) and [00_Home/Scope & Limitations.md](00_Home/Scope%20&%20Limitations.md).

## Research Question

> "How do configurations of political alignment among national governments, local authorities and displaced populations shape the composition of government protection and repression across territories and policy domains?"

Full breakdown, hypotheses (H1–H3), and dependent/independent variables: [00_Home/Research Questions.md](00_Home/Research%20Questions.md).

## Research Puzzle

Existing scholarship explains a great deal about *why displacement happens* and, increasingly, about the formal policies states adopt *after* displacement occurs — but considerably less about the political relationships that explain why governments respond to displaced populations with protection in some circumstances and repression or exclusion in others. See [00_Home/Project Brief.md](00_Home/Project%20Brief.md).

## Theoretical Framework

Political alignment is treated as a **multilevel configuration** — among national government, local authority, and displaced population — rather than a single scalar relationship, conditioned by the **institutional location of authority** over the relevant policy domain. Builds on and extends the GRID project's own "Protect and Repress" framing.

- [01_Theory/Core Argument.md](01_Theory/Core%20Argument.md)
- [01_Theory/Political Alignment.md](01_Theory/Political%20Alignment.md)
- [01_Theory/Protection.md](01_Theory/Protection.md) / [01_Theory/Repression.md](01_Theory/Repression.md)

## Mechanisms

A one-sentence conceptual model — *pre-displacement alignment configuration → political incentives and relationships → domain-specific government response, conditioned by institutional authority* — is expanded into a full CONCEPT → MECHANISM → EXPECTED RELATIONSHIP → OBSERVABLE IMPLICATION chain per hypothesis, with agent-proposed elaboration clearly distinguished from the researcher's own claims.

- [01_Theory/Mechanisms.md](01_Theory/Mechanisms.md)
- [01_Theory/Observable Implications.md](01_Theory/Observable%20Implications.md)

## Comparative Research Design

A nested, asymmetric, mixed-method design (Lieberman, 2005): a cross-national statistical tier (all GRID countries, 1989–latest), a subnational quantitative tier (Colombia, proposed candidate case), and a comparative qualitative/process-tracing tier (Iraq and Burundi, explicitly not treated as statistically equivalent to Colombia).

- [03_Comparative Design/Unit of Analysis.md](03_Comparative%20Design/Unit%20of%20Analysis.md)
- [03_Comparative Design/Comparative Strategy.md](03_Comparative%20Design/Comparative%20Strategy.md)
- [03_Comparative Design/Case Selection.md](03_Comparative%20Design/Case%20Selection.md)
- [03_Comparative Design/Temporal Scope.md](03_Comparative%20Design/Temporal%20Scope.md)

## Dataset Architecture

Government response is coded as **multi-domain** (pilot domain: humanitarian assistance) and **de jure/de facto** separately, cross-tabulated into a consistency matrix. Political alignment is coded **relationally** across three dyads, aggregated into a full configuration vector and a five-category structure — never a scalar average. Institutional authority is coded **per domain and episode**, not as a country-level constant, from four separate indicators.

- [02_Data/Data Dictionary.md](02_Data/Data%20Dictionary.md) · [02_Data/Variables.md](02_Data/Variables.md)
- [02_Data/Data Sources.md](02_Data/Data%20Sources.md) — real IDMC/World Bank displacement data (Burundi, Iraq, Colombia, 2008–2025) grounding the episode/scope side of the schema
- [02_Data/pilot_country_year_displacement.csv](02_Data/pilot_country_year_displacement.csv) — real, sourced country-year displacement panel

**No synthetic demonstration data currently exists in this repository.** All data present is real, empirical, and cited (see [Data Provenance](07_Reproducibility/Data%20Provenance.md)). If synthetic data is added in future, it will be explicitly labeled `SYNTHETIC DATA — DEMONSTRATION ONLY` per the repository's non-fabrication rule.

## Coding Strategy

A step-by-step protocol (episode identification → alignment coding → evidence-confidence assessment → configuration/structure derivation → authority-locus derivation → response coding → consistency derivation → documentation) with an explicit evidence-confidence scheme (High/Medium/Low/Insufficient) and a 3-tier evidence hierarchy.

- [02_Data/Coding Protocol.md](02_Data/Coding%20Protocol.md)
- [02_Data/Evidence Standards.md](02_Data/Evidence%20Standards.md)

**Status: not yet piloted.** Zero observations have been coded for political alignment, authority locus, or government response — see [06_Analysis/Pilot Findings.md](06_Analysis/Pilot%20Findings.md).

## Pilot Analysis

Real descriptive statistics computed from the IDMC displacement data (e.g., Colombia's conflict-driven IDP stock rose from 3.0M in 2008 to a 2024 peak of 7.27M, while Burundi's and Iraq's each declined substantially over the same window). These describe **displacement magnitude only** — they are not evidence for or against the project's hypotheses, which require the coding pass above.

- [06_Analysis/Descriptive Analysis.md](06_Analysis/Descriptive%20Analysis.md)
- [06_Analysis/Comparative Analysis.md](06_Analysis/Comparative%20Analysis.md)
- [06_Analysis/Pilot Findings.md](06_Analysis/Pilot%20Findings.md) — states explicitly what has and has not been found

## Reproducibility

Every number in this repository traces to a cited source through a documented chain, with a worked example.

- [07_Reproducibility/Research Workflow.md](07_Reproducibility/Research%20Workflow.md)
- [07_Reproducibility/Data Provenance.md](07_Reproducibility/Data%20Provenance.md)
- [07_Reproducibility/Reproducibility Guide.md](07_Reproducibility/Reproducibility%20Guide.md)

## Repository Structure

```
00_Home/                  Project brief, research questions, scope, GRID Position 1 alignment
01_Theory/                Core argument, concepts, mechanisms, observable implications
02_Data/                  Data dictionary, variables, coding protocol, evidence standards, data sources, real pilot data
03_Comparative Design/    Unit of analysis, comparative strategy, case selection, temporal scope
05_Literature/            Literature map and thematic literature notes
06_Analysis/              Descriptive/comparative analysis, pilot findings, limitations, next steps
07_Reproducibility/       Workflow, data provenance, reproducibility guide
99_Admin/                 Ingestion report, research design audit, changelog
Research Project/         Original researcher materials (Project.md, AGENT.md, two measurement memos) — never overwritten
```

Note: `04_Methods/` (quantitative/qualitative/mixed-methods strategy detail beyond what's in Comparative Design) has not yet been built.

## Limitations

- Political alignment, authority locus, and government response remain **entirely uncoded** — this pilot demonstrates design and infrastructure, not empirical findings.
- Real displacement data covers only three countries (Burundi, Iraq, Colombia), 2008–2025 — not the full cross-national GRID scope.
- The unit of analysis for the full cross-national tier (country-year vs. country-year-episode) remains open pending the finalized GRID dataset.
- A World Bank supplementary file could not be parsed in this environment (legacy binary format) and was not incorporated.

Full detail: [00_Home/Scope & Limitations.md](00_Home/Scope%20&%20Limitations.md), [06_Analysis/Limitations.md](06_Analysis/Limitations.md), [99_Admin/Research Design Audit.md](99_Admin/Research%20Design%20Audit.md).

## Next Steps

See [06_Analysis/Next Steps.md](06_Analysis/Next%20Steps.md) — primarily: selecting real pilot episodes, gathering documentary/political evidence for them, and running the first real coding pass against the protocol above.

## License

Not yet chosen. License selection affects reuse rights and is left to the researcher rather than defaulted by the agent — see `CITATION.cff` for a placeholder citation entry pending the researcher's details.

## Provenance of This Repository

Built by an AI research-repository agent ([Research Project/AGENT.md](Research%20Project/AGENT.md)) operating on the researcher's original project statement ([Research Project/Project.md](Research%20Project/Project.md)) and two subsequent researcher-authored measurement memos. Every substantive decision, researcher input, and agent proposal is logged in [99_Admin/Changelog.md](99_Admin/Changelog.md), with researcher material and agent proposals explicitly distinguished throughout.
