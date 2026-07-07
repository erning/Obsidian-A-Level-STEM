---
title: Gravitational Fields Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/13 Gravitational Fields/00 Overview|Gravitational Fields]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/fields
  - lecture-notes
---

# Gravitational Fields Lecture Notes

A gravitational field is a way of describing how a mass affects the space around it. If another mass is placed in that space, it experiences a gravitational force. This topic uses two related but different ideas: gravitational field strength, which is force per unit mass, and gravitational potential, which is potential energy per unit mass.

Keep the distinction clear:

- Field strength tells you about force.
- Potential tells you about energy.

## Source Route

- Primary syllabus source: CAIE Physics 9702, Topic 13 Gravitational fields.
- Main subtopics: gravitational field strength, Newton's law of gravitation, field of a point mass, circular orbits, geostationary orbits, gravitational potential, and gravitational potential energy.
- Coursebook route: field lines, inverse-square force, point mass fields, near-surface uniform field approximation, potential wells, and satellite orbits.
- Useful earlier knowledge: force, weight, circular motion, work done, energy, inverse-square relationships, and vectors.

## Visual Guide

![[assets/generated/physics/gravitational-fields.svg]]

The visual guide separates two pictures: field lines show force direction and relative field strength; the potential curve shows energy per unit mass and is negative when zero is chosen at infinity.

## 1. Gravitational Fields and Field Lines

A gravitational field is an example of a field of force. A mass creates a gravitational field around it, and another mass placed in the field experiences an attractive force.

Field lines represent a gravitational field:

- The direction of a field line shows the direction of the gravitational force on a small test mass.
- The spacing of the field lines shows the strength of the field. Closer lines mean a stronger field.
- Around a spherical mass, the field lines are radial and point towards the centre.

Close to the Earth's surface, over distances small compared with the Earth's radius, the field lines are almost parallel and equally spaced. The field can then be treated as uniform, and $g$ is approximately constant.

Far from the Earth, the radial nature of the field matters. The field gets weaker as distance from the Earth's centre increases.

## 2. Gravitational Field Strength

Gravitational field strength at a point is the gravitational force per unit mass on a small test mass placed at that point.

$$
g = \frac{F}{m}
$$

where:

- $g$ is gravitational field strength in $\text{N kg}^{-1}$
- $F$ is gravitational force in $\text{N}$
- $m$ is the mass experiencing the force in $\text{kg}$

The unit $\text{N kg}^{-1}$ is equivalent to $\text{m s}^{-2}$, because

$$
1\ \text{N kg}^{-1} = 1\ \text{m s}^{-2}
$$

Near the Earth's surface, $g \approx 9.81\ \text{N kg}^{-1}$, so a mass of $1\ \text{kg}$ has weight about $9.81\ \text{N}$.

Field strength is a vector. Its direction is the direction of the gravitational force on a mass. Around a planet, this direction is towards the planet's centre.

## 3. Newton's Law of Gravitation

Newton's law of gravitation states that any two point masses attract each other with a force that is directly proportional to the product of their masses and inversely proportional to the square of their separation.

For two point masses $m_1$ and $m_2$ separated by distance $r$:

$$
F = \frac{Gm_1m_2}{r^2}
$$

where

$$
G = 6.67 \times 10^{-11}\ \text{N m}^2\text{ kg}^{-2}
$$

The force is attractive. Each mass exerts a force of the same magnitude on the other, but in the opposite direction.

The word point mass matters. For real spherical bodies, a uniform sphere acts, for points outside it, as if all its mass were concentrated at its centre. This is why you use centre-to-centre distance when calculating the gravitational force between planets, moons, or satellites.

The inverse-square relationship means:

- doubling $r$ makes the force one quarter as large
- tripling $r$ makes the force one ninth as large
- the force never becomes exactly zero at a finite distance

## 4. Field Strength of a Point Mass

The gravitational field strength due to a mass $M$ at distance $r$ from its centre can be derived from Newton's law.

The force on a small test mass $m$ is

$$
F = \frac{GMm}{r^2}
$$

