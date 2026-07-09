---
title: Magnetic Fields Worked Examples
subject: Physics
syllabus: 9702
parent: "[Magnetic Fields](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/fields
  - worked-examples
---

# Magnetic Fields Worked Examples

These examples model the standard CAIE route through magnetic field
representations, magnetic forces, Hall voltage, charged-particle motion,
magnetic fields due to currents, and electromagnetic induction.

## Source Route

- Syllabus: CAIE Physics 9702 section 20, Magnetic fields.
- Main subtopics: concept of a magnetic field, force on a current-carrying
  conductor, force on a moving charge, magnetic fields due to currents, and
  electromagnetic induction.
- Coursebook route: field-line patterns, motor effect, charged-particle
  circular motion, Hall probes, flux linkage, Faraday's law, and Lenz's law.

## Example 1: Field Lines and Current Direction

**Prompt.** Describe the magnetic field pattern around a long straight wire
carrying current upwards, and state how the direction is found.

**Solution.**

The field lines are concentric circles around the wire. Their spacing is closer
near the wire, so the field is stronger near the wire and weaker farther away.

Use the right-hand grip rule: point the right thumb in the direction of the
conventional current. The curled fingers show the direction of the magnetic
field lines.

If the current is reversed, the direction of every field line is reversed. The
shape of the pattern stays the same.

**What this example trains.** Field lines show direction and relative field
strength. A magnetic field due to a current is not drawn as straight lines
parallel to the current.

## Example 2: Force on a Current-Carrying Conductor

**Prompt.** A straight wire of length $0.18\ \mathrm{m}$ carries a current of
$2.5\ \mathrm{A}$ in a uniform magnetic field of flux density
$0.40\ \mathrm{T}$. The wire is perpendicular to the field. Find the force on
the wire. Then find the force if the angle between the wire and the field is
$30^\circ$.

**Solution.**

Use

$$
F=BIL\sin\theta.
$$

For a perpendicular wire, $\theta=90^\circ$, so

$$
F=(0.40)(2.5)(0.18)\sin 90^\circ
=0.18\ \mathrm{N}.
$$

At $30^\circ$,

$$
F=(0.40)(2.5)(0.18)\sin 30^\circ
=0.090\ \mathrm{N}.
$$

The direction is found using Fleming's left-hand rule. If the current or field
is reversed, the force direction is reversed.

**What this example trains.** The angle in $F=BIL\sin\theta$ is the angle
between the conductor and the magnetic field, not the angle to the force.

## Example 3: Defining Magnetic Flux Density

**Prompt.** A wire of length $8.0\ \mathrm{cm}$ is at right angles to a
magnetic field. It carries a current of $3.0\ \mathrm{A}$ and experiences a
force of $0.060\ \mathrm{N}$. Find the magnetic flux density.

**Solution.**

The wire is at right angles to the field, so $\sin\theta=1$ and

$$
B=\frac{F}{IL}.
$$

Convert the length:

$$
8.0\ \mathrm{cm}=0.080\ \mathrm{m}.
$$

Therefore

$$
B=\frac{0.060}{(3.0)(0.080)}
=0.25\ \mathrm{T}.
$$

This matches the definition of magnetic flux density: force per unit current
per unit length on a wire placed at right angles to the field.

**What this example trains.** The tesla is defined using the right-angle case,
so the $\sin\theta$ factor is not present in the definition.

## Example 4: Hall Voltage

**Prompt.** A semiconductor Hall probe has charge-carrier number density
$5.0 \times 10^{22}\ \mathrm{m^{-3}}$ and thickness
$0.50\ \mathrm{mm}$. A current of $20\ \mathrm{mA}$ passes through it in a
magnetic field of flux density $0.25\ \mathrm{T}$. Find the Hall voltage,
using $q=1.60 \times 10^{-19}\ \mathrm{C}$.

**Solution.**

Use

$$
V_H=\frac{BI}{ntq}.
$$

Convert the current and thickness:

$$
20\ \mathrm{mA}=2.0 \times 10^{-2}\ \mathrm{A},
$$

$$
0.50\ \mathrm{mm}=5.0 \times 10^{-4}\ \mathrm{m}.
$$

Then

$$
V_H=
\frac{(0.25)(2.0 \times 10^{-2})}
{(5.0 \times 10^{22})(5.0 \times 10^{-4})(1.60 \times 10^{-19})}
=1.25 \times 10^{-3}\ \mathrm{V}.
$$

So

$$
V_H=1.25\ \mathrm{mV}.
$$

A Hall probe gives its maximum reading when the magnetic field is perpendicular
to the active face of the probe.

**What this example trains.** Hall voltage comes from magnetic force separating
moving charge carriers until the electric force balances it.

## Example 5: Force on a Moving Charge

**Prompt.** A proton moves at $4.0 \times 10^6\ \mathrm{m\ s^{-1}}$
perpendicular to a uniform magnetic field of flux density $0.12\ \mathrm{T}$.
Find the magnetic force on the proton. Explain what happens to its speed.

**Solution.**

For a moving charge,

$$
F=BQv\sin\theta.
$$

Here $\theta=90^\circ$, so

$$
F=(0.12)(1.60 \times 10^{-19})(4.0 \times 10^6)
=7.68 \times 10^{-14}\ \mathrm{N}.
$$

