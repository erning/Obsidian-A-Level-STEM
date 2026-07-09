---
title: Electricity Worked Examples
subject: Physics
syllabus: 9702
parent: "[Electricity](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/electricity
  - worked-examples
---

# Electricity Worked Examples

These examples model the standard CAIE route through charge flow, potential
difference, electrical power, resistance, $I$-$V$ characteristics, and
resistivity.

Use $e=1.60\times 10^{-19}\ \mathrm{C}$ where needed.

## Source Route

- Syllabus: CAIE Physics 9702 section 9, Electricity.
- Coursebook route: Chapters 8 and 10, especially electric current, potential
  difference, resistance, component characteristics, and resistivity.

## Example 1: Current as Rate of Flow of Charge

**Prompt.** A steady current of $0.35\ \mathrm{A}$ flows for
$4.0\ \mathrm{min}$. Find the charge that passes a point and the number of
electrons this represents.

**Solution.**

Convert time:

$$
t=4.0\ \mathrm{min}=240\ \mathrm{s}.
$$

Use

$$
Q=It.
$$

Thus

$$
Q=(0.35)(240)=84\ \mathrm{C}.
$$

The number of electrons is

$$
N=\frac{Q}{e}
=\frac{84}{1.60\times 10^{-19}}
=5.25\times 10^{20}.
$$

**What this example trains.** Current is charge per unit time; minutes must be
converted to seconds.

## Example 2: Quantisation of Charge

**Prompt.** An isolated particle has charge $-4.80\times 10^{-19}\ \mathrm{C}$.
How many elementary charges does this represent? Explain whether
$+5.00\times 10^{-19}\ \mathrm{C}$ is possible for an isolated ion.

**Solution.**

Divide by the elementary charge:

$$
\frac{-4.80\times 10^{-19}}{1.60\times 10^{-19}}
=-3.
$$

So the charge is $-3e$. It could represent three excess electrons.

For $+5.00\times 10^{-19}\ \mathrm{C}$,

$$
\frac{5.00\times 10^{-19}}{1.60\times 10^{-19}}
=3.125.
$$

This is not an integer, so it is not a possible net charge for an isolated ion.

**What this example trains.** Charge on isolated particles or ions comes in
integer multiples of $e$.

## Example 3: Drift Velocity

**Prompt.** A metal wire has cross-sectional area
$1.2\times 10^{-6}\ \mathrm{m^2}$ and free electron number density
$8.5\times 10^{28}\ \mathrm{m^{-3}}$. A current of $3.0\ \mathrm{A}$ flows.
Estimate the mean drift velocity of the electrons.

**Solution.**

Use the magnitude form of

$$
I=Anvq.
$$

Rearrange:

$$
v=\frac{I}{Anq}.
$$

Substitute:

$$
v=
\frac{3.0}
{(1.2\times 10^{-6})(8.5\times 10^{28})(1.60\times 10^{-19})}
=1.84\times 10^{-4}\ \mathrm{m\ s^{-1}}.
$$

This is a small speed. The circuit responds quickly because the electric field
is established through the circuit, not because one electron travels around the
whole circuit quickly.

**What this example trains.** Drift speed in metals is usually small even when
current begins almost immediately.

## Example 4: Potential Difference as Energy per Charge

**Prompt.** A component has potential difference $12\ \mathrm{V}$ across it.
$45\ \mathrm{C}$ of charge passes through the component in $30\ \mathrm{s}$.
Find the energy transferred and the current.

**Solution.**

Potential difference is energy transferred per unit charge:

$$
V=\frac{W}{Q}.
$$

So

$$
W=VQ=(12)(45)=540\ \mathrm{J}.
$$

Current:

$$
I=\frac{Q}{t}
=\frac{45}{30}
=1.5\ \mathrm{A}.
$$

**What this example trains.** Potential difference is not current. It is energy
per coulomb.

## Example 5: Electrical Power in a Resistor

**Prompt.** A resistor of resistance $8.0\ \Omega$ carries current
$2.5\ \mathrm{A}$ for $3.0\ \mathrm{min}$. Find the potential difference, the
power dissipated, and the energy transferred.

**Solution.**

Potential difference:

$$
V=IR=(2.5)(8.0)=20\ \mathrm{V}.
$$

Power:

$$
P=I^2R=(2.5)^2(8.0)=50\ \mathrm{W}.
$$

