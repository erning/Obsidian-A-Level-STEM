---
title: Forces, Density and Pressure Worked Examples
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/04 Forces Density and Pressure/00 Overview|Forces, Density and Pressure]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/mechanics
  - worked-examples
---

# Forces, Density and Pressure Worked Examples

These examples show how to decide whether a force problem is about translation,
rotation, pressure, or fluid upthrust.

Take $g=9.81\ \mathrm{m\ s^{-2}}$ where needed.

## Example 1: Moment of an Angled Force

**Prompt.** A force of $120\ \mathrm{N}$ is applied to a spanner
$0.35\ \mathrm{m}$ from the centre of a nut. The force makes an angle of
$60^\circ$ with the spanner. Find the moment about the nut.

### Solution

The moment is

$$
M=Fd_\perp.
$$

The perpendicular distance from the pivot to the line of action is

$$
d_\perp=0.35\sin60^\circ.
$$

So

$$
M=(120)(0.35\sin60^\circ)
=36.4\ \mathrm{N\ m}.
$$

### Check

If the force were perpendicular to the spanner, the moment would be
$120(0.35)=42\ \mathrm{N\ m}$. The angled force gives a smaller moment, as
expected.

## Example 2: Principle of Moments with a Beam

**Prompt.** A light horizontal beam is pivoted at its left end. A
$120\ \mathrm{N}$ load acts $1.5\ \mathrm{m}$ from the pivot. An upward force is
applied $3.0\ \mathrm{m}$ from the pivot to keep the beam horizontal. Find the
upward force and the force exerted by the pivot on the beam.

### Solution

Take moments about the pivot. The pivot force has no moment about the pivot
because its line of action passes through the pivot.

Clockwise moment from the load:

$$
120(1.5)=180\ \mathrm{N\ m}.
$$

For equilibrium, the anticlockwise moment from the upward force $F$ must be the
same:

$$
F(3.0)=180.
$$

So

$$
F=60\ \mathrm{N}.
$$

For vertical force equilibrium,

$$
R+60-120=0,
$$

where $R$ is the vertical force from the pivot. Hence

$$
R=60\ \mathrm{N}.
$$

### Check

Both equilibrium conditions are needed: zero resultant moment gives the applied
force, and zero resultant force gives the pivot force.

## Example 3: Triangle of Forces

**Prompt.** A sign of weight $49.1\ \mathrm{N}$ is held by two light strings.
The left string makes $30^\circ$ with the horizontal and the right string makes
$60^\circ$ with the horizontal. Find the two tensions.

### Solution

Let the left tension be $T_L$ and the right tension be $T_R$.

Horizontal equilibrium gives

$$
T_L\cos30^\circ=T_R\cos60^\circ.
$$

So

$$
T_R=\frac{\cos30^\circ}{\cos60^\circ}T_L
=1.732T_L.
$$

Vertical equilibrium gives

$$
T_L\sin30^\circ+T_R\sin60^\circ=49.1.
$$

Substitute for $T_R$:

$$
T_L(0.500)+(1.732T_L)(0.866)=49.1.
$$

So

$$
2.00T_L=49.1,
$$

and

$$
T_L=24.5\ \mathrm{N}.
$$

Then

$$
T_R=42.5\ \mathrm{N}.
$$

### Check

The steeper right string has the larger tension because it also balances the
horizontal component of the shallower left string.

## Example 4: Torque of a Couple

**Prompt.** Two equal and opposite forces of $18\ \mathrm{N}$ act on a steering
wheel. The perpendicular distance between their lines of action is
$0.42\ \mathrm{m}$. Find the torque of the couple.

### Solution

The torque of a couple is

$$
\tau=Fd,
$$

where $F$ is one of the forces and $d$ is the perpendicular separation between
the forces.

Thus

$$
\tau=(18)(0.42)=7.56\ \mathrm{N\ m}.
$$

### Check

Do not double the answer. The formula already uses the separation between the
two forces.

## Example 5: Density and Unit Conversion

