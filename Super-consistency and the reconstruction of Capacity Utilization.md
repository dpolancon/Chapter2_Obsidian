---
type: note
status: active
layer: method
design_role: estimation_clarification
scope: chapter2_core_support
related_to: 02D_Mechanism_Map
elated_to: Chapter3_Identification
---



# Super-consistency and the reconstruction of $\mu$

## Core claim

Super-consistency secures the recovery of the long-run transformation relation.  
It does not secure the empirical reconstruction of $\mu$.

---

## 1. The distinction

Cointegrated estimators (OLS, DOLS, FM-OLS, IM-OLS) are designed to recover the long-run coefficient vector under integration.

This establishes:

> whether the transformation relation can be estimated.

It does not establish:

> whether the utilization series derived from that relation is theoretically and empirically admissible.

The distinction is necessary because $\mu$ is not directly estimated. It is reconstructed.

---

## 2. Identification sequence

The empirical object is produced through a sequence:

$$
\text{long-run coefficients} \rightarrow \hat{\theta}_t \rightarrow \hat{Y}_t^p \rightarrow \hat{\mu}_t
$$

Super-consistency applies only to the first step.

Everything downstream remains contingent on:
- normalization,
- deterministic specification,
- interaction structure,
- and the conceptual status of the residual.

---

## 3. Estimator layer (literature anchor)

In linear cointegration:

- OLS is super-consistent but second-order biased  
- DOLS corrects via leads/lags of differences  
- FM-OLS corrects via long-run variance  
- IM-OLS avoids kernel/bandwidth selection  

(Cointegration estimator properties: see Phillips & Hansen; Stock & Watson; cointReg package documentation)

These estimators are equivalent asymptotically **only in linear settings**.

---

## 4. Breakdown under threshold settings

Once regime switching is introduced:

- equivalence across OLS / DOLS / FM-OLS breaks down  
- long-run relation is no longer globally stable  
- lead-lag correction becomes misaligned with regime shifts  

In this setting:

> FGLS becomes the relevant estimator family for threshold cointegration.

(Threshold cointegration literature; TAR/SETAR results; see working note synthesis)

---

## 5. Implication for $\mu$

Even under super-consistency:

- $\theta_t$ is estimated  
- but $\mu_t$ is reconstructed  

This requires:

1. translating the long-run relation into productive capacity  
2. imposing a benchmark normalization  
3. interpreting the residual as utilization  

So:

> coefficient consistency does not imply object consistency.

---

## 6. U.S. case

In the U.S.:

- the long-run transformation relation is stable  
- interaction term $\omega_t k_t$ is identifiable  
- super-consistent estimators are appropriate  

But:

> $\mu_t$ still depends on normalization and translation to $Y_t^p$.

So the gain is partial:
- strong $\theta_t$
- conditional $\mu_t$

---

## 7. Chile case

In Chile, the distinction becomes binding.

The previous design attempted to:

- estimate long-run relation (DOLS)
- activate regimes via ECT
- allow coefficient switching
- reconstruct $\theta_t$ and $\mu_t$

This collapses:

1. long-run identification  
2. regime activation  

Into one step.

This is not admissible.

So:

> failure of DOLS is a specification failure, not an empirical refutation.

---

## 8. Correct separation

### Long-run layer
- identify transformation relation  
- choose estimator consistent with structure  

### Regime layer
- define regimes using observed variables  
- do not use generated ECT  

### Reconstruction layer
- recover $\theta_t$  
- construct $Y_t^p$  
- derive $\mu_t$

---

## 9. Locked statement

**Super-consistency belongs to long-run coefficient recovery. The empirical reconstruction of $\mu$ requires a second operation: translating the transformation relation into productive capacity and only then into utilization under an explicit normalization rule.**