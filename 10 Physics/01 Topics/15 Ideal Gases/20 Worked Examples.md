---
title: Ideal Gases Worked Examples
subject: Physics
syllabus: 9702
parent: "[Ideal Gases](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/thermal-physics
  - worked-examples
---

# Ideal Gases Worked Examples

These examples model the standard CAIE route through amount of substance,
particle number, the ideal gas equation, kinetic theory assumptions, molecular
pressure, root-mean-square speed, and mean translational kinetic energy.

## Source Route

- Syllabus: CAIE Physics 9702 section 15, Ideal gases.
- Main subtopics: the mole, equation of state, and kinetic theory of gases.
- Coursebook route: Avogadro constant, ideal gas equation, molecular
  collisions, kinetic theory assumptions, pressure equation, Boltzmann
  constant, and r.m.s. speed.

Use

$$
N_\mathrm{A}=6.02 \times 10^{23}\ \mathrm{mol^{-1}},
\quad
R=8.31\ \mathrm{J\ mol^{-1}\ K^{-1}},
\quad
k=1.38 \times 10^{-23}\ \mathrm{J\ K^{-1}}
$$

unless a question gives other values.

## Example 1: Mole and Particle Number

**Prompt.** A sample contains $4.0\ \mathrm{g}$ of helium. The molar mass of
helium is $4.0\ \mathrm{g\ mol^{-1}}$. Find the amount of substance and the
number of atoms.

**Solution.**

Amount of substance is

$$
n=\frac{m}{M}.
$$

Using grams consistently,

$$
n=\frac{4.0}{4.0}=1.0\ \mathrm{mol}.
$$

The number of atoms is

$$
N=nN_\mathrm{A}
=(1.0)(6.02 \times 10^{23})
=6.02 \times 10^{23}.
$$

**What this example trains.** The mole is a counting unit, scaled by Avogadro's
constant.

## Example 2: Using $pV=nRT$

**Prompt.** Find the volume occupied by $0.250\ \mathrm{mol}$ of an ideal gas
at pressure $1.00 \times 10^5\ \mathrm{Pa}$ and temperature
$27.0\ ^\circ\mathrm{C}$.

**Solution.**

First convert temperature to kelvin:

$$
T=27.0+273.15=300.15\ \mathrm{K}.
$$

Use

$$
pV=nRT.
$$

Rearrange:

$$
V=\frac{nRT}{p}.
$$

Substitute:

$$
V=
\frac{(0.250)(8.31)(300.15)}
{1.00 \times 10^5}
=6.24 \times 10^{-3}\ \mathrm{m^3}.
$$

**What this example trains.** Temperature in the ideal gas equation must be in
kelvin.

## Example 3: A Two-State Gas Change

**Prompt.** A fixed mass of ideal gas has pressure
$1.20 \times 10^5\ \mathrm{Pa}$, volume $200\ \mathrm{cm^3}$, and temperature
$20.0\ ^\circ\mathrm{C}$. It is heated to $80.0\ ^\circ\mathrm{C}$ and its
volume becomes $250\ \mathrm{cm^3}$. Find the new pressure.

**Solution.**

For a fixed amount of ideal gas,

$$
\frac{pV}{T}=\text{constant}.
$$

So

$$
\frac{p_1V_1}{T_1}
=
\frac{p_2V_2}{T_2}.
$$

Convert temperatures:

$$
T_1=293.15\ \mathrm{K},
\qquad
T_2=353.15\ \mathrm{K}.
$$

Rearrange:

$$
p_2=\frac{p_1V_1T_2}{T_1V_2}.
$$

The volume units cancel because both volumes are in the same unit:

$$
p_2=
\frac{(1.20 \times 10^5)(200)(353.15)}
{(293.15)(250)}
=1.16 \times 10^5\ \mathrm{Pa}.
$$

**What this example trains.** In a two-state problem, convert only absolute
temperatures; consistent volume units can cancel in a ratio.

## Example 4: Using $pV=NkT$

