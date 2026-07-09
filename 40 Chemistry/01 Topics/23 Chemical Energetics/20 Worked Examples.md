---
title: 23 Chemical Energetics - Worked Examples
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/a-level
  - chemistry/9701/physical-chemistry
---

# 23 Chemical Energetics - Worked Examples

## Example 1: Born-Haber Cycle For Sodium Chloride

Data for $\ce{NaCl(s)}$, in $\text{kJ mol}^{-1}$:

| Quantity | Value |
|---|---:|
| $\Delta H^\circ_{\text{f}}(\ce{NaCl})$ | -411 |
| $\Delta H^\circ_{\text{at}}(\ce{Na})$ | +108 |
| $\Delta H^\circ_{\text{at}}(\ce{Cl})$ | +122 |
| $\text{IE}_1(\ce{Na})$ | +496 |
| $\text{EA}_1(\ce{Cl})$ | -349 |

Find $\Delta H^\circ_{\text{latt}}$ for:

$$
\ce{Na+(g) + Cl-(g) -> NaCl(s)}
$$

Using the syllabus lattice-energy convention:

$$
-411 = 108 + 122 + 496 - 349 + \Delta H^\circ_{\text{latt}}
$$

$$
\Delta H^\circ_{\text{latt}} = -411 - 377 = -788\ \text{kJ mol}^{-1}
$$

Check: the answer is negative because gaseous ions form an ionic lattice.

## Example 2: Born-Haber Cycle With 2+ And 2- Ions

Data for $\ce{MgO(s)}$, in $\text{kJ mol}^{-1}$:

| Quantity | Value |
|---|---:|
| $\Delta H^\circ_{\text{f}}(\ce{MgO})$ | -602 |
| $\Delta H^\circ_{\text{at}}(\ce{Mg})$ | +148 |
| $\Delta H^\circ_{\text{at}}(\ce{O})$ from $\ce{1/2O2(g)}$ | +249 |
| $\text{IE}_1(\ce{Mg}) + \text{IE}_2(\ce{Mg})$ | +2187 |
| $\text{EA}_1(\ce{O})$ | -141 |
| $\text{EA}_2(\ce{O})$ | +744 |

Find $\Delta H^\circ_{\text{latt}}$ for:

$$
\ce{Mg^{2+}(g) + O^{2-}(g) -> MgO(s)}
$$

Set up the formation route:

$$
-602 = 148 + 249 + 2187 - 141 + 744 + \Delta H^\circ_{\text{latt}}
$$

The non-lattice sum is:

$$
148 + 249 + 2187 - 141 + 744 = 3187
$$

Therefore:

$$
\Delta H^\circ_{\text{latt}} = -602 - 3187 = -3789\ \text{kJ mol}^{-1}
$$

Check: this has a much larger magnitude than $\ce{NaCl}$ because $\ce{Mg^{2+}}$ and $\ce{O^{2-}}$ have higher charges.

## Example 3: Solution And Hydration Cycle

For $\ce{KCl(s)}$:

| Quantity | Value / $\text{kJ mol}^{-1}$ |
|---|---:|
| $\Delta H^\circ_{\text{latt}}(\ce{KCl})$ | -715 |
| $\Delta H^\circ_{\text{hyd}}(\ce{K+})$ | -322 |
| $\Delta H^\circ_{\text{hyd}}(\ce{Cl-})$ | -364 |

Find $\Delta H^\circ_{\text{sol}}$ for:

$$
\ce{KCl(s) -> K+(aq) + Cl-(aq)}
$$

Use:

$$
\Delta H^\circ_{\text{sol}}
= -\Delta H^\circ_{\text{latt}}
+ \Delta H^\circ_{\text{hyd}}(\ce{K+})
+ \Delta H^\circ_{\text{hyd}}(\ce{Cl-})
$$

$$
\Delta H^\circ_{\text{sol}} = +715 - 322 - 364 = +29\ \text{kJ mol}^{-1}
$$

Check: dissolving is slightly endothermic by enthalpy, but this alone does not decide solubility.

## Example 4: Explaining Lattice And Hydration Trends

Predict which has the larger numerical magnitude lattice energy, $\ce{NaF}$ or $\ce{MgO}$.

Both are ionic solids, but $\ce{MgO}$ contains $\ce{Mg^{2+}}$ and $\ce{O^{2-}}$, while $\ce{NaF}$ contains $\ce{Na+}$ and $\ce{F-}$. The higher charges in $\ce{MgO}$ produce much stronger electrostatic attraction. $\ce{Mg^{2+}}$ and $\ce{O^{2-}}$ also have high charge density. Therefore $\ce{MgO}$ has the larger numerical magnitude lattice energy.

The same charge-density idea explains hydration enthalpy. $\ce{Mg^{2+}}$ has a more exothermic hydration enthalpy than $\ce{Na+}$ because its higher charge and smaller radius attract water molecules more strongly.

## Example 5: Entropy Change From Standard Entropies

Use the data below to calculate $\Delta S^\circ$ for:

$$
\ce{N2(g) + 3H2(g) -> 2NH3(g)}
$$

| Species | $S^\circ$ / $\text{J mol}^{-1}\text{ K}^{-1}$ |
|---|---:|
| $\ce{N2(g)}$ | 192 |
| $\ce{H2(g)}$ | 131 |
| $\ce{NH3(g)}$ | 193 |

$$
\Delta S^\circ = 2(193) - [192 + 3(131)]
$$

$$
\Delta S^\circ = 386 - 585 = -199\ \text{J mol}^{-1}\text{ K}^{-1}
$$

Check: four moles of gas form two moles of gas, so a negative entropy change is reasonable.

## Example 6: Gibbs Free Energy And Temperature

For:

$$
\ce{CaCO3(s) -> CaO(s) + CO2(g)}
$$

take $\Delta H^\circ = +178\ \text{kJ mol}^{-1}$ and $\Delta S^\circ = +161\ \text{J mol}^{-1}\text{ K}^{-1}$.

At $298\ \text{K}$:

$$
\Delta S^\circ = 0.161\ \text{kJ mol}^{-1}\text{ K}^{-1}
$$

$$
\Delta G^\circ = 178 - 298(0.161) = +130\ \text{kJ mol}^{-1}
$$

The process is not feasible under standard conditions at $298\ \text{K}$.

At the approximate temperature where feasibility changes, set $\Delta G^\circ = 0$:

$$
T = \frac{\Delta H^\circ}{\Delta S^\circ}
= \frac{178}{0.161}
= 1.11 \times 10^3\ \text{K}
$$

Because both $\Delta H^\circ$ and $\Delta S^\circ$ are positive, high temperature makes the process more feasible.
