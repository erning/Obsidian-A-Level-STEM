---
title: Deformation of Solids Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/06 Deformation of Solids/00 Overview|Deformation of Solids]]"
status: draft
tags:
  - physics/9702/topic
  - physics/9702/mechanics
  - lecture-notes
---

# Deformation of Solids Lecture Notes

Forces do not only change motion. They can also change shape. A spring extends,
a wire stretches, a beam bends, and a rubber band stores energy when it is
pulled. This topic studies one-dimensional deformation: stretching and
compression along a line.

The main question is how a solid responds when a load is applied. Sometimes the
solid returns to its original shape. Sometimes it is permanently deformed. The
graphs and equations in this topic let you describe that behaviour
quantitatively.

## Visual guide

![[assets/generated/physics/deformation-of-solids.svg]]

The diagram links load, extension, Hooke's law, stress, strain, Young modulus,
elastic behaviour, plastic behaviour, and elastic potential energy.

## Source route

This note follows CAIE Physics 9702 section 6, Deformation of solids:

- 6.1 Stress and strain
- 6.2 Elastic and plastic behaviour

The matching coursebook route is Chapter 7, especially the sections on
compressive and tensile forces, springs, stretching materials, stress and
strain, Young modulus, and elastic potential energy.

## 1. Tensile and compressive deformation

Deformation means a change in shape or size caused by forces.

A tensile force stretches a material. The material becomes longer in the
direction of the force. A compressive force squashes a material. The material
becomes shorter in the direction of the force.

For this syllabus section, forces and deformations are treated in one dimension.
That means the extension or compression is measured along the line of the
applied load.

The load is the force applied to the object. The extension $x$ is the increase
in length:

$$
x = \text{new length} - \text{original length}
$$

For compression, the same idea applies, but the length decreases. You may call
the change a compression rather than an extension.

## 2. Force-extension graphs

A simple way to study deformation is to hang loads from a spring and measure
the extension for each load. Plotting force on the vertical axis and extension
on the horizontal axis gives a force-extension graph.

The graph is experimental evidence. Its shape tells you how the object behaves.

- A straight line through the origin means force is proportional to extension.
- A steeper straight line means a stiffer spring or wire.
- A curved region means force is no longer proportional to extension.
- If unloading does not return to the original length, permanent deformation
  has occurred.

The gradient of a force-extension graph in the straight-line region is the
spring constant.

## 3. Hooke's law and spring constant

Hooke's law states that the extension of a material is directly proportional to
the applied force, provided the limit of proportionality is not exceeded.

For a spring or wire obeying Hooke's law,

$$
F = kx
$$

where $F$ is the load, $x$ is the extension, and $k$ is the spring constant. The
spring constant is

$$
k = \frac{F}{x}
$$

Its unit is

$$
\text{N m}^{-1}
$$

A larger value of $k$ means a stiffer spring: more force is needed for the same
extension.

The limit of proportionality is the point beyond which extension is no longer
directly proportional to load. Beyond this point, the graph is no longer a
straight line through the origin and $F = kx$ can no longer be used with a
constant $k$.

## 4. Elastic and plastic behaviour

Elastic deformation means the object returns to its original shape and size
when the load is removed.

Plastic deformation means the object does not return to its original shape and
size when the load is removed. The deformation is permanent.

The elastic limit is the greatest load or deformation for which the material
still returns to its original shape when the load is removed.

The elastic limit is not necessarily the same as the limit of proportionality.
They may be close, but they describe different ideas:

- The limit of proportionality is about whether $F$ is proportional to $x$.
- The elastic limit is about whether the deformation is fully reversible.

This distinction matters when reading graphs. A material can stop obeying
Hooke's law before it becomes permanently deformed.

## 5. Stress

The force needed to stretch a wire depends partly on the wire's cross-sectional
area. A thicker wire needs a larger force for the same kind of material
response. Stress removes this geometry factor by comparing force with area.

Tensile stress is defined as force per unit cross-sectional area:

$$
\sigma = \frac{F}{A}
$$

where $\sigma$ is stress, $F$ is the applied tensile force, and $A$ is the
cross-sectional area normal to the force.

The unit of stress is

$$
\text{N m}^{-2}
$$

which is the same as the pascal:

$$
1\ \text{Pa} = 1\ \text{N m}^{-2}
$$

Stress is not the same as force. It tells you how concentrated the force is
over the material's cross-section.

## 6. Strain

The extension of a wire depends partly on its original length. A long wire
extends more than a short wire of the same material and cross-section under the
same stress. Strain removes this geometry factor by comparing extension with
original length.

Tensile strain is defined as extension divided by original length:

$$
\varepsilon = \frac{x}{L}
$$

where $\varepsilon$ is strain, $x$ is extension, and $L$ is the original length.

Strain has no unit because it is a ratio of two lengths. It may be written as a
decimal or as a percentage.

Strain is not the same as extension. Extension is an actual length change.
Strain is the fractional change in length.

## 7. Young modulus

The spring constant describes the stiffness of a particular spring or wire. It
depends on material and geometry. A thicker wire, a shorter wire, or a different
material will change the spring constant.

The Young modulus describes the stiffness of the material itself in the linear
elastic region. It is defined as

$$
E = \frac{\text{stress}}{\text{strain}}
$$

or

$$
E = \frac{\sigma}{\varepsilon}
$$

