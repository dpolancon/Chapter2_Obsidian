---
type: implementation_memo
status: active
layer: code_stage_design
design_role: us_s30_formal_stability_protocol
scope: chapter2_results_repo
country: US
stage: S30
repo: Capacity-Utilization-US_Chile
created: 2026-05-14
related_to:
  - US_S30_SUBSTANTIVE_REVIEW_2026-05-14_PRELIMINARY
  - R09_structural_break_protocol
  - M10_Empirical_Identification_Framework
  - N02_SuperConsistency
  - Price-deflator protocol for ME-NRC Non Financial-capital composition
---

# C04 - US S30 Stability Protocol

## 0. Purpose

This memo defines the next bounded coding step for the US S30 layer only.

It does not authorize S40 code. It does not reconstruct productive capacity. It does not compute utilization. It does not expand the estimator grid. It does not touch Chile.

The next code pass should adjudicate whether the existing US S30 results contain a restricted B1 pathway that is admissible enough to open later S40 work under an explicit fragility discipline. The cointegrating relation remains the primary empirical object; formal stability evidence supports the S30 adjudication rather than replacing the object-level assessment.

Proposed future script, not created here:

```text
codes/US_S30_formal_stability_adjudication.R
```

The script should consume the existing US S30 outputs and write additional S30 adjudication artifacts. It should not overwrite the estimator grid as if the prior S30 pass had promoted a candidate.

## 1. Current S30 status

The existing S30 run produced zero core candidates under the declared proxy-stability discipline.

The present stability evidence is useful but incomplete because Hansen-type parameter-instability evidence was not implemented. The existing S30 stability label is therefore:

```text
proxy_stability_diagnostic
```

The next pass should add the preferred formal stability diagnostic before any S40 productive-capacity reconstruction can be considered.

## 2. Specification disposition

The next S30 code must use the following adjudicated disposition, regardless of the original `promotion_eligible` flags in the first-pass specification register.

| spec_id | Adjudicated role | S40 eligibility after this memo | Treatment in next code |
|---|---|---:|---|
| `SPEC_B0_CAPITAL_ONLY` | supporting benchmark | no | Keep as baseline reference only. It may be reported beside B1 to contextualize stability, but it cannot carry S40. |
| `SPEC_B1_WAGE_BASELINE` | leading restricted candidate under review | conditional | This is the only specification still eligible for restricted S40 pathway adjudication. It is not promoted unless it passes the hierarchical gate below. |
| `SPEC_C1_COMPOSITION_STOCK` | mechanism evidence | no | Keep as diagnostic/mechanism evidence. It can show that the ME-NRC composition proxy matters, but it cannot define the reconstruction specification. |
| `SPEC_C2_FULL_COMPOSITION` | diagnostic-only | no | Demote from core eligibility because severe collinearity makes the full interaction structure non-promotable. |
| `SPEC_D1_CURRENT_COST_DIAGNOSTIC` | diagnostic-only | no | Keep only as valuation-composition diagnostic. |
| `SPEC_D2_PRICE_WEDGE_DIAGNOSTIC` | diagnostic-only | no | Keep only as relative-price wedge diagnostic. |

Operationally, the new S30 adjudication output should include a fresh disposition table rather than silently editing the historical first-pass register. The first-pass register records what was attempted; the new table records what remains admissible after substantive review.

## 3. Candidate eligibility rule

Only `SPEC_B1_WAGE_BASELINE` remains eligible for restricted S40 pathway review.

Eligibility means only this:

```text
eligible_for_restricted_s40_adjudication = TRUE
```

It does not mean:

```text
promoted_to_S40 = TRUE
```

B1 can move forward only as a restricted candidate if it passes the object-admissibility tier and receives supportive or mixed stability evidence using the existing S30 variable set, estimator roles, and historical-window register. If the evidence is mixed, any later S40 output must carry a fragility flag. If the evidence is contradictory or unavailable, the US benchmark stops at S30.