**Prompt.** A gas occupies $1.00 \times 10^{-2}\ \mathrm{m^3}$ at pressure
$1.00 \times 10^5\ \mathrm{Pa}$ and temperature $300\ \mathrm{K}$. Find the
number of molecules and the amount of substance.

**Solution.**

Use the molecular form of the ideal gas equation:

$$
pV=NkT.
$$

So

$$
N=\frac{pV}{kT}
=
\frac{(1.00 \times 10^5)(1.00 \times 10^{-2})}
{(1.38 \times 10^{-23})(300)}
=2.42 \times 10^{23}.
$$

The amount of substance is

$$
n=\frac{N}{N_\mathrm{A}}
=
\frac{2.42 \times 10^{23}}{6.02 \times 10^{23}}
=0.402\ \mathrm{mol}.
$$

**What this example trains.** Use $N$ for number of molecules and $n$ for
amount of substance in moles.

## Example 5: Explaining Gas Pressure

**Prompt.** Explain why the pressure of a gas increases when its temperature
is raised at constant volume.

**Solution.**

Gas molecules move randomly and collide with the container walls. In each
elastic collision, a molecule's momentum changes, so the wall exerts a force
on the molecule. By Newton's third law, the molecule exerts a force on the
wall.

Pressure is force per unit area, so the total effect of many molecular
collisions produces gas pressure.

At higher thermodynamic temperature, molecules have greater average
translational kinetic energy. Their speeds are larger on average. At constant
volume, they collide with the walls more frequently and each collision changes
more momentum. Therefore the pressure increases.

**What this example trains.** Pressure is explained by rate of momentum
transfer to the walls.

## Example 6: R.M.S. Speed from Temperature

**Prompt.** Estimate the root-mean-square speed of nitrogen molecules at
$300\ \mathrm{K}$. The molar mass of nitrogen is
$0.0280\ \mathrm{kg\ mol^{-1}}$.

**Solution.**

For one mole of gas, the total translational kinetic energy relation gives

$$
\frac{1}{2}M c_{\mathrm{r.m.s.}}^2
=
\frac{3}{2}RT.
$$

Therefore

$$
c_{\mathrm{r.m.s.}}
=
\sqrt{\frac{3RT}{M}}.
$$

Substitute:

$$
c_{\mathrm{r.m.s.}}
=
\sqrt{\frac{3(8.31)(300)}{0.0280}}
=5.17 \times 10^2\ \mathrm{m\ s^{-1}}.
$$

**What this example trains.** R.M.S. speed comes from mean-square speed, not
from the simple arithmetic mean of molecular speeds.

## Example 7: Mean Translational Kinetic Energy

**Prompt.** Find the mean translational kinetic energy of one ideal-gas
molecule at $300\ \mathrm{K}$ and at $600\ \mathrm{K}$.

**Solution.**

For an ideal gas molecule,

$$
\langle E_k\rangle=\frac{3}{2}kT.
$$

At $300\ \mathrm{K}$,

$$
\langle E_k\rangle
=
\frac{3}{2}(1.38 \times 10^{-23})(300)
=6.21 \times 10^{-21}\ \mathrm{J}.
$$

At $600\ \mathrm{K}$,

$$
\langle E_k\rangle
=
\frac{3}{2}(1.38 \times 10^{-23})(600)
=1.24 \times 10^{-20}\ \mathrm{J}.
$$

Doubling the thermodynamic temperature doubles the mean translational kinetic
energy.

**What this example trains.** Thermodynamic temperature is proportional to the
average translational kinetic energy per molecule.

## Example 8: When the Ideal Model Fails

**Prompt.** State the assumptions of the ideal gas model and explain why real
gases deviate from it at high pressure or low temperature.

**Solution.**

The kinetic theory model assumes that:

- there are many molecules moving randomly
- molecular volume is negligible compared with container volume
- intermolecular forces are negligible except during collisions
- collisions are elastic
- collision duration is negligible compared with time between collisions

At high pressure, molecules are closer together, so their own volume is no
longer negligible. At low temperature, molecules move more slowly and
intermolecular attractions become more important. The gas may also approach
condensation.

**What this example trains.** The ideal gas equation is a model with physical
conditions, not just an algebraic formula.
