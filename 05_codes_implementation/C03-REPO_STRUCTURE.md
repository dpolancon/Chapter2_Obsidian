---
type: repo_governance_memo
status: active
layer: implementation_design
design_role: target_structure_and_code_stage_implementation
scope: chapter2_results_repo
repo: Capacity-Utilization-US_Chile
branch_context: curation/local-current-state-2026-05-03
related_to:
  - H00_Okishio_Vidal_Decentralized_Accumulation
  - H01_Cajas_to_Transformation_Elasticity
  - H02_Theta_to_Empirical_Coefficients
  - N01_Two_Corridor_Transformation_Elasticity
  - N02_Peripheral_Mechanization_Constraint
  - N04_Composition_of_Accumulation_and_Transformation
  - R01_Marx_Okishio_Regime_Diagnostic_Guardrail
  - R02_Threshold_Model_Peripheral_Diagnostic
  - R03_Interpretation_of_Theta_as_Contradictory_Object
  - R04_What_is_Identified_vs_Reconstructed
  - M10_Empirical_Identification_Framework
  - 03B_Process_Tracing_Playbook
created: 2026-05-05
---

# Target repo structure and code-stage implementation

## 0. Purpose

This memo defines the target structure for the `Capacity-Utilization-US_Chile` repository before promoting or rewriting scripts.

It is a repo-governance note for implementation.

It does not promote files.  
It does not rename files.  
It does not authorize deletion.  
It defines the architecture that code promotion must follow.

The repository should function as the **data-management and results-production engine** for Chapter 2.

It should not reproduce the Obsidian vault.

The vault governs the theoretical and methodological contract.  
The repo executes that contract through data construction, admissibility checks, coefficient recovery, reconstruction, diagnostics, and result-package production.

---

# 1. Repository role lock

The repository should contain:

- reproducible data construction;
- source-of-truth panels;
- composition and mechanization variables;
- periodization and stability checks;
- long-run transformation relation estimates;
- reconstructed productive capacity;
- derived capacity utilization;
- profitability and recapitalization corridor outputs;
- diagnostics and robustness checks;
- paper-facing result packages.

The repository should not contain:

- qualitative source packs;
- manuscript reservoirs;
- Obsidian governance notes except when mirrored as implementation locks;
- broad theoretical drafting infrastructure;
- unrelated corridor archives.

Those belong in the vault or in archived artifact spaces.

---

# 2. Governing architecture

The active repo structure should follow this division:

```text
codes/
data/
output/
artifacts/
```

## 2.1 `codes/`

`codes/` is the flat production-command surface.

There should be **no country folders inside `codes/`**.

Country and comparative scope should be encoded in filenames:

- `CL_` = Chile
- `US_` = United States
- `CMP_` = comparative / cross-case

Stage should also be encoded in filenames:

- `S00`, `S10`, `S20`, `S30`, `S40`, `S50`, `S60`, `S70`, `S90`, `S99`

The naming convention is:

```text
CASE_STAGE_object_task.R
```

Examples:

```text
CL_S10_source_of_truth_panel.R
US_S30_transformation_relation_fmols.R
CMP_S70_structural_comparison.R
```

## 2.2 `data/`

`data/` should remain source-oriented and panel-oriented.

Country folders are acceptable here because raw and processed sources are usually country-specific.

```text
data/
  raw/
    Chile/
    US/
    WBOP/
  processed/
    Chile/
    US/
    WBOP/
  final/
    chile/
    US/
    comparative/
  metadata/
```

## 2.3 `output/`

`output/` should be differentiated by analytical destination:

```text
output/
  chile/
  US/
  comparative/
```

Each destination should mirror the stage logic.

```text
output/chile/
  S10_source_of_truth/
  S20_composition_admissibility/
  S30_transformation_relation/
  S40_theta_tot_mu/
  S50_thetaM_corridor_interpretation/
  S60_peripheral_constraint/
  S90_diagnostics/
  S99_results_package/
```

Equivalent structures should be used for:

```text
output/US/
output/comparative/
```

## 2.4 `artifacts/`

`artifacts/` stores repo governance, curation logs, archived material, and reconstruction plans.

