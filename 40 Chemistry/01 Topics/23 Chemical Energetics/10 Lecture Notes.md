---
title: 23 Chemical Energetics - Lecture Notes
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/a-level
  - chemistry/9701/physical-chemistry
---

# 23 Chemical Energetics - Lecture Notes

## Source Route

These notes follow the CAIE Chemistry 9701 syllabus for 2025-2027, A Level subject content, sections 23.1-23.4: lattice energy and Born-Haber cycles, enthalpies of solution and hydration, entropy change, and Gibbs free energy change. No Chemistry coursebook alignment is claimed.

## Learning Scope

This topic extends AS enthalpy cycles into ionic solids and thermodynamic feasibility. You need to define the required enthalpy terms, build Born-Haber and solution cycles, explain lattice and hydration trends using charge and radius, calculate entropy changes from standard entropy data, and use Gibbs free energy to decide whether a reaction or process is thermodynamically feasible under stated conditions.

## Ionic Enthalpy Terms

The **enthalpy change of atomisation**, $\Delta H^\circ_{\text{at}}$, is the enthalpy change when one mole of gaseous atoms is formed from an element in its standard state.

For sodium:

$$
\ce{Na(s) -> Na(g)}
$$

For chlorine atoms, one mole of atoms is formed from half a mole of chlorine molecules:

$$
\ce{1/2Cl2(g) -> Cl(g)}
$$

The syllabus defines **lattice energy**, $\Delta H^\circ_{\text{latt}}$, as the enthalpy change when gaseous ions form one mole of solid ionic lattice.

$$
\ce{Na+(g) + Cl-(g) -> NaCl(s)}
$$

With this convention, lattice energy is usually negative because forming the lattice releases energy. Some data books use lattice dissociation enthalpy instead, which has the opposite sign. In this topic, check the definition before substituting.

The **first electron affinity**, $\text{EA}_1$, is the enthalpy change when one mole of gaseous atoms each gains one electron to form one mole of gaseous 1- ions.

$$
\ce{Cl(g) + e- -> Cl-(g)}
$$

First electron affinity is often exothermic because the incoming electron is attracted to the nucleus. It is affected by nuclear charge, atomic radius, shielding, and electron-electron repulsion. In Group 17, chlorine has a more exothermic first electron affinity than fluorine because the incoming electron in fluorine enters a very small shell with greater repulsion. Below chlorine, increasing radius and shielding make first electron affinities less exothermic. In Group 16, first electron affinities are less exothermic than the corresponding Group 17 values because Group 16 atoms are one electron further from a full outer shell. Oxygen is less exothermic than sulfur because the incoming electron enters a compact 2p orbital with strong electron-electron repulsion; below sulfur, increasing radius and shielding usually make first electron affinities less exothermic. The second electron affinity in Group 16 is endothermic because an electron is added to an already negative ion.

## Born-Haber Cycles

A Born-Haber cycle is a Hess cycle for forming an ionic solid from its elements. It separates the standard enthalpy change of formation into atomisation, ionisation, electron affinity, and lattice energy steps.

For a simple 1+/1- ionic solid such as sodium chloride:

$$
\ce{Na(s) + 1/2Cl2(g) -> NaCl(s)}
$$

Using the syllabus lattice-energy convention:

$$
\Delta H^\circ_{\text{f}} =
\Delta H^\circ_{\text{at}}(\ce{Na})
+ \Delta H^\circ_{\text{at}}(\ce{Cl})
+ \text{IE}_1(\ce{Na})
+ \text{EA}_1(\ce{Cl})
+ \Delta H^\circ_{\text{latt}}(\ce{NaCl})
$$

For 2+ or 2- ions, include all required ionisation energies or electron affinities. For magnesium oxide, the cycle includes $\text{IE}_1+\text{IE}_2$ for magnesium and $\text{EA}_1+\text{EA}_2$ for oxygen. The syllabus limits Born-Haber work to +1 and +2 cations and -1 and -2 anions.

The numerical magnitude of lattice energy increases when ionic charge increases and when ionic radius decreases. Higher charges create stronger electrostatic attraction. Smaller ions bring opposite charges closer together. This is why $\ce{MgO}$ has a much larger magnitude lattice energy than $\ce{NaCl}$.

## Solution And Hydration Cycles

The **enthalpy change of hydration**, $\Delta H^\circ_{\text{hyd}}$, is the enthalpy change when one mole of gaseous ions forms one mole of aqueous ions.

