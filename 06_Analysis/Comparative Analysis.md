---
type: analysis
project: GRID
position: 1
status: pilot
---

# Comparative Analysis

Command: `/analysis`. **REAL DATA ANALYSIS.** Builds on [[Descriptive Analysis]] to compare displacement trajectories across the three case-study countries. Still describes displacement magnitude only — see the scope warning in [[Descriptive Analysis]] and [[Pilot Findings]].

| Element | Value |
|---|---|
| Population | Burundi, Iraq, Colombia |
| Unit of analysis | Country-year |
| Time period | 2008–2025 |
| Variables | `conflict_stock_displacement`, `disaster_stock_displacement`, `disaster_new_displacement` |
| Method | Cross-country comparison of trajectory shape (declining / rising / mixed) |
| Data source | IDMC Global Internal Displacement Database (see [[Data Sources]]) |

## Three Distinct Trajectory Shapes

| Country | Conflict-stock trajectory (2008–2025) | Interpretation |
|---|---|---|
| **Burundi** | Declining, front-loaded: peak in 2009 (157,000), falling to 6,800 by 2025 | A conflict-displacement situation substantially resolved *within* the observation window — most of the decline happens early (2009→2013) then levels off at a low base. |
| **Iraq** | Rising then declining: low in 2008–2013, sharp peak in 2014–2015 (ISIS-period conflict), declining every year since | A single dominant conflict shock visible in the data, followed by a sustained, still-ongoing return/resolution process. |
| **Colombia** | Rising, still near-peak: from 3,000,000 (2008) to a 2024 peak of 7,265,000, still at 7,211,000 in 2025 | The only one of the three cases with **no resolution phase visible** in the observed window — a genuinely protracted situation, consistent with Colombia's long-running civil conflict. |

## Why This Matters for Case Selection

[[Case Selection]] frames Iraq and Burundi as complementary, asymmetric cases rather than a matched pair with Colombia. The real data now gives empirical texture to that asymmetry: Colombia's displacement crisis has not turned a corner within the observed period, while Burundi's and Iraq's each show a clear (if very different) resolution trajectory. This is directly relevant to any future coding of `response_de_jure`/`response_de_facto` — a protracted, still-rising case (Colombia) and two resolving cases (Burundi, Iraq) offer different empirical settings for observing whether government response tracks or diverges from these displacement trajectories.

## Disaster Displacement Is Not Negligible in Any of the Three Cases

All three countries show substantial disaster-driven new displacement over the period (Burundi: 382,400; Iraq: 406,200; Colombia: 4,295,500 — see [[Descriptive Analysis]]). This matters directly for the pilot: since the pilot domain is **humanitarian assistance** (not conflict response specifically), disaster-driven episodes are legitimate, sizable candidates for pilot coding alongside conflict-driven ones, not a marginal category to be ignored.

## What This Analysis Cannot Say

- Nothing here compares political alignment, `authority_locus`, or government response across the three countries — those variables are uncoded (see [[Pilot Findings]]).
- Trajectory shape differences could reflect many factors other than government response (conflict intensity, external humanitarian intervention, host-community absorption capacity) — per the researcher's own methodological safeguard to "separate political choice from capacity constraints, territorial control, conflict intensity" ([[Refined Measurement Framework]] §9, restated in [[Coding Protocol]]).

## Related

[[Descriptive Analysis]] · [[Data Sources]] · [[Case Selection]] · [[Pilot Findings]] · [[Limitations]]
