---
title: Nuclear Physics Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/23 Nuclear Physics/00 Overview|Nuclear Physics]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/modern-physics
  - lecture-notes
---

# Nuclear Physics Lecture Notes

Nuclear physics connects the structure of the nucleus with energy and probability. The first half of the topic explains why nuclear reactions can release large amounts of energy. The second half explains why radioactive decay is unpredictable for one nucleus but has a stable exponential pattern for a large sample.

## Source Route

- Primary syllabus source: CAIE Physics 9702.
- 23 Nuclear physics
- 23.1 Mass defect and nuclear binding energy
- 23.2 Radioactive decay
- Coursebook route: Physics Coursebook Chapter 29: nuclear equations, mass-energy equivalence, binding energy, fission, fusion, and radioactive decay.

## Visual Guide

![[assets/generated/physics/nuclear-physics.svg]]

Figure: Binding energy per nucleon explains nuclear stability, while exponential decay describes the statistical behaviour of unstable nuclei.

## 1. Nuclear Notation And Balanced Equations

A nucleus is written in the form

$$
{}^{A}_{Z}X,
$$

where $A$ is the nucleon number and $Z$ is the proton number. The neutron number is

$$
N = A - Z.
$$

In a nuclear equation, nucleon number and proton number are conserved. This is the main checking tool. Add the top numbers on both sides, then add the bottom numbers on both sides.

For alpha decay, the emitted alpha particle is a helium nucleus:

$$
{}^{4}_{2}\mathrm{He}.
$$

The parent nucleus loses four nucleons and two protons. For beta-minus decay, a neutron changes into a proton and an electron is emitted, so $A$ is unchanged and $Z$ increases by one. For beta-plus decay, $A$ is unchanged and $Z$ decreases by one. Gamma emission changes neither $A$ nor $Z$ because a gamma ray is electromagnetic radiation emitted by an excited nucleus.

The course does not require detailed weak interaction theory here. It does require you to balance simple nuclear equations cleanly and to recognise the parent nucleus, daughter nucleus, and emitted radiation.

## 2. Mass-Energy Equivalence

Einstein's mass-energy equation is

$$
E = mc^2.
$$

For nuclear reactions, the useful form is

$$
\Delta E = \Delta mc^2.
$$

The speed of light is very large:

$$
c = 3.00 \times 10^8\,\text{m s}^{-1}.
$$

Because $c^2$ is enormous, a tiny change in rest mass can correspond to a large energy change. In nuclear physics, energy release is usually found from a decrease in total rest mass:

$$
E_{\text{released}} = \Delta m c^2,
$$

where $\Delta m$ is the initial total rest mass minus the final total rest mass. If the final total rest mass is smaller, the missing mass has appeared as energy, often kinetic energy of the products and sometimes gamma radiation.

## 3. Mass Defect

The mass of a nucleus is less than the total mass of the separated protons and neutrons that make it. This difference is the mass defect.

For a nucleus with nucleon number $A$ and proton number $Z$,

$$
\Delta m = Zm_p + (A-Z)m_n - m_{\text{nucleus}}.
$$

Here $m_p$ is the proton mass, $m_n$ is the neutron mass, and $m_{\text{nucleus}}$ is the mass of the nucleus.

This mass difference is not a measurement mistake. When separate nucleons bind together, the system loses energy and its mass decreases. To pull the nucleus apart again, external energy must be supplied.

## 4. Binding Energy

The binding energy of a nucleus is the minimum energy required to separate the nucleus completely into its individual nucleons.

Using the mass defect,

$$
E_{\text{b}} = \Delta m c^2.
$$

This is a common language trap. Binding energy is not energy sitting inside the nucleus waiting to come out. It is the energy that must be supplied to break the nucleus apart. A nucleus with a larger binding energy per nucleon is generally more stable because its nucleons are more tightly bound.

The binding energy per nucleon is

$$
\frac{E_{\text{b}}}{A}.
$$

It is the best simple comparison between nuclei of different sizes.

## 5. The Binding Energy Per Nucleon Graph

The graph of binding energy per nucleon against nucleon number has a characteristic shape:

- It rises steeply for light nuclei.
- It reaches a maximum near iron and nickel.
- It decreases slowly for very heavy nuclei.

The higher the binding energy per nucleon, the more stable the nuclide is in this model. Nuclear processes that move products toward a higher binding energy per nucleon tend to release energy.

This graph explains why both fusion and fission can release energy, even though they look like opposite processes.

## 6. Fusion

Nuclear fusion is the process in which two light nuclei join to form a heavier nucleus.

Fusion can release energy when the product has a greater total binding energy than the original nuclei. On the binding energy per nucleon graph, light nuclei can move upward by joining together. The energy released equals the increase in total binding energy, or equivalently the decrease in total rest mass:

$$
E_{\text{released}} = \Delta m c^2.
$$

Fusion requires very high temperature because positively charged nuclei repel each other. They need enough kinetic energy to get close enough for the strong nuclear force to bind them.

## 7. Fission

Nuclear fission is the process in which a heavy nucleus splits into two smaller nuclei. It is more than the emission of an alpha or beta particle. It is the splitting of a massive nucleus into large fragments.

Heavy nuclei can release energy by splitting into fragments with a higher binding energy per nucleon. A typical induced fission reaction begins when a uranium-235 nucleus absorbs a slow neutron and forms an unstable uranium-236 nucleus. It then splits into smaller nuclei and emits more neutrons.

The energy released appears mainly as kinetic energy of the fission fragments and emitted neutrons, with some energy in gamma radiation. In a calculation, compare the total rest mass before and after the reaction.

## 8. Radioactive Decay Is Random And Spontaneous

