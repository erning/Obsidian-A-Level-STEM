---
title: Thermodynamics Worked Examples
subject: Physics
syllabus: 9702
parent: "[Thermodynamics](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/thermal-physics
  - worked-examples
---

# Thermodynamics Worked Examples

These examples model the standard CAIE route through internal energy, heating,
work done by or on a gas, constant-pressure expansion, $p$-$V$ graph areas,
and the first law of thermodynamics.

## Source Route

- Syllabus: CAIE Physics 9702 section 16, Thermodynamics.
- Main subtopics: internal energy and the first law of thermodynamics.
- Coursebook route: molecular kinetic and potential energy, heating, work,
  gas expansion, compression, and energy accounting for a system.

This note uses the syllabus sign convention:

$$
\Delta U=q+W,
$$

where $q$ is energy transferred to the system by heating, and $W$ is work done
on the system.

## Example 1: Internal Energy as a State Quantity

**Prompt.** Explain what internal energy means and describe how it changes
when a solid is warmed and when it melts at constant temperature.

**Solution.**

Internal energy is the sum of the random kinetic energies and molecular
potential energies of the particles in a system.

When a solid is warmed within the solid state, its temperature rises. The
average random kinetic energy of its particles increases, so its internal
energy increases.

When a solid melts at constant temperature, the average random kinetic energy
does not increase. Energy is still transferred to the system, but it changes
the arrangement and separation of particles. The molecular potential energy
part of internal energy increases.

Internal energy is a state quantity. Heating and work are energy-transfer
processes, not energy stored inside the system.

**What this example trains.** Do not describe heat as something contained in a
system.

## Example 2: First Law with Signs

**Prompt.** A gas receives $500\ \mathrm{J}$ by heating and does
$120\ \mathrm{J}$ of work on the surroundings. Find the change in internal
energy.

**Solution.**

Use

$$
\Delta U=q+W,
$$

where $W$ is work done on the system.

Energy transferred to the gas by heating is

$$
q=+500\ \mathrm{J}.
$$

The gas does work on the surroundings, so work done on the gas is negative:

$$
W=-120\ \mathrm{J}.
$$

Therefore

$$
\Delta U=500-120=380\ \mathrm{J}.
$$

The gas internal energy increases by $380\ \mathrm{J}$.

**What this example trains.** Work done by the gas has the opposite sign from
work done on the gas.

## Example 3: Constant-Pressure Expansion

**Prompt.** A gas expands at constant pressure
$1.5 \times 10^5\ \mathrm{Pa}$ from
$2.0 \times 10^{-3}\ \mathrm{m^3}$ to
$5.0 \times 10^{-3}\ \mathrm{m^3}$. It receives
$800\ \mathrm{J}$ by heating. Find the work done by the gas, the work done on
the gas, and the change in internal energy.

**Solution.**

Volume change:

$$
\Delta V
=5.0 \times 10^{-3}-2.0 \times 10^{-3}
=3.0 \times 10^{-3}\ \mathrm{m^3}.
$$

Work done by the gas:

$$
W_{\text{by gas}}=p\Delta V
=(1.5 \times 10^5)(3.0 \times 10^{-3})
=450\ \mathrm{J}.
$$

Work done on the gas is the negative of this:

$$
W=-450\ \mathrm{J}.
$$

Using the first law,

$$
\Delta U=q+W=800-450=350\ \mathrm{J}.
$$

**What this example trains.** Expansion uses positive area for work done by
the gas, but negative work done on the gas.

## Example 4: Compression with No Heat Transfer

**Prompt.** A gas is compressed at constant pressure
$2.0 \times 10^5\ \mathrm{Pa}$. Its volume changes from
$4.0 \times 10^{-3}\ \mathrm{m^3}$ to
$2.5 \times 10^{-3}\ \mathrm{m^3}$. No energy is transferred by heating. Find
the change in internal energy.

**Solution.**

Volume change:

$$
\Delta V
=2.5 \times 10^{-3}-4.0 \times 10^{-3}
=-1.5 \times 10^{-3}\ \mathrm{m^3}.
$$

Work done by the gas:

$$
W_{\text{by gas}}=p\Delta V
=(2.0 \times 10^5)(-1.5 \times 10^{-3})
=-300\ \mathrm{J}.
$$

So work done on the gas is

$$
W=+300\ \mathrm{J}.
$$

Since $q=0$,

$$
\Delta U=0+300=300\ \mathrm{J}.
$$

The internal energy increases. For an ideal gas, this would correspond to a
temperature rise.

**What this example trains.** Compression means work is done on the gas.

## Example 5: Work from a $p$-$V$ Graph

**Prompt.** On a $p$-$V$ graph, a gas expands at constant pressure
$2.5 \times 10^5\ \mathrm{Pa}$ from
$1.0 \times 10^{-3}\ \mathrm{m^3}$ to
$3.0 \times 10^{-3}\ \mathrm{m^3}$. Find the area under the graph and state
what it represents.

**Solution.**

The area under a $p$-$V$ graph represents work done by the gas.

For constant pressure, the area is a rectangle:

$$
W_{\text{by gas}}=p\Delta V.
$$

Here

$$
\Delta V=2.0 \times 10^{-3}\ \mathrm{m^3}.
$$

So

$$
W_{\text{by gas}}
=(2.5 \times 10^5)(2.0 \times 10^{-3})
=500\ \mathrm{J}.
$$

For the first law convention in this note, work done on the gas is

$$
W=-500\ \mathrm{J}.
$$

**What this example trains.** Graph area gives work done by the gas, so convert
the sign before using $\Delta U=q+W$.

## Example 6: Constant-Volume Heating

**Prompt.** A gas in a rigid container receives $650\ \mathrm{J}$ by heating.
Find the work done and the change in internal energy.

**Solution.**

The container is rigid, so

$$
\Delta V=0.
$$

Therefore no boundary work is done:

$$
W=0.
$$

The first law gives

$$
\Delta U=q+W=650+0=650\ \mathrm{J}.
$$

All the energy transferred by heating increases the internal energy.

**What this example trains.** At constant volume, the first law simplifies
because there is no expansion or compression work.

## Example 7: Slow Isothermal Expansion of an Ideal Gas

**Prompt.** During a slow isothermal expansion of an ideal gas,
$240\ \mathrm{J}$ of work is done by the gas. Find $\Delta U$, $W$, and $q$.

**Solution.**

For an ideal gas, internal energy depends only on temperature. Isothermal means
constant temperature, so

$$
\Delta U=0.
$$

The gas does $240\ \mathrm{J}$ of work, so work done on the gas is

$$
W=-240\ \mathrm{J}.
$$

Use the first law:

$$
0=q-240.
$$

Hence

$$
q=+240\ \mathrm{J}.
$$

Energy must enter by heating to replace the energy transferred out as work.

**What this example trains.** In an isothermal ideal-gas process, work and
heating balance so that internal energy does not change.

## Example 8: Particle Explanation for Compression

**Prompt.** Explain in molecular terms why quickly compressing an insulated gas
can raise its temperature.

**Solution.**

Because the gas is insulated, there is negligible energy transfer by heating:

$$
q=0.
$$

During compression, the surroundings do work on the gas, so

$$
W>0.
$$

The first law gives

$$
\Delta U=W>0.
$$

At the particle level, molecules collide with a boundary moving inwards. They
can rebound with greater kinetic energy. The random kinetic energy of the
molecules increases, so the temperature rises.

**What this example trains.** A good thermodynamics explanation combines the
first law with a molecular picture.
