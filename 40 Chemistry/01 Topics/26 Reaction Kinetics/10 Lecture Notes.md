---
title: 26 Reaction Kinetics - Lecture Notes
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/a-level
  - chemistry/9701/physical-chemistry
---

# 26 Reaction Kinetics - Lecture Notes

## Source Route

These notes follow the CAIE Chemistry 9701 syllabus for 2025-2027, A Level subject content, sections 26.1-26.2: simple rate equations, orders of reaction, rate constants, half-life, mechanisms, rate-determining step, intermediates, temperature effects, and homogeneous and heterogeneous catalysts. No Chemistry coursebook alignment is claimed.

## Learning Scope

A Level kinetics uses experimental data to write rate equations and test mechanisms. You need to deduce orders from initial rates, graphs, and half-life data; calculate rate constants and their units; connect a rate equation to a possible rate-determining step; and explain how catalysts work in homogeneous and heterogeneous systems.

## Rate Equations And Orders

A rate equation shows how rate depends on the concentrations of reactants. For two reactants:

$$
\text{rate} = k[\ce{A}]^m[\ce{B}]^n
$$

where $k$ is the rate constant, $m$ is the order with respect to $\ce{A}$, and $n$ is the order with respect to $\ce{B}$. In the syllabus form, $m$ and $n$ may be 0, 1, or 2. The overall order is $m+n$.

Orders are found from experimental data, not from the coefficients in the overall chemical equation.

Meaning of common orders:

| Order | Effect of doubling concentration | Graph of rate against concentration |
|---:|---|---|
| 0 | Rate unchanged | Horizontal line |
| 1 | Rate doubles | Straight line through origin |
| 2 | Rate quadruples | Upward curve |

The rate constant depends on temperature. Its units depend on the overall order because the rate normally has units $\text{mol dm}^{-3}\text{ s}^{-1}$.

Examples:

| Overall order | Example rate equation | Units of $k$ |
|---:|---|---|
| 0 | $\text{rate}=k$ | $\text{mol dm}^{-3}\text{ s}^{-1}$ |
| 1 | $\text{rate}=k[\ce{A}]$ | $\text{s}^{-1}$ |
| 2 | $\text{rate}=k[\ce{A}][\ce{B}]$ | $\text{dm}^3\text{ mol}^{-1}\text{ s}^{-1}$ |
| 3 | $\text{rate}=k[\ce{A}]^2[\ce{B}]$ | $\text{dm}^6\text{ mol}^{-2}\text{ s}^{-1}$ |

## Deducing Orders From Initial Rates

The initial rates method compares experiments where one concentration changes and the others are kept constant. If changing $[\ce{A}]$ by a factor of 2 changes rate by a factor of 4, the order with respect to $\ce{A}$ is 2 because $2^2=4$.

General comparison:

$$
\frac{\text{rate}_2}{\text{rate}_1}
= \left(\frac{[\ce{A}]_2}{[\ce{A}]_1}\right)^m
$$

when all other concentrations are constant.

## Graphs And Initial Rates

For concentration-time data, the rate at a time is the gradient of the tangent to the concentration-time graph. Because reactant concentration decreases, the gradient is negative, but rate is reported as a positive value:

$$
\text{rate} = -\frac{\Delta[\text{reactant}]}{\Delta t}
$$

For rate-concentration graphs:

- zero order gives a horizontal line
- first order gives a straight line through the origin
- second order gives a curve whose gradient increases with concentration

## Half-Life

Half-life, $t_{1/2}$, is the time taken for the concentration of a reactant to fall to half its value.

For a first-order reaction, half-life is independent of concentration. This is a key diagnostic. If a concentration-time table shows equal half-lives as concentration halves repeatedly, the reaction is first order with respect to that reactant.

For a first-order reaction:

$$
k = \frac{0.693}{t_{1/2}}
$$

with $k$ in $\text{s}^{-1}$ if $t_{1/2}$ is in seconds.

## Mechanisms And Rate-Determining Step

A reaction mechanism is a sequence of elementary steps that add together to give the overall reaction. The **rate-determining step** is the slowest step. An **intermediate** is formed in one step and used up in a later step; it does not appear in the overall equation. A **catalyst** is used in one step and regenerated in a later step.

For a proposed mechanism, check:

1. The steps add to the overall reaction.
2. The slow step is consistent with the rate equation.
3. Intermediates cancel from the overall equation.
4. Catalysts are regenerated.

If the slow step is:

$$
\ce{A + B -> P}
$$

then the rate equation suggested by that elementary slow step is:

$$
\text{rate} = k[\ce{A}][\ce{B}]
$$

If the observed rate equation is different from the stoichiometric equation, that is evidence that the overall reaction does not occur in one elementary step.

## Temperature And Rate Constant

Increasing temperature increases the rate constant and therefore increases rate when concentrations are unchanged. More particles have energy equal to or greater than the activation energy, so successful collisions are more frequent. A higher temperature changes $k$, not the reaction order.

## Catalysts

A catalyst increases the rate of a reaction by providing an alternative route with lower activation energy. It is regenerated and is not used up overall.

A **heterogeneous catalyst** is in a different phase from the reactants. Its mode of action includes adsorption of reactants onto the surface, weakening of bonds, reaction on the surface, and desorption of products.

Examples:

- iron in the Haber process:

$$
\ce{N2(g) + 3H2(g) <=> 2NH3(g)}
$$

- palladium, platinum, and rhodium in catalytic converters, for example:

$$
\ce{2NO(g) + 2CO(g) -> N2(g) + 2CO2(g)}
$$

A **homogeneous catalyst** is in the same phase as the reactants. It is used in one step and reformed in a later step.

Atmospheric oxides of nitrogen can catalyse oxidation of sulfur dioxide. A simplified cycle is:

$$
\ce{SO2(g) + NO2(g) -> SO3(g) + NO(g)}
$$

$$
\ce{2NO(g) + O2(g) -> 2NO2(g)}
$$

Iron(II) and iron(III) ions can catalyse the reaction between iodide ions and peroxodisulfate ions:

$$
\ce{S2O8^{2-}(aq) + 2I-(aq) -> 2SO4^{2-}(aq) + I2(aq)}
$$

through steps involving $\ce{Fe^{2+}}$ and $\ce{Fe^{3+}}$ being interconverted.

## Working Routine

1. Let data decide the rate equation.
2. Compare experiments where only one concentration changes.
3. Calculate $k$ from the rate equation after orders are known.
4. Derive units of $k$ by rearranging the rate equation.
5. Use equal half-lives as evidence for first-order behaviour.
6. For mechanisms, add the steps and check the slow step against the rate equation.
7. Separate thermodynamic feasibility from kinetic speed.

## Common Mistakes

- Copying stoichiometric coefficients into the rate equation without evidence.
- Comparing two initial-rate experiments where more than one concentration changes.
- Giving units for $k$ before finding the overall order.
- Treating half-life as concentration-independent for every reaction.
- Calling an intermediate a catalyst when it is not regenerated.
- Saying a catalyst changes the equilibrium yield; it changes rate, not the equilibrium position.

## Connections

- [[40 Chemistry/01 Topics/08 Reaction Kinetics/00 Overview|AS Reaction Kinetics]]
- [[40 Chemistry/01 Topics/25 Equilibria/00 Overview|A Level Equilibria]]
- [[40 Chemistry/01 Topics/23 Chemical Energetics/00 Overview|A Level Chemical Energetics]]