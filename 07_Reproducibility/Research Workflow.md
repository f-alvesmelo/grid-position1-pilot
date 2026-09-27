---
type: method
project: GRID
position: 1
status: pilot
---

# Research Workflow

Command: `/reproduce`. Documents the actual chain built in this repository, per AGENT.md §18: PROJECT → VARIABLES → DATA → CODING → ANALYSIS → OUTPUT. A researcher unfamiliar with this repository should be able to follow this page to understand how any number in `06_Analysis/` traces back to a source file.

## The Chain, As Built

```
PROJECT
  Research Project/Project.md (original proposal)
  + Research Project/Measurement Research Design.md (memo 1: alignment/response/temporal/country scope)
  + Research Project/Refined Measurement Framework.md (memo 2: aggregation/confidence/authority-locus)
        ↓
THEORY (01_Theory/)
  Core Argument, Concepts, Political Alignment, Protection, Repression, Mechanisms, Observable Implications
        ↓
COMPARATIVE DESIGN (03_Comparative Design/)
  Unit of Analysis, Comparative Strategy, Case Selection, Temporal Scope
        ↓
VARIABLES (02_Data/Data Dictionary.md, Variables.md)
  align_NG_local, align_NG_IDP, align_local_IDP, alignment_configuration, alignment_structure,
  alignment_confidence, alignment_evidence_coverage, authority_formal/budget/admin/actual/locus,
  response_de_jure, response_de_facto, response_consistency
        ↓
CODING PROTOCOL (02_Data/Coding Protocol.md, Evidence Standards.md)
  Step-by-step rules for turning evidence into the variables above — NOT YET APPLIED to any real observation
        ↓
DATA (02_Data/Data Sources.md, pilot_country_year_displacement.csv)
  Real IDMC/World Bank displacement data, Burundi/Iraq/Colombia, 2008–2025
  Populates: country, year, episode_id (partial), displacement_cause
  Does NOT populate: align_*, authority_*, response_* (still uncoded — see Pilot Findings)
        ↓
ANALYSIS (06_Analysis/)
  Descriptive Analysis, Comparative Analysis — computed via awk directly on the CSV
        ↓
OUTPUT
  Real, sourced numbers (e.g., Colombia conflict stock 3.0M→7.27M, 2008–2024)
  Explicitly labeled as displacement-magnitude findings, NOT tests of H1–H3 (see Pilot Findings)
```

## How a Number Gets From Source to Output (Worked Example)

The "Colombia conflict stock peaked at 7,265,000 in 2024" figure in [[Descriptive Analysis]] traces as follows:

1. **Source**: `IDMC_Internal_Displacement_Conflict-Violence_Disasters.xlsx`, sheet `1_Displacement_data`, row where ISO3=COL, Year=2024, column D ("Conflict Stock Displacement").
2. **Extraction**: `xl/worksheets/sheet1.xml` unzipped and parsed with a `perl` script keyed to spreadsheet **column letters** (not position-of-appearance — see the correction noted in [[Data Sources]]), filtered to ISO3 ∈ {BDI, IRQ, COL}.
3. **Storage**: written to [[pilot_country_year_displacement.csv]], column `conflict_stock_displacement`, row `COL,Colombia,2024`.
4. **Computation**: `awk` peak-year script in [[Descriptive Analysis]]'s underlying computation, comparing all years' `conflict_stock_displacement` per country.
5. **Output**: reported in [[Descriptive Analysis]] §2 and [[Comparative Analysis]], with the source file cited.

## What Is NOT Yet Reproducible (Because It Doesn't Exist Yet)

- Any number describing `align_*`, `authority_*`, or `response_*` — these have zero coded observations (see [[Pilot Findings]]). There is nothing to reproduce yet for the project's actual dependent/independent variables.
- The researcher's own planned R pipeline (harmonisation → estimation → clustered inference → reproducible visualisation, per [[Project Brief]]) has not been built — the descriptive statistics here were computed with `awk` as a pilot-stage substitute, explicitly noted as such in [[Limitations]].

## Related

[[Data Provenance]] · [[Reproducibility Guide]] · [[Descriptive Analysis]] · [[Data Sources]] · [[Pilot Findings]]
