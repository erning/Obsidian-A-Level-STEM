---
title: Ideal Gases Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/15 Ideal Gases/00 Overview|Ideal Gases]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/thermal-physics
  - lecture-notes
---

# Ideal Gases Lecture Notes

Ideal gases give a clean model for connecting two descriptions of the same system. At the macroscopic level, you measure pressure, volume, temperature, and amount of substance. At the microscopic level, you picture a very large number of molecules moving randomly and colliding with the container walls.

The important skill is to move between these two descriptions without losing the assumptions. The equation $pV = nRT$ is not just an algebraic rule. It is a compact statement about a gas whose molecular volume and intermolecular forces are small enough to ignore.

## Source Route

- Primary syllabus source: CAIE Physics 9702.
- 15 Ideal gases
- 15.1 The mole
- 15.2 Equation of state
- 15.3 Kinetic theory of gases
- Coursebook route: Physics Coursebook Chapter 20, Ideal gases.

## Visual Guide

![[assets/generated/physics/ideal-gases.svg]]

Figure: The particle model links microscopic molecular motion with macroscopic pressure, volume, and temperature.

## 1. The Variables of a Gas

For an ideal gas problem, identify these variables before writing an equation:

- $p$: pressure of the gas, measured in pascals.
- $V$: volume occupied by the gas, measured in cubic metres.
- $T$: thermodynamic temperature, measured in kelvin.
- $n$: amount of substance, measured in moles.
- $N$: number of molecules.

Temperature must be in kelvin in gas equations. Celsius temperature measures the same size of temperature interval, but it does not start at absolute zero, so it cannot be used directly in $pV = nRT$ or $pV = NkT$.

Amount of substance is an SI base quantity. Its SI base unit is the mole, symbol $\mathrm{mol}$. It is not the same as mass. Mass tells you how much matter is present by inertia or weight; amount of substance tells you how many elementary entities are present, scaled by Avogadro's constant.

## 2. Mole and Avogadro's Constant

One mole contains a number of particles equal to Avogadro's constant:

$$
N_\text{A} = 6.02 \times 10^{23}\ \mathrm{mol}^{-1}
$$

The basic link between amount of substance and number of molecules is

$$
N = nN_\text{A}.
$$

If the mass $m_\text{gas}$ of a gas sample and its molar mass $M$ are known, then

$$
n = \frac{m_\text{gas}}{M}.
$$

Use consistent units. If $M$ is in $\mathrm{kg\ mol^{-1}}$, then $m_\text{gas}$ must be in kilograms. If $M$ is in $\mathrm{g\ mol^{-1}}$, then $m_\text{gas}$ must be in grams.

## 3. Ideal Gas Equation

An ideal gas is a gas that obeys

$$
pV \propto T
$$

for a fixed amount of gas, where $T$ is thermodynamic temperature. The full equation of state is

$$
pV = nRT,
$$

where

$$
R = 8.31\ \mathrm{J\ mol^{-1}\ K^{-1}}.
$$

Since $N = nN_\text{A}$, the same equation can be written using the number of molecules:

$$
pV = NkT,
$$

where $k$ is the Boltzmann constant:

$$
k = \frac{R}{N_\text{A}} = 1.38 \times 10^{-23}\ \mathrm{J\ K^{-1}}.
$$

Use $pV = nRT$ when the amount of substance in moles is given or convenient. Use $pV = NkT$ when the question is about individual molecules, number of particles, or kinetic theory.

For a fixed amount of gas, the equation also gives

$$
\frac{pV}{T} = \text{constant}.
$$

This form is useful for comparing two states of the same gas sample.

## 4. When the Ideal Model Works

The ideal gas model is most reliable when the gas is at low pressure and high temperature. In that situation, the molecules are far apart compared with their own size, and attractive forces between molecules are small for most of the motion.

Real gases deviate from ideal behaviour at high pressure or low temperature. At high pressure, the volume of the molecules themselves becomes less negligible. At low temperature, intermolecular forces become more significant, and the gas may approach condensation.

So before using the model, ask two questions:

- Is the gas being treated as dilute enough for molecular volume to be ignored?
- Is the temperature high enough that intermolecular forces are not dominating the behaviour?

In many A Level problems, ideal behaviour is stated or implied. Still, naming the assumption keeps the physics clear.

## 5. Pressure from Molecular Collisions

Gas pressure comes from molecular collisions with the container walls. A molecule moving towards a wall has momentum. When it collides elastically with the wall, its velocity component perpendicular to the wall reverses. Its momentum changes, so the wall exerts a force on the molecule. By Newton's third law, the molecule exerts an equal and opposite force on the wall.

The pressure is the total force per unit area due to a very large number of such collisions:

$$
p = \frac{F}{A}.
$$

This explains several familiar patterns:

- If the volume is reduced at constant temperature, molecules hit the walls more frequently, so the pressure increases.
- If the temperature rises at constant volume, the molecules have larger speeds on average, so each collision transfers more momentum and collisions occur more frequently.
- If more molecules are added to the same volume at the same temperature, there are more collisions per second, so the pressure increases.

The word "random" matters. Individual molecules do not all move with the same speed or in the same direction, but for a large sample their average behaviour is stable and measurable.

## 6. Kinetic Theory Assumptions

The kinetic theory derivation uses a simplified molecular model:

