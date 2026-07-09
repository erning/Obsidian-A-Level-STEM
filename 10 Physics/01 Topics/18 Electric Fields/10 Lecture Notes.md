---
title: Electric Fields Lecture Notes
subject: Physics
syllabus: 9702
parent: "[Electric Fields](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/fields
  - lecture-notes
---

# Electric Fields Lecture Notes

An electric field is a force field produced by electric charge. It tells you what force a positive test charge would experience at each point in space.

This topic has three linked ideas: force, field strength, and potential. Force describes what happens to a particular charge. Field strength describes the force per unit positive charge at a point. Potential describes energy per unit positive charge at a point.

## Source Route

- Primary syllabus source: CAIE Physics 9702.
- 18 Electric fields
- 18.1 Electric fields and field lines
- 18.2 Uniform electric fields
- 18.3 Electric force between point charges
- 18.4 Electric field of a point charge
- 18.5 Electric potential
- Coursebook route: Physics Coursebook Chapters 21 and 22, electric fields and Coulomb's law.

## Visual Guide

![electric-fields](../../../assets/generated/physics/electric-fields.svg)

Figure: Field lines show direction and relative strength; equipotentials show the energy landscape.

## 1. Electric Field as a Force Field

An electric field exists at any point where an electric charge would experience a force. The direction of an electric field is defined as the direction of the force on a small positive test charge.

This convention matters:

- a positive charge experiences a force in the direction of the electric field;
- a negative charge experiences a force opposite to the electric field.

Electric field strength is defined as force per unit positive charge:

$$
E = \frac{F}{q}.
$$

Rearranging gives the force on a charge in an electric field:

$$
F = qE.
$$

If $q$ is negative, the sign tells you that the force is opposite to the field direction. The units of electric field strength are

$$
\mathrm{N\ C^{-1}}.
$$

The same unit can also be written as

$$
\mathrm{V\ m^{-1}}.
$$

These are equivalent.

## 2. Field Lines

Electric fields are represented by field lines. A field line shows the direction of the force on a positive test charge.

Rules for reading field-line diagrams:

- field lines point away from positive charges and towards negative charges;
- closer field lines mean a stronger field;
- parallel, equally spaced field lines represent a uniform field;
- radial field lines represent the field around a point charge or outside a charged sphere;
- field lines do not cross, because the field cannot have two directions at the same point.

Field lines are a representation, not physical threads in space. They are useful because they carry both direction and relative strength in one diagram.

## 3. Uniform Electric Fields

A uniform electric field has the same magnitude and direction at every point. A good approximation is the field between two large parallel plates with opposite charges, away from the plate edges.

For parallel plates separated by distance $\Delta d$ with potential difference $\Delta V$, the magnitude of the uniform electric field is

$$
E = \frac{\Delta V}{\Delta d}.
$$

This is why electric field strength can be measured in $\mathrm{V\ m^{-1}}$.

As a vector relation, the electric field points in the direction of decreasing electric potential:

$$
E = -\frac{\Delta V}{\Delta d}
$$

along the chosen direction. The minus sign means that a positive charge is pushed "downhill" in potential.

## 4. Motion of Charged Particles in a Uniform Field

In a uniform field, the force on a charge is constant:

$$
F = qE.
$$

So the acceleration is constant:

$$
a = \frac{F}{m} = \frac{qE}{m}.
$$

For a particle that starts from rest, it accelerates along the force direction. A positive particle accelerates along the electric field, while an electron accelerates opposite to the electric field.

If a charged particle enters a uniform electric field with velocity perpendicular to the field, the motion is like projectile motion:

- the velocity component parallel to the plates remains constant if no force acts in that direction;
- the component along the electric force changes uniformly;
- the path is parabolic.

In many electron-beam questions, gravity is negligible compared with the electric force.

## 5. Coulomb's Law

Coulomb's law gives the force between two point charges in free space:

$$
F = \frac{Q_1Q_2}{4\pi\varepsilon_0r^2}.
$$

Here:

- $Q_1$ and $Q_2$ are the charges;
- $r$ is the separation of their centres;
- $\varepsilon_0$ is the permittivity of free space.

For magnitudes, use

$$
|F| = \frac{|Q_1Q_2|}{4\pi\varepsilon_0r^2}.
$$

The sign tells the type of force:

- like charges repel;
- unlike charges attract.

For a point outside a spherical conductor, the charge on the sphere may be considered to be a point charge at its centre. This is why distances are measured from the centre of the sphere, not from its surface, when applying Coulomb's law outside the sphere.

The inverse-square dependence is important. If the separation doubles, the force becomes one quarter of its previous value.

## 6. Electric Field of a Point Charge

To find the electric field strength due to a point charge $Q$, imagine placing a small positive test charge at distance $r$. Divide Coulomb's force by the test charge. This gives

$$
E = \frac{Q}{4\pi\varepsilon_0r^2}.
$$

For magnitude,

$$
|E| = \frac{|Q|}{4\pi\varepsilon_0r^2}.
$$

The direction depends on the sign of $Q$:

- away from a positive charge;
- towards a negative charge.

