---
title: Physical Quantities and Units Worked Examples
subject: Physics
syllabus: 9702
parent: "[Physical Quantities and Units](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/foundations
  - worked-examples
---

# Physical Quantities and Units Worked Examples

These examples model how to use units, uncertainties, and vectors as part of
the physics, not as decoration after the calculation.

## Example 1: Estimating a Length from a Benchmark

**Prompt.** A student writes that a school corridor is about $0.80\ \mathrm{km}$
long. The corridor has 24 classroom doors along one side. A classroom door is
about $0.90\ \mathrm{m}$ wide. Use this information to make an order-of-magnitude
check on the claim.

### Solution

Use the door width as a benchmark. If the corridor were only as long as the
doors placed side by side, its length would be about

$$
24 \times 0.90\ \mathrm{m}=21.6\ \mathrm{m}.
$$

There are gaps between doors, so a sensible estimate might be
$30\ \mathrm{m}$ to $50\ \mathrm{m}$, depending on the layout. The claimed length is

$$
0.80\ \mathrm{km}=800\ \mathrm{m}.
$$

This is much larger than the estimate. It would require a corridor roughly

$$
\frac{800}{40}=20
$$

times as long as the rough benchmark estimate.

### Check

The comparison uses quantities in the same unit, metres. The claim is not just
slightly high; it is about one order of magnitude too large for an ordinary
school corridor.

## Example 2: Prefixes and Cubed Units

**Prompt.** A volume of oil is $2.0\ \mathrm{cm^3}$. It spreads across a water
surface of area $0.40\ \mathrm{m^2}$. Estimate the thickness of the oil film.

### Solution

First convert the volume to SI units. Since

$$
1\ \mathrm{cm}=10^{-2}\ \mathrm{m},
$$

then

$$
1\ \mathrm{cm^3}=(10^{-2}\ \mathrm{m})^3=10^{-6}\ \mathrm{m^3}.
$$

So

$$
2.0\ \mathrm{cm^3}=2.0\times 10^{-6}\ \mathrm{m^3}.
$$

Use

$$
\text{volume}=\text{area}\times\text{thickness}.
$$

Thus

$$
\text{thickness}
=\frac{2.0\times 10^{-6}}{0.40}
=5.0\times 10^{-6}\ \mathrm{m}.
$$

In micrometres,

$$
5.0\times 10^{-6}\ \mathrm{m}=5.0\ \mu\mathrm{m}.
$$

### Check

The film is very thin, as expected. The key unit step is cubing the centimetre
conversion factor, not just multiplying by $10^{-2}$.

## Example 3: Derived Units and Pressure

**Prompt.** A force of $18\ \mathrm{N}$ acts normally on an area of
$2.5\ \mathrm{cm^2}$. Calculate the pressure and express the pascal in SI base
units.

### Solution

Pressure is force per unit area:

$$
p=\frac{F}{A}.
$$

Convert the area:

$$
2.5\ \mathrm{cm^2}
=2.5\times (10^{-2}\ \mathrm{m})^2
=2.5\times 10^{-4}\ \mathrm{m^2}.
$$

Now calculate:

$$
p=\frac{18}{2.5\times 10^{-4}}
=7.2\times 10^4\ \mathrm{Pa}.
$$

The unit of pressure is

$$
\mathrm{Pa}=\mathrm{N\ m^{-2}}.
$$

Since

$$
\mathrm{N}=\mathrm{kg\ m\ s^{-2}},
$$

then

$$
\mathrm{Pa}
=\mathrm{kg\ m\ s^{-2}\ m^{-2}}
=\mathrm{kg\ m^{-1}\ s^{-2}}.
$$

### Check

The pressure is large because the area is small. The base-unit form has
dimensions of force divided by area, as required.

## Example 4: Homogeneity of a Pendulum Equation

**Prompt.** The period $T$ of a simple pendulum is given by

$$
T=2\pi\sqrt{\frac{l}{g}},
$$

where $l$ is length and $g$ is acceleration. Show that the equation is
homogeneous, then find $T$ for $l=0.640\ \mathrm{m}$ and
$g=9.81\ \mathrm{m\ s^{-2}}$.

### Solution

The unit of $l$ is $\mathrm{m}$. The unit of $g$ is $\mathrm{m\ s^{-2}}$. Therefore

$$
\frac{l}{g}
\quad \text{has unit} \quad
\frac{\mathrm{m}}{\mathrm{m\ s^{-2}}}
=\mathrm{s^2}.
$$

So

$$
\sqrt{\frac{l}{g}}
\quad \text{has unit} \quad
\mathrm{s}.
$$

The factor $2\pi$ is dimensionless, so the right-hand side has unit
$\mathrm{s}$, the same as $T$.

Now calculate:

$$
T=2\pi\sqrt{\frac{0.640}{9.81}}
=1.60\ \mathrm{s}
$$

to three significant figures.

### Check

The unit check can show that the equation is possible. It cannot prove that the
factor $2\pi$ is correct, because numerical constants have no units.

## Example 5: Random Error and Zero Error

**Prompt.** A micrometer gives these diameter readings for a wire, in
millimetres:

$$
12.44,\quad 12.45,\quad 12.43,\quad 12.47,\quad 12.46.
$$

When the micrometer jaws are closed, it reads $+0.02\ \mathrm{mm}$. Find a
corrected value for the diameter with an uncertainty.

### Solution

First find the mean reading:

$$
\bar{x}
=\frac{12.44+12.45+12.43+12.47+12.46}{5}
=12.45\ \mathrm{mm}.
$$

