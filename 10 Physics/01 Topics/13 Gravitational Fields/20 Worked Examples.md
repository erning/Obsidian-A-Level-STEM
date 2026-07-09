---
title: Gravitational Fields Worked Examples
subject: Physics
syllabus: 9702
parent: "[Gravitational Fields](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/fields
  - worked-examples
---

# Gravitational Fields Worked Examples

These examples model the standard CAIE route through gravitational field
strength, Newton's law of gravitation, radial fields, circular orbits,
geostationary satellites, gravitational potential, and gravitational potential
energy.

## Source Route

- Syllabus: CAIE Physics 9702 section 13, Gravitational fields.
- Main subtopics: gravitational field, point-mass force, point-mass field,
  circular orbits, geostationary orbit, gravitational potential, and
  gravitational potential energy.
- Coursebook route: field lines, inverse-square force, uniform-sphere
  approximation, potential wells, and satellite orbits.

Take

$$
G=6.67 \times 10^{-11}\ \mathrm{N\ m^2\ kg^{-2}}
$$

unless a question gives another value.

## Example 1: Field Strength as Force per Unit Mass

**Prompt.** A $3.0\ \mathrm{kg}$ mass is placed in a gravitational field of
strength $1.6\ \mathrm{N\ kg^{-1}}$. Find the gravitational force on the
mass, and state its direction.

**Solution.**

Gravitational field strength is force per unit mass:

$$
g=\frac{F}{m}.
$$

Therefore

$$
F=mg=(3.0)(1.6)=4.8\ \mathrm{N}.
$$

The force is in the direction of the gravitational field. Around a planet, that
direction is towards the centre of the planet.

**What this example trains.** Field strength is a force idea. Its unit
$\mathrm{N\ kg^{-1}}$ means newtons per kilogram of test mass.

## Example 2: Newton's Law of Gravitation

**Prompt.** A satellite of mass $1000\ \mathrm{kg}$ is at distance
$7.0 \times 10^6\ \mathrm{m}$ from the centre of the Earth. Use
$M_{\mathrm{E}}=5.97 \times 10^{24}\ \mathrm{kg}$ to find the gravitational
force on the satellite.

**Solution.**

Use the centre-to-centre distance in Newton's law of gravitation:

$$
F=\frac{G M_{\mathrm{E}}m}{r^2}.
$$

Substitute:

$$
F=
\frac{(6.67 \times 10^{-11})(5.97 \times 10^{24})(1000)}
{(7.0 \times 10^6)^2}.
$$

So

$$
F=8.1 \times 10^3\ \mathrm{N}.
$$

The force is attractive, so it acts towards the centre of the Earth.

**What this example trains.** For a spherical body, use distance from the
centre when the point is outside the body.

## Example 3: Deriving and Using $g=\frac{GM}{r^2}$

**Prompt.** Derive the field strength due to a point mass $M$, and use it to
explain why the field strength at distance $2R$ from a planet's centre is one
quarter of the value at distance $R$.

**Solution.**

The force on a small test mass $m$ at distance $r$ from a point mass $M$ is

$$
F=\frac{GMm}{r^2}.
$$

Field strength is force per unit mass:

$$
g=\frac{F}{m}.
$$

Therefore

$$
g=\frac{GM}{r^2}.
$$

At $r=R$,

$$
g_R=\frac{GM}{R^2}.
$$

At $r=2R$,

$$
g_{2R}=\frac{GM}{(2R)^2}
=\frac{GM}{4R^2}
=\frac{g_R}{4}.
$$

**What this example trains.** Force and field strength both follow the
inverse-square dependence.

## Example 4: Circular Orbit Speed and Period

**Prompt.** A satellite orbits the Earth in a circle of radius
$7.0 \times 10^6\ \mathrm{m}$. Use
$M_{\mathrm{E}}=5.97 \times 10^{24}\ \mathrm{kg}$ to find its orbital speed
and period.

**Solution.**

Gravity provides the centripetal force:

$$
\frac{GM_{\mathrm{E}}m}{r^2}
=
\frac{mv^2}{r}.
$$

The satellite mass cancels:

$$
v=\sqrt{\frac{GM_{\mathrm{E}}}{r}}.
$$

So

$$
v=
\sqrt{\frac{(6.67 \times 10^{-11})(5.97 \times 10^{24})}
{7.0 \times 10^6}}
=7.5 \times 10^3\ \mathrm{m\ s^{-1}}.
$$

The period is

