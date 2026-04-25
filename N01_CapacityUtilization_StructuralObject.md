---
type: note
status: active
layer: method
design_role: empirical_identification_clarification
scope: chapter2_core_support
related_to: 07_Empirical_Identification_Framework; 04A_SuperConsistency_vs_Mu_Reconstruction
priority: high
---

# Capacity Utilization ($\mu$) as a structural object

## Core claim

The empirical identification of the rate of capacity utilization is not exhausted by recovering a residual from output after fitting a long-run trend.

In this framework, $\mu_t$ is not a free residual in the Shaikhian sense. It is a **structurally reconstructed object**. It is identified through the transformation relation linking accumulation to productive-capacity growth, and that relation is itself endogenously mediated by distribution. The empirical recovery of $\mu_t$ therefore begins with the identification of $\theta_t$, proceeds through the recovery of productive capacity $Y_t^p$, and only then reaches utilization. The remaining caveat is not conceptual but operational: level recovery still requires a pinch-year normalization. :contentReference[oaicite:0]{index=0}

---

## 1. Why this distinction matters

The key empirical danger is to confuse two different objects:

1. a residual left over after estimating output on capital, and  
2. a structurally identified utilization rate reconstructed from a mediated transformation relation.

The first is weakly specified. The second is theoretically loaded.

The present framework adopts the second route. Output, capital, and wage share are observed. Productive capacity, transformation elasticity, and utilization are not directly observed. They must be recovered in sequence. That means the empirical problem is not simply to subtract a trend from actual output. It is to identify the structure through which accumulation is transformed into productive capacity and, from there, the extent to which actual output stands above or below that capacity. :contentReference[oaicite:1]{index=1}

---

## 2. The identification sequence

The empirical reconstruction follows a strict order:

$$
\text{long-run transformation relation}
\rightarrow
\hat{\theta}_t
\rightarrow
\hat{Y}_t^p
\rightarrow
\hat{\mu}_t
$$

This sequence has strong implications.

First, $\mu_t$ is not estimated directly.  
Second, $\mu_t$ is not conceptually prior to the transformation relation.  
Third, the long-run coefficients do not finish the identification problem; they only open it.

So the proper statement is:

**the direct target of estimation is the transformation relation; utilization is a downstream structural recovery.**

---

## 3. Distribution enters the identification of $\mu$

In this framework, distribution does not enter as an auxiliary control added after the fact. It enters as part of the mechanism by which accumulation is transformed into productive capacity.

That is why the U.S. benchmark relation takes the form

$$
y_t = c + \beta_1 k_t + \beta_2(\omega_t k_t) + \xi_t
$$

with

$$
\hat{\theta}_t = \hat{\beta}_1 + \hat{\beta}_2 \omega_t.
$$

The implication is decisive. Distribution affects utilization **through** its mediation of the transformation elasticity. This means that the reconstruction of $\mu_t$ is endogenous to distribution from the start. Distribution does not arrive later as an interpretation layered on top of an already recovered utilization series. It enters inside the recovery of $\theta_t$ itself. :contentReference[oaicite:2]{index=2}

So the correct chain is:

$$
\omega_t \rightarrow \theta_t \rightarrow Y_t^p \rightarrow \mu_t
$$

not

$$
\omega_t \rightarrow \mu_t
$$

directly, and not

$$
\mu_t = \text{residual after trend removal}.
$$

---

## 4. Distinction from Shaikh

This framework remains indebted to Shaikh for posing the utilization problem as a problem of reconstruction rather than of accepting inherited survey proxies. But it departs from Shaikh at a decisive point.

In Shaikh’s setup, utilization is often treated empirically through the long-run wedge between actual output and productive capacity, with the residual carrying the utilization content once the productive-capacity path is identified.

Here that wedge is not treated as a conceptually self-sufficient residual. The wedge is only admissible because it emerges from a **previous structural identification** of the transformation elasticity. In other words:

- the utilization series is not what remains once the explanatory work is done;
- the utilization series is what becomes identifiable **because** the explanatory work has been done.

That is the distinction that must remain explicit in the dissertation.

So the sharp sentence is:

**Unlike a residualized utilization concept, the present $\mu_t$ is structurally mediated by distribution through the identification of $\theta_t$ and only then recovered as the relation between actual and productive-capacity output.**

---

## 5. The role of super-consistent estimation

Super-consistent estimators matter here, but only within limits.

They secure, at best, the recovery of the long-run coefficient vector under integration. They do not by themselves secure the empirical reconstruction of $\mu_t$. That reconstruction still depends on:

- recovering a meaningful $\hat{\theta}_t$,
- translating the long-run relation into a productive-capacity path,
- and imposing a level normalization that pins the utilization index to a benchmark year.

So super-consistency belongs to the first step of the problem, not to the whole problem. It strengthens the identification of the transformation relation; it does not abolish the downstream reconstruction problem. :contentReference[oaicite:3]{index=3}

---

## 6. The pinch-year normalization

The remaining caveat is operational but indispensable.

Because the identifying closure works first in growth terms, level recovery requires one benchmark condition:

$$
\mu_{t_0} = 1
$$

at a pinch year interpreted as approximate full-capacity or frontier operation.

This normalization does not make $\mu_t$ residual. It performs a different task. It converts a structurally identified growth-side object into an empirical level series. The pinch-year rule is therefore a **level pin**, not a substitute for structural identification.

This distinction should remain explicit:

- structural identification gives the transformation logic,
- pinch-year normalization gives the level anchoring.

The normalization is necessary, but it does not do the analytical work that belongs to $\theta_t$.

---

## 7. Comparative empirical implication

The distinction applies in both country cases, though differently.

### U.S.

In the U.S., the long-run transformation relation is comparatively clean. Distribution enters through the interaction term, the transformation elasticity is recovered directly, and utilization is then reconstructed after normalization. The point is not that the U.S. case avoids reconstruction, but that the reconstruction is more linear.

### Chile

In Chile, the architecture is more recursive. The external-constraint problem, the role of capital composition, and the partition between crisis detection and long-run frontier estimation make the utilization reconstruction more mediated. But the same principle holds: utilization is not a free residual. It is recovered only after the transformation relation has been identified and normalized. :contentReference[oaicite:4]{index=4}

So the shared sentence is:

**In both cases, utilization is identified first in structural growth terms and only later converted into levels through a pinch-year normalization.**

---

## 8. Defense-facing statement

The dissertation should be able to defend the following proposition clearly:

**The identification of capacity utilization is endogenous to distribution because distribution mediates the transformation elasticity linking accumulation to productive-capacity growth. For that reason, utilization is not treated here as a residual left over after estimating output on capital. It is reconstructed as a structural object, with the sole remaining operational caveat that level recovery requires a pinch-year normalization.**

That is the version that should survive committee questioning.

---

## 9. Locked sentence for reuse

**Capacity utilization is not estimated here as a residual. It is reconstructed as a structural object: distribution mediates the transformation elasticity, the transformation elasticity identifies productive capacity, and utilization is then recovered relative to that capacity under an explicit pinch-year normalization.**