$$
\ce{Na+(g) -> Na+(aq)}
$$

The **enthalpy change of solution**, $\Delta H^\circ_{\text{sol}}$, is the enthalpy change when one mole of a substance dissolves in enough solvent to form an infinitely dilute solution.

$$
\ce{NaCl(s) -> Na+(aq) + Cl-(aq)}
$$

With lattice energy defined for lattice formation:

$$
\Delta H^\circ_{\text{sol}}
= -\Delta H^\circ_{\text{latt}}
+ \sum \Delta H^\circ_{\text{hyd}}(\text{ions})
$$

The term $-\Delta H^\circ_{\text{latt}}$ represents separating the solid lattice into gaseous ions. Hydration enthalpies are normally negative because ion-water attractions form. Their numerical magnitude increases for ions with higher charge and smaller radius because these ions have greater charge density and form stronger ion-dipole attractions with water.

Whether an ionic solid dissolves exothermically depends on the balance between energy needed to separate the lattice and energy released during hydration. A positive $\Delta H^\circ_{\text{sol}}$ does not automatically mean the salt is insoluble, because entropy can also help drive dissolving.

## Entropy Change

Entropy, $S$, is the number of possible arrangements of the particles and their energy in a given system. A process usually has a positive entropy change when particles or energy become more widely distributed.

Common signs:

| Change | Usual sign of $\Delta S$ | Reason |
|---|---:|---|
| Solid melts or liquid boils | Positive | Particles have more possible arrangements |
| Gas condenses or liquid freezes | Negative | Particles become more ordered |
| Temperature increases | Positive | Energy can be arranged in more ways |
| More moles of gas are produced | Positive | Gas particles have many possible positions |
| Fewer moles of gas are produced | Negative | Fewer gas particles reduce possible arrangements |

For a reaction:

$$
\Delta S^\circ = \sum S^\circ(\text{products}) - \sum S^\circ(\text{reactants})
$$

Use the stoichiometric coefficients from the balanced equation. Standard entropy values are usually in $\text{J mol}^{-1}\text{ K}^{-1}$.

## Gibbs Free Energy And Feasibility

The Gibbs equation is:

$$
\Delta G^\circ = \Delta H^\circ - T\Delta S^\circ
$$

A reaction or process is thermodynamically feasible under standard conditions if $\Delta G^\circ < 0$. If $\Delta G^\circ > 0$, it is not feasible under those stated conditions. If $\Delta G^\circ = 0$, the system is at equilibrium under those conditions.

Before substituting, convert entropy from $\text{J mol}^{-1}\text{ K}^{-1}$ to $\text{kJ mol}^{-1}\text{ K}^{-1}$ if $\Delta H^\circ$ is in $\text{kJ mol}^{-1}$.

Temperature changes feasibility through the $-T\Delta S^\circ$ term:

| $\Delta H^\circ$ | $\Delta S^\circ$ | Temperature effect |
|---:|---:|---|
| Negative | Positive | Feasible at all temperatures in the simple model |
| Negative | Negative | More feasible at low temperature |
| Positive | Positive | More feasible at high temperature |
| Positive | Negative | Not feasible at any temperature in the simple model |

Feasibility is thermodynamic. It does not prove that a reaction is fast. A reaction can have negative $\Delta G^\circ$ but proceed slowly because of a high activation energy.

## Working Routine

1. Write the balanced equation with state symbols.
2. Identify the data type: Born-Haber, solution cycle, entropy, or Gibbs.
3. Draw or mentally trace the cycle before calculating.
4. Keep signs tied to definitions, especially for lattice energy.
5. Convert entropy units before using the Gibbs equation.
6. End with a chemical interpretation: charge density, disorder, temperature, or feasibility.

## Common Mistakes

- Using lattice dissociation data when the question defines lattice formation, or the reverse.
- Forgetting second ionisation energy or second electron affinity for 2+ or 2- ions.
- Treating hydration enthalpy as positive.
- Mixing $\text{J mol}^{-1}\text{ K}^{-1}$ and $\text{kJ mol}^{-1}$ in $\Delta G^\circ = \Delta H^\circ - T\Delta S^\circ$.
- Saying "spontaneous" or "feasible" as if it also means "fast".

## Connections

This topic supports [Electrochemistry](../24%20Electrochemistry/00%20Overview.md), where $\Delta G^\circ$ is linked to standard cell potential. It also supports inorganic trend explanations in [Group 2](../27%20Group%202/00%20Overview.md), especially solubility and thermal stability patterns.