This is a radial field. It is not uniform, because $E$ changes with distance. Doubling $r$ reduces the field strength by a factor of four.

Electric fields obey superposition. If more than one charge produces a field at a point, add the field vectors, not just the magnitudes.

## 7. Electric Potential

Electric potential at a point is defined as the work done per unit positive charge in bringing a small test charge from infinity to that point.

Equivalently,

$$
V = \frac{E_\text{p}}{q},
$$

where $E_\text{p}$ is electric potential energy and $q$ is the charge placed at the point.

Electric potential is a scalar. It can be positive or negative, but it has no direction. The zero of potential is usually chosen at infinity for isolated point charges.

For a point charge $Q$ in free space,

$$
V = \frac{Q}{4\pi\varepsilon_0r}.
$$

The sign of $V$ is the sign of $Q$. A positive source charge gives positive potential; a negative source charge gives negative potential.

For several source charges, add the potentials algebraically:

$$
V_\text{total} = V_1 + V_2 + V_3 + \cdots.
$$

This is easier than adding electric fields, because potential is scalar.

## 8. Electric Potential Energy of Two Charges

The electric potential energy of a charge $q$ placed at potential $V$ is

$$
E_\text{p} = qV.
$$

For two point charges $Q$ and $q$ separated by distance $r$,

$$
E_\text{p} = \frac{Qq}{4\pi\varepsilon_0r}.
$$

The sign matters:

- two like charges have positive potential energy relative to infinity;
- two unlike charges have negative potential energy relative to infinity.

Positive potential energy means work must be done by an external agent to bring the charges together from infinity. Negative potential energy means energy is released as the charges come together.

## 9. Potential Gradient and Field Strength

Electric field strength is equal to the negative of the potential gradient:

$$
E = -\frac{dV}{dr}.
$$

In one-dimensional problems, this means the field points in the direction in which potential decreases most rapidly. For a uniform field between parallel plates,

$$
|E| = \frac{\Delta V}{\Delta d}.
$$

For a potential-distance graph, the electric field strength at a point is found from the negative gradient of the tangent at that point.

Equipotential lines or surfaces connect points of equal potential. Moving a charge along an equipotential requires no work, because $\Delta V = 0$.

Electric field lines are perpendicular to equipotential surfaces. If they were not perpendicular, there would be a component of electric field along the equipotential, and a charge would gain or lose energy while moving along a line of equal potential.

## 10. Comparing Electric and Gravitational Fields

Electric fields and gravitational fields share the same field language:

- field strength is force per unit property;
- field lines show direction and relative strength;
- radial fields obey inverse-square laws;
- potential is energy per unit property.

The major difference is charge sign. Mass is always positive, so gravity is always attractive. Electric charge can be positive or negative, so electric forces can attract or repel, and electric potentials can be positive or negative.

This is why sign conventions are more important in electric fields than in gravitational fields.

## 11. Problem-Solving Routine

For force and field problems:

1. Draw the charges and label their signs.
2. Decide whether the field is uniform or radial.
3. For a uniform field, use $E = \frac{\Delta V}{\Delta d}$ and $F = qE$.
4. For point charges, use Coulomb's law or $E = \frac{Q}{4\pi\varepsilon_0r^2}$.
5. Decide direction from charge signs and the positive-test-charge convention.
6. Add vectors if multiple fields act at one point.

For potential and energy problems:

1. Set zero potential, usually at infinity.
2. Use $V = \frac{Q}{4\pi\varepsilon_0r}$ for a point charge.
3. Add potentials algebraically if several charges contribute.
4. Use $E_\text{p} = qV$ or $E_\text{p} = \frac{Qq}{4\pi\varepsilon_0r}$.
5. Use $E = -\frac{dV}{dr}$ when moving between potential graphs and field strength.

## 12. Common Traps

- Forgetting that electric field direction is defined using a positive test charge.
- Treating the force on an electron as being in the field direction.
- Mixing up electric potential $V$ with electric potential energy $E_\text{p}$.
- Adding electric field magnitudes when the fields point in different directions.
- Using uniform-field equations for a point-charge field.
- Measuring distance from the surface of a charged sphere when the point-charge model requires distance from the centre.
- Dropping signs in potential and potential energy calculations.

## 13. Quick Self-Check

You are ready to move on when you can:

- define electric field strength as force per unit positive charge;
- use $F = qE$ with correct force direction;
- draw and interpret field lines for uniform and radial fields;
- use $E = \frac{\Delta V}{\Delta d}$ for parallel plates;
- describe charged-particle motion in a uniform electric field;
- use Coulomb's law for point charges;
- use $E = \frac{Q}{4\pi\varepsilon_0r^2}$ and $V = \frac{Q}{4\pi\varepsilon_0r}$;
- explain why $E = -\frac{dV}{dr}$;
- calculate electric potential energy using $E_\text{p} = \frac{Qq}{4\pi\varepsilon_0r}$.

## Connections

- [Gravitational Fields](../13%20Gravitational%20Fields/00%20Overview.md)
- [Capacitance](../19%20Capacitance/00%20Overview.md)