```text
artifacts/
  repo_state_logs/
  archived_chapter_material/
  archived_corridors/
  code_recycling_memos/
```

---

# 3. Analytical lock behind the repo structure

The repo architecture is not cosmetic.

It encodes the analytical distinction between:

$$
\theta_t^M
$$

and:

$$
\theta_t^{tot}
$$

where:

$$
\theta_t^M
$$

is the structural machinery-specific transformation elasticity, while:

$$
\theta_t^{tot}
=
s_t\theta_t^M+(1-s_t)\theta^O
$$

is the composition-weighted transformation elasticity identified in the data.

The empirical model does not directly estimate the machinery-specific transformation elasticity.

It estimates an aggregate, composition-weighted object from which the machinery-specific mechanism is interpreted.

The identification guardrail is:

- coefficients are estimated;
- $$\theta_t^{tot}$$ is identified;
- $$\theta_t^M$$ is inferred or interpreted through the model structure;
- productive capacity is reconstructed;
- utilization is derived after reconstruction.

---

# 4. Core theoretical locks translated into implementation

## 4.1 θ is contradictory, not optimal

The transformation elasticity must not be treated as:

- an efficiency parameter;
- a production-function elasticity;
- a technological constant;
- the result of optimal allocation;
- the outcome of a representative firm.

It should be treated as:

> the historically realized transformation of accumulation into productive capacity under decentralized accumulation and internally contradictory firm behavior.

## 4.2 q is realized mechanization, not pure optimum

The coherent mechanization solution:

$$
q^*(\omega)
$$

is a benchmark or limiting case.

Actual mechanization:

$$
q_t
$$

is a realized outcome of contradictory internal responses to market pressure.

## 4.3 Composition is structurally necessary

All accumulation contributes to productive capacity, but not symmetrically.

Machinery and equipment:

- build capacity;
- transmit distributive conflict into mechanization and productivity.

Non-machinery capital and infrastructure:

- build capacity;
- do not directly transmit mechanization or distributive conflict.

Therefore, the machinery share is required:

$$
s_t=\frac{K_t^M}{K_t}
$$

and the machinery share of accumulation is required:

$$
\varphi_t=\frac{I_t^M}{I_t^A}
$$

## 4.4 Peripheral constraint is not optional

For Chile, the external mechanization wedge is:

$$
\mathcal{E}_t=\Lambda_t\varphi_t
$$

where:

$$
\Lambda_t
$$

is the shadow cost or proxy for foreign-exchange pressure.

The preferred threshold dummy is:

$$
D_t(\hat{\gamma})=\mathbf{1}\{\mathcal{E}_t>\hat{\gamma}\}
$$

This dummy should be estimated or constructed only after admissibility checks.

---

# 5. Stage map

## S00 — Setup, paths, packages, and helpers

Purpose:

Create reusable infrastructure.

S00 should contain:

- path definitions;
- package loading;
- helper functions;
- plotting themes;
- IO utilities;
- shared transformations.

Examples:

```text
S00_paths.R
S00_packages.R
S00_helpers_io.R
S00_helpers_plots.R
S00_helpers_econometrics.R
```

S00 should not run country-specific estimation.

---

## S10 — Source-of-truth data construction

Purpose:

Build canonical country panels.

S10 does not run econometrics.  
S10 does not reconstruct utilization.  
S10 does not produce final paper-facing figures.

Expected tasks:

- harmonize raw data;
- construct real output;
- construct total capital;
- construct machinery and non-machinery capital where possible;
- construct wage share;
- construct price indexes;
- construct profitability inputs;
- construct external-constraint candidates;
- export canonical panels.

Examples:

```text
CL_S10_source_of_truth_panel.R
US_S10_source_of_truth_panel.R
CMP_S10_panel_alignment.R
```

---

## S20 — Composition, mechanization, periodization, and admissibility

Purpose:

Construct the objects required before coefficient recovery.

S20 is the gate between source data and estimation.

Expected objects:

$$
s_t=\frac{K_t^M}{K_t}
$$

$$
\varphi_t=\frac{I_t^M}{I_t^A}
$$

$$
\mathcal{E}_t=\Lambda_t\varphi_t
$$

