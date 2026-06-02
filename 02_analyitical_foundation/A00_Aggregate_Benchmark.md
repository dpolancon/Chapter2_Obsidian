---
title: "A00: Aggregate Transformation Benchmark"
type: "note"
subtype: "object_alias"
status: "active"
layer: "analytical_foundation"
design_role: "legacy_alias"
scope: "chapter2_core"
created: 2026-06-01
updated: 2026-06-01
related_to:
  - "A00_Aggregate_Transformation_Benchmark"
  - "A03_TransformationElasticity_Two-CapitalCapacityComposition"
  - "N01_CapacityUtilization_StructuralObject"
  - "M10_Empirical_Identification_Framework"
---

# A00: Aggregate Transformation Benchmark

This legacy note aliases [[A00_Aggregate_Transformation_Benchmark]].

The locked A00 formulation is:

$$
\text{aggregate } K_t,\quad \text{time-varying } \theta_t.
$$

A00 defines the baseline aggregate identification of the transformation elasticity with undifferentiated total real productive capital ($K_t$). It does not distinguish $K^{ME}$ from $K^{NRC}$, and it does not define a constant-$\theta$ benchmark.

The baseline A00 econometric object is:

$$
y_t = c + \beta_1 k_t + \beta_2(\omega_t k_t) + \xi_t,
$$

which implies:

$$
\theta_t = \beta_1 + \beta_2\omega_t.
$$

A03 opens this aggregate $\theta_t$ into two-capital composition channels. A04 is activated when peripheral or external realization constraints contaminate the baseline aggregate interaction relation.
