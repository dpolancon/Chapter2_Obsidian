
# Memo 2 — Chile Code Recycling Map

## 1. Status

The Chile code map is currently provisional because the full Chile code batch has not yet been loaded.

This memo maps the existing Chile flat-script inventory and defines how those scripts should be recycled once inspected.

Chile is the central case for the newest analytical additions:

```
composition of accumulationmachinery vs non-machinery capitalexternal mechanization wedgeestimated threshold dummyperipheral BOP / imported-machinery constraint
```

The Chile side cannot be promoted as a simple continuation of old `stage1/stage2` code.

## 2. Analytical lock for Chile

Chile must be rebuilt around the asymmetric accumulation-composition framework.

The updated foundation says:

```
All accumulation contributes to productive capacity, but not symmetrically.Machinery and equipment build capacity and transmit distributive conflict into mechanization and productivity.Non-residential infrastructure builds capacity but does not transmit mechanization or distributive conflict.
```

This is why composition is central: `s_t = K^M_t / K_t` mediates the machinery channel, while `φ_t = I^M_t / I^A_t` captures the machinery share of accumulation.

The peripheral extension adds the external mechanization wedge:

```
E_t = Λ_t φ_t
```

because imported machinery makes the mechanizing component of accumulation foreign-exchange constrained.

## 3. Required Chile target sequence

The Chile code should be reconstructed into:

```
CL_S10_source_of_truth_panel.RCL_S20_composition_mechanization_external_constraint.RCL_S20_periodization_stability_admissibility.RCL_S20_external_constraint_threshold_index.RCL_S30_transformation_relation_fmols_imols_dols.RCL_S40_theta_tot_mu_reconstruction.RCL_S50_thetaM_corridor_interpretation.RCL_S60_peripheral_mechanization_constraint.RCL_S60_bop_recapitalization_corridor.RCL_S90_threshold_dummy_fgls_admissibility.RCL_S99_results_package.R
```

Again: flat `codes/`, no country folders.

## 4. Chile script recycling table