$$
D_t(\hat{\gamma})=\mathbf{1}\{\mathcal{E}_t>\hat{\gamma}\}
$$

Expected tasks:

- construct composition variables;
- construct mechanization variables;
- construct external-constraint index or proxies;
- define candidate historical windows;
- test integration order;
- check deterministic components;
- check structural breaks;
- check parameter stability;
- estimate or prepare threshold candidates;
- construct the estimated threshold dummy only if admissible.

Examples:

```text
CL_S20_composition_mechanization_external_constraint.R
CL_S20_periodization_stability_admissibility.R
CL_S20_external_constraint_threshold_index.R
US_S20_composition_stability_admissibility.R
CMP_S20_comparative_window_register.R
```

S20 is mandatory.

No S30 coefficient recovery should be treated as definitive unless its S20 assumptions are logged.

---

## S30 — Reduced-form transformation coefficient recovery

Purpose:

Estimate the reduced-form long-run transformation relation.

S30 estimates coefficients.  
S30 does not reconstruct utilization.

Estimator-role lock:

- FM-OLS = main estimator;
- IM-OLS = robustness estimator;
- DOLS = fragility / stress diagnostic.

Examples:

```text
CL_S30_transformation_relation_fmols.R
CL_S30_transformation_relation_imols.R
CL_S30_transformation_relation_dols_fragility.R
US_S30_transformation_relation_fmols.R
US_S30_transformation_relation_imols.R
US_S30_transformation_relation_dols_fragility.R
```

For Chile, the S30 equation should allow composition-weighted transformation logic.

The relevant interaction surface may include:

$$
k_t
$$

$$
(s_t-\bar{s})k_t
$$

$$
\omega_t(s_t-\bar{s})k_t
$$

$$
D_t(\hat{\gamma})(s_t-\bar{s})k_t
$$

$$
D_t(\hat{\gamma})\omega_t(s_t-\bar{s})k_t
$$

The purpose is not to estimate:

$$
\theta_t^M
$$

directly.

The purpose is to estimate coefficients that identify the behavior of:

$$
\theta_t^{tot}
$$

---

## S40 — Reconstruction of aggregate transformation and utilization

Purpose:

Reconstruct:

$$
\theta_t^{tot}
$$

then:

$$
Y_t^p
$$

then:

$$
\mu_t
$$

The correct sequence is:

$$
\text{reduced-form coefficient recovery}
\rightarrow
\hat{\theta}_t^{tot}
\rightarrow
\hat{Y}_t^p
\rightarrow
\text{level anchoring}
\rightarrow
\hat{\mu}_t
$$

S40 is not an estimator stage.  
S40 is a reconstruction stage.

Examples:

```text
CL_S40_theta_tot_mu_reconstruction.R
US_S40_theta_tot_mu_reconstruction.R
CMP_S40_theta_tot_alignment.R
```

Guardrail:

Do not claim that S40 estimates:

$$
\theta_t^M
$$

S40 reconstructs the aggregate transformation object and derives utilization after productive capacity is reconstructed and anchored.

---

## S50 — Machinery-channel interpretation and productive-capacity corridor

Purpose:

Interpret the reconstructed aggregate object through the structural machinery channel.

The productive-capacity corridor is:

$$
\theta \rightarrow \mu \rightarrow r
$$

S50 asks how reconstructed capacity utilization relates to profitability and regime interpretation.

Expected tasks:

- interpret $$\theta_t^{tot}$$ behavior;
- infer machinery-channel behavior;
- evaluate wage-share conditioning;
- connect utilization to profitability;
- organize the productive-capacity corridor.

Examples:

```text
CL_S50_thetaM_corridor_interpretation.R
US_S50_thetaM_corridor_interpretation.R
CMP_S50_theta_mu_r_comparison.R
```

Guardrail:

S50 interprets:

$$
\theta_t^M
$$

It does not claim to estimate:

$$
\theta_t^M
$$

directly.

---

## S60 — Recapitalization, external constraint, and peripheral mechanism

Purpose:

Handle the second corridor:

$$
\chi \rightarrow k \rightarrow g
$$

For Chile, S60 also handles the peripheral external-mechanization constraint.

