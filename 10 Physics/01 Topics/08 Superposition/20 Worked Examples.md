---
title: Superposition Worked Examples
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/08 Superposition/00 Overview|Superposition]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/waves
  - worked-examples
---

# Superposition Worked Examples

These examples model the standard CAIE route through displacement addition,
stationary waves, diffraction, interference, double-slit fringes, and
diffraction gratings.

## Source Route

- Syllabus: CAIE Physics 9702 section 8, Superposition.
- Coursebook route: Chapters 13 and 14, especially superposition of waves,
  diffraction, interference, diffraction gratings, and stationary waves.

## Example 1: Algebraic Addition of Displacements

**Prompt.** At one point and one instant, three overlapping waves give
displacements $+2.5\ \mathrm{mm}$, $-1.0\ \mathrm{mm}$, and
$+0.8\ \mathrm{mm}$. Find the resultant displacement.

**Solution.**

The principle of superposition says that the resultant displacement is the
algebraic sum of the individual displacements:

$$
s=s_1+s_2+s_3.
$$

So

$$
s=+2.5-1.0+0.8
=+2.3\ \mathrm{mm}.
$$

The positive sign means the resultant displacement is in the chosen positive
direction.

**What this example trains.** Superposition adds signed displacements, not
intensities.

## Example 2: Path Difference and Interference Type

**Prompt.** Two coherent waves of wavelength $0.64\ \mathrm{m}$ arrive at a
point with path difference $1.60\ \mathrm{m}$. Decide whether the interference
is constructive or destructive, and find the phase difference.

**Solution.**

Express the path difference in wavelengths:

$$
\frac{1.60}{0.64}=2.5.
$$

So the path difference is

$$
2.5\lambda=\left(2+\frac{1}{2}\right)\lambda.
$$

This is an odd number of half wavelengths, so the waves arrive in antiphase and
produce destructive interference.

The phase difference is

$$
\phi=2\pi(2.5)=5\pi\ \mathrm{rad}.
$$

Equivalently,

$$
\phi=360^\circ(2.5)=900^\circ.
$$

Modulo one cycle, this is equivalent to $180^\circ$.

**What this example trains.** Convert path difference into wavelengths before
deciding the interference condition.

## Example 3: Diffraction and Gap Width

**Prompt.** Plane water waves pass through three gaps: gap A is about
$10\lambda$ wide, gap B is about $2\lambda$ wide, and gap C is about
$\lambda$ wide. Compare the diffraction in each case.

**Solution.**

Diffraction is the spreading of waves as they pass through a gap or around an
edge. It is greatest when the gap width is comparable with the wavelength.

- Gap A, about $10\lambda$, gives little spreading.
- Gap B, about $2\lambda$, gives noticeable but limited spreading.
- Gap C, about $\lambda$, gives strong spreading.

The wavelength has not changed. The change is in how widely the wavefronts
spread after passing through the gap.

**What this example trains.** Diffraction is judged by comparing aperture size
with wavelength.

## Example 4: Double-Slit Fringe Spacing

**Prompt.** Monochromatic light of wavelength $590\ \mathrm{nm}$ is incident
on a double slit. The slit separation is $0.30\ \mathrm{mm}$ and the screen is
$1.5\ \mathrm{m}$ away. Calculate the fringe spacing.

**Solution.**

For double-slit interference,

$$
x=\frac{\lambda D}{a}.
$$

Convert:

$$
\lambda=590\times 10^{-9}\ \mathrm{m},
\qquad
a=0.30\times 10^{-3}\ \mathrm{m}.
$$

Then

$$
x=\frac{(590\times 10^{-9})(1.5)}{0.30\times 10^{-3}}
=2.95\times 10^{-3}\ \mathrm{m}.
$$

The fringe spacing is $2.95\ \mathrm{mm}$.

**What this example trains.** Convert nanometres and millimetres before using
$x=\lambda D/a$.

## Example 5: Finding Wavelength from Measured Fringes

**Prompt.** In a double-slit experiment, the distance from the first bright
fringe to the eleventh bright fringe is $24.0\ \mathrm{mm}$. The slit
separation is $0.25\ \mathrm{mm}$ and the screen distance is
$1.2\ \mathrm{m}$. Find the wavelength.

**Solution.**

From the first to the eleventh bright fringe there are $10$ fringe spacings:

$$
x=\frac{24.0\ \mathrm{mm}}{10}
=2.40\ \mathrm{mm}
=2.40\times 10^{-3}\ \mathrm{m}.
$$

Use

$$
\lambda=\frac{ax}{D}.
$$

Thus

$$
\lambda=
\frac{(0.25\times 10^{-3})(2.40\times 10^{-3})}{1.2}
=5.0\times 10^{-7}\ \mathrm{m}.
$$