Radioactive decay is random because it is impossible to predict when a particular nucleus will decay. Count rate fluctuations from a detector provide direct evidence of this randomness.

Radioactive decay is spontaneous because the decay of a nucleus is not affected by external conditions such as temperature, pressure, or chemical reactions. The nucleus does not age in the everyday sense. If a nucleus has not decayed yet, that does not mean it is about to decay.

The key reconciliation is this: one nucleus is unpredictable, but a large sample follows a statistical pattern. With many nuclei, the average behaviour becomes exponential.

## 9. Activity And Decay Constant

Activity is the rate at which nuclei decay:

$$
A = -\frac{dN}{dt}.
$$

The unit of activity is the becquerel:

$$
1\,\text{Bq} = 1\,\text{s}^{-1}.
$$

The decay constant $\lambda$ is the probability per unit time that an individual nucleus will decay. Its unit is the inverse of time, for example $\text{s}^{-1}$.

For a sample with $N$ undecayed nuclei,

$$
A = \lambda N.
$$

A larger $\lambda$ means a greater probability of decay per unit time, so the sample has a larger activity for the same number of undecayed nuclei.

In experiments, the measured count rate is often less than the activity because not every emitted particle or photon is detected. Background count must also be subtracted when it is significant.

## 10. Exponential Decay

Radioactive decay is exponential because the rate of decay is proportional to the number of undecayed nuclei remaining.

The general equation is

$$
x = x_0 e^{-\lambda t},
$$

where $x$ can represent:

- number of undecayed nuclei $N$,
- activity $A$,
- received or corrected count rate $R$.

So the same form may appear as

$$
N = N_0 e^{-\lambda t},
$$

$$
A = A_0 e^{-\lambda t},
$$

or

$$
R = R_0 e^{-\lambda t}.
$$

Use compatible units. If $\lambda$ is in $\text{s}^{-1}$, then $t$ must be in seconds. The exponent $-\lambda t$ must be dimensionless.

## 11. Half-Life

The half-life $t_{1/2}$ of a radioactive isotope is the mean time taken for half the active nuclei in a sample to decay.

After one half-life, $N$, $A$, and the corrected count rate are all halved. After two half-lives, they are one quarter of the original values. After $n$ half-lives,

$$
\frac{x}{x_0} = \left(\frac{1}{2}\right)^n.
$$

The decay constant and half-life are related by

$$
\lambda = \frac{0.693}{t_{1/2}},
$$

or

$$
t_{1/2} = \frac{0.693}{\lambda}.
$$

The half-life does not depend on the amount of material you start with. A larger sample has a larger initial activity, but the fraction remaining after each half-life is the same.

## 12. Reading And Linearising Decay Graphs

On a graph of $x$ against $t$, exponential decay curves downward and approaches zero without reaching it in the ideal model. To estimate half-life from a graph, choose a value of $x$, find the time when it has fallen to $x/2$, and read the time difference.

Taking logarithms gives

$$
\ln x = \ln x_0 - \lambda t.
$$

So a graph of $\ln x$ against $t$ is a straight line with gradient $-\lambda$. This is a useful way to identify an exponential model and estimate the decay constant from data.

## 13. Problem Routines

For nuclear equation problems:

1. Write each nuclide as ${}^{A}_{Z}X$.
2. Add nucleon numbers on both sides.
3. Add proton numbers on both sides.
4. Use the missing numbers to identify the unknown particle or daughter nucleus.

For binding energy problems:

1. Find the total mass of the separated nucleons.
2. Subtract the nuclear mass to get the mass defect.
3. Use $E_{\text{b}} = \Delta m c^2$.
4. Divide by $A$ if binding energy per nucleon is needed.

For reaction energy problems:

1. Add total rest mass before the reaction.
2. Add total rest mass after the reaction.
3. Use the decrease in rest mass in $E_{\text{released}} = \Delta m c^2$.

For radioactive decay problems:

1. Decide whether the known quantity is $N$, $A$, $R$, $\lambda$, or $t_{1/2}$.
2. Convert units so that $\lambda t$ is dimensionless.
3. Use $x = x_0 e^{-\lambda t}$ or the half-life fraction method.
4. If count rate data are used, subtract background count rate first when needed.

## 14. Common Traps

- Confusing nucleon number $A$ with neutron number $N$.
- Forgetting that both $A$ and $Z$ must balance in nuclear equations.
- Treating binding energy as energy stored inside a nucleus.
- Using binding energy per nucleon when total binding energy is needed.
- Thinking that half-life changes when the starting sample is larger.
- Mixing activity, count rate, and number of undecayed nuclei.
- Forgetting that the unit of $\lambda$ must match the unit of time.

## 15. Quick Self-Check

You have the topic if you can do these without notes:

- Balance an alpha or beta decay equation using $A$ and $Z$.
- Explain mass defect and binding energy in words.
- Use $E = mc^2$ or $\Delta E = \Delta mc^2$ to calculate nuclear energy changes.
- Use the binding energy per nucleon graph to explain why fusion and fission can release energy.
- Explain why radioactive decay is both random and spontaneous.
- Use $A = \lambda N$, $x = x_0e^{-\lambda t}$, and $\lambda = 0.693/t_{1/2}$ correctly.

## Connections

- [[10 Physics/01 Topics/11 Particle Physics/00 Overview|Particle Physics]]
- [[10 Physics/01 Topics/22 Quantum Physics/00 Overview|Quantum Physics]]
- [[20 Mathematics/01 Pure Mathematics/07 Logarithms Exponentials and Numerical Methods/00 Overview|Logarithms, Exponentials and Numerical Methods]]
