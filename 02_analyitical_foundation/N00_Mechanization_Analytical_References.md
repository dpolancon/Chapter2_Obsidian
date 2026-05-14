---
type: note
status: active
layer: analytical_foundation
design_role: reference_map
scope: chapter2_core_support
related_to:
  - H01_Cajas_to_Transformation_Elasticity
created: 2026-05-05
---

# Mechanization analytical foundations — reference map

## Core claim

The mechanization problem used in this framework is grounded in a Marxian reinterpretation of induced innovation, where firms choose the rate of mechanization to reduce costs under technological and distributive constraints.

This note maps the intellectual sources that support that formulation.

It does **not** perform derivations or define analytical objects.

---

## 1. Structural role in the architecture

This note provides:

- intellectual genealogy of the mechanization problem  
- theoretical justification for modeling technical change as a choice  
- traceability across sources used in Chapter 2  

This note does not:

- derive \( q^*(\omega) \)  
- define \( \theta \)  
- perform transformations  

All analytical operations occur in:

- H01_Cajas_to_Transformation_Elasticity  
- N01_Two_Corridor_Transformation_Elasticity  
- N02_Peripheral_Mechanization_Constraint  

---

## 2. Core mechanization foundation

- Cajas Guajirro, J. (2024)  
  *An extended Goodwin model with endogenous technical change and labor supply*  
  https://doi.org/10.1016/j.strueco.2024.03.006  

**Role:**

- Micro-foundation of mechanization as an optimization problem  
- Mechanization is chosen, not given  
- Productivity depends nonlinearly on mechanization  

**Function in this framework:**

Provides the conceptual basis for treating technical change as:

> a choice over the rate of mechanization under distributive conditions

Used in:

- H01_Cajas_to_Transformation_Elasticity

---

## 3. Marxian foundation

- Marx, K. (1867) *Capital, Vol. I*  
  https://www.marxists.org/archive/marx/works/1867-c1/  

- Marx, K. (1885) *Capital, Vol. II*  
  https://www.marxists.org/archive/marx/works/1885-c2/  

- Sweezy, P. (1964) *The Theory of Capitalist Development*  
  https://monthlyreview.org/product/the_theory_of_capitalist_development/  

**Role:**

- Mechanization as response to wage pressure  
- Mechanization as labor-disciplining device  
- Accumulation drives technical change  
- Technical change reshapes class relations  

**Function in this framework:**

Grounds the mechanism:

$$
\omega \rightarrow q \rightarrow a
$$

Used in:

- H01 (mechanization logic)
- R01 (interpretation)

---

## 4. Induced innovation tradition

- Kennedy, C. (1964)  
  https://www.jstor.org/stable/2295860  

- Shah, A., & Desai, M. (1981)  
  https://doi.org/10.1016/0165-1889(81)90018-2  

- Duménil, G., & Lévy, D. (1995)  
  https://www.jstor.org/stable/2359958  

- Duménil, G., & Lévy, D. (2003)  
  https://doi.org/10.1016/S0954-349X(02)00030-4  

**Role:**

- Technical change as cost-minimizing choice  
- Optimization under technological frontier  

**Limitation:**

- Focus on capital productivity  
- Do not isolate mechanization \(q\)

**Function in this framework:**

Serves as background tradition from which the mechanization problem is extracted.

---

## 5. Kaldor — productivity and periphery

- Kaldor, N. (1957)  
  https://www.jstor.org/stable/2227704  

- Kaldor, N. (1959) (Chile context)  

**Role:**

- Productivity linked to capital deepening  
- Investment depends on structural conditions  
- Capital goods often externally constrained  

**Function in this framework:**

Supports:

$$
a = f(q)
$$

and motivates the peripheral extension where mechanization depends on imported machinery.

Used in:

- N02_Peripheral_Mechanization_Constraint

---

## 6. Basu — closure and reproduction

- Basu, D. (2022) — reproduction schemas  
- Basu, D. (2024)  
  https://doi.org/10.1093/cje/beae010  

**Role:**

- Defines normal profitability and accumulation  
- Provides closure conditions:

  - strong labor  
  - weak labor  
  - labor surplus  

**Function in this framework:**

Anchors the normal accumulation corridor:

$$
r^N,\quad \chi^N,\quad g_K^N
$$

Used in:

- N01
- R01
- R02

---

## 7. Marx–Okishio literature

- Okishio, N. (1961)  
  https://www.jstor.org/stable/4224337  

- Morishima, M. (1973)  
  https://doi.org/10.1017/CBO9780511559995  

- Foley, D. (1986)  
  https://www.hup.harvard.edu/books/9780674923299  

- Roemer, J. (1981)  
  https://doi.org/10.1017/CBO9780511558615  

**Role:**

- Formal theorem on profitability and technical change  

**Function in this framework:**

Reinterpreted as:

> closure-dependent mechanism rather than universal law

Used in:

- R01_Marx_Okishio_Regime_Diagnostic_Guardrail

---

## 8. Regulationist tradition

