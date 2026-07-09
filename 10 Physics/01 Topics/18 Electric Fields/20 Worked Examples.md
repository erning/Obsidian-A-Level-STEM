---
title: Electric Fields Worked Examples
subject: Physics
syllabus: 9702
parent: "[Electric Fields](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/fields
  - worked-examples
---

# Electric Fields Worked Examples

These examples model the standard CAIE route through field strength, uniform
fields, Coulomb's law, point-charge fields, electric potential, potential
energy, potential gradient, field lines, and equipotentials.

## Source Route

- Syllabus: CAIE Physics 9702 section 18, Electric fields.
- Main subtopics: field lines, uniform electric fields, point-charge force,
  point-charge field, electric potential, and electric potential energy.
- Coursebook route: parallel plates, charged-particle motion, Coulomb's law,
  radial fields, potential, equipotentials, and potential gradient.

Use

$$
\frac{1}{4\pi\varepsilon_0}
=8.99 \times 10^9\ \mathrm{N\ m^2\ C^{-2}}
$$

unless a question gives another value.

## Example 1: Force in an Electric Field

**Prompt.** A uniform electric field has strength
$2.0 \times 10^4\ \mathrm{N\ C^{-1}}$ to the right. Find the force on a
$+3.0\ \mu\mathrm{C}$ charge and state the force direction. Then state the
direction of the force on a negative charge placed in the same field.

**Solution.**

Electric field strength is force per unit positive charge:

$$
E=\frac{F}{q}.
$$

So

$$
F=qE=(3.0 \times 10^{-6})(2.0 \times 10^4)
=6.0 \times 10^{-2}\ \mathrm{N}.
$$

The positive charge feels a force to the right, in the direction of the field.
A negative charge feels a force opposite to the field direction.

**What this example trains.** Electric field direction is defined using a
positive test charge.

## Example 2: Parallel Plates

**Prompt.** Parallel plates are separated by $1.5 \times 10^{-2}\ \mathrm{m}$
and have potential difference $600\ \mathrm{V}$. Find the field strength
between the plates and the force on a proton.

**Solution.**

For a uniform field between parallel plates,

$$
E=\frac{\Delta V}{\Delta d}.
$$

Thus

$$
E=\frac{600}{1.5 \times 10^{-2}}
=4.0 \times 10^4\ \mathrm{V\ m^{-1}}.
$$

This is also $4.0 \times 10^4\ \mathrm{N\ C^{-1}}$.

For a proton,

$$
q=+1.60 \times 10^{-19}\ \mathrm{C}.
$$

So

$$
F=qE=(1.60 \times 10^{-19})(4.0 \times 10^4)
=6.4 \times 10^{-15}\ \mathrm{N}.
$$

The force is in the direction of the electric field.

**What this example trains.** $\mathrm{V\ m^{-1}}$ and $\mathrm{N\ C^{-1}}$
are equivalent units for electric field strength.

## Example 3: Charged-Particle Acceleration

**Prompt.** An electron is placed at rest in a uniform electric field of
strength $5.0 \times 10^4\ \mathrm{N\ C^{-1}}$. Find the magnitude of its
acceleration. Use $e=1.60 \times 10^{-19}\ \mathrm{C}$ and
$m_e=9.11 \times 10^{-31}\ \mathrm{kg}$.

**Solution.**

Force magnitude:

$$
F=eE=(1.60 \times 10^{-19})(5.0 \times 10^4)
=8.0 \times 10^{-15}\ \mathrm{N}.
$$

Acceleration magnitude:

$$
a=\frac{F}{m_e}
=
\frac{8.0 \times 10^{-15}}{9.11 \times 10^{-31}}
=8.8 \times 10^{15}\ \mathrm{m\ s^{-2}}.
$$

The electron has negative charge, so its acceleration is opposite to the
electric field direction.

**What this example trains.** Use the sign of charge for direction after
finding the magnitude.

## Example 4: Coulomb's Law

**Prompt.** Charges $+2.0\ \mu\mathrm{C}$ and $-3.0\ \mu\mathrm{C}$ are
separated by $0.20\ \mathrm{m}$ in free space. Find the force magnitude and
state whether the force is attractive or repulsive.

**Solution.**

Use Coulomb's law for magnitudes:

$$
F=\frac{|Q_1Q_2|}{4\pi\varepsilon_0r^2}.
$$

Substitute:

$$
F=
\frac{(8.99 \times 10^9)(2.0 \times 10^{-6})(3.0 \times 10^{-6})}
{(0.20)^2}
=1.35\ \mathrm{N}.
$$

The charges have opposite signs, so the force is attractive.

**What this example trains.** Magnitude comes from the absolute values; the
type of force comes from the signs.

## Example 5: Field and Potential of a Point Charge

**Prompt.** Find the electric field strength and electric potential at a point
$0.30\ \mathrm{m}$ from a charge $+4.0\ \mathrm{nC}$.

**Solution.**

For a point charge,

$$
E=\frac{Q}{4\pi\varepsilon_0r^2}.
$$

Magnitude:

$$
E=
\frac{(8.99 \times 10^9)(4.0 \times 10^{-9})}
{(0.30)^2}
=4.0 \times 10^2\ \mathrm{N\ C^{-1}}.
$$

The field is directed away from the positive charge.

Potential:

$$
V=\frac{Q}{4\pi\varepsilon_0r}
=
\frac{(8.99 \times 10^9)(4.0 \times 10^{-9})}
{0.30}
=1.20 \times 10^2\ \mathrm{V}.
$$

**What this example trains.** Point-charge field follows $1/r^2$, while
point-charge potential follows $1/r$.

## Example 6: Electric Potential Energy

**Prompt.** A charge $-2.0\ \mu\mathrm{C}$ is placed at the point in Example 5,
where $V=120\ \mathrm{V}$. Find its electric potential energy.

**Solution.**

Electric potential energy is

$$
E_p=qV.
$$

So

$$
E_p=(-2.0 \times 10^{-6})(120)
=-2.4 \times 10^{-4}\ \mathrm{J}.
$$

The value is negative because the test charge is negative while the potential
is positive. This corresponds to attraction between unlike charges.

**What this example trains.** Potential is a property of the point; potential
energy also depends on the charge placed there.

## Example 7: Potential Gradient

**Prompt.** Electric potential falls uniformly from $600\ \mathrm{V}$ to
$0\ \mathrm{V}$ over a distance $0.020\ \mathrm{m}$. Find the electric field
strength and direction.

**Solution.**

Magnitude:

$$
E=\frac{\Delta V}{\Delta d}
=\frac{600}{0.020}
=3.0 \times 10^4\ \mathrm{V\ m^{-1}}.
$$

The electric field points in the direction of decreasing potential. Therefore
it points from the $600\ \mathrm{V}$ side towards the $0\ \mathrm{V}$ side.

In one dimension,

$$
E=-\frac{\Delta V}{\Delta d}
$$

when direction is included.

**What this example trains.** Electric field is the negative potential
gradient.

## Example 8: Field Lines and Equipotentials

**Prompt.** Describe the field lines and equipotentials between two large
parallel plates, one positive and one negative.

**Solution.**

Away from the edges, the electric field is uniform. Field lines are straight,
parallel, equally spaced, and directed from the positive plate to the negative
plate.

Equipotentials are surfaces of constant potential. Between parallel plates,
they are planes parallel to the plates. They are perpendicular to the field
lines.

Moving a charge along one equipotential requires no work because

$$
\Delta V=0.
$$

**What this example trains.** Field lines and equipotentials describe the same
field in complementary ways.