The peripheral external-mechanization wedge is:

$$
\mathcal{E}_t=\Lambda_t\varphi_t
$$

where:

$$
\varphi_t=\frac{I_t^M}{I_t^A}
$$

and:

$$
\Lambda_t
$$

is the shadow cost or proxy for foreign-exchange pressure.

Expected Chile scripts:

```text
CL_S60_peripheral_mechanization_constraint.R
CL_S60_bop_recapitalization_corridor.R
```

Expected US script:

```text
US_S60_recapitalization_benchmark.R
```

Expected comparative script:

```text
CMP_S60_external_constraint_comparison.R
```

S60 does not replace S40.

It interprets whether profitability and surplus are translated into renewed accumulation and growth, especially under external constraint.

---

## S70 — Comparative synthesis

Purpose:

Compare reconstructed objects across structurally unequal positions.

This is not national-container comparison.

It compares how the same structural problem appears under different historical and world-market conditions.

Expected scripts:

```text
CL_S70_center_periphery_synthesis.R
US_S70_center_benchmark_synthesis.R
CMP_S70_structural_comparison.R
```

The comparative object is not:

```text
Chile vs US as isolated national cases
```

but:

```text
center and periphery as differentiated positions within a hierarchically organized world economy
```

---

## S90 — Diagnostics, robustness, threshold/FGLS stress tests

Purpose:

Run diagnostics and robustness checks.

S90 does not authorize estimation shortcuts.

It includes:

- DOLS fragility checks;
- lead-lag sensitivity;
- VIF and collinearity checks;
- window sensitivity;
- break versus threshold diagnostics;
- threshold significance;
- weak identification checks;
- FGLS admissibility;
- bootstrap / sup-Wald procedures where required.

Examples:

```text
CL_S90_threshold_dummy_fgls_admissibility.R
CL_S90_break_threshold_stress_tests.R
US_S90_dols_fragility_diagnostics.R
US_S90_specification_stress_tests.R
CMP_S90_regime_stability_stress_tests.R
```

Guardrail:

S90 cannot override S20.

Threshold-FGLS belongs only after threshold behavior is independently justified.

---

## S99 — Result-package export

Purpose:

Export final results.

S99 should not silently reconstruct analytical objects.

Expected outputs:

- tables;
- figures;
- appendices;
- paper-facing result sheets;
- advisor-facing figures;
- diagnostics summaries;
- reproducibility manifests.

Examples:

```text
CL_S99_results_package.R
US_S99_results_package.R
CMP_S99_comparative_results_package.R
```

---

# 6. Flat code naming convention

The final code naming convention is:

```text
CASE_STAGE_object_task.R
```

where:

```text
CASE = CL | US | CMP
STAGE = S00 | S10 | S20 | S30 | S40 | S50 | S60 | S70 | S90 | S99
```

Examples:

```text
CL_S10_source_of_truth_panel.R
CL_S20_external_constraint_threshold_index.R
CL_S30_transformation_relation_fmols.R
CL_S40_theta_tot_mu_reconstruction.R
CL_S60_bop_recapitalization_corridor.R
US_S90_dols_fragility_diagnostics.R
CMP_S70_structural_comparison.R
```

---

# 7. US implementation plan

## 7.1 US target sequence

```text
US_S10_source_of_truth_panel.R
US_S20_composition_stability_admissibility.R
US_S30_transformation_relation_fmols.R
US_S30_transformation_relation_imols.R
US_S30_transformation_relation_dols_fragility.R
US_S40_theta_tot_mu_reconstruction.R
US_S50_thetaM_corridor_interpretation.R
US_S50_theta_mu_profitability_corridor.R
US_S60_recapitalization_benchmark.R
US_S90_dols_fragility_diagnostics.R
US_S99_results_package.R
```

## 7.2 US recycling logic

Current DOLS-era scripts should not be promoted directly.

They should be recycled as follows:

