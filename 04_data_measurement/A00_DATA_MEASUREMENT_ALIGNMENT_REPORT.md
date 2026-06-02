---
title: "A00 Data Measurement Alignment Report"
type: "report"
status: "active"
layer: "empirical_design"
design_role: "data_measurement_alignment_review"
scope: "chapter2_core_support"
created: 2026-06-01
updated: 2026-06-01
related_to:
  - A00_Aggregate_Transformation_Benchmark
  - A03_TransformationElasticity_Two-CapitalCapacityComposition
  - A04_PeripheralTransformationElasticity
  - M10_Empirical_Identification_Framework
  - N01_CapacityUtilization_StructuralObject
---

# A00 Data Measurement Alignment Report

## 1. Executive summary

`04_data_measurement` is mostly aligned but needs minor to substantive follow-up updates.

The folder correctly emphasizes stock-flow consistency, asset-specific deflators, real versus current-cost registers, and level anchoring. The main alignment issue is that the data notes were written around the ME/NRC composition architecture and should now more clearly distinguish the A00 baseline from the A03 decomposition.

No substantive changes were made to the data-measurement notes in this pass. Only this report was added.

## Markdown and Obsidian Hygiene Fixes

- Backticked conceptual wikilinks in active analytical notes were converted to active wikilinks.
- Incorrect references to `A03_Transformation_Elasticity_Two-CapitalCapacityComposition` were corrected to `A03_TransformationElasticity_Two-CapitalCapacityComposition`.
- The legacy `A00_Aggregate_Benchmark.md` alias was removed after the vault scan found no active conceptual links requiring it.
- YAML frontmatter was checked for wikilink brackets and duplicate A00 references.
- Display-math fences were audited for one-sided malformed blocks.

## 2. File-by-file assessment

### `04_data_measurement/D01_GPIM_heterogeneous_capital_SFC.md`

- current role: GPIM stock-flow consistency and valuation-register protocol.
- relevant A00/A03/A04 issue: The note is strong on heterogeneous capital, real GPIM construction, ME/NRC component stocks, deflators, stock-flow consistency, and capacity/profitability register separation. It currently foregrounds composition shares and `theta_t^{tot}` as the transformation relation, which reads closer to A03 than A00. It should more explicitly state that A00 first uses aggregate real productive capital $K_t$, and that ME/NRC component construction becomes A03 decomposition or proxy work.
- decision: substantive_update_recommended
- reason: The note discusses aggregate capital construction, ME/NRC component stocks, productive capacity, utilization, and the transformation relation. Those are directly affected by the A00/A03 boundary. It does not appear to assert constant $\theta$, but it should add a clear A00 baseline paragraph and then locate ME/NRC shares as A03 decomposition inputs.
- proposed patch direction: Add a short A00 baseline section near the capacity register or transformation-elasticity section: aggregate real GPIM $K_t$ supports A00, the baseline relation is $y_t = c + \beta_1 k_t + \beta_2(\omega_t k_t) + \xi_t$, and ME/NRC shares are A03 decomposition/proxy variables. Add a note that wage-share measurement is required for the interaction term.

### `04_data_measurement/D02_PriceDeflator_Protocol_K_Composition.md`

- current role: Price-deflator and ME/NRC composition-share protocol.
- relevant A00/A03/A04 issue: The note is mainly an A03 measurement protocol. It correctly treats ME and NRC as distinct accounts and deflator structures, but it should avoid being read as the A00 baseline capital object. A00 needs aggregate real productive capital $K_t$; this note governs the component-composition layer once A03 is activated.
- decision: minor_update_recommended
- reason: The note does not imply constant $\theta$ or residual utilization. Its main gap is an explicit boundary sentence: ME/NRC component shares are A03 decomposition/proxy variables, not the starting A00 benchmark.
- proposed patch direction: Add a boundary note near the core claim or sector-anchor section: A00 uses aggregate $K_t$ and the distributive interaction; this protocol supports A03 composition measurement and robustness denominators.

### `04_data_measurement/D03_capacity_utilization_level_anchor_pinch_year_protocol.md`

- current role: Capacity-utilization level anchor and pinch-year normalization protocol.
- relevant A00/A03/A04 issue: The note correctly separates coefficient recovery from level anchoring and does not treat residuals as identifying utilization. Its reconstruction sequence is generic and uses `long-run coefficient recovery -> theta_tot -> Yp -> mu`, so it should be aligned with the current M10 sequence.
- decision: minor_update_recommended
- reason: The level-anchor architecture is consistent, but the sequence should name the A00 aggregate interaction relation, $\hat{\theta}_t$, capacity reconstruction, level anchoring, and then $\hat{\mu}_t$.
- proposed patch direction: Replace the generic sequence with:

$$
\text{A00 aggregate interaction relation}
\rightarrow
\hat{\theta}_t
\rightarrow
\hat{Y}_t^p
\rightarrow
\text{level anchoring}
\rightarrow
\hat{\mu}_t.
$$

Keep the pinch-year rules intact.

## 3. Cross-folder risks

- constant-$\theta$ language: No direct constant-$\theta$ conflict was found in the inspected data notes.
- ambiguous aggregate capital language: D01 and D02 should distinguish aggregate A00 $K_t$ from A03 ME/NRC component construction.
- premature ME/NRC decomposition: D01 and D02 begin from ME/NRC composition logic; this is valid for A03 but should be labeled as escalation or decomposition relative to A00.
- residual-utilization slippage: No residual-identification slippage was found in the inspected data notes.
- unclear deflator treatment: Deflator treatment is mostly strong; the risk is not deflator logic but the boundary between aggregate $K_t$ and component shares.
- missing wage-share/interacted-term measurement: D01 should add the measurement implication for $\omega_t k_t$ because it discusses transformation-relation variables.
- inconsistent note naming or broken wikilinks: Mechanical A03 spelling issues were fixed outside this folder. The data notes still include older `related_to` keys that may not correspond to current canonical note names, but this pass did not rewrite their conceptual dependencies.

## 4. Recommended next pass

Safe mechanical fixes:

- Verify whether old `related_to` entries such as `N04_Composition_of_Accumulation_and_Transformation`, `R04_What_is_Identified_vs_Reconstructed`, and long descriptive note titles resolve to existing notes.
- Add direct plain-key `related_to` entries for A00/A03/M10 where appropriate, without wikilink brackets.

Conceptual data-measurement updates:

- Add an A00 baseline paragraph to D01.
- Add an A00/A03 boundary sentence to D02.
- Align D03's reconstruction sequence with M10.

Econometric/data implementation updates:

- Define the measurement source and construction rule for $\omega_t$.
- Define the construction rule for the interaction variable $\omega_t k_t$.
- Separate the aggregate A00 capital series from A03 ME/NRC component proxy variables in export metadata.

## 5. Validation checklist

- [x] Obsidian wikilinks fixed where appropriate.
- [x] Backticked wikilinks preserved only in reports/logs/syntax examples.
- [x] Wrong A03 spelling corrected.
- [x] A00 legacy alias either removed or explicitly retained with reason.
- [x] No active conceptual links point to `A00_Aggregate_Benchmark`.
- [x] YAML frontmatter remains valid.
- [x] `04_data_measurement` notes inspected.
- [x] Data-measurement update needs classified.
- [x] No substantive changes made to `04_data_measurement` outside mechanical hygiene.
