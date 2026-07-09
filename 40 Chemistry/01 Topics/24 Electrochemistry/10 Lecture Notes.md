---
title: 24 Electrochemistry - Lecture Notes
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/a-level
  - chemistry/9701/physical-chemistry
---

# 24 Electrochemistry - Lecture Notes

## Source Route

These notes follow the CAIE Chemistry 9701 syllabus for 2025-2027, A Level subject content, sections 24.1-24.2: electrolysis, standard electrode potentials, standard cell potentials, the Nernst equation, and the link between cell potential and Gibbs free energy. No Chemistry coursebook alignment is claimed.

## Learning Scope

This topic uses redox ideas quantitatively. You need to predict electrolysis products, calculate amounts formed from charge, describe how electrode potentials are measured, combine standard electrode potentials to predict cell behaviour, use concentration effects through the Nernst equation, and connect electrical work to $\Delta G^\circ$.

## Electrolysis

Electrolysis uses an external power supply to force a non-spontaneous redox reaction. The cathode is where reduction occurs, and the anode is where oxidation occurs.

For molten electrolytes, the ions present come from the compound itself. For molten sodium chloride:

Cathode:

$$
\ce{Na+ + e- -> Na}
$$

Anode:

$$
\ce{2Cl- -> Cl2 + 2e-}
$$

For aqueous electrolytes, water and ions can both compete. Product prediction depends on the state of the electrolyte, the position of species in the redox series or electrode-potential series, and concentration. In aqueous sodium chloride, concentrated solution favours chlorine at the anode, while dilute solution may give oxygen from water or hydroxide ions.

Faraday calculations use charge:

$$
Q = It
$$

where $Q$ is charge in coulombs, $I$ is current in amperes, and $t$ is time in seconds.

The Faraday constant is the charge per mole of electrons:

$$
F = Le
$$

where $L$ is the Avogadro constant and $e$ is the charge on one electron. Use:

$$
n(\text{electrons}) = \frac{Q}{F}
$$

Then connect moles of electrons to moles of product using the half-equation. For example:

$$
\ce{Cu^{2+} + 2e- -> Cu}
$$

requires 2 mol of electrons for 1 mol of copper.

An electrolytic method can determine the Avogadro constant by measuring current, time, and the amount of substance deposited or liberated. From $Q=It$, calculate $F$ using the moles of electrons transferred, then use $L=F/e$.

## Standard Electrode Potentials

A **standard electrode potential**, $E^\circ$, is a standard reduction potential measured relative to the standard hydrogen electrode. It is measured under standard conditions, usually $298\ \text{K}$, $1\ \text{mol dm}^{-3}$ aqueous ions, and $101\ \text{kPa}$ gases.

The standard hydrogen electrode has:

$$
\ce{2H+(aq) + 2e- <=> H2(g)}
$$

with $E^\circ = 0.00\ \text{V}$. A platinum electrode provides a conducting surface, hydrogen gas is bubbled over it at standard pressure, and the solution contains $\ce{H+}$ at standard concentration.

A metal/metal ion half-cell uses a metal electrode in a solution of its ions, such as:

$$
\ce{Cu^{2+}(aq) + 2e- <=> Cu(s)}
$$

A non-metal half-cell may use an inert platinum electrode, such as:

$$
\ce{Cl2(g) + 2e- <=> 2Cl-(aq)}
$$

Ions of the same element in different oxidation states also need an inert electrode, for example:

$$
\ce{Fe^{3+}(aq) + e- <=> Fe^{2+}(aq)}
$$

The half-cell is connected to the standard hydrogen electrode using a salt bridge and a high-resistance voltmeter.

## Standard Cell Potentials

A **standard cell potential**, $E^\circ_{\text{cell}}$, is found by combining two standard electrode potentials.

When using standard reduction potentials:

$$
E^\circ_{\text{cell}} = E^\circ_{\text{cathode}} - E^\circ_{\text{anode}}
$$

The half-cell with the more positive reduction potential is more likely to be reduced. It is the cathode in a feasible simple cell. The half-cell with the less positive reduction potential is oxidised and acts as the anode.