```text
US_dols_diagnostic.R
→ US_S90_dols_fragility_diagnostics.R

us_dols_spec_grid_cointReg.R
→ US_S90_dols_spec_grid_fragility.R

US_dols_try_fullsample.R
→ US_S20_historical_break_window_scan.R
  or US_S90_known_break_stress_test.R

US_dols_try_fullsample_v2.R
→ US_S30_transformation_relation_fmols_imols_dols.R

us_dols_mu_theta_graph.R
→ US_S40_theta_tot_mu_reconstruction.R
  and US_S99_theta_mu_figures.R

us_dols_theta_graph.R
→ US_S99_theta_figures.R

us_profitability_analysis.R
→ US_S50_theta_mu_profitability_corridor.R

us_profitability_analysis_results_pack.R
→ US_S99_profitability_results_package.R
```

## 7.3 US guardrail

The old US move was:

$$
\text{DOLS coefficients}
\rightarrow
\theta_t=\beta_1+\beta_2\omega_t
\rightarrow
Y_t^p
\rightarrow
\mu_t
$$

The new US move must be:

$$
\text{source-of-truth panel}
\rightarrow
\text{composition/admissibility}
\rightarrow
\text{reduced-form coefficient recovery}
\rightarrow
\theta_t^{tot}
\rightarrow
Y_t^p
\rightarrow
\mu_t
\rightarrow
\theta_t^M \text{ interpretation}
\rightarrow
\text{profitability corridor}
$$

---

# 8. Chile implementation plan

## 8.1 Chile target sequence

```text
CL_S10_source_of_truth_panel.R
CL_S20_composition_mechanization_external_constraint.R
CL_S20_periodization_stability_admissibility.R
CL_S20_external_constraint_threshold_index.R
CL_S30_transformation_relation_fmols.R
CL_S30_transformation_relation_imols.R
CL_S30_transformation_relation_dols_fragility.R
CL_S40_theta_tot_mu_reconstruction.R
CL_S50_thetaM_corridor_interpretation.R
CL_S50_theta_mu_profitability_corridor.R
CL_S60_peripheral_mechanization_constraint.R
CL_S60_bop_recapitalization_corridor.R
CL_S90_threshold_dummy_fgls_admissibility.R
CL_S99_results_package.R
```

## 8.2 Chile required analytical variables

Chile requires explicit construction of:

$$
s_t=\frac{K_t^M}{K_t}
$$

$$
\varphi_t=\frac{I_t^M}{I_t^A}
$$

$$
\mathcal{E}_t=\Lambda_t\varphi_t
$$

$$
D_t(\hat{\gamma})=\mathbf{1}\{\mathcal{E}_t>\hat{\gamma}\}
$$

These variables are not optional extras.

They are required by the asymmetric accumulation-composition framework.

## 8.3 Chile threshold logic

The peripheral threshold should not be coded as a generic continuous external-wedge effect only.

The preferred threshold logic is:

$$
\mathcal{E}_t=\Lambda_t\varphi_t
$$

Estimate:

$$
\hat{\gamma}
$$

Construct:

$$
D_t(\hat{\gamma})=\mathbf{1}\{\mathcal{E}_t>\hat{\gamma}\}
$$

Then estimate the threshold-dummy interaction model.

A generic representation is:

$$
y_t
=
c
+
\delta D_t
+
\beta_1 k_t
+
\beta_2(\omega_t k_t)
+
\alpha_1(D_t k_t)
+
\alpha_2[D_t(\omega_t k_t)]
+
\varepsilon_t
$$

Under low external constraint:

$$
\theta_L(\omega_t)=\beta_1+\beta_2\omega_t
$$

Under high external constraint:

$$
\theta_H(\omega_t)
=
(\beta_1+\alpha_1)
+
(\beta_2+\alpha_2)\omega_t
$$

With the composition-weighted architecture, the preferred interaction surface should be adapted to the machinery channel:

$$
(s_t-\bar{s})k_t
$$

$$
\omega_t(s_t-\bar{s})k_t
$$

$$
D_t(\hat{\gamma})(s_t-\bar{s})k_t
$$

$$
D_t(\hat{\gamma})\omega_t(s_t-\bar{s})k_t
$$

The point is not simply whether an external-constraint coefficient is negative.

The stronger question is whether the transformation relation changes once the imported-machinery constraint becomes binding.

## 8.4 Chile recycling logic

Current Chile flat candidates should be recycled as follows:

