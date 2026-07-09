---
title: "Chemical Energetics - Worked Examples"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/as-level
  - chemistry/9701/physical-chemistry
---

# Chemical Energetics - Worked Examples

## Example 1: Calorimetry For Neutralisation

**Question.** $25.0\ \mathrm{cm^3}$ of $1.00\ \mathrm{mol\,dm^{-3}}$ hydrochloric acid is mixed with $25.0\ \mathrm{cm^3}$ of $1.00\ \mathrm{mol\,dm^{-3}}$ sodium hydroxide. The temperature rises by $6.8\ ^\circ\mathrm{C}$. Assume the density of the final solution is $1.00\ \mathrm{g\,cm^{-3}}$ and $c = 4.18\ \mathrm{J\,g^{-1}\,K^{-1}}$. Calculate $\Delta H_{neut}$.

The ionic reaction is:

$$
\ce{H+(aq) + OH-(aq) -> H2O(l)}
$$

**Working.**

Total volume of solution:

$$
25.0 + 25.0 = 50.0\ \mathrm{cm^3}
$$

Mass of solution:

$$
m = 50.0\ \mathrm{g}
$$

Heat gained by solution:

$$
q = mc\Delta T = 50.0 \times 4.18 \times 6.8 = 1421.2\ \mathrm{J}
$$

Amount of acid and alkali:

$$
n = \frac{25.0}{1000} \times 1.00 = 0.0250\ \mathrm{mol}
$$

The acid and alkali react in a 1:1 ratio, so $0.0250\ \mathrm{mol}$ of water is formed.

$$
\Delta H_{neut} = -\frac{1421.2}{0.0250} = -56848\ \mathrm{J\,mol^{-1}}
$$

$$
\Delta H_{neut} = -56.8\ \mathrm{kJ\,mol^{-1}}
$$

**Check.** The temperature rises, so the reaction is exothermic. A negative value is correct.

## Example 2: Bond Energy Estimate

**Question.** Estimate the enthalpy change for:

$$
\ce{H2(g) + Cl2(g) -> 2HCl(g)}
$$

Use bond energies: $\ce{H-H} = 436\ \mathrm{kJ\,mol^{-1}}$, $\ce{Cl-Cl} = 243\ \mathrm{kJ\,mol^{-1}}$, $\ce{H-Cl} = 431\ \mathrm{kJ\,mol^{-1}}$.

**Working.**

Bonds broken:

$$
1(\ce{H-H}) + 1(\ce{Cl-Cl}) = 436 + 243 = 679\ \mathrm{kJ\,mol^{-1}}
$$

Bonds made:

$$
2(\ce{H-Cl}) = 2 \times 431 = 862\ \mathrm{kJ\,mol^{-1}}
$$

$$
\Delta H_r = \text{bonds broken} - \text{bonds made}
$$

$$
\Delta H_r = 679 - 862 = -183\ \mathrm{kJ\,mol^{-1}}
$$

**Check.** More energy is released in making $\ce{H-Cl}$ bonds than is absorbed in breaking reactant bonds, so the sign is negative.

## Example 3: Hess's Law With Formation Enthalpies

**Question.** Calculate $\Delta H_r^\ominus$ for:

$$
\ce{CH4(g) + 2O2(g) -> CO2(g) + 2H2O(l)}
$$

Use $\Delta H_f^\ominus(\ce{CH4(g)}) = -75\ \mathrm{kJ\,mol^{-1}}$, $\Delta H_f^\ominus(\ce{CO2(g)}) = -394\ \mathrm{kJ\,mol^{-1}}$, and $\Delta H_f^\ominus(\ce{H2O(l)}) = -286\ \mathrm{kJ\,mol^{-1}}$.

**Working.**

The standard enthalpy change of formation of $\ce{O2(g)}$ is zero because oxygen gas is an element in its standard state.

$$
\Delta H_r^\ominus = \sum \Delta H_f^\ominus(\text{products}) - \sum \Delta H_f^\ominus(\text{reactants})
$$

Products:

$$
(-394) + 2(-286) = -966\ \mathrm{kJ\,mol^{-1}}
$$

Reactants:

$$
(-75) + 2(0) = -75\ \mathrm{kJ\,mol^{-1}}
$$

$$
\Delta H_r^\ominus = -966 - (-75) = -891\ \mathrm{kJ\,mol^{-1}}
$$

**Check.** Methane combustion is exothermic, so a large negative value is sensible.

## Example 4: Hess's Law With Combustion Enthalpies

**Question.** Calculate $\Delta H_r^\ominus$ for:

$$
\ce{C2H4(g) + H2(g) -> C2H6(g)}
$$

Use $\Delta H_c^\ominus(\ce{C2H4(g)}) = -1411\ \mathrm{kJ\,mol^{-1}}$, $\Delta H_c^\ominus(\ce{H2(g)}) = -286\ \mathrm{kJ\,mol^{-1}}$, and $\Delta H_c^\ominus(\ce{C2H6(g)}) = -1560\ \mathrm{kJ\,mol^{-1}}$.

**Working.**

All substances can be combusted to the same products, $\ce{CO2(g)}$ and $\ce{H2O(l)}$. Using combustion data:

$$
\Delta H_r^\ominus = \sum \Delta H_c^\ominus(\text{reactants}) - \sum \Delta H_c^\ominus(\text{products})
$$

Reactants:

$$
(-1411) + (-286) = -1697\ \mathrm{kJ\,mol^{-1}}
$$

Products:

$$
-1560\ \mathrm{kJ\,mol^{-1}}
$$

$$
\Delta H_r^\ominus = -1697 - (-1560) = -137\ \mathrm{kJ\,mol^{-1}}
$$

**Check.** The answer is negative, so hydrogenation is exothermic. The value is much smaller in magnitude than combustion because the reaction is not complete oxidation.

## Example 5: Interpreting An Energy Profile

**Question.** A reaction pathway diagram shows reactants at $120\ \mathrm{kJ\,mol^{-1}}$, products at $45\ \mathrm{kJ\,mol^{-1}}$, and the peak at $210\ \mathrm{kJ\,mol^{-1}}$. Find $\Delta H$ and $E_A$.

**Working.**

Enthalpy change:

$$
\Delta H = H_\text{products} - H_\text{reactants}
$$

$$
\Delta H = 45 - 120 = -75\ \mathrm{kJ\,mol^{-1}}
$$

Activation energy:

$$
E_A = H_\text{peak} - H_\text{reactants}
$$

$$
E_A = 210 - 120 = 90\ \mathrm{kJ\,mol^{-1}}
$$

**Check.** Products are lower than reactants, so the reaction is exothermic and $\Delta H$ is negative. The activation energy is positive.