The force is perpendicular to the velocity and to the magnetic field. It
changes the direction of the velocity, but it does no work on the proton, so
the proton's speed is unchanged.

**What this example trains.** A magnetic field can change direction without
changing kinetic energy when the force is perpendicular to the motion.

## Example 6: Circular Motion and Velocity Selection

**Prompt.** A proton enters a uniform magnetic field of flux density
$0.20\ \mathrm{T}$ at right angles with speed
$3.0 \times 10^6\ \mathrm{m\ s^{-1}}$. Find the radius of its path. Then find
the selected speed in crossed electric and magnetic fields where
$E=1.8 \times 10^4\ \mathrm{V\ m^{-1}}$ and $B=0.060\ \mathrm{T}$.

**Solution.**

In the circular path, magnetic force provides centripetal force:

$$
BQv=\frac{mv^2}{r}.
$$

So

$$
r=\frac{mv}{BQ}.
$$

Substitute $m=1.67 \times 10^{-27}\ \mathrm{kg}$ and
$Q=1.60 \times 10^{-19}\ \mathrm{C}$:

$$
r=
\frac{(1.67 \times 10^{-27})(3.0 \times 10^6)}
{(0.20)(1.60 \times 10^{-19})}
=0.157\ \mathrm{m}.
$$

For a velocity selector, undeflected particles have equal electric and
magnetic force magnitudes:

$$
QE=BQv.
$$

Thus

$$
v=\frac{E}{B}
=\frac{1.8 \times 10^4}{0.060}
=3.0 \times 10^5\ \mathrm{m\ s^{-1}}.
$$

**What this example trains.** Circular motion uses a magnetic force as the
centripetal force; velocity selection uses cancellation between electric and
magnetic forces.

## Example 7: Fields Due to Currents and Wire Forces

**Prompt.** Two long parallel wires carry currents in the same direction.
Explain why the wires attract. State what changes if one current is reversed.

**Solution.**

Each wire produces a magnetic field around itself. The other wire is a
current-carrying conductor placed in that magnetic field, so it experiences a
force.

Using the right-hand grip rule for the field around one wire and Fleming's
left-hand rule for the force on the other wire shows that currents in the same
direction attract. The forces on the two wires have the same magnitude and
opposite directions.

If one current is reversed, the magnetic field direction due to that wire is
reversed. Fleming's left-hand rule then gives a force away from the other wire,
so currents in opposite directions repel.

**What this example trains.** Forces between current-carrying conductors are
not a new kind of force law in this syllabus; they follow from the magnetic
field due to one current acting on the other current.

## Example 8: Flux Linkage and Faraday's Law

**Prompt.** A coil has $150$ turns and cross-sectional area
$2.0 \times 10^{-3}\ \mathrm{m^2}$. The magnetic field is perpendicular to
the plane of the coil. The magnetic flux density increases uniformly from
$0.10\ \mathrm{T}$ to $0.45\ \mathrm{T}$ in $0.20\ \mathrm{s}$. Find the
magnitude of the induced e.m.f.

**Solution.**

For a field perpendicular to the plane of the coil, the field is parallel to
the normal to the area, so

$$
\Phi=BA.
$$

The change in magnetic flux density is

$$
\Delta B=0.45-0.10=0.35\ \mathrm{T}.
$$

The change in flux linkage is

$$
\Delta(N\Phi)=N A\Delta B
=(150)(2.0 \times 10^{-3})(0.35)
=0.105\ \mathrm{Wb\,turn}.
$$

Faraday's law gives

$$
|\mathcal{E}|=
\left|\frac{\Delta(N\Phi)}{\Delta t}\right|
=\frac{0.105}{0.20}
=0.525\ \mathrm{V}.
$$

Lenz's law determines the direction of the induced e.m.f.: its effect opposes
the increase in flux linkage.

**What this example trains.** Induced e.m.f. depends on the rate of change of
flux linkage, not only on the final magnetic flux.

## Example 9: Moving Conductor and Lenz's Law

**Prompt.** A metal rod of length $0.40\ \mathrm{m}$ moves at
$5.0\ \mathrm{m\ s^{-1}}$ at right angles to a uniform magnetic field of
flux density $0.30\ \mathrm{T}$. The rod is part of a circuit of resistance
$3.0\ \Omega$. Find the induced e.m.f., the current, and the magnetic force
that opposes the motion.

**Solution.**

For a straight conductor moving perpendicular to the field,

$$
\mathcal{E}=BLv.
$$

So

$$
\mathcal{E}=(0.30)(0.40)(5.0)=0.60\ \mathrm{V}.
$$

The induced current is

$$
I=\frac{\mathcal{E}}{R}
=\frac{0.60}{3.0}
=0.20\ \mathrm{A}.
$$

The magnetic force on the current-carrying rod is

$$
F=BIL
=(0.30)(0.20)(0.40)
=2.4 \times 10^{-2}\ \mathrm{N}.
$$

By Lenz's law, this force is in the direction that opposes the motion producing
the induced current. The mechanical power needed is

$$
Fv=(2.4 \times 10^{-2})(5.0)=0.12\ \mathrm{W},
$$

which matches the electrical power dissipated:

$$
I^2R=(0.20)^2(3.0)=0.12\ \mathrm{W}.
$$

**What this example trains.** Lenz's law is an energy check: the induced effect
opposes the change that produces it.