Using $\sigma = \dfrac{F}{A}$ and $\varepsilon = \dfrac{x}{L}$,

$$
E = \frac{F/A}{x/L}
  = \frac{FL}{Ax}
$$

The unit of Young modulus is the same as stress, because strain has no unit:

$$
\text{Pa}
$$

On a stress-strain graph, the gradient of the initial straight-line section is
the Young modulus:

$$
E = \frac{\Delta \sigma}{\Delta \varepsilon}
$$

A material with a larger Young modulus is stiffer. Steel has a much larger
Young modulus than rubber, so steel needs a much larger stress to produce the
same strain.

## 8. Measuring the Young modulus of a wire

To determine the Young modulus of a metal wire, you need measurements of force,
extension, original length, and cross-sectional area.

Use a long, thin wire because the extension is small. A longer wire gives a
larger measurable extension for the same strain. Measure the original length
$L$ from the clamp to the marker or reference point.

Measure the diameter $d$ of the wire with a micrometer screw gauge at several
positions and in different orientations. Use the mean diameter to calculate the
cross-sectional area:

$$
A = \frac{\pi d^2}{4}
$$

Add loads gradually. For each load, calculate the force $F = mg$ and measure
the extension $x$. A travelling microscope, vernier scale, or another fine
scale can be used to measure small extensions.

Plot $F$ against $x$ for the elastic, straight-line region. The gradient is

$$
\frac{F}{x}
$$

Since

$$
E = \frac{FL}{Ax}
$$

the Young modulus can be found from

$$
E = \frac{L}{A} \times \text{gradient of the } F\text{-}x \text{ graph}
$$

The load should be removed gradually after taking readings to check that the
wire returns to its original length. If it does not, the elastic limit has been
exceeded and the straight-line data should not be treated as purely elastic.

## 9. Work done in deformation

Stretching or compressing a material requires work because a force moves
through a distance. The work done is stored as elastic potential energy if the
material is elastically deformed.

For any force-extension graph, the work done is the area under the graph:

$$
W = \text{area under the } F\text{-}x \text{ graph}
$$

This is true even when the graph is curved, although the area may need to be
found by counting squares or using numerical methods.

In the Hooke's law region, the force-extension graph is a straight line through
the origin. The area under the graph is a triangle:

$$
E_p = \frac{1}{2}Fx
$$

Since $F = kx$ in this region,

$$
E_p = \frac{1}{2}kx^2
$$

These two equations apply to a material deformed within its limit of
proportionality.

If the material is plastically deformed, not all the work done can be recovered.
Some energy is transferred to internal energy as the material's internal
structure changes.

## 10. Reading deformation graphs

Force-extension and stress-strain graphs carry a lot of physical information.

For a force-extension graph:

- The gradient in the linear region gives the spring constant.
- The area under the graph gives the work done.
- The end of the straight-line region marks the limit of proportionality.
- A non-zero extension after unloading shows plastic deformation.

For a stress-strain graph:

- The gradient in the initial linear region gives the Young modulus.
- The graph allows comparison of materials without depending on specimen size.
- The linear region shows where stress is proportional to strain.

Always check which graph you are using. The gradient of a force-extension graph
is not the Young modulus unless geometry has already been built into the axes.

## 11. A working routine

Use this routine for deformation problems.

1. Decide whether the problem concerns a particular spring or wire, or the
   material itself.
2. For a particular spring or wire, use $F = kx$ only in the proportional
   region.
3. For material stiffness, calculate stress and strain, then use
   $E = \sigma/\varepsilon$.
4. Use original length for strain, not final length.
5. Use cross-sectional area normal to the force for stress.
6. Use graph gradient for stiffness and graph area for work done.
7. Check whether the deformation is elastic or plastic before using stored
   elastic energy formulae.

## 12. Common mistakes

- Confusing extension $x$ with strain $\varepsilon$.
- Confusing spring constant $k$ with Young modulus $E$.
- Using Hooke's law beyond the limit of proportionality.
- Treating the elastic limit and limit of proportionality as automatically the
  same point.
- Using diameter instead of cross-sectional area in stress.
- Using final length instead of original length in strain.
- Forgetting that area under a force-extension graph has units of energy.
- Using $E_p = \frac{1}{2}kx^2$ for a non-linear or plastic region.

## Quick self-check

You are ready to move on when you can answer these without notes.

1. What is the difference between tensile and compressive deformation?
2. What does the gradient of a force-extension graph represent?
3. What condition must be satisfied before using $F = kx$?
4. How do elastic deformation and plastic deformation differ?
5. Why do stress and strain let you compare materials rather than specimens?
6. How is Young modulus found from a stress-strain graph?
7. What measurements are needed to find the Young modulus of a wire?
8. Why is the elastic potential energy in a Hooke's law spring
   $\frac{1}{2}kx^2$ rather than $kx^2$?

## Connections

- [[10 Physics/01 Topics/04 Forces Density and Pressure/10 Lecture Notes|Forces, Density and Pressure]]
  introduced force per unit area, which becomes stress here.
- [[10 Physics/01 Topics/05 Work Energy and Power/10 Lecture Notes|Work, Energy and Power]]
  introduced work done as area under a force-displacement graph.
- [[20 Mathematics/02 Mechanics/04 Work Energy Power and Elasticity/00 Overview|Work, Energy, Power and Elasticity]]
  develops the mechanics of springs and elastic energy.
