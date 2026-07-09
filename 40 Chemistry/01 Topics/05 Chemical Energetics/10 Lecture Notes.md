---
title: "Chemical Energetics - Lecture Notes"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/as-level
  - chemistry/9701/physical-chemistry
---

# Chemical Energetics - Lecture Notes

## Source Route

These notes follow CAIE Chemistry 9701 AS Level Physical chemistry, Topic 5, Chemical energetics: 5.1 Enthalpy change, $\Delta H$, and 5.2 Hess's law. No coursebook alignment is claimed.

## Why Enthalpy Is Useful

Chemical reactions involve energy transfer. At constant pressure, the heat energy change is described as an enthalpy change, $\Delta H$. The unit is usually $\mathrm{kJ\,mol^{-1}}$, because an enthalpy change is attached to the amount represented by a balanced chemical equation.

For example, if a reaction equation is written for one mole of a fuel, the enthalpy change is the energy change per mole of that fuel reacting as shown. If the equation is doubled, the enthalpy change is doubled. If the equation is reversed, the sign of the enthalpy change is reversed.

The sign convention is essential:

| Type of reaction | Energy transfer | Relative enthalpy of products | Sign of $\Delta H$ |
|---|---|---|---|
| Exothermic | Energy is released to the surroundings | Lower than reactants | Negative |
| Endothermic | Energy is absorbed from the surroundings | Higher than reactants | Positive |

For an exothermic reaction such as combustion, the reacting chemicals lose enthalpy overall. The surroundings gain energy, often seen as a temperature rise. For an endothermic reaction, the reacting chemicals gain enthalpy overall, and the surroundings may cool.

## Reaction Pathway Diagrams

A reaction pathway diagram shows enthalpy on the vertical axis and progress of reaction on the horizontal axis. The vertical gap between reactants and products is $\Delta H$. The rise from reactants to the top of the curve is the activation energy, $E_A$.

$E_A$ is not the same as $\Delta H$. Activation energy is the minimum energy needed for reactant particles to reach the transition state and react. Enthalpy change is the difference between products and reactants after the reaction has occurred.

For an exothermic reaction:

- products are below reactants;
- $\Delta H$ is negative;
- the activation energy is still positive because the reaction must pass through a higher-energy transition state.

For an endothermic reaction:

- products are above reactants;
- $\Delta H$ is positive;
- the activation energy is measured from reactants to the top of the pathway.

When a catalyst is involved, the pathway has a lower activation energy because the reaction follows a different mechanism. The catalyst does not change $\Delta H$, because the reactants and products are the same.

## Standard Conditions And Enthalpy Terms

The syllabus uses standard conditions of 298 K and 101 kPa, shown by the symbol $^\ominus$. A standard enthalpy change is measured or quoted when all substances are in their standard states under these conditions.

Several enthalpy terms appear often at AS level.

The standard enthalpy change of reaction, $\Delta H_r^\ominus$, is the enthalpy change when the molar quantities shown in the equation react under standard conditions.

The standard enthalpy change of formation, $\Delta H_f^\ominus$, is the enthalpy change when one mole of a compound is formed from its elements in their standard states under standard conditions. For example:

$$
\ce{C(s, graphite) + O2(g) -> CO2(g)}
$$

This equation represents formation of one mole of $\ce{CO2(g)}$. By definition, the standard enthalpy change of formation of an element in its standard state is zero.

The standard enthalpy change of combustion, $\Delta H_c^\ominus$, is the enthalpy change when one mole of a substance is completely burned in oxygen under standard conditions. For methane:

$$
\ce{CH4(g) + 2O2(g) -> CO2(g) + 2H2O(l)}
$$

The standard enthalpy change of neutralisation, $\Delta H_{neut}^\ominus$, is the enthalpy change when one mole of water is formed by reaction between an acid and an alkali under standard conditions. For a strong acid and a strong alkali:

$$
\ce{H+(aq) + OH-(aq) -> H2O(l)}
$$

Strong acid and strong alkali neutralisations have similar values because the same ionic reaction is responsible for the heat change.

## Bond Breaking And Bond Making

Chemical reactions transfer energy because bonds are broken and new bonds are made.

Breaking bonds is endothermic. Energy must be supplied to separate bonded atoms, so bond enthalpies for bond breaking are positive.

Making bonds is exothermic. Energy is released when new bonds form.

An approximate reaction enthalpy can be calculated using:

$$
\Delta H_r = \sum \text{bond energies of bonds broken} - \sum \text{bond energies of bonds made}
$$

This works because the calculation imagines all required bonds in the reactants being broken, then all bonds in the products being made. If more energy is released in bond making than is absorbed in bond breaking, $\Delta H_r$ is negative.

