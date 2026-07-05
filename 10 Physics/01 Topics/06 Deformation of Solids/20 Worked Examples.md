---
title: Deformation of Solids Worked Examples
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/06 Deformation of Solids/00 Overview|Deformation of Solids]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/mechanics
  - worked-examples
---

# Deformation of Solids Worked Examples

These examples model the standard CAIE route through Hooke's law, stress,
strain, Young modulus, elastic and plastic deformation, and elastic potential
energy.

## Source Route

- Syllabus: CAIE Physics 9702 section 6, Deformation of solids.
- Coursebook route: Chapter 7, especially Hooke's law, stretching materials,
  Young modulus, and elastic potential energy.

## Example 1: Hooke's Law and Spring Constant

**Prompt.** A spring extends by $3.0\ \mathrm{cm}$ when a load of
$6.0\ \mathrm{N}$ is applied. The spring is within its limit of
proportionality. Find the spring constant and the extension for a load of
$10\ \mathrm{N}$.

**Solution.**

Convert extension to metres:

$$
x=3.0\ \mathrm{cm}=0.030\ \mathrm{m}.
$$

Using Hooke's law,

$$
F=kx.
$$

So

$$
k=\frac{F}{x}
=\frac{6.0}{0.030}
=200\ \mathrm{N\ m^{-1}}.
$$

For a load of $10\ \mathrm{N}$,

$$
x=\frac{F}{k}
=\frac{10}{200}
=0.050\ \mathrm{m}.
$$

This is $5.0\ \mathrm{cm}$, provided the limit of proportionality is still not
exceeded.

**What this example trains.** Use $F=kx$ only in the proportional region and
convert extension into metres.

## Example 2: Gradient of a Force-Extension Graph

**Prompt.** In the straight-line part of a force-extension graph, a force of
$12\ \mathrm{N}$ gives an extension of $4.0\ \mathrm{mm}$. Find the spring
constant and the work done in stretching the spring to this point.

**Solution.**

The gradient of a force-extension graph is the spring constant:

$$
k=\frac{F}{x}
=\frac{12}{4.0\times 10^{-3}}
=3.0\times 10^3\ \mathrm{N\ m^{-1}}.
$$

The work done is the area under the graph. In the straight-line region this is
a triangle:

$$
E_p=\frac{1}{2}Fx
=\frac{1}{2}(12)(4.0\times 10^{-3})
=2.4\times 10^{-2}\ \mathrm{J}.
$$

**What this example trains.** The gradient gives stiffness; the area gives
energy.

## Example 3: Stress, Strain, and Young Modulus

**Prompt.** A wire has original length $1.50\ \mathrm{m}$ and diameter
$0.50\ \mathrm{mm}$. A tensile force of $25\ \mathrm{N}$ extends it by
$1.2\ \mathrm{mm}$. Calculate the stress, strain, and Young modulus.

**Solution.**

Cross-sectional area:

$$
A=\frac{\pi d^2}{4}
=\frac{\pi(0.50\times 10^{-3})^2}{4}
=1.96\times 10^{-7}\ \mathrm{m^2}.
$$

Stress:

$$
\sigma=\frac{F}{A}
=\frac{25}{1.96\times 10^{-7}}
=1.27\times 10^8\ \mathrm{Pa}.
$$

Strain:

$$
\varepsilon=\frac{x}{L}
=\frac{1.2\times 10^{-3}}{1.50}
=8.0\times 10^{-4}.
$$

Young modulus:

$$
E=\frac{\sigma}{\varepsilon}
=\frac{1.27\times 10^8}{8.0\times 10^{-4}}
=1.59\times 10^{11}\ \mathrm{Pa}.
$$

**What this example trains.** Stress uses cross-sectional area; strain uses
original length.

## Example 4: Finding Extension from Young Modulus

**Prompt.** A copper wire of length $2.0\ \mathrm{m}$ and diameter
$0.80\ \mathrm{mm}$ is pulled by a force of $15\ \mathrm{N}$. Use
$E=1.3\times 10^{11}\ \mathrm{Pa}$ to estimate the extension.

**Solution.**

Use

$$
E=\frac{FL}{Ax}.
$$

First calculate the cross-sectional area:

$$
A=\frac{\pi(0.80\times 10^{-3})^2}{4}
=5.03\times 10^{-7}\ \mathrm{m^2}.
$$

Rearrange for extension:

$$
x=\frac{FL}{AE}.
$$

Substitute:

$$
x=\frac{(15)(2.0)}
{(5.03\times 10^{-7})(1.3\times 10^{11})}
=4.59\times 10^{-4}\ \mathrm{m}.
$$