This is $500\ \mathrm{nm}$, in the visible range.

**What this example trains.** Measuring across many fringe spacings reduces
percentage uncertainty, but you must divide by the number of spacings.

## Example 6: Diffraction Grating Angle and Possible Orders

**Prompt.** Light of wavelength $600\ \mathrm{nm}$ is incident normally on a
grating with $500$ lines per millimetre. Find the angle of the second-order
maximum and the largest possible order.

**Solution.**

Convert the line density:

$$
500\ \mathrm{mm^{-1}}=5.00\times 10^5\ \mathrm{m^{-1}}.
$$

The grating spacing is

$$
d=\frac{1}{5.00\times 10^5}
=2.00\times 10^{-6}\ \mathrm{m}.
$$

Use

$$
d\sin\theta=n\lambda.
$$

For $n=2$,

$$
\sin\theta=\frac{2(600\times 10^{-9})}{2.00\times 10^{-6}}
=0.600.
$$

Therefore

$$
\theta=36.9^\circ.
$$

The largest possible order is the largest integer satisfying

$$
n\lambda\le d.
$$

So

$$
n\le \frac{d}{\lambda}
=\frac{2.00\times 10^{-6}}{600\times 10^{-9}}
=3.33.
$$

The largest possible order is $3$.

**What this example trains.** Convert grating line density and check
$\sin\theta\le 1$.

## Example 7: Finding Wavelength with a Grating

**Prompt.** A diffraction grating has spacing $1.67\times 10^{-6}\ \mathrm{m}$.
The first-order maximum is observed at $19.2^\circ$. Calculate the wavelength.

**Solution.**

Use

$$
d\sin\theta=n\lambda.
$$

For first order, $n=1$, so

$$
\lambda=d\sin\theta.
$$

Thus

$$
\lambda=(1.67\times 10^{-6})\sin19.2^\circ
=5.49\times 10^{-7}\ \mathrm{m}.
$$

This is about $549\ \mathrm{nm}$.

**What this example trains.** The grating equation can be used to measure
wavelength from an angle.

## Example 8: Wavelength from a Stationary Wave

**Prompt.** Adjacent nodes in a stationary wave on a string are separated by
$25\ \mathrm{cm}$. The wave speed on the string is
$12\ \mathrm{m\ s^{-1}}$. Find the wavelength and frequency of the progressive
waves that formed the stationary wave.

**Solution.**

Adjacent nodes are separated by $\lambda/2$, so

$$
\lambda=2(25\ \mathrm{cm})
=50\ \mathrm{cm}
=0.50\ \mathrm{m}.
$$

Using $v=f\lambda$,

$$
f=\frac{v}{\lambda}
=\frac{12}{0.50}
=24\ \mathrm{Hz}.
$$

**What this example trains.** Node spacing is half a wavelength.

## Example 9: A Fixed String Mode

**Prompt.** A string fixed at both ends has length $0.80\ \mathrm{m}$. It
vibrates in a mode with three antinodes at frequency $150\ \mathrm{Hz}$. Find
the wavelength and wave speed on the string.

**Solution.**

For a string fixed at both ends, each loop is half a wavelength. Three
antinodes means three loops:

$$
L=3\frac{\lambda}{2}.
$$

Thus

$$
\lambda=\frac{2L}{3}
=\frac{2(0.80)}{3}
=0.533\ \mathrm{m}.
$$

Wave speed:

$$
v=f\lambda=(150)(0.533)
=80.0\ \mathrm{m\ s^{-1}}.
$$

**What this example trains.** Boundary conditions set the allowed wavelength.

## Example 10: Microwave Stationary Wave Experiment

**Prompt.** In a microwave stationary wave experiment, the distance from the
first minimum to the sixth minimum is $7.5\ \mathrm{cm}$. Find the wavelength
and frequency of the microwaves, using $c=3.0\times 10^8\ \mathrm{m\ s^{-1}}$.

**Solution.**

From the first to the sixth minimum there are $5$ spacings:

$$
\text{node spacing}=\frac{7.5\ \mathrm{cm}}{5}
=1.5\ \mathrm{cm}.
$$

Adjacent minima are separated by $\lambda/2$, so

$$
\lambda=2(1.5\ \mathrm{cm})
=3.0\ \mathrm{cm}
=3.0\times 10^{-2}\ \mathrm{m}.
$$

Frequency:

$$
f=\frac{c}{\lambda}
=\frac{3.0\times 10^8}{3.0\times 10^{-2}}
=1.0\times 10^{10}\ \mathrm{Hz}.
$$

**What this example trains.** Measuring several node spacings improves
precision, but the node spacing is still $\lambda/2$.