By definition,

$$
g = \frac{F}{m}
$$

so

$$
g = \frac{GM}{r^2}
$$

This gives the magnitude of the field strength. The direction is towards the mass $M$.

Use this equation when the source mass can be treated as a point mass or when you are outside a uniform spherical mass.

Near the Earth's surface, $r$ is approximately the Earth's radius $R$. If the height $h$ is small compared with $R$, then $R + h$ is almost the same as $R$, so $g$ changes very little. That is why $g$ is approximately constant for small changes in height near the Earth's surface.

## 5. Weight and Free Fall

Weight is the gravitational force on a mass:

$$
W = mg
$$

This equation uses the local value of $g$. On the Moon or another planet, the same object has the same mass but a different weight because the gravitational field strength is different.

The quantity $g$ can also be interpreted as the acceleration of free fall. If the only force on an object is gravity, then

$$
F = mg
$$

and Newton's second law gives

$$
F = ma
$$

so

$$
a = g
$$

This is why $\text{N kg}^{-1}$ and $\text{m s}^{-2}$ are equivalent units for gravitational field strength.

## 6. Circular Orbits

For a satellite in a circular orbit, gravity provides the centripetal force. If a satellite of mass $m$ orbits a planet of mass $M$ at orbital radius $r$, then

$$
\frac{GMm}{r^2} = \frac{mv^2}{r}
$$

The satellite mass cancels:

$$
v^2 = \frac{GM}{r}
$$

so

$$
v = \sqrt{\frac{GM}{r}}
$$

This means all satellites in the same circular orbit around the same planet have the same orbital speed, regardless of their mass.

The centripetal acceleration is caused by the gravitational field:

$$
a = \frac{v^2}{r} = \frac{GM}{r^2}
$$

This is the same as $g$ at that orbital radius. The satellite is in free fall, but its tangential speed keeps it moving around the planet rather than falling straight down.

## 7. Orbital Period

For a circular orbit, the orbital speed is also

$$
v = \frac{2\pi r}{T}
$$

where $T$ is the orbital period.

Combine this with

$$
v^2 = \frac{GM}{r}
$$

to get

$$
\left(\frac{2\pi r}{T}\right)^2 = \frac{GM}{r}
$$

so

$$
T^2 = \frac{4\pi^2r^3}{GM}
$$

This shows that, for circular orbits around the same central mass,

$$
T^2 \propto r^3
$$

A larger orbital radius means a longer period and a lower orbital speed.

## 8. Geostationary Orbits

A geostationary satellite remains above the same point on the Earth's surface.

For this to happen, the satellite must:

- have an orbital period of $24\ \text{h}$
- orbit from west to east
- orbit directly above the Equator
- have the same angular speed as the Earth's rotation

The orbit must be equatorial because the centre of the orbit must be the Earth's centre. If the orbit were inclined, the satellite would move north and south in the sky instead of staying above one fixed point on the surface.

For the Earth, the geostationary orbital radius is about $4.22 \times 10^7\ \text{m}$ from the Earth's centre, or about $42\ 200\ \text{km}$ from the centre.

Geostationary satellites are useful for communication and broadcasting because a ground dish can point in one fixed direction.

## 9. Gravitational Potential

Gravitational potential at a point is the work done per unit mass in bringing a small test mass from infinity to that point.

The symbol for gravitational potential is $\phi$.

For a point mass $M$:

$$
\phi = -\frac{GM}{r}
$$

where $r$ is the distance from the centre of the mass.

The unit is

$$
\text{J kg}^{-1}
$$

The negative sign is important. The gravitational potential is defined to be zero at infinity. Because gravity is attractive, a mass loses gravitational potential energy as it moves from infinity towards another mass. Therefore gravitational potential near a mass is negative.

As $r$ increases:

- $\phi$ becomes less negative
- $\phi$ approaches zero

As $r$ decreases:

- $\phi$ becomes more negative
- the mass is deeper in the gravitational potential well

## 10. Gravitational Potential Energy