This is $0.459\ \mathrm{mm}$.

**What this example trains.** Young modulus can predict extension when
geometry and load are known.

## Example 5: Young Modulus from a Stress-Strain Graph

**Prompt.** The initial straight-line part of a stress-strain graph passes
through the point
$(\varepsilon,\sigma)=(1.2\times 10^{-3},2.4\times 10^8\ \mathrm{Pa})$.
Find the Young modulus.

**Solution.**

The gradient of a stress-strain graph in the linear elastic region is the Young
modulus:

$$
E=\frac{\Delta\sigma}{\Delta\varepsilon}.
$$

Thus

$$
E=\frac{2.4\times 10^8}{1.2\times 10^{-3}}
=2.0\times 10^{11}\ \mathrm{Pa}.
$$

**What this example trains.** Do not use the gradient of a force-extension
graph as the Young modulus unless the axes are stress and strain.

## Example 6: Elastic and Plastic Deformation from Unloading

**Prompt.** A wire is loaded until its extension is $5.0\ \mathrm{mm}$. When
the load is removed, the wire still has an extension of $1.0\ \mathrm{mm}$.
State what this shows and find the elastic recovery.

**Solution.**

If the wire does not return to its original length after unloading, it has
undergone plastic deformation. The permanent extension is

$$
1.0\ \mathrm{mm}.
$$

The elastic recovery is the part of the extension recovered during unloading:

$$
5.0\ \mathrm{mm}-1.0\ \mathrm{mm}
=4.0\ \mathrm{mm}.
$$

The elastic limit must have been exceeded.

**What this example trains.** The elastic limit is about reversibility, not
only about whether the graph is straight.

## Example 7: Elastic Potential Energy in a Spring

**Prompt.** A spring has force constant $4800\ \mathrm{N\ m^{-1}}$. Calculate
the elastic potential energy stored when it is compressed by $2.0\ \mathrm{mm}$,
within its limit of proportionality.

**Solution.**

For a spring obeying Hooke's law,

$$
E_p=\frac{1}{2}kx^2.
$$

Convert the compression:

$$
x=2.0\times 10^{-3}\ \mathrm{m}.
$$

Then

$$
E_p=\frac{1}{2}(4800)(2.0\times 10^{-3})^2
=9.6\times 10^{-3}\ \mathrm{J}.
$$

**What this example trains.** The energy formula uses the square of the
extension in metres.

## Example 8: Area under a Non-Linear Force-Extension Graph

**Prompt.** A simplified force-extension graph for a metal rises linearly from
$0$ to $20\ \mathrm{N}$ at $5.0\ \mathrm{mm}$ extension, then remains at about
$20\ \mathrm{N}$ until it breaks at $12.0\ \mathrm{mm}$. Estimate the elastic
potential energy up to the limit of proportionality and the total work done to
break the metal.

**Solution.**

Up to the limit of proportionality, the graph is a triangle:

$$
E_{\text{elastic}}
=\frac{1}{2}(20)(5.0\times 10^{-3})
=5.0\times 10^{-2}\ \mathrm{J}.
$$

From $5.0\ \mathrm{mm}$ to $12.0\ \mathrm{mm}$, estimate the area as a
rectangle:

$$
W_{\text{plastic}}
=(20)(7.0\times 10^{-3})
=1.4\times 10^{-1}\ \mathrm{J}.
$$

Total work done:

$$
W_{\text{total}}
=0.050+0.140
=0.190\ \mathrm{J}.
$$

**What this example trains.** Graph area is work done even when the graph is no
longer linear.

## Example 9: Young Modulus Experiment from a Gradient

**Prompt.** In a Young modulus experiment, a wire has length
$1.80\ \mathrm{m}$ and diameter $0.40\ \mathrm{mm}$. The straight-line part of
the force-extension graph has gradient $1.35\times 10^4\ \mathrm{N\ m^{-1}}$.
Find the Young modulus and state two precautions.

**Solution.**

Area of the wire:

$$
A=\frac{\pi(0.40\times 10^{-3})^2}{4}
=1.26\times 10^{-7}\ \mathrm{m^2}.
$$

Since the graph gradient is $F/x$,

$$
E=\frac{L}{A}\times \text{gradient}.
$$

So

$$
E=\frac{1.80}{1.26\times 10^{-7}}
(1.35\times 10^4)
=1.93\times 10^{11}\ \mathrm{Pa}.
$$

Two useful precautions are:

- Measure the diameter at several positions and average the value before
  calculating $A$.
- Remove the load gradually after taking readings to check that the wire has
  not been plastically deformed.

**What this example trains.** The experiment combines graph gradient with
specimen geometry.