$$
T=\frac{2\pi r}{v}
=
\frac{2\pi(7.0 \times 10^6)}{7.54 \times 10^3}
=5.8 \times 10^3\ \mathrm{s}.
$$

This is about $97\ \mathrm{min}$.

**What this example trains.** In a circular orbit, the satellite is in free
fall and gravity is the inward resultant.

## Example 5: Geostationary Orbit Radius

**Prompt.** Estimate the radius of a geostationary orbit around the Earth.
Use $T=24.0\ \mathrm{h}$ and
$M_{\mathrm{E}}=5.97 \times 10^{24}\ \mathrm{kg}$.

**Solution.**

For a circular orbit,

$$
T^2=\frac{4\pi^2r^3}{GM_{\mathrm{E}}}.
$$

Rearrange:

$$
r^3=\frac{GM_{\mathrm{E}}T^2}{4\pi^2}.
$$

Convert the period:

$$
T=24.0 \times 3600=86400\ \mathrm{s}.
$$

Then

$$
r=
\left(
\frac{(6.67 \times 10^{-11})(5.97 \times 10^{24})(86400)^2}
{4\pi^2}
\right)^{1/3}.
$$

So

$$
r=4.22 \times 10^7\ \mathrm{m}
$$

from the Earth's centre. The height above the surface is about

$$
4.22 \times 10^7 - 6.37 \times 10^6
=3.58 \times 10^7\ \mathrm{m}.
$$

A geostationary orbit must also be west to east and directly above the Equator.

**What this example trains.** Geostationary radius is measured from the Earth's
centre, not from the surface.

## Example 6: Gravitational Potential and Potential Energy

**Prompt.** Find the gravitational potential at the Earth's surface using
$M_{\mathrm{E}}=5.97 \times 10^{24}\ \mathrm{kg}$ and
$R_{\mathrm{E}}=6.37 \times 10^6\ \mathrm{m}$. Hence find the gravitational
potential energy of a $500\ \mathrm{kg}$ spacecraft at the surface.

**Solution.**

For a point mass or a uniform sphere outside its surface,

$$
\phi=-\frac{GM}{r}.
$$

At the Earth's surface,

$$
\phi=
-\frac{(6.67 \times 10^{-11})(5.97 \times 10^{24})}
{6.37 \times 10^6}
=-6.25 \times 10^7\ \mathrm{J\ kg^{-1}}.
$$

Potential energy is

$$
E_p=m\phi.
$$

So

$$
E_p=(500)(-6.25 \times 10^7)
=-3.13 \times 10^{10}\ \mathrm{J}.
$$

The negative sign appears because zero potential energy is chosen at infinite
separation.

**What this example trains.** Gravitational potential is energy per unit mass,
not force per unit mass.

## Example 7: Energy Change Between Two Radii

**Prompt.** A $1000\ \mathrm{kg}$ satellite is moved from
$r_1=7.0 \times 10^6\ \mathrm{m}$ to
$r_2=1.40 \times 10^7\ \mathrm{m}$ from the Earth's centre. Find the change in
gravitational potential energy.

**Solution.**

Use

$$
\Delta E_p
=
GMm\left(\frac{1}{r_1}-\frac{1}{r_2}\right).
$$

Substitute:

$$
\Delta E_p
=
(6.67 \times 10^{-11})(5.97 \times 10^{24})(1000)
\left(
\frac{1}{7.0 \times 10^6}
-
\frac{1}{1.40 \times 10^7}
\right).
$$

This gives

$$
\Delta E_p=2.8 \times 10^{10}\ \mathrm{J}.
$$

The change is positive because the satellite is moved farther from the Earth,
so its potential energy becomes less negative.

**What this example trains.** Energy must be supplied to move a bound mass
outwards in a gravitational field.

## Example 8: Field Strength Versus Potential

**Prompt.** At distance $r$ from a point mass, the field strength is $g$ and
the potential is $\phi$. What are the field strength and potential at distance
$2r$?

**Solution.**

For field strength,

$$
g=\frac{GM}{r^2}.
$$

Doubling the distance gives

$$
g_{2r}
=
\frac{GM}{(2r)^2}
=\frac{g}{4}.
$$

For gravitational potential,

$$
\phi=-\frac{GM}{r}.
$$

Doubling the distance gives

$$
\phi_{2r}
=
-\frac{GM}{2r}
=
\frac{\phi}{2}.
$$

Since $\phi$ is negative, $\frac{\phi}{2}$ is less negative and closer to
zero.

**What this example trains.** Field strength is inverse-square; potential is
inverse-distance.