Gravitational potential energy is related to gravitational potential by

$$
E_p = m\phi
$$

For two point masses $M$ and $m$ separated by distance $r$:

$$
E_p = -\frac{GMm}{r}
$$

This is the gravitational potential energy of the two-mass system when the zero of potential energy is chosen at infinite separation.

The negative value means energy must be supplied to separate the masses to infinity. A mass bound to a planet has negative gravitational potential energy relative to infinity.

For a change in position from $r_1$ to $r_2$:

$$
\Delta E_p = m(\phi_2 - \phi_1)
$$

Using the point-mass potential:

$$
\Delta E_p
=
GMm\left(\frac{1}{r_1} - \frac{1}{r_2}\right)
$$

when moving from $r_1$ to $r_2$.

Near the Earth's surface, for small height changes, this reduces approximately to

$$
\Delta E_p \approx mg\Delta h
$$

The approximation works only when $g$ is nearly constant over the height change.

## 11. Field Strength Versus Potential

Field strength and potential are related, but they are not the same quantity.

Field strength:

- is force per unit mass
- has unit $\text{N kg}^{-1}$
- is a vector
- tells you the direction and magnitude of force on a mass

Potential:

- is potential energy per unit mass
- has unit $\text{J kg}^{-1}$
- is a scalar
- tells you energy change per unit mass when moving from infinity

At distance $r$ from a point mass:

$$
g = \frac{GM}{r^2}
$$

but

$$
\phi = -\frac{GM}{r}
$$

So field strength follows an inverse-square dependence, while potential follows an inverse-distance dependence.

## 12. Working Routine

Use this routine for gravitational-field questions:

1. Decide whether the question is about force, field strength, potential, potential energy, or orbit.
2. Check whether the mass can be treated as a point mass or uniform sphere.
3. Measure $r$ from the centre of the mass, not from the surface, unless the question explicitly asks for height.
4. Use $F = \frac{Gm_1m_2}{r^2}$ for force between two masses.
5. Use $g = \frac{GM}{r^2}$ for field strength caused by one mass.
6. Use $\phi = -\frac{GM}{r}$ for potential.
7. Use $E_p = -\frac{GMm}{r}$ for gravitational potential energy.
8. For circular orbits, equate gravitational force to centripetal force.
9. For geostationary orbit questions, check period, direction, and equatorial plane.
10. Track signs for potential and potential energy carefully.

## Common Traps

- Measuring orbital radius from the surface instead of from the centre.
- Treating gravitational field strength and gravitational potential as the same thing.
- Forgetting that gravitational potential is negative when zero is at infinity.
- Using $\Delta E_p = mg\Delta h$ over very large height changes where $g$ is not constant.
- Forgetting that a uniform sphere acts like a point mass only for points outside the sphere.
- Thinking astronauts in low Earth orbit feel no gravity. They are in free fall.
- Saying geostationary means any 24-hour orbit. It must also be west to east and above the Equator.
- Forgetting that inverse-square dependence applies to force and field strength, not potential.

## Quick Self-Check

You should be able to answer these without looking back:

- What does a gravitational field line show?
- What is gravitational field strength?
- Why can the Earth be treated as a point mass for objects outside it?
- How do you derive $g = \frac{GM}{r^2}$ from Newton's law of gravitation?
- Why is $g$ approximately constant near the Earth's surface?
- How do you find orbital speed by combining gravity with circular motion?
- What conditions must a geostationary satellite satisfy?
- Why is gravitational potential negative?
- What is the difference between gravitational potential and gravitational potential energy?

## Connections

- [[10 Physics/01 Topics/12 Motion in a Circle/00 Overview|Motion in a Circle]] supplies centripetal acceleration and centripetal force.
- [[10 Physics/01 Topics/18 Electric Fields/00 Overview|Electric Fields]] uses parallel ideas: field strength, potential, and potential energy.
- [[10 Physics/01 Topics/25 Astronomy and Cosmology/00 Overview|Astronomy and Cosmology]] uses gravity to describe stars, galaxies, and cosmic structure.