Estimate the random uncertainty from half the range:

$$
\Delta x
=\frac{12.47-12.43}{2}
=0.02\ \mathrm{mm}.
$$

The zero error is positive, so the micrometer reads too high. Subtract it from
the mean reading:

$$
12.45\ \mathrm{mm}-0.02\ \mathrm{mm}
=12.43\ \mathrm{mm}.
$$

So a suitable corrected result is

$$
d=(12.43\pm0.02)\ \mathrm{mm}.
$$

### Check

Repeating readings helps estimate the random uncertainty. It does not remove
the systematic zero error; that must be corrected separately.

## Example 6: Combining Uncertainties in a Derived Quantity

**Prompt.** A cube has mass

$$
m=(48.0\pm0.1)\ \mathrm{g}
$$

and side length

$$
a=(2.00\pm0.01)\ \mathrm{cm}.
$$

Find its density in $\mathrm{kg\ m^{-3}}$ with an uncertainty.

### Solution

The density is

$$
\rho=\frac{m}{a^3}.
$$

The central value is

$$
\rho=\frac{48.0}{2.00^3}
=\frac{48.0}{8.00}
=6.00\ \mathrm{g\ cm^{-3}}.
$$

Convert the unit:

$$
1\ \mathrm{g\ cm^{-3}}
=\frac{10^{-3}\ \mathrm{kg}}{10^{-6}\ \mathrm{m^3}}
=10^3\ \mathrm{kg\ m^{-3}}.
$$

So

$$
\rho=6.00\times 10^3\ \mathrm{kg\ m^{-3}}.
$$

For multiplication, division, and powers, add percentage uncertainties. The
mass percentage uncertainty is

$$
\frac{0.1}{48.0}\times 100\%=0.21\%.
$$

The side-length percentage uncertainty is

$$
\frac{0.01}{2.00}\times 100\%=0.50\%.
$$

Because $a$ is cubed, this contributes

$$
3(0.50\%)=1.50\%.
$$

The total percentage uncertainty in $\rho$ is approximately

$$
0.21\%+1.50\%=1.71\%.
$$

The absolute uncertainty is

$$
0.0171(6.00\times 10^3)
=1.03\times 10^2\ \mathrm{kg\ m^{-3}}.
$$

A sensible final result is

$$
\rho=(6.00\pm0.10)\times 10^3\ \mathrm{kg\ m^{-3}}.
$$

### Check

The density is much larger than water, so the value is plausible for a dense
solid. The uncertainty is dominated by the cubed length measurement.

## Example 7: Adding Coplanar Vectors by Components

**Prompt.** A force of $18\ \mathrm{N}$ acts at $35^\circ$ above east. A second
force of $12\ \mathrm{N}$ acts due west. Find the resultant force.

### Solution

Take east as positive $x$ and north as positive $y$.

For the $18\ \mathrm{N}$ force:

$$
F_x=18\cos35^\circ=14.7\ \mathrm{N},
$$

$$
F_y=18\sin35^\circ=10.3\ \mathrm{N}.
$$

The westward force has components

$$
(-12,\ 0)\ \mathrm{N}.
$$

So the resultant components are

$$
R_x=14.7-12=2.7\ \mathrm{N},
$$

$$
R_y=10.3\ \mathrm{N}.
$$

The magnitude is

$$
R=\sqrt{2.7^2+10.3^2}
=10.7\ \mathrm{N}.
$$

The direction above east is

$$
\theta=\tan^{-1}\left(\frac{10.3}{2.7}\right)
=75^\circ.
$$

The resultant is approximately

$$
10.7\ \mathrm{N}\ \text{at}\ 75^\circ\ \text{north of east}.
$$

### Check

The resultant is mostly north because the eastward component of the angled
force is nearly cancelled by the westward force.

## Example 8: Subtracting Vectors

**Prompt.** A ball's velocity changes from $8.0\ \mathrm{m\ s^{-1}}$ east to
$6.0\ \mathrm{m\ s^{-1}}$ north in $0.50\ \mathrm{s}$. Find the average
acceleration.

### Solution

Use

$$
\Delta \mathbf{v}=\mathbf{v}_{\text{final}}-\mathbf{v}_{\text{initial}}.
$$

Take east as positive $x$ and north as positive $y$. Then

$$
\mathbf{v}_{\text{initial}}=(8.0,\ 0)\ \mathrm{m\ s^{-1}},
$$

and

$$
\mathbf{v}_{\text{final}}=(0,\ 6.0)\ \mathrm{m\ s^{-1}}.
$$

So

$$
\Delta \mathbf{v}=(-8.0,\ 6.0)\ \mathrm{m\ s^{-1}}.
$$

The magnitude of the change in velocity is

$$
|\Delta \mathbf{v}|
=\sqrt{8.0^2+6.0^2}
=10.0\ \mathrm{m\ s^{-1}}.
$$

The average acceleration has magnitude

$$
a=\frac{10.0}{0.50}
=20\ \mathrm{m\ s^{-2}}.
$$

The direction is the direction of $\Delta \mathbf{v}$:

$$
\theta=\tan^{-1}\left(\frac{8.0}{6.0}\right)=53^\circ.
$$

So the acceleration is

$$
20\ \mathrm{m\ s^{-2}}\ \text{at}\ 53^\circ\ \text{west of north}.
$$

### Check

The acceleration is not directed north. It must point in the direction of the
change in velocity, which includes losing eastward velocity and gaining
northward velocity.
