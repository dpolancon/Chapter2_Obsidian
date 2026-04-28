---
type: master_note
status: active
layer: method
design_role: empirical_strategy_scaffold
scope: chapter2_core_support
related_to:
  - N01_CapacityUtilization_StructuralObject
  - N02_SuperConsistency
  - R01_residual_vs_structural_identification
  - R02_DOLS_reconstruction_dilemma
  - R03_super_consistency_mechanics_hinge
  - R04_FMOLS_structural_preservation
  - R05_LRV_kernel_bandwidth_regime_misalignment
  - R06_IMOLS_integration_ladder_reconstruction
  - R07_FGLS_threshold_cointegration_admissibility
  - R08_threshold_break_diagnostics_to_FGLS
  - L00_Econometrics_References
priority: high
---

# M10 Empirical Identification Framework

## Core claim

Chapter 2 does not estimate utilization directly.

It estimates the long-run transformation relation, reconstructs productive capacity, anchors its level, and only then derives utilization.

Main reference notes: [[N01_CapacityUtilization_StructuralObject]], [[N02_SuperConsistency]], [[R01_residual_vs_structural_identification]].

---

## 1. Object layer

Source notes:

- [[N01_CapacityUtilization_StructuralObject]]
- [[R01_residual_vs_structural_identification]]

Rule:

Do not identify $\mu_t$ by residual.

Admissible sequence:

$$
\text{structural relation}
\rightarrow
\hat{Y}_t^p
\rightarrow
\hat{\mu}_t
$$

The residual is an implication of reconstruction, not the foundation of identification.

---

## 2. Super-consistency layer

Source notes:

- [[N02_SuperConsistency]]
- [[R03_super_consistency_mechanics_hinge]]

Rule:

Super-consistency secures coefficient recovery, not object recovery.

Estimator families:

- DOLS → [[R02_DOLS_reconstruction_dilemma]]
- FM-OLS → [[R04_FMOLS_structural_preservation]]
- IM-OLS → [[R06_IMOLS_integration_ladder_reconstruction]]

Each estimator solves second-order bias differently and introduces a different structural cost.

---

## 3. Estimator assignment

Source notes:

- [[R04_FMOLS_structural_preservation]]
- [[R06_IMOLS_integration_ladder_reconstruction]]
- [[R02_DOLS_reconstruction_dilemma]]

Assignment:

- FM-OLS: main estimator for log-level long-run reconstruction.
- IM-OLS: robustness check.
- DOLS: fragility diagnostic.

Rule:

FM-OLS reconstructs.  
IM-OLS checks.  
DOLS stresses fragility.

---

## 4. FM-OLS warning layer

Source note:

- [[R05_LRV_kernel_bandwidth_regime_misalignment]]

Rule:

FM-OLS preserves the theoretical regressor matrix, but its long-run variance correction may smooth across historical regime boundaries.

Therefore, FM-OLS is preferred for global long-run reconstruction, not for identifying regime-dependent transformation elasticities by itself.

---

## 5. Diagnostic layer

Source note:

- [[R08_threshold_break_diagnostics_to_FGLS]]

Rule:

Before threshold estimation, distinguish:

- unit roots;
- deterministic components;
- structural breaks;
- nonlinear unit roots;
- threshold cointegration.

Threshold cointegration is not a robustness check. It is a structural claim about regime-dependent equilibrium.

---

## 6. Regime layer

Source note:

- [[R07_FGLS_threshold_cointegration_admissibility]]

Rule:

FGLS becomes admissible only after threshold behavior is independently justified.

It cannot:

- identify cointegration by itself;
- activate regimes by itself;
- validate productive capacity by itself;
- reconstruct utilization by itself.

---

## 7. Reconstruction layer

Source notes:

- [[N01_CapacityUtilization_StructuralObject]]
- [[R01_residual_vs_structural_identification]]
- [[N02_SuperConsistency]]

Final sequence:

$$
\text{diagnostic ladder}
\rightarrow
\text{long-run coefficient recovery}
\rightarrow
\hat{\theta}_t
\rightarrow
\hat{Y}_t^p
\rightarrow
\text{level anchoring}
\rightarrow
\hat{\mu}_t
$$

This sequence blocks residual identification and keeps productive capacity as the object recovered before utilization.

---

## 8. Operational estimator map

| Role | Estimator / method | Function | Source note |
|---|---|---|---|
| Object definition | Structural reconstruction | Defines $\mu_t$ as derived ratio | [[N01_CapacityUtilization_StructuralObject]] |
| Residual guardrail | Identification rule | Blocks residual ontology | [[R01_residual_vs_structural_identification]] |
| Main reconstruction | FM-OLS | Long-run log-level coefficient recovery | [[R04_FMOLS_structural_preservation]] |
| Robustness | IM-OLS | Coefficient robustness without DOLS/FM-OLS tuning structure | [[R06_IMOLS_integration_ladder_reconstruction]] |
| Fragility | DOLS | Stress test via lead-lag absorption | [[R02_DOLS_reconstruction_dilemma]] |
| Estimator taxonomy | Super-consistency hinge | Maps DOLS / FM-OLS / IM-OLS | [[R03_super_consistency_mechanics_hinge]] |
| FM-OLS warning | LRV/kernel layer | Flags covariance-window smearing | [[R05_LRV_kernel_bandwidth_regime_misalignment]] |
| System admissibility | VECM / Johansen | Cointegration rank/system check | [[L00_Econometrics_References]] |
| Diagnostic ladder | Haldrup layer | Unit roots, breaks, nonlinearities | [[R08_threshold_break_diagnostics_to_FGLS]] |
| Regime estimation | Threshold-FGLS | Regime-specific coefficient recovery after admissibility | [[R07_FGLS_threshold_cointegration_admissibility]] |

---

## 9. Reference control

Reference ledger:

- [[L00_Econometrics_References]]

Rule:

Do not scatter econometric references unless the note needs standalone portability. The ledger controls reference consistency.

---

## 10. Locked statement

**Chapter 2 does not estimate utilization directly. It estimates the long-run transformation relation, reconstructs productive capacity, anchors its level, and only then derives utilization. FM-OLS is the main estimator, IM-OLS is the robustness check, DOLS is the fragility diagnostic, and threshold-FGLS belongs only to the regime layer after diagnostic admissibility.**