For a zinc-copper cell:

$$
\ce{Cu^{2+}(aq) + 2e- <=> Cu(s)} \quad E^\circ = +0.34\ \text{V}
$$

$$
\ce{Zn^{2+}(aq) + 2e- <=> Zn(s)} \quad E^\circ = -0.76\ \text{V}
$$

Copper(II) ions are reduced and zinc is oxidised:

$$
\ce{Zn(s) + Cu^{2+}(aq) -> Zn^{2+}(aq) + Cu(s)}
$$

$$
E^\circ_{\text{cell}} = +0.34 - (-0.76) = +1.10\ \text{V}
$$

If $E^\circ_{\text{cell}}$ is positive, the reaction is feasible under standard conditions. Electron flow in the external circuit is from the anode to the cathode.

Do not multiply electrode potentials when balancing electrons. $E^\circ$ is an intensive quantity, so it does not scale with the number of moles.

## Oxidising And Reducing Agents

A more positive $E^\circ$ value indicates a stronger tendency to be reduced, so the oxidised species on the left side of a reduction half-equation is a stronger oxidising agent. A less positive or more negative $E^\circ$ value indicates that the reduced species is more easily oxidised and is a stronger reducing agent.

Use the relevant half-equations to construct the full redox equation. Reverse the half-equation that is being oxidised, balance electrons, then add and cancel.

## Concentration Effects And The Nernst Equation

Electrode potentials change when concentrations change. For a reduction half-equation written as:

$$
\ce{Ox + z e- <=> Red}
$$

the syllabus form of the Nernst equation at $298\ \text{K}$ is:

$$
E = E^\circ + \frac{0.059}{z}\log\frac{[\text{oxidised species}]}{[\text{reduced species}]}
$$

For:

$$
\ce{Fe^{3+}(aq) + e- <=> Fe^{2+}(aq)}
$$

$$
E = E^\circ + 0.059\log\frac{[\ce{Fe^{3+}}]}{[\ce{Fe^{2+}}]}
$$

Increasing the concentration of the oxidised species raises the electrode potential. Increasing the concentration of the reduced species lowers it. For a metal/ion half-cell such as $\ce{Cu^{2+}/Cu}$, the solid metal is not included in the concentration ratio.

## Gibbs Free Energy

For standard conditions:

$$
\Delta G^\circ = -nE^\circ_{\text{cell}}F
$$

where $n$ is the number of moles of electrons transferred in the balanced cell reaction and $F$ is the Faraday constant. If $E^\circ_{\text{cell}}$ is positive, $\Delta G^\circ$ is negative, so the reaction is thermodynamically feasible under standard conditions.

## Working Routine

1. Write the relevant half-equations.
2. Identify oxidation and reduction from electron loss and gain.
3. For electrolysis, use $Q=It$, then convert charge to moles of electrons.
4. For cells, choose the cathode as the more positive reduction potential when predicting a feasible simple cell.
5. Calculate $E^\circ_{\text{cell}}$ without multiplying electrode potentials.
6. Use concentration ratios only when non-standard conditions are part of the question.
7. Link $E^\circ_{\text{cell}}$ to feasibility through $\Delta G^\circ = -nE^\circ_{\text{cell}}F$ when required.

## Common Mistakes

- Confusing anode and cathode by memorising charge instead of oxidation and reduction.
- Forgetting that aqueous electrolysis includes water as a possible reactant.
- Using minutes instead of seconds in $Q=It$.
- Reversing a half-equation but mishandling the sign when calculating a cell potential.
- Multiplying $E^\circ$ values by stoichiometric coefficients.
- Applying standard electrode potentials to non-standard concentrations without comment.

## Connections

- [[40 Chemistry/01 Topics/06 Electrochemistry/00 Overview|AS Electrochemistry]]
- [[40 Chemistry/01 Topics/23 Chemical Energetics/00 Overview|A Level Chemical Energetics]]
- [[40 Chemistry/01 Topics/28 Chemistry of Transition Elements/00 Overview|Chemistry of Transition Elements]]
- [[40 Chemistry/01 Topics/25 Equilibria/00 Overview|A Level Equilibria]]