|Current script|Recycling status|New target|Treatment|
|---|---|---|---|
|`CL_00_source_of_truth_chile.R`|Likely keep/rebuild|`CL_S10_source_of_truth_panel.R`|Canonical panel builder. Must output clean yearly panel with capital composition, wage share, output, prices, and external-constraint candidates.|
|`CL_01_stage1_mu.R`|Split aggressively|`CL_S20_*`, `CL_S30_*`, `CL_S40_*`|Name suggests it likely compresses admissibility, estimation, and μ reconstruction. Under the lock, those must be separated.|
|`CL_01_stage1_mu_source_truth_break_sig_STAGE1_ONLY.R`|Keep as admissibility donor|`CL_S20_periodization_stability_admissibility.R`|Recycle break/significance diagnostics. It should not produce final μ.|
|`CL_01_stage1_mu_source_truth_break_sig_full.R`|Keep as extended diagnostic donor|`CL_S20_periodization_stability_admissibility_full.R`|Use for robustness of admissibility, not final reconstruction.|
|`CL_03_results_package_mu_theta_wsh.R`|Split|`CL_S40_theta_tot_mu_reconstruction.R` + `CL_S99_capacity_results_package.R`|If it computes θ/μ and exports, separate computation from packaging.|
|`CL_04_results_presentation.R`|Keep downstream|`CL_S99_results_presentation.R`|Presentation/export only. No object construction.|
|`CL_05_profitability_analysis_core.R`|Keep downstream|`CL_S50_theta_mu_profitability_corridor.R`|Must consume rebuilt μ/θ objects, not old stage objects.|
|`CL_05_profitability_analysis_core_BENCH.R`|Keep as benchmark donor|`CL_S90_profitability_benchmark_stress.R`|Benchmark/stress only unless it proves cleaner than core.|
|`CL_06_results_package_profitability.R`|Keep exporter|`CL_S99_profitability_results_package.R`|Result-package export after S50.|
|`CL_07_results_package_profitability_diagnostics.R`|Keep diagnostic exporter|`CL_S90_profitability_diagnostics.R`|Diagnostics only.|
|`CL_08_results_package_profitability_diagnostics_shortrun.R`|Keep diagnostic exporter|`CL_S90_profitability_short_run_diagnostics.R`|Stress-test layer.|
|`CL_09_results_package_profitability_diagnostics_very_shortrun.R`|Keep diagnostic exporter|`CL_S90_profitability_very_short_run_diagnostics.R`|Stress-test layer.|
|`CL_10_class_struggle_diagnostic.R`|Keep, reclassify|`CL_S50_distribution_conflict_diagnostic.R` or `CL_S90_distribution_stress.R`|Useful for wage-share/conflict interpretation, but must not substitute for θ reconstruction.|
|`CL_11_dys_diagnostic_package.R`|Keep diagnostic|`CL_S90_dysfunctionality_diagnostic_package.R`|Downstream diagnosis.|
|`CL_12_capacity_utilization_diagnostic.R`|Keep diagnostic|`CL_S90_capacity_utilization_diagnostic.R`|Must diagnose derived μ, not define it.|
|`CL_12_capacity_utilization_diagnostic_rebased2010.R`|Keep as robustness|`CL_S90_capacity_utilization_rebase2010_diagnostic.R`|Rebase sensitivity.|
|`CL_12_capacity_utilization_diagnostic_rebased2010_v2.R`|Keep as robustness|`CL_S90_capacity_utilization_rebase2010_diagnostic_v2.R`|Rebase sensitivity / possible replacement.|
|`CL_A_stage1_ECT_audit.R`|Keep, but demote|`CL_S90_ect_audit_not_regime_classifier.R`|Critical guardrail: ECT cannot activate regimes by itself.|
|`CL_B_stage2_mu_Diagnostic.R`|Keep diagnostic|`CL_S90_mu_reconstruction_diagnostic.R`|Diagnose μ after S40 reconstruction.|
|`chile_class_struggle_astorga_weisskopf_v2.R`|Keep interpretive donor|`CL_S50_distribution_conflict_astorga_weisskopf.R`|Use for class-struggle/profitability interpretation, not primary θ estimation.|

The current inventory confirms these Chile flat candidates exist in the repo, together with the US scripts and legacy folders.

## 5. Chile S10 role

`CL_S10_source_of_truth_panel.R` should build the canonical Chile panel.

Expected variables:

```
yearY_realK_total_realK_machinery_realK_other_reals_t = K_machinery / K_totalI_totalI_machineryφ_t = I_machinery / I_totalomega_texternal-constraint proxiesterms-of-trade / import-capacity variablesprice indexesprofitability inputs
```

This script should not estimate θ, construct μ, or export final figures.

## 6. Chile S20 role

Chile needs a heavier S20 layer than the US.

The Chile S20 layer should be split into three scripts if necessary:

```
CL_S20_composition_mechanization_external_constraint.RCL_S20_periodization_stability_admissibility.RCL_S20_external_constraint_threshold_index.R
```

The S20 layer must construct:

```
s_t      = K^M_t / K_tφ_t      = I^M_t / I^A_tE_t      = Λ_t φ_tD_t(γ̂)  = 1{E_t > γ̂}, if threshold admissibility is established
```

It must also adjudicate:

```
integration orderbreaksdeterministic componentswindow stabilityparameter stabilitythreshold admissibility
```

This layer prevents the Chile pipeline from jumping directly from data construction into μ.

## 7. Chile S30 role

`CL_S30_transformation_relation_fmols_imols_dols.R` should estimate the reduced-form long-run transformation relation.

It should not directly claim to estimate `θ^M`.

It estimates coefficients used to identify `θ^tot`.

The S30 model should allow for the composition-weighted structure:

```
k_t(s_t - s̄)k_tω_t(s_t - s̄)k_tD_t(s_t - s̄)k_tD_tω_t(s_t - s̄)k_t
```

This follows the updated composition logic: the machinery channel is expressed through composition and interactions, while aggregate capacity is still formed by total capital.

## 8. Chile S40 role