No composition-augmented specification should be promoted as a substitute if B1 fails. C1 remains mechanism evidence, and C2 remains diagnostic-only.

## 4. Preferred stability diagnostics before S40

The next S30 script should add the preferred formal stability diagnostic for the B1 cointegrating relation:

```text
y_t ~ k_t + omega_k_t
```

The minimum required diagnostic checks are:

1. Run a Hansen-type parameter-instability test, or the closest implementable equivalent, as preferred formal stability evidence for the B1 cointegrating regression.
2. Apply it to the existing S30 reference windows only; do not add new candidate windows.
3. Report whether the procedure is the exact Hansen test or an operational proxy.
4. Report test statistic, p-value if available, critical values if available, implementation package/function, and failure reason if the test cannot be computed.
5. Preserve the estimator-role hierarchy: FM-OLS main, IM-OLS robustness, DOLS fragility diagnostic.
6. Carry forward effective sample size, DOLS survival/failure, neighborhood reversals, collinearity flags, and rolling diagnostics from the existing S30 outputs.
7. Classify the stability evidence as `supportive`, `mixed`, `contradictory`, or `unavailable`.

Suggested evidence mapping:

| Formal result | Evidence class |
|---|---|
| No instability rejection at 10 percent | `supportive` |
| Rejection at 10 percent but not 5 percent | `mixed`; restricted S40 may open only with a fragility flag if Tier 1 also passes |
| Rejection at 5 percent or stronger | `contradictory`; S40 remains blocked |
| Test unavailable or effective sample inadequate | `unavailable`; S40 remains blocked |

The code should report 10, 5, and 1 percent results when the implementation provides them. A preferred coefficient sign, magnitude, or significance level cannot override the hierarchical S40 gate.

## 5. Gregory-Hansen and Hansen-style break tests

Hansen-type parameter-instability testing is the preferred formal stability diagnostic because S30 is asking whether the cointegrating relation can be treated as sufficiently stable for restricted downstream use.

Gregory-Hansen style tests may be used only as a bounded supporting stress check. Their role is to ask whether cointegration is recovered when one unknown regime shift is allowed. They do not select the S40 window, do not create a regime model, and do not convert the chapter into a structural-break paper.

Rules for the next code:

- Run the Hansen-type check for B1 as the preferred formal diagnostic supporting S30 adjudication.
- Run Gregory-Hansen for B1 only if the implementation stack can do so cleanly.
- If Gregory-Hansen is run, export the estimated break date and model variant as diagnostic evidence only.
- Do not use the Gregory-Hansen break date to redefine historical windows.
- Do not run Bai-Perron, Kejriwal-Perron, threshold-FGLS, or multiple-break searches in this step.
- Do not promote C1 or C2 because a break-adjusted test looks more favorable.
- Do not report rolling or recursive paths as regime identifiers.

Admissible interpretation:

```text
The one-break diagnostic suggests whether B1's cointegration evidence is sensitive to allowing a single unknown shift.
```

Inadmissible interpretation:

```text
The break test discovered the regime structure for S40.
```

## 6. Export artifacts required from the next empirical script

The next script should write only US S30 artifacts under:

```text
C:/ReposGitHub/Capacity-Utilization-US_Chile/output/US/S30_transformation_relation/
```

Required exports:

| Artifact | Required content |
|---|---|
| `us_s30_formal_spec_disposition.csv` | One row per existing S30 specification with adjudicated role, S40 eligibility, diagnostic-only flag, and exclusion reason. |
| `us_s30_hansen_stability_tests.csv` | B1 Hansen-type stability evidence by existing reference window, including exact/proxy flag, statistic, p-value or critical values, evidence class, package/function, and failure reason. |
| `us_s30_gregory_hansen_stress.csv` | B1 one-break cointegration stress results if implemented; otherwise a row recording `not_implemented` and the reason. |
| `us_s30_formal_stability_decision.csv` | Final hierarchical S30 gate table with Tier 1, Tier 2, and Tier 3 status; B1 restricted-pathway decision; fragility flag; and whether S40 remains blocked. |
| `US_S30_formal_stability_adjudication_report.md` | Short human-readable report summarizing disposition, formal tests, Gregory-Hansen treatment, and S40 gate result. |
| `us_s30_formal_stability_manifest.csv` | Run timestamp, input files, package availability, test implementations, unchanged estimator settings, and explicit `no_s40_code = TRUE`. |