Some bond energies are exact, especially for simple gaseous species where a particular bond is being broken. Many values in data tables are average bond energies. An average bond energy is taken over several compounds, so a bond energy calculation often gives an estimate rather than an exact experimental enthalpy change.

## Calorimetry

Calorimetry uses a temperature change to estimate heat energy transferred. In simple aqueous experiments, the heat energy gained or lost by the solution is:

$$
q = mc\Delta T
$$

where:

- $q$ is energy transferred, usually in J;
- $m$ is the mass of solution, usually in g;
- $c$ is the specific heat capacity, often taken as $4.18\ \mathrm{J\,g^{-1}\,K^{-1}}$ for dilute aqueous solutions;
- $\Delta T$ is the temperature change in K or $^\circ\mathrm{C}$.

The reaction enthalpy is then:

$$
\Delta H = -\frac{mc\Delta T}{n}
$$

The negative sign appears because the temperature change measured for the solution is the opposite viewpoint from the enthalpy change of the reacting chemicals. If the solution warms, $mc\Delta T$ is positive and the reaction is exothermic, so $\Delta H$ is negative.

In calorimetry questions, identify the amount $n$ carefully. It should match the enthalpy change being calculated. For neutralisation, $n$ is often the amount of water formed. For combustion, $n$ is the amount of fuel burned. If reactants are mixed, the limiting reactant controls the maximum amount of reaction.

Simple calorimetry is approximate. Heat may be lost to the surroundings, some heat warms the apparatus, and assumptions about density and specific heat capacity may not be exact. These limitations normally make the measured temperature change smaller than the true value for an exothermic reaction, so the magnitude of $\Delta H$ may be underestimated.

## Hess's Law

Hess's law states that the enthalpy change of a reaction is independent of the route taken, provided the initial and final conditions are the same. Enthalpy is a state function: it depends on the state of the reactants and products, not on the path between them.

This allows you to calculate an enthalpy change that is difficult to measure directly by using other enthalpy changes that are known.

The practical rules are simple:

- if an equation is reversed, change the sign of $\Delta H$;
- if an equation is multiplied, multiply $\Delta H$ by the same factor;
- add equations so that unwanted species cancel;
- add the corresponding enthalpy changes.

Hess cycles may use enthalpy changes of formation. A common relationship is:

$$
\Delta H_r^\ominus = \sum \Delta H_f^\ominus(\text{products}) - \sum \Delta H_f^\ominus(\text{reactants})
$$

Remember to multiply each $\Delta H_f^\ominus$ value by the coefficient in the balanced equation.

Hess cycles may also use enthalpy changes of combustion. For a reaction between substances that can all be burned to the same products, combustion data can provide a route from reactants and products down to common combustion products. One useful form is:

$$
\Delta H_r^\ominus = \sum \Delta H_c^\ominus(\text{reactants}) - \sum \Delta H_c^\ominus(\text{products})
$$

This sign order is different from the formation formula because the arrows in the cycle usually point from each substance down to the common combustion products. If unsure, draw the cycle and follow arrows rather than relying on memory.

## Working Routine

When solving an energetics problem, use this order.

1. Write or check the balanced equation.
2. Decide what one mole of reaction means from the equation.
3. Identify whether the data are calorimetry, bond energies, formation enthalpies or combustion enthalpies.
4. Track signs when equations are reversed or scaled.
5. Give the final answer with sign and units.
6. Check whether the sign is chemically reasonable from the description or diagram.

## Common Mistakes

Do not use $q = mc\Delta T$ with the wrong mass. In a simple solution experiment, $m$ is usually the mass of the solution, not the mass of a solid reactant.

Do not drop the sign. A value of $-57\ \mathrm{kJ\,mol^{-1}}$ and $+57\ \mathrm{kJ\,mol^{-1}}$ describe opposite energy transfers.

Do not compare activation energy and enthalpy change as if they are the same quantity. Activation energy is a barrier; enthalpy change is a difference between start and finish.

Do not treat bond energy calculations as perfect experimental values when average bond energies are used.

## Quick Self-Checks

- Can you explain why $\Delta H$ is negative when the temperature of the surroundings rises?
- Can you label $E_A$ and $\Delta H$ correctly on an exothermic pathway diagram?
- Can you decide whether $n$ in $\Delta H = -mc\Delta T/n$ is the amount of fuel, water formed or limiting reactant?
- Can you build the same Hess calculation by adding equations and by drawing an energy cycle?

## Connections

- [Reaction Kinetics](../08%20Reaction%20Kinetics/10%20Lecture%20Notes.md)
- [A Level Chemical Energetics](../23%20Chemical%20Energetics/00%20Overview.md)
- [Practical Skills](../../02%20Practical%20Skills/00%20Overview.md)
