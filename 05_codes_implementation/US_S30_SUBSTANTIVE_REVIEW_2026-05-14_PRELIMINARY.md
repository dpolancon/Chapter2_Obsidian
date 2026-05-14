# US S30 Substantive Review — Preliminary Memo

**Proposed repo path:** `artifacts/repo_state_logs/us_s30_transformation_relation/US_S30_SUBSTANTIVE_REVIEW_2026-05-14.md`  
**Status:** preliminary substantive review based on the carry-over contract and known S30 classification summary. Coefficient-level confirmation still requires local inspection of the S30 CSVs and report files.

## 1. Decision

S40 should remain blocked as the default productive-capacity reconstruction pathway.

The correct next path is a **formal-stability path**, with a bounded mechanism-evidence interpretation of C1 and a restricted-candidate status for B1. B1 can remain the leading specification for review, but it should not be promoted to S40 on the current evidence. The decisive reason is simple: S30 produced zero core candidates under the declared stability discipline, and the current stability screen is explicitly a proxy diagnostic rather than a formal parameter-instability test.

A conservative B1 route can be kept alive only as a labelled candidate-under-review, not as a promoted productive-capacity benchmark. If used later, it should be introduced as a restricted sensitivity reconstruction after a formal stability check or after an explicit methodological override is documented.

## 2. Answers to the seven review questions

### 1. Is B1 defensible as a conservative restricted S40 candidate despite fragility?

Not yet as an S40 candidate. Yes as the leading restricted object for further review.

B1 is attractive because it avoids the severe collinearity that damages fuller composition specifications and because it carries the wage-share/distributional channel directly. That gives it theoretical discipline and practical cleanliness. But its current classification remains fragile, and the pipeline rule forbids promotion by coefficient appeal. Therefore B1 should be labelled:

> **Leading restricted candidate under review; not yet S40-promoted.**

This keeps the door open without violating the S30 gate.

### 2. Does C1 provide mechanism evidence without being used for S40?

Yes. C1 should be reported as mechanism evidence, not as a reconstruction engine.

C1 tests whether the ME–NRC stock-composition proxy adds information to the transformation relation. Since the proxy is Tier-B and not a direct NFCorp asset-composition split, it can support a mechanism reading only with careful language. The correct language is:

> C1 indicates that composition is empirically relevant to the transformation relation, but the evidence is not stable enough to define the productive-capacity reconstruction specification.

That is useful and dissertation-facing: composition matters, but the available proxy cannot carry the core S40 object.

### 3. Is C2 formally demoted to diagnostic-only in the next pass?

Yes. C2 should be demoted from core eligibility.

The full composition interaction is repeatedly damaged by severe collinearity. That is not a minor nuisance; it means the model is asking the available data to distinguish too many closely related channels at once. C2 should remain in the S30 archive as a stress diagnostic showing the limits of the Tier-B composition bridge.

Recommended label:

> **SPEC_C2_FULL_COMPOSITION = diagnostic-only; excluded from core promotion gates because of severe collinearity.**

### 4. Are DOLS failures mainly sample-size stress rather than substantive contradiction?

Provisionally, yes.

The carry-over record says DOLS ran, but some window/specification cells were rejected after lead/lag construction reduced the effective sample. That is a DOLS stress pattern, not automatically a substantive contradiction. The memo should distinguish:

- failure because the cell becomes too short after DOLS lead/lag construction;
- failure because surviving DOLS estimates contradict FM-OLS and IM-OLS;
- failure because DOLS survives but sharply widens uncertainty.

Only the second case would be a substantive contradiction. The known record currently supports the first interpretation.

### 5. Are rolling FM-OLS paths structured enough for historical interpretation?

They can be used as historical diagnostics, not as regime identifiers.

The locked S30 rule already decides the key issue: rolling and recursive estimates do not identify regimes. They can help narrate where instability becomes visible, especially if movements cluster around historically meaningful windows, but they cannot define the window choice and cannot promote a specification.

Recommended language:

> Rolling FM-OLS paths are admissible as instability diagnostics and historical illustrations. They are not admissible as regime-selection devices.

### 6. Is a formal Hansen/Gregory-Hansen stability module needed before S40?

Yes, if S40 is meant to produce a defensible US benchmark rather than an explicitly exploratory sensitivity reconstruction.

The present S30 screen is a proxy-stability diagnostic. That is useful, but it does not settle parameter stability of the cointegrating vector. A bounded formal module is warranted before S40 if the chapter wants to avoid both arbitrary split-window selection and overclaiming from fragile super-consistent estimates.

Recommended implementation scope:

1. Hansen-type parameter-instability tests for the cointegrating regression where feasible.
2. Gregory-Hansen-style residual-based cointegration tests with one unknown regime shift as a stress check, not as a new regime-mining exercise.
3. A small decision table: stable, unstable-with-known-window-support, unstable-without-promotable-candidate.

This module should not expand the estimator grid. It should adjudicate whether B1 can be promoted or whether the US benchmark must stop at S30.

### 7. Should the paper report “no stable S30 core candidate” as a substantive result?

Yes. This is a result, not a failure.

The paper should report that under the declared historical-window, estimator-triangulation, and proxy-stability discipline, no US S30 specification qualifies as a stable core candidate. That finding matters because it prevents the chapter from manufacturing a productive-capacity path from a convenient coefficient. It also clarifies the empirical status of the composition mechanism: theoretically important and empirically suggestive, but not yet stable enough to carry S40.

## 3. Specification disposition table

| Specification | Review disposition | S40 status | Reporting role |
|---|---|---|---|
| B0 capital only | Supporting benchmark | Not eligible as core | Baseline reference only |
| B1 wage baseline | Leading restricted candidate under review | Blocked pending formal stability check | Main candidate to adjudicate |
| C1 composition stock | Mechanism-informative but unstable | Not eligible | Report as mechanism evidence |
| C2 full composition | Diagnostic-only | Demoted from core eligibility | Stress test / collinearity evidence |
| D1/D2 valuation and price diagnostics | Diagnostic-only | Not eligible | Current-cost and relative-price checks |

## 4. Memo-level conclusion

The recommended decision is:

> **S40 remains blocked for the US benchmark. B1 is retained as the leading restricted candidate for formal stability adjudication. C1 is reported as mechanism evidence but excluded from reconstruction. C2 is demoted to diagnostic-only. The paper should report no stable S30 core candidate as a substantive result under the declared discipline.**

This is the cleanest path because it preserves the anti-arbitrariness rule, avoids promotion by coefficient appeal, and still extracts the substantive lesson from S30: the transformation relation is estimable, but not yet stable enough to reconstruct productive capacity for the US benchmark without an additional stability gate.

## 5. Recommended next bounded patch

No S40 code.

The next bounded patch should create a formal S30 stability adjudication module and a one-page decision table. The patch should not touch Chile scripts, profitability analysis, S40 reconstruction, or the broader repo curation surface.

Suggested next label:

`US_S30_FORMAL_STABILITY_ADJUDICATION_2026-05-14`