- The gas contains a very large number of molecules moving randomly.
- Molecules collide elastically with each other and with the container walls.
- The molecules are treated as hard spheres.
- The volume of the molecules is negligible compared with the volume of the container.
- The forces between molecules are negligible except during collisions.
- The duration of a collision is negligible compared with the time between collisions.

These assumptions are not decorative. They explain why the derivation can ignore intermolecular potential energy, use elastic momentum changes, and average the motion over many molecules.

## 7. Deriving the Pressure Equation

Consider one molecule of mass $m$ in a cube of side $l$. Let its velocity component perpendicular to one wall be $c_x$.

In an elastic collision with that wall, the molecule's velocity component changes from $c_x$ to $-c_x$. The change in the molecule's momentum is

$$
\Delta p_x = -2mc_x.
$$

The wall receives an impulse of magnitude $2mc_x$. The time between successive collisions with the same wall is

$$
\Delta t = \frac{2l}{c_x}.
$$

The average force due to this one molecule is therefore

$$
F = \frac{2mc_x}{2l/c_x} = \frac{mc_x^2}{l}.
$$

Since the wall has area $l^2$, the pressure contribution from this molecule is

$$
p = \frac{F}{l^2} = \frac{mc_x^2}{l^3}.
$$

For $N$ molecules, add the contributions:

$$
p = \frac{m}{V}\sum c_x^2,
$$

where $V = l^3$. For random three-dimensional motion,

$$
\langle c_x^2\rangle = \frac{1}{3}\langle c^2\rangle.
$$

So

$$
p = \frac{1}{3}\frac{Nm}{V}\langle c^2\rangle,
$$

or

$$
pV = \frac{1}{3}Nm\langle c^2\rangle.
$$

Here $m$ is the mass of one molecule, $N$ is the number of molecules, and $\langle c^2\rangle$ is the mean-square speed.

## 8. Mean-Square Speed and R.M.S. Speed

The mean-square speed is the average value of $c^2$:

$$
\langle c^2\rangle = \frac{c_1^2 + c_2^2 + c_3^2 + \cdots + c_N^2}{N}.
$$

The root-mean-square speed is

$$
c_{\text{r.m.s.}} = \sqrt{\langle c^2\rangle}.
$$

Do not confuse $c_{\text{r.m.s.}}$ with the mean speed $\langle c\rangle$. Squaring gives faster molecules extra weight, so these quantities are generally different.

## 9. Temperature and Molecular Kinetic Energy

Compare the kinetic theory result

$$
pV = \frac{1}{3}Nm\langle c^2\rangle
$$

with the molecular form of the ideal gas equation:

$$
pV = NkT.
$$

Equating the two expressions gives

$$
\frac{1}{3}m\langle c^2\rangle = kT.
$$

Multiplying by $\frac{3}{2}$ gives

$$
\frac{1}{2}m\langle c^2\rangle = \frac{3}{2}kT.
$$

The left-hand side is the mean translational kinetic energy of one molecule. Therefore

$$
\langle E_\text{k}\rangle = \frac{3}{2}kT.
$$

This is one of the deepest results in the topic: thermodynamic temperature is proportional to the average translational kinetic energy of the molecules. It is not a measure of the kinetic energy of one particular molecule, because individual molecular speeds vary continuously through collisions.

## 10. Problem-Solving Routine

For an ideal gas calculation:

1. Convert temperature to kelvin.
2. Convert pressure to pascals and volume to cubic metres.
3. Decide whether the convenient amount variable is $n$ or $N$.
4. Choose $pV = nRT$, $pV = NkT$, or a two-state form of $\frac{pV}{T} = \text{constant}$.
5. Check whether the result makes physical sense. Higher $T$ at fixed $V$ should mean higher $p$; larger $V$ at fixed $T$ should mean lower $p$.

For a kinetic theory explanation:

1. Start with molecular collisions and momentum change.
2. Connect force to rate of change of momentum.
3. Divide by area to obtain pressure.
4. Use random three-dimensional motion to justify the factor $\frac{1}{3}$.
5. Link $\langle c^2\rangle$ to temperature through $\langle E_\text{k}\rangle = \frac{3}{2}kT$.

## 11. Common Traps

- Using degrees Celsius in $pV = nRT$.
- Mixing grams with kilograms when using molar mass.
- Treating $N$ and $n$ as the same quantity.
- Forgetting that $m$ in $pV = \frac{1}{3}Nm\langle c^2\rangle$ is the mass of one molecule, not the mass of the whole gas sample.
- Confusing mean speed with root-mean-square speed.
- Using the ideal gas model without noticing high pressure or low temperature conditions.

## 12. Quick Self-Check

You are ready to move on when you can:

- explain pressure in terms of molecular collisions and momentum change;
- use both $pV = nRT$ and $pV = NkT$ with correct units;
- convert between $n$, $N$, molar mass, and mass;
- state the assumptions behind the kinetic theory model;
- derive the shape of $pV = \frac{1}{3}Nm\langle c^2\rangle$;
- explain why $\langle E_\text{k}\rangle = \frac{3}{2}kT$ makes temperature a molecular energy scale.

## Connections

- [[10 Physics/01 Topics/14 Temperature/00 Overview|Temperature]]
- [[10 Physics/01 Topics/16 Thermodynamics/00 Overview|Thermodynamics]]