**Prompt.** A metal cylinder has mass $0.540\ \mathrm{kg}$ and volume
$30.0\ \mathrm{cm^3}$. Find its density in $\mathrm{kg\ m^{-3}}$.

### Solution

Convert the volume:

$$
30.0\ \mathrm{cm^3}
=30.0\times 10^{-6}\ \mathrm{m^3}
=3.00\times 10^{-5}\ \mathrm{m^3}.
$$

Density is

$$
\rho=\frac{m}{V}.
$$

So

$$
\rho=\frac{0.540}{3.00\times 10^{-5}}
=1.80\times 10^4\ \mathrm{kg\ m^{-3}}.
$$

### Check

The density is much greater than water, so a dense metal is plausible.

## Example 6: Pressure from Contact Area

**Prompt.** A person of weight $650\ \mathrm{N}$ stands on two shoes with total
contact area $0.050\ \mathrm{m^2}$. Find the pressure on the floor. Then find
the pressure if the same weight is supported by narrow heels of total area
$2.0\times 10^{-3}\ \mathrm{m^2}$.

### Solution

Pressure is normal force per unit area:

$$
p=\frac{F}{A}.
$$

For the shoes,

$$
p=\frac{650}{0.050}
=1.3\times 10^4\ \mathrm{Pa}.
$$

For the narrow heels,

$$
p=\frac{650}{2.0\times 10^{-3}}
=3.25\times 10^5\ \mathrm{Pa}.
$$

### Check

The force is the same, but the smaller area gives a much larger pressure.

## Example 7: Hydrostatic Pressure Difference

**Prompt.** Find the pressure difference between the surface of a freshwater
lake and a point $12\ \mathrm{m}$ below the surface. Use
$\rho=1000\ \mathrm{kg\ m^{-3}}$.

### Solution

Use

$$
\Delta p=\rho g\Delta h.
$$

Thus

$$
\Delta p=(1000)(9.81)(12)
=1.18\times 10^5\ \mathrm{Pa}.
$$

If atmospheric pressure is required, it must be added separately. The equation
above gives only the pressure difference due to the water.

### Check

Pressure increases with depth, so the pressure at $12\ \mathrm{m}$ is greater
than the pressure at the surface.

## Example 8: Upthrust and Apparent Weight

**Prompt.** A block has mass $0.80\ \mathrm{kg}$ and volume
$3.0\times 10^{-4}\ \mathrm{m^3}$. It is fully submerged in water of density
$1000\ \mathrm{kg\ m^{-3}}$. Find the upthrust and the apparent weight.

### Solution

The weight of the block is

$$
W=mg=(0.80)(9.81)=7.85\ \mathrm{N}.
$$

The upthrust is the weight of displaced water:

$$
F_{\text{upthrust}}=\rho gV.
$$

So

$$
F_{\text{upthrust}}
=(1000)(9.81)(3.0\times 10^{-4})
=2.94\ \mathrm{N}.
$$

The apparent weight is

$$
7.85-2.94=4.91\ \mathrm{N}.
$$

### Check

The apparent weight is smaller than the true weight because the upthrust acts
upwards.

## Example 9: Floating Fraction

**Prompt.** A wooden block of density $600\ \mathrm{kg\ m^{-3}}$ floats in
water of density $1000\ \mathrm{kg\ m^{-3}}$. Find the fraction of its volume
that is submerged.

### Solution

For a floating object,

$$
\text{upthrust}=\text{weight}.
$$

Let the total volume be $V$ and the submerged volume be $V_s$. Then

$$
\rho_{\text{water}}gV_s=\rho_{\text{wood}}gV.
$$

Cancel $g$ and divide by $V$:

$$
\frac{V_s}{V}
=\frac{\rho_{\text{wood}}}{\rho_{\text{water}}}
=\frac{600}{1000}
=0.60.
$$

So $60\%$ of the block's volume is submerged.

### Check

The wood is less dense than water, so the block floats with only part of its
volume below the surface.
