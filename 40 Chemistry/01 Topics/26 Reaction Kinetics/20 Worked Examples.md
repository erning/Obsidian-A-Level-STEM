---
title: 26 Reaction Kinetics - Worked Examples
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/a-level
  - chemistry/9701/physical-chemistry
---

# 26 Reaction Kinetics - Worked Examples

## Example 1: Deducing A Rate Equation From Initial Rates

For a reaction involving $\ce{A}$ and $\ce{B}$:

| Experiment | $[\ce{A}]$ / $\text{mol dm}^{-3}$ | $[\ce{B}]$ / $\text{mol dm}^{-3}$ | Initial rate / $\text{mol dm}^{-3}\text{ s}^{-1}$ |
|---:|---:|---:|---:|
| 1 | 0.100 | 0.100 | $2.00 \times 10^{-4}$ |
| 2 | 0.200 | 0.100 | $8.00 \times 10^{-4}$ |
| 3 | 0.100 | 0.200 | $4.00 \times 10^{-4}$ |

Compare experiments 1 and 2. $[\ce{A}]$ doubles while $[\ce{B}]$ stays constant. Rate increases by a factor of 4, so the order with respect to $\ce{A}$ is 2.

Compare experiments 1 and 3. $[\ce{B}]$ doubles while $[\ce{A}]$ stays constant. Rate doubles, so the order with respect to $\ce{B}$ is 1.

Therefore:

$$
\text{rate} = k[\ce{A}]^2[\ce{B}]
$$

The overall order is 3.

## Example 2: Calculating A Rate Constant And Its Units

Use experiment 1 from Example 1:

$$
2.00 \times 10^{-4} = k(0.100)^2(0.100)
$$

$$
k = \frac{2.00 \times 10^{-4}}{1.00 \times 10^{-3}}
= 0.200
$$

For a third-order rate equation:

$$
k = \frac{\text{mol dm}^{-3}\text{ s}^{-1}}{(\text{mol dm}^{-3})^3}
$$

$$
k = 0.200\ \text{dm}^6\text{ mol}^{-2}\text{ s}^{-1}
$$

## Example 3: Initial Rate From A Tangent

A tangent to a concentration-time graph for reactant $\ce{X}$ passes through $(0\ \text{s}, 0.100\ \text{mol dm}^{-3})$ and $(40\ \text{s}, 0.060\ \text{mol dm}^{-3})$.

Gradient:

$$
\frac{\Delta[\ce{X}]}{\Delta t}
= \frac{0.060 - 0.100}{40 - 0}
= -1.00 \times 10^{-3}\ \text{mol dm}^{-3}\text{ s}^{-1}
$$

The rate is positive:

$$
\text{initial rate} = 1.00 \times 10^{-3}\ \text{mol dm}^{-3}\text{ s}^{-1}
$$

## Example 4: First-Order Half-Life

The concentration of $\ce{R}$ changes as follows:

| Time / s | $[\ce{R}]$ / $\text{mol dm}^{-3}$ |
|---:|---:|
| 0 | 0.800 |
| 50 | 0.400 |
| 100 | 0.200 |
| 150 | 0.100 |

The concentration halves every $50\ \text{s}$, so the reaction is first order with respect to $\ce{R}$.

$$
k = \frac{0.693}{t_{1/2}}
= \frac{0.693}{50}
= 1.39 \times 10^{-2}\ \text{s}^{-1}
$$

After three half-lives, the concentration is $0.800/2^3 = 0.100\ \text{mol dm}^{-3}$, matching the data.

## Example 5: Mechanism And Rate-Determining Step

The reaction:

$$
\ce{NO2(g) + CO(g) -> NO(g) + CO2(g)}
$$

has the proposed mechanism:

Step 1, slow:

$$
\ce{NO2(g) + NO2(g) -> NO3(g) + NO(g)}
$$

Step 2, fast:

$$
\ce{NO3(g) + CO(g) -> NO2(g) + CO2(g)}
$$

Adding the two steps cancels $\ce{NO3}$ and one $\ce{NO2}$, giving the overall equation.

The slow step contains two $\ce{NO2}$ particles, so the predicted rate equation is:

$$
\text{rate} = k[\ce{NO2}]^2
$$

$\ce{NO3}$ is an intermediate because it is formed then consumed. $\ce{NO2}$ is not a catalyst overall because one mole of $\ce{NO2}$ is consumed in the net reaction.

## Example 6: Identifying A Homogeneous Catalyst

The reaction between iodide and peroxodisulfate ions is:

$$
\ce{S2O8^{2-}(aq) + 2I-(aq) -> 2SO4^{2-}(aq) + I2(aq)}
$$

It can be catalysed by $\ce{Fe^{2+}}/\ce{Fe^{3+}}$:

$$
\ce{S2O8^{2-}(aq) + 2Fe^{2+}(aq) -> 2SO4^{2-}(aq) + 2Fe^{3+}(aq)}
$$

$$
\ce{2Fe^{3+}(aq) + 2I-(aq) -> 2Fe^{2+}(aq) + I2(aq)}
$$

Adding the steps cancels $\ce{Fe^{2+}}$ and $\ce{Fe^{3+}}$, giving the overall reaction. The iron ions act as a homogeneous catalyst because they are in aqueous solution with the reactants and are regenerated overall.

## Example 7: Explaining Heterogeneous Catalysis

In the Haber process:

$$
\ce{N2(g) + 3H2(g) <=> 2NH3(g)}
$$

iron is a heterogeneous catalyst. Nitrogen and hydrogen molecules adsorb onto the iron surface. Adsorption weakens bonds within the molecules and holds reactants close together in a suitable orientation. New bonds form on the surface, then ammonia desorbs. The iron provides an alternative route with lower activation energy and is not consumed.