Time:

$$
t=3.0\ \mathrm{min}=180\ \mathrm{s}.
$$

Energy transferred:

$$
W=Pt=(50)(180)=9.0\times 10^3\ \mathrm{J}.
$$

**What this example trains.** Choose the power formula that matches the given
quantities.

## Example 6: Resistance from an $I$-$V$ Graph

**Prompt.** A metallic conductor at constant temperature has an $I$ against
$V$ graph that is a straight line through the origin. At $V=6.0\ \mathrm{V}$,
$I=0.24\ \mathrm{A}$. Find its resistance and the graph gradient.

**Solution.**

Resistance is

$$
R=\frac{V}{I}
=\frac{6.0}{0.24}
=25\ \Omega.
$$

For an $I$ against $V$ graph, the gradient is

$$
\frac{I}{V}=\frac{0.24}{6.0}
=0.040\ \mathrm{A\ V^{-1}}.
$$

This gradient is $1/R$, not $R$.

**What this example trains.** Always check which quantity is on each axis.

## Example 7: Testing Ohm's Law

**Prompt.** A component has current $10\ \mathrm{mA}$ when the p.d. is
$2.0\ \mathrm{V}$. When the p.d. is increased to $8.0\ \mathrm{V}$, the current
is $60\ \mathrm{mA}$. Does it obey Ohm's law?

**Solution.**

Calculate resistance at each operating point:

$$
R_1=\frac{2.0}{10\times 10^{-3}}
=200\ \Omega.
$$

For the second point,

$$
R_2=\frac{8.0}{60\times 10^{-3}}
=133\ \Omega.
$$

The resistance is not constant, so the current is not directly proportional to
the p.d. The component does not obey Ohm's law under these conditions.

**What this example trains.** Ohm's law is a proportionality condition, not
just the equation $V=IR$.

## Example 8: Filament Lamp Resistance

**Prompt.** A filament lamp takes current $0.30\ \mathrm{A}$ at
$2.0\ \mathrm{V}$ and current $0.60\ \mathrm{A}$ at $6.0\ \mathrm{V}$. Find the
resistance at each p.d. and explain the change.

**Solution.**

At $2.0\ \mathrm{V}$,

$$
R=\frac{2.0}{0.30}=6.7\ \Omega.
$$

At $6.0\ \mathrm{V}$,

$$
R=\frac{6.0}{0.60}=10\ \Omega.
$$

The resistance has increased. A larger current heats the filament, so the metal
ions vibrate more strongly. Electrons collide with the ions more frequently,
which increases the resistance.

**What this example trains.** A filament lamp is non-ohmic because its
temperature changes.

## Example 9: Resistivity of a Wire

**Prompt.** A wire of length $2.0\ \mathrm{m}$ and diameter
$0.40\ \mathrm{mm}$ has resistance $0.50\ \Omega$ at a fixed temperature.
Calculate its resistivity.

**Solution.**

Cross-sectional area:

$$
A=\frac{\pi d^2}{4}
=\frac{\pi(0.40\times 10^{-3})^2}{4}
=1.26\times 10^{-7}\ \mathrm{m^2}.
$$

Use

$$
R=\frac{\rho L}{A}.
$$

Rearrange:

$$
\rho=\frac{RA}{L}.
$$

Substitute:

$$
\rho=\frac{(0.50)(1.26\times 10^{-7})}{2.0}
=3.14\times 10^{-8}\ \Omega\ \mathrm{m}.
$$

**What this example trains.** Resistivity has unit $\Omega\ \mathrm{m}$ and
uses area, not diameter.

## Example 10: LDRs, Thermistors, and Diodes

**Prompt.** State how the resistance changes for an LDR in brighter light, for
an NTC thermistor at higher temperature, and for a silicon diode as forward
p.d. increases beyond about $0.6\ \mathrm{V}$.

**Solution.**

- For an LDR, brighter light releases more charge carriers in the
  semiconductor, so the resistance decreases.
- For an NTC thermistor, increasing temperature releases more charge carriers,
  so the resistance decreases.
- For a silicon diode, very little current flows until the forward p.d. reaches
  about $0.6\ \mathrm{V}$. Above this, the current rises rapidly and the
  effective resistance becomes much smaller.

**What this example trains.** Component resistance can depend on light,
temperature, and direction of applied p.d.