- Aglietta, M. (1979)  
  https://www.versobooks.com/products/2223-a-theory-of-capitalist-regulation  

- Boyer, R. (1990)  
  https://doi.org/10.7312/boye91738  

**Role:**

- Fordism vs post-Fordism  
- Institutional wage stabilization  
- Regime-dependent dynamics  

**Function in this framework:**

Supports regime interpretation of:

$$
\beta_2
$$

Used in:

- R01
- R02

---

## 9. Peripheral constraint literature

- Prebisch, R. (1950)  
  https://repositorio.cepal.org/handle/11362/29973  

- Thirlwall, A. (1979)  
  https://www.jstor.org/stable/2231793  

**Role:**

- External constraint on accumulation  
- Import dependence of capital goods  

**Function in this framework:**

Justifies the external mechanization wedge in the periphery.

Used in:

- N02
- R02

---

## Locked rule

This note is a reference map.

It must not:

- derive equations  
- define analytical objects  
- perform transformations  

All analytical content must remain in:

- N-notes (objects)  
- H-notes (transformations)  
- R-notes (rules)

---

## 10. Equation–reference support map

This section maps each key analytical component to the references that justify it.

Its purpose is to make explicit:

> which theoretical sources support each equation used in the analytical framework

---

### 10.1 Mechanization–productivity frontier

$$
a(q)=\lambda_0+\lambda_1 q+\lambda_2 q^2,\qquad \lambda_2<0
$$

**Supported by:**

- Kaldor (1957) → productivity as function of capital deepening  
- Cajas (2024) → nonlinear productivity effects of mechanization  
- Marx (Vol. I) → productivity gains from machinery  

**Interpretation:**

- mechanization raises productivity  
- effects are nonlinear and bounded  

---

### 10.2 Mechanization optimization problem

$$
\min_q \left[(1-\omega)q - a(q)\right]
$$

**Supported by:**

- Cajas (2024) → cost-minimizing mechanization choice  
- Kennedy (1964), Duménil & Lévy → induced innovation  

**Interpretation:**

- technical change is a choice  
- distribution enters as a cost condition  

---

### 10.3 Optimal mechanization response

$$
q^*(\omega)
$$

**Supported by:**

- Cajas (2024) → mechanization increases with wage pressure  
- Marx → mechanization as response to rising wages  

**Interpretation:**

$$
\omega \uparrow \Rightarrow q^* \uparrow \quad (\text{locally})
$$

---

### 10.4 Derived productivity–mechanization balance

$$
b = a - q
$$

**Supported by:**

- Accounting identity:  
$$
\frac{Y}{K} = \frac{Y/L}{K/L}
$$

- Kaldor → productivity linked to capital deepening  

**Interpretation:**

- capital productivity is not autonomous  
- reflects balance between labor productivity and mechanization  

---

### 10.5 Normal accumulation corridor

$$
g_K^N = \chi^N r^N - \delta
$$

$$
r^N = B^N (1-\omega)
$$

**Supported by:**

- Basu (2022, 2024) → reproduction schemas  
- Marx (Vol. II) → capital circuit  

**Interpretation:**

- accumulation depends on profitability and recapitalization  
- not mechanically tied to savings  

---

### 10.6 Transformation elasticity

$$
\theta^N = 1 + \frac{a - q}{g_K^N}
$$

**Supported by:**

- This framework (synthesis)  
- Basu → reproduction benchmark  
- Kaldor → productivity–capital link  

**Interpretation:**

- measures capacity payoff of accumulation  
- depends on two corridors  

---

### 10.7 Empirical reduced form

$$
\theta(\omega) = \beta_1 + \beta_2 \omega
$$

**Supported by:**

- Mapping from structural model  
- Cointegration framework (Chapter 2 econometrics)  

**Interpretation:**

- \(\beta_2\) captures distributive conditioning  
- reduced-form summary of both corridors  

---

### 10.8 Peripheral mechanization constraint

$$
m^P = (1-\omega) + \Lambda \varphi
$$

$$
q^{P,*} = f(\omega, \Lambda \varphi)
$$

**Supported by:**

- Kaldor (Chile) → import dependence of capital goods  
- Prebisch → structural external constraint  
- Thirlwall → balance-of-payments constraint  

**Interpretation:**

- mechanization depends on foreign exchange  
- accumulation ≠ mechanization in the periphery  

---

### 10.9 Threshold regime structure

$$
\theta =
\begin{cases}
\theta_L, & s \leq \gamma \\
\theta_H, & s > \gamma
\end{cases}
$$

**Supported by:**

- Basu → closure-dependent outcomes  
- Regulation theory → regime shifts  

**Interpretation:**

- transformation elasticity is not globally stable  
- regimes define corridor dominance  

---

## Locked interpretation

Each equation in the analytical framework is supported by a specific theoretical tradition.

The framework is therefore:

- not ad hoc  
- not purely empirical  
- structurally grounded in multiple strands of political economy  

This section ensures traceability between:

> equations → mechanisms → theoretical sources