`CL_S40_theta_tot_mu_reconstruction.R` should reconstruct:

```
θ^totYpμ
```

It should not claim to recover `θ^M` directly.

Correct sequence:

```
reduced-form coefficients→ θ^tot→ Yp→ level anchoring→ μ
```

This preserves the identification/reconstruction boundary: coefficients identify the aggregate transformation object, while machinery-specific transformation remains inferred.

## 9. Chile S50 role

`CL_S50_thetaM_corridor_interpretation.R` should interpret the machinery-specific mechanism.

It asks how `θ^tot` behavior reflects:

```
machinery compositionwage-share conflictmechanization-productivity balancenormal profit-recapitalization corridor
```

This is where the two-corridor structure enters interpretively. The two-corridor foundation states that the empirical wage-share interaction is not a generic distributive effect, but a reduced-form trace of the technical-mechanization corridor and the normal profit-recapitalization corridor.

## 10. Chile S60 role

Chile requires a distinct S60 layer because the peripheral mechanism is not reducible to the general productive-capacity corridor.

`CL_S60_peripheral_mechanization_constraint.R` should interpret:

```
machinery accumulationimported machinery dependenceforeign-exchange pressureexternal mechanization wedge
```

`CL_S60_bop_recapitalization_corridor.R` should interpret:

```
χ → k → g
```

under external constraint.

The point is not only that profitability changes. The point is whether profitability becomes renewed accumulation and growth when imported machinery and foreign-exchange constraints bind.

## 11. Chile S90 role

`CL_S90_threshold_dummy_fgls_admissibility.R` should stress-test the threshold architecture.

The threshold model should not be a generic continuous external-wedge model. The preferred logic is:

```
E_t = Λ_t φ_tγ̂ = estimated thresholdD_t(γ̂) = 1{E_t > γ̂}
```

Then test whether the high-external-constraint regime changes the transformation relation.

The uploaded threshold note already states that the threshold model identifies when the external mechanization wedge becomes binding and whether the wage-share coefficient changes once the constraint binds.

S90 must test:

```
threshold significanceγ̂ sensitivityweak identificationbreak vs threshold distinctionFGLS admissibilitybootstrap / sup-Wald where applicable
```

But S90 cannot override S20. FGLS cannot become a shortcut around the diagnostic ladder.

## 12. Chile S99 role

`CL_S99_results_package.R` should export only final paper-facing and advisor-facing results.

It should not reconstruct objects silently.

Expected outputs:

```
tablesfiguresdiagnostic appendicesperiod summariesθ^tot / μ plotsthreshold-regime visualizationsprofitability-corridor summariesBOP/external-constraint summaries
```

## 13. Chile locked memo statement

The Chile code should be rebuilt around the asymmetric composition framework.

The final Chile architecture must:

```
separate total accumulation from machinery accumulationconstruct s_t and φ_t explicitlyconstruct E_t = Λ_tφ_t or proxyestimate γ̂ where admissibleconstruct D_t(γ̂)estimate reduced-form transformation coefficientsreconstruct θ^tot and μinterpret θ^M through machinery-channel logicinterpret peripheral constraint through S60stress-test threshold/FGLS only in S90
```

No ECT-driven regime activation.  
No direct jump from source panel to μ.  
No direct claim that coefficients estimate `θ^M`.

---

# Combined Closing Lock

The country memos produce the following combined rule:

```
US = rebuild DOLS-era code into FM-OLS-centered aggregate θ^tot reconstruction,     with IM-OLS robustness and DOLS fragility diagnostics.Chile = rebuild stage-style code into composition/external-constraint architecture,        with s_t, φ_t, E_t, estimated γ̂, D_t(γ̂), θ^tot reconstruction,        and θ^M interpretation through the peripheral machinery channel.
```

The next repo action should be to create:

```
artifacts/repo_state_logs/CODE_RECYCLING_COUNTRY_MEMOS_2026-05-05.md
```

Commit message:

```
audit: map country code recycling under analytical lock
```

That commit should include only the memo file. No scripts should be moved yet.