```text
CL_00_source_of_truth_chile.R
→ CL_S10_source_of_truth_panel.R

CL_01_stage1_mu.R
→ split into CL_S20, CL_S30, and CL_S40 components

CL_01_stage1_mu_source_truth_break_sig_STAGE1_ONLY.R
→ CL_S20_periodization_stability_admissibility.R

CL_01_stage1_mu_source_truth_break_sig_full.R
→ CL_S20_periodization_stability_admissibility_full.R

CL_03_results_package_mu_theta_wsh.R
→ CL_S40_theta_tot_mu_reconstruction.R
  and CL_S99_capacity_results_package.R

CL_04_results_presentation.R
→ CL_S99_results_presentation.R

CL_05_profitability_analysis_core.R
→ CL_S50_theta_mu_profitability_corridor.R

CL_05_profitability_analysis_core_BENCH.R
→ CL_S90_profitability_benchmark_stress.R

CL_06_results_package_profitability.R
→ CL_S99_profitability_results_package.R

CL_07_results_package_profitability_diagnostics.R
→ CL_S90_profitability_diagnostics.R

CL_08_results_package_profitability_diagnostics_shortrun.R
→ CL_S90_profitability_short_run_diagnostics.R

CL_09_results_package_profitability_diagnostics_very_shortrun.R
→ CL_S90_profitability_very_short_run_diagnostics.R

CL_10_class_struggle_diagnostic.R
→ CL_S50_distribution_conflict_diagnostic.R
  or CL_S90_distribution_stress.R

CL_11_dys_diagnostic_package.R
→ CL_S90_dysfunctionality_diagnostic_package.R

CL_12_capacity_utilization_diagnostic.R
→ CL_S90_capacity_utilization_diagnostic.R

CL_12_capacity_utilization_diagnostic_rebased2010.R
→ CL_S90_capacity_utilization_rebase2010_diagnostic.R

CL_12_capacity_utilization_diagnostic_rebased2010_v2.R
→ CL_S90_capacity_utilization_rebase2010_diagnostic_v2.R

CL_A_stage1_ECT_audit.R
→ CL_S90_ect_audit_not_regime_classifier.R

CL_B_stage2_mu_Diagnostic.R
→ CL_S90_mu_reconstruction_diagnostic.R

chile_class_struggle_astorga_weisskopf_v2.R
→ CL_S50_distribution_conflict_astorga_weisskopf.R
```

## 8.5 Chile guardrail

No ECT-driven regime activation.

No direct jump from source panel to utilization.

No direct claim that coefficients estimate:

$$
\theta_t^M
$$

No FGLS before threshold admissibility.

---

# 9. Comparative implementation plan

The comparative layer should not duplicate country-specific code.

It should consume stabilized country outputs.

Expected comparative scripts:

```text
CMP_S10_panel_alignment.R
CMP_S20_comparative_window_register.R
CMP_S40_theta_tot_alignment.R
CMP_S50_theta_mu_r_comparison.R
CMP_S60_external_constraint_comparison.R
CMP_S70_structural_comparison.R
CMP_S90_regime_stability_stress_tests.R
CMP_S99_comparative_results_package.R
```

Comparative outputs should live under:

```text
output/comparative/
  S20_window_register/
  S40_theta_tot_alignment/
  S50_thetaM_interpretation_comparison/
  S60_external_constraint_comparison/
  S70_synthesis/
  S99_results_package/
```

The comparative layer asks:

> how does the reconstructed object behave across structurally unequal positions?

It does not treat Chile as a deviation from the United States.

---

# 10. Script promotion protocol

Before any script is renamed or promoted, classify it into one of the following statuses:

```text
PROMOTE_AS_CORE
RECYCLE_AND_SPLIT
DEMOTE_TO_DIAGNOSTIC
MERGE_INTO_RESULTS_PACKAGE
ARCHIVE_REVIEW
DROP_AFTER_LEDGER
```

## 10.1 `PROMOTE_AS_CORE`

Use only when a script already performs one bounded production-stage task cleanly.

## 10.2 `RECYCLE_AND_SPLIT`

Use when a script mixes stages, for example:

```text
data construction + estimation + reconstruction + plotting
```

These scripts must be split before promotion.

## 10.3 `DEMOTE_TO_DIAGNOSTIC`

Use for scripts useful as robustness or stress tests but not admissible as production core.

Most DOLS-era scripts fall here unless rebuilt into FM-OLS/IM-OLS/DOLS estimator grids.

## 10.4 `MERGE_INTO_RESULTS_PACKAGE`

Use for scripts that only generate graphs, tables, or final outputs.

## 10.5 `ARCHIVE_REVIEW`

Use for legacy scripts that may contain recoverable logic but are not currently interpretable.

## 10.6 `DROP_AFTER_LEDGER`

Use only after a deletion ledger records what was removed and why.

---

# 11. Promotion rules

## Rule 1 — No direct promotion

No current flat script is definitive merely because it exists.

Current scripts are recyclable material.

## Rule 2 — No country folders in `codes/`

Use flat code filenames.

Do not create:

```text
codes/chile/
codes/US/
```

Country belongs in the filename.

## Rule 3 — S20 before S30

No coefficient recovery is definitive unless its S20 assumptions are logged.

## Rule 4 — S30 before S40

No utilization reconstruction before reduced-form coefficient recovery.

## Rule 5 — S40 before S50/S60

No profitability or peripheral interpretation before utilization is reconstructed.

## Rule 6 — S90 cannot override S20

Diagnostics and stress tests cannot substitute for admissibility.

Threshold-FGLS enters only after threshold behavior is independently justified.

## Rule 7 — Results packages do not silently compute objects

S99 exports.

It does not quietly reconstruct θ, μ, or profitability objects.

---

# 12. Non-negotiable guardrails

Do not write:

> θ measures technological efficiency.

Write:

> θ measures the historically realized transformation of accumulation into productive capacity under decentralized accumulation and internally contradictory firm behavior.

Do not write:

> the model estimates θ^M directly.

Write:

> the model identifies θ^tot and interprets θ^M through composition and interaction structure.

Do not write:

> the threshold model tests the Marx–Okishio theorem.

Write:

> the threshold model estimates regime switches in Marx–Okishio closure logic as they appear in the transformation of accumulation into productive capacity.

Do not write:

> the residual identifies utilization.

Write:

> utilization is derived after reconstructing and anchoring productive capacity.

Do not write:

> FGLS resolves instability.

Write:

> FGLS is admissible only after the diagnostic ladder justifies threshold behavior.

---

# 13. Implementation sequence

The implementation should proceed in this order:

```text
1. Commit this target structure memo.

2. Classify all current flat scripts against the S10–S99 architecture.

3. Build or stabilize S00 helpers.

4. Build US_S10 and CL_S10 source-of-truth panels.

5. Build S20 admissibility scripts.

6. Rebuild S30 estimator scripts around FM-OLS main, IM-OLS robustness, DOLS fragility.

7. Rebuild S40 θ^tot and μ reconstruction.

8. Reconnect profitability scripts as S50.

9. Build Chile S60 peripheral mechanism layer.

10. Move diagnostics into S90.

11. Build final S99 result packages.
```

---

# 14. Next repo commits

Suggested bounded commits:

```text
audit: align target repo structure with analytical foundations
audit: classify flat scripts against theory-locked stage map
chore: add S00 helper skeletons
chore: rebuild US source-of-truth panel
chore: rebuild Chile source-of-truth panel
```

Each commit should be narrow.

Do not combine structure, script movement, and data/output changes in the same commit.

---

# 15. Locked formulation

The repository should encode the analytical sequence of Chapter 2.

The code surface remains flat.  
Country and comparative scope are encoded through filename prefixes.  
Stages encode the movement from data construction to admissibility, coefficient recovery, reconstruction, interpretation, diagnostics, and export.

The empirical object directly identified in code is:

$$
\theta_t^{tot}
$$

The structural machinery-specific object:

$$
\theta_t^M
$$

is interpreted through composition, distribution, and external-constraint mechanisms.

The code architecture must therefore prevent a direct jump from data to utilization, from coefficients to structural θ, or from diagnostics to regime claims.

This is the production architecture for Chapter 2.