Forbidden exports in this step:

- productive-capacity paths;
- `Yp` series;
- utilization or `mu` series;
- profitability outputs;
- Chile outputs;
- new estimator-grid expansions;
- paper-facing tables presented as final chapter results.

## 7. S40 hierarchical stop-rule

S40 may open only as a restricted B1 pathway. The gate is hierarchical.

### Tier 1: object admissibility

All Tier 1 conditions must pass:

1. B1 is the candidate being evaluated.
2. No severe collinearity flag applies to B1.
3. Existing S30 estimator triangulation does not show a substantive contradiction from IM-OLS or surviving DOLS estimates.

If Tier 1 fails, S40 remains blocked regardless of later stability or stress-test evidence.

### Tier 2: stability evidence

Tier 2 uses Hansen-type evidence as the preferred formal stability diagnostic, together with existing neighborhood diagnostics:

1. Hansen-type evidence is `supportive` or `mixed`.
2. Neighborhood diagnostics do not overturn the interpretation.

If Tier 2 is `supportive` and Tier 1 passes, S40 may open only as a restricted B1 pathway. If Tier 2 is `mixed` and Tier 1 passes, S40 may open only as a restricted B1 pathway with an explicit fragility flag. If Tier 2 is `contradictory` or `unavailable`, S40 remains blocked.

### Tier 3: supporting stress checks

Gregory-Hansen, if run, is a supporting stress check only. It may report one-break cointegration sensitivity, but it cannot redefine historical windows, create regimes, or promote any non-B1 specification.

The decision table must explicitly record one of:

```text
s40_gate = pass_restricted
s40_gate = pass_restricted_fragility_flag
s40_gate = blocked
```

If the hierarchical gate blocks S40, the correct result is:

```text
US S40 blocked: no admissible restricted B1 pathway under S30 evidence.
```

This is a substantive S30 finding, not a failed code path.

## Ready to code only if

- [ ] The script is limited to US S30 formal stability adjudication.
- [ ] The script consumes existing S30 outputs instead of expanding the estimator grid.
- [ ] `SPEC_B1_WAGE_BASELINE` is the only restricted S40-pathway candidate under review.
- [ ] `SPEC_C1_COMPOSITION_STOCK` is mechanism evidence only.
- [ ] `SPEC_C2_FULL_COMPOSITION`, `SPEC_D1_CURRENT_COST_DIAGNOSTIC`, and `SPEC_D2_PRICE_WEDGE_DIAGNOSTIC` are diagnostic-only.
- [ ] Hansen-type parameter-instability testing is the preferred formal stability diagnostic, with exact/proxy status reported.
- [ ] Stability evidence is classified as `supportive`, `mixed`, `contradictory`, or `unavailable`.
- [ ] The S40 decision uses the Tier 1 object-admissibility, Tier 2 stability-evidence, and Tier 3 supporting-stress hierarchy.
- [ ] Mixed Tier 2 evidence opens S40 only with an explicit fragility flag.
- [ ] Contradictory or unavailable Tier 2 evidence leaves S40 blocked.
- [ ] Gregory-Hansen is optional, one-break-only, and diagnostic; it does not choose regimes or windows.
- [ ] No S40 code, productive-capacity reconstruction, utilization computation, profitability analysis, or Chile output is produced.
- [ ] The script exports a formal S30 gate decision that never promotes C1, C2, D1, or D2.
