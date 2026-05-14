# Memo 1 — US Code Recycling Map

## 1. Status

The US code batch should be treated as **recyclable DOLS-era material**, not as definitive production code.

The scripts contain useful machinery:

```
estimator gridswindow comparisonsDOLS sensitivity checksθ pathsμ reconstruction routinesprofitability decompositionresult-package exports
```

But they are still organized around an older pipeline where DOLS carries too much weight. Under the current analytical lock, that is no longer admissible as the main reconstruction architecture.

The US side must be rebuilt around:

```
FM-OLS = main reconstruction estimatorIM-OLS = robustness estimatorDOLS   = fragility / stress diagnostic
```

This estimator-role hierarchy is already locked in the empirical identification framework: Chapter 2 estimates the long-run transformation relation, reconstructs productive capacity, anchors it, and only then derives utilization; FM-OLS reconstructs, IM-OLS checks, and DOLS stresses fragility.

## 2. Main problem with the current US batch

The old US logic is approximately:

```
DOLS coefficients→ θ_t = β1 + β2ω_t→ Yp→ μ→ graphs / profitability
```

That is too direct.

The new logic must be:

```
source-of-truth US panel→ composition and admissibility layer→ reduced-form coefficient recovery→ θ^tot reconstruction→ Yp reconstruction→ μ derivation→ θ^M interpretation→ profitability corridor→ results package
```

This matters because the updated analytical foundation distinguishes what is identified from what is reconstructed. The empirical model identifies `θ^tot`; `θ^M` is not directly estimated, but inferred through the model structure and the behavior of estimated coefficients.

## 3. Required US target sequence

The US code should be reconstructed into the following flat sequence:

```
US_S10_source_of_truth_panel.RUS_S20_composition_stability_admissibility.RUS_S30_transformation_relation_fmols_imols_dols.RUS_S40_theta_tot_mu_reconstruction.RUS_S50_theta_mu_profitability_corridor.RUS_S90_dols_fragility_diagnostics.RUS_S99_results_package.R
```

This is a flat `codes/` architecture.  
No country folders inside `codes/`.

## 4. US script recycling table

|Current script|Recycling status|New target|Treatment|
|---|---|---|---|
|`US_dols_diagnostic.R`|Keep as diagnostic donor|`US_S90_dols_fragility_diagnostics.R`|Recycle rolling VIF, lead-lag sensitivity, estimator-comparator, candidate dummy diagnostics. Do not allow it to define reconstruction.|
|`us_dols_spec_grid_cointReg.R`|Keep as stress-test donor|`US_S90_dols_spec_grid_fragility.R`|Preserve grid logic, collinearity checks, and specification sensitivity. DOLS remains fragility diagnostic, not main estimator.|
|`US_dols_try_fullsample.R`|Partial donor|`US_S20_historical_break_window_scan.R` or `US_S90_known_break_stress_test.R`|Use known-break and window logic as admissibility/stability evidence, not as final regime truth.|
|`US_dols_try_fullsample_v2.R`|Strongest estimator donor|`US_S30_transformation_relation_fmols_imols_dols.R`|Main donor for estimator-grid reconstruction because it already moves beyond pure DOLS. FM-OLS should become main, IM-OLS robustness, DOLS fragility.|
|`us_dols_mu_theta_graph.R`|Rebuild|`US_S40_theta_tot_mu_reconstruction.R` + `US_S99_theta_mu_figures.R`|Keep plotting/export ideas, but rebuild θ/μ around `θ^tot`, not old DOLS θ.|
|`us_dols_theta_graph.R`|Merge into export layer|`US_S99_theta_figures.R`|Should not remain standalone. It depends on upstream reconstructed θ objects.|
|`us_profitability_analysis.R`|Keep downstream|`US_S50_theta_mu_profitability_corridor.R`|Strong analytical engine, but it must consume rebuilt `θ^tot`, `Yp`, and `μ`.|
|`us_profitability_analysis_results_pack.R`|Keep downstream exporter|`US_S99_profitability_results_package.R`|Preserve tables, figures, and result-package logic after paths are standardized.|

## 5. US S10 gap

The current US batch lacks a clean source-of-truth builder.

A new script is required:

```
US_S10_source_of_truth_panel.R
```

Its function should be limited to canonical panel construction. It should not run econometrics, reconstruct μ, or generate paper-facing outputs.

Expected variables:

```
yearY_realK_total_realK_machinery_real, if availableK_other_real, if availables_t = K_machinery / K_totalomega_tpYpKprofitability inputs
```

The current scripts appear to repeatedly rebuild real output, real capital, and wage-share objects internally. That should stop. Each script should not behave as a tiny independent republic.

## 6. US S20 role

The US still needs an admissibility layer, even without the peripheral external-mechanization wedge.

`US_S20_composition_stability_admissibility.R` should:

```
construct or validate s_t if availabledefine estimation windowscheck integration ordercheck deterministic componentscheck breaks / stabilityprepare admissible samples for S30record what can and cannot be interpreted as stable
```

This layer prevents a direct jump from source data to θ/μ reconstruction.

## 7. US S30 role

`US_S30_transformation_relation_fmols_imols_dols.R` should estimate the reduced-form long-run transformation relation.

Estimator roles:

```
FM-OLS = mainIM-OLS = robustnessDOLS   = fragility / stress
```

The script should not derive final μ as its main task. Its output should be coefficient objects and estimator-comparison diagnostics.

## 8. US S40 role

`US_S40_theta_tot_mu_reconstruction.R` should take the S30 coefficient output and reconstruct:

```
θ^totYpμ
```

This is where productive capacity and utilization are derived.

It must not treat DOLS residuals as primitive utilization.

The correct logic is:

```
estimated reduced-form relation→ θ^tot→ reconstructed Yp→ level anchoring→ derived μ
```

This preserves the empirical identification rule: utilization is derived only after productive capacity is reconstructed and anchored.

## 9. US S50 role

`US_S50_theta_mu_profitability_corridor.R` should consume the reconstructed μ and θ objects.

Its purpose is to interpret:

```
θ → μ → r
```

This corresponds to the productive-capacity corridor. The process-tracing playbook defines this corridor as `θ → μ → r`, distinct from the recapitalization corridor `χ → k → g`.

## 10. US S90 role

DOLS belongs mainly here.

`US_S90_dols_fragility_diagnostics.R` should include:

```
lead-lag sensitivityDOLS grid testswindow robustnesscollinearity / VIF checksknown-break stress testsfull-sample fragility checks
```

DOLS can reveal fragility. It should not define the main reconstruction.

## 11. US S99 role

`US_S99_results_package.R` should collect and export final outputs only after upstream objects are rebuilt.

Expected outputs:

```
tablesfiguresdiagnostic summariespaper-facing result sheetsadvisor-facing figures
```

It should not silently recompute θ or μ.

## 12. US locked memo statement

The US code batch is not promoted as-is.

It is recycled as follows:

```
DOLS-era estimation scripts → S90 fragility diagnosticsfullsample / FM / IM donor scripts → S30 estimator gridθ/μ graph scripts → S40 reconstruction + S99 figuresprofitability scripts → S50 corridor interpretation + S99 result package
```

The final US architecture must be FM-OLS-centered, IM-OLS-checked, DOLS-stressed, and rebuilt around `θ^tot`, not direct `θ^M`.