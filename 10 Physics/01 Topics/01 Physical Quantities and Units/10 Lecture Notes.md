---
title: Physical Quantities and Units Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/01 Physical Quantities and Units/00 Overview|Physical Quantities and Units]]"
status: draft
tags:
  - physics/9702/topic
  - physics/9702/foundations
  - lecture-notes
---

# Physical Quantities and Units Lecture Notes

Physics begins when a description becomes measurable. "The trolley moves fast" is a useful observation, but it is not yet a physics statement. "The trolley has an average speed of $0.76\ \mathrm{m\ s^{-1}}$" is different: it gives a quantity, a numerical magnitude, a unit, and enough structure for another person to check the result.

This topic is the toolkit for that kind of statement. By the end of it, you should be able to read a physical quantity as more than a number. You should be able to ask what it measures, what unit it carries, how uncertain it is, and whether direction matters.

The habit is simple:

1. Name the quantity.
2. Write the value with its unit.
3. Check whether the unit makes sense.
4. State the uncertainty when the value comes from measurement.
5. Treat direction explicitly when the quantity is a vector.

## Visual guide

![[assets/generated/physics/physical-quantities-and-units.svg]]

This guide connects the main ideas of the topic: quantities need units, measurements need uncertainties, and vectors need components when directions matter.

## Source route

The syllabus route is CAIE Physics 9702, section 1:

- 1.1 Physical quantities
- 1.2 SI units
- 1.3 Errors and uncertainties
- 1.4 Scalars and vectors

The coursebook treats these ideas in several places: Appendix 1 for physical quantities, SI units, prefixes, and estimation; Practical Skills P1 for errors and uncertainties; early mechanics chapters for scalars, vectors, vector addition, and components.

## 1. Physical quantities

A physical quantity consists of a numerical magnitude and a unit. Both parts matter.

$$
\text{physical quantity}=\text{numerical magnitude}+\text{unit}
$$

For example,

$$
l=2.40\ \mathrm{m}
$$

means that the length is $2.40$ metres. The number $2.40$ on its own is incomplete. It could mean $2.40\ \mathrm{m}$, $2.40\ \mathrm{cm}$, $2.40\ \mathrm{s}$, or something else entirely.

Units are not decoration at the end of a calculation. They are part of the physical meaning. If

$$
v=\frac{s}{t},
$$

and displacement is measured in metres while time is measured in seconds, then the unit of velocity is

$$
\mathrm{m\ s^{-1}}.
$$

When you meet a new equation, read it aloud in quantities before substituting numbers. For

$$
p=\frac{F}{A},
$$

say: pressure is force per unit area. This is more useful than memorising a symbol pattern, because it tells you what the equation means.

## 2. Estimating physical quantities

An estimate is a rough but sensible value. It is not a guess without thinking. It uses benchmarks that you already know.

Useful benchmarks include:

| Quantity | Approximate value |
|---|---:|
| Mass of a person | $70\ \mathrm{kg}$ |
| Height of a person | $2\ \mathrm{m}$ |
| Walking speed | $1\ \mathrm{m\ s^{-1}}$ |
| Speed of a car on a motorway | $30\ \mathrm{m\ s^{-1}}$ |
| Density of water | $1000\ \mathrm{kg\ m^{-3}}$ |
| Weight of an apple | $1\ \mathrm{N}$ |
| e.m.f. of a car battery | $12\ \mathrm{V}$ |

Estimation is a guardrail. If a calculation gives a walking speed of $800\ \mathrm{m\ s^{-1}}$, the arithmetic may be tidy, but the answer is physically absurd. Stop and check the units, the powers of ten, and whether you converted prefixes correctly.

## 3. SI base units

The SI system builds units from a small set of base units. The coursebook lists seven base units:

| Base quantity | SI base unit | Symbol |
|---|---|---|
| mass | kilogram | $\mathrm{kg}$ |
| length | metre | $\mathrm{m}$ |
| time | second | $\mathrm{s}$ |
| electric current | ampere | $\mathrm{A}$ |
| thermodynamic temperature | kelvin | $\mathrm{K}$ |
| amount of substance | mole | $\mathrm{mol}$ |
| luminous intensity | candela | $\mathrm{cd}$ |

In this physics course, mass, length, time, current, and temperature appear constantly. Mole appears in thermal and nuclear contexts. Candela is part of SI, but it is rarely needed in these notes.

Write unit symbols carefully:

- Use $\mathrm{m}$ for metre and $\mathrm{s}$ for second.
- Use $\mathrm{kg}$ as the SI base unit for mass, not $\mathrm{g}$.
- Use negative powers for compound units when that is clearer: $\mathrm{m\ s^{-1}}$ instead of $\mathrm{m/s}$.
- Leave a space between the number and the unit: $4.8\ \mathrm{N}$.

## 4. Derived units

Most physical units are derived from base units. Start from a definition or equation, then replace each quantity by its unit.

For force,

$$
F=ma.
$$

Mass has unit $\mathrm{kg}$ and acceleration has unit $\mathrm{m\ s^{-2}}$, so

$$
\mathrm{N}=\mathrm{kg\ m\ s^{-2}}.
$$

The newton is a named derived unit:

$$
1\ \mathrm{N}=1\ \mathrm{kg\ m\ s^{-2}}.
$$

Common derived units include:

| Quantity | Unit | In SI base units |
|---|---|---|
| frequency | $\mathrm{Hz}$ | $\mathrm{s^{-1}}$ |
| force | $\mathrm{N}$ | $\mathrm{kg\ m\ s^{-2}}$ |
| energy, work | $\mathrm{J}$ | $\mathrm{kg\ m^2\ s^{-2}}$ |
| power | $\mathrm{W}$ | $\mathrm{kg\ m^2\ s^{-3}}$ |
| pressure | $\mathrm{Pa}$ | $\mathrm{kg\ m^{-1}\ s^{-2}}$ |
| charge | $\mathrm{C}$ | $\mathrm{A\ s}$ |
| potential difference | $\mathrm{V}$ | $\mathrm{kg\ m^2\ A^{-1}\ s^{-3}}$ |
| resistance | $\Omega$ | $\mathrm{kg\ m^2\ A^{-2}\ s^{-3}}$ |

You do not need to memorise every base-unit form at once. You do need to be able to derive them.

For pressure,

$$
p=\frac{F}{A}.
$$

The unit is

$$
\mathrm{N\ m^{-2}}.
$$

Replacing $\mathrm{N}$ by $\mathrm{kg\ m\ s^{-2}}$ gives

$$
\mathrm{N\ m^{-2}}
=\mathrm{kg\ m\ s^{-2}\ m^{-2}}
=\mathrm{kg\ m^{-1}\ s^{-2}}.
$$

This habit becomes very useful later. It lets you check unfamiliar formulae instead of relying on memory.

## 5. Prefixes and powers of ten

Physics uses very small and very large quantities. Prefixes are shorthand for powers of ten.

| Prefix | Symbol | Multiplier |
|---|---|---:|
| tera | $\mathrm{T}$ | $10^{12}$ |
| giga | $\mathrm{G}$ | $10^9$ |
| mega | $\mathrm{M}$ | $10^6$ |
| kilo | $\mathrm{k}$ | $10^3$ |
| deci | $\mathrm{d}$ | $10^{-1}$ |
| centi | $\mathrm{c}$ | $10^{-2}$ |
| milli | $\mathrm{m}$ | $10^{-3}$ |
| micro | $\mu$ | $10^{-6}$ |
| nano | $\mathrm{n}$ | $10^{-9}$ |
| pico | $\mathrm{p}$ | $10^{-12}$ |

Convert to SI units before using a formula unless there is a clear reason not to.

$$
3.5\ \mathrm{km}=3.5\times 10^3\ \mathrm{m}
$$

$$
250\ \mu\mathrm{s}=250\times 10^{-6}\ \mathrm{s}=2.50\times 10^{-4}\ \mathrm{s}
$$

$$
3.2\ \mathrm{k}\Omega=3.2\times 10^3\ \Omega
$$

Be careful when the unit is squared or cubed. The prefix is part of the whole unit:

$$
1\ \mathrm{cm}=10^{-2}\ \mathrm{m}
$$

but

$$
1\ \mathrm{cm^3}=(10^{-2}\ \mathrm{m})^3=10^{-6}\ \mathrm{m^3}.
$$

This is a common source of powers-of-ten errors.

## 6. Homogeneity of physical equations

A physical equation must be homogeneous: every term must have the same unit.

Consider

$$
s=ut+\frac{1}{2}at^2.
$$

The left-hand side is displacement, with unit $\mathrm{m}$. On the right-hand side,

$$
ut=(\mathrm{m\ s^{-1}})(\mathrm{s})=\mathrm{m},
$$

and

$$
at^2=(\mathrm{m\ s^{-2}})(\mathrm{s^2})=\mathrm{m}.
$$

Both terms on the right have unit $\mathrm{m}$, so the equation passes the unit check.

Try the same check with kinetic energy:

$$
E_k=\frac{1}{2}mv^2.
$$

The right-hand side has units

$$
\mathrm{kg}(\mathrm{m\ s^{-1}})^2
=\mathrm{kg\ m^2\ s^{-2}},
$$

which is the unit of energy, $\mathrm{J}$.

Homogeneity can prove that an equation is impossible if the units do not match. It cannot prove that an equation is correct. For example, a missing numerical factor such as $2$ or $\frac{1}{2}$ will not be detected by units.

Two extra checks are worth remembering:

- You cannot add terms with different units.
- The argument of a trigonometric, logarithmic, or exponential function must be dimensionless.

For example, $\sin\theta$ is acceptable because $\theta$ is an angle. But $\sin(5\ \mathrm{m})$ is not a meaningful physical expression.

## 7. Errors and uncertainties

Measurements are never exact. A measured value should be treated as an estimate of a true value, with some uncertainty.

For example,

$$
x=(2.40\pm0.02)\ \mathrm{m}
$$

means that the measured length is $2.40\ \mathrm{m}$ and the absolute uncertainty is $0.02\ \mathrm{m}$.

The fractional uncertainty is

$$
\frac{0.02}{2.40}.
$$

The percentage uncertainty is

$$
\frac{0.02}{2.40}\times 100\%=0.83\%.
$$

Use these words precisely:

| Term | Meaning |
|---|---|
| absolute uncertainty | uncertainty written in the same unit as the measured quantity |
| fractional uncertainty | absolute uncertainty divided by the measured value |
| percentage uncertainty | fractional uncertainty multiplied by $100\%$ |
| precision | how close repeated readings are to each other |
| accuracy | how close a reading is to the true value |

Precision and accuracy are not the same. A set of readings can be precise but inaccurate if they cluster tightly around the wrong value. That often happens when there is a systematic error.

## 8. Random, systematic, and zero errors

A random error causes readings to vary in an unpredictable way from one measurement to another. Repeating the measurement and taking a mean can reduce the effect of random error.

A systematic error shifts readings in the same direction each time. Repeating the measurement does not remove it. You need to identify the cause, such as calibration error, poor method, or an instrument that is not reading zero when the true value is zero.

A zero error is a systematic error caused by an instrument giving a non-zero reading when the true value is zero. For example, a micrometer that reads $0.03\ \mathrm{mm}$ when fully closed has a zero error.

When estimating uncertainty, use the context:

- For a single reading from an analogue scale, the uncertainty is often about half the smallest division, if the scale can be read to that precision.
- For a digital instrument, the uncertainty is often related to the smallest change in the displayed reading.
- For repeated readings, a common estimate of the absolute uncertainty is half the range:

$$
\Delta x=\frac{x_{\max}-x_{\min}}{2}.
$$

The exact convention depends on the instrument and the experiment. The important point is to state a sensible uncertainty and use it consistently.

## 9. Combining uncertainties

When values are combined in a calculation, their uncertainties must be combined too.

For addition or subtraction, add absolute uncertainties.

If

$$
L=a-b,
$$

where

$$
a=(5.20\pm0.02)\ \mathrm{cm}
$$

and

$$
b=(1.10\pm0.01)\ \mathrm{cm},
$$

then

$$
L=4.10\ \mathrm{cm}
$$

with uncertainty

$$
\Delta L=0.02+0.01=0.03\ \mathrm{cm}.
$$

So

$$
L=(4.10\pm0.03)\ \mathrm{cm}.
$$

For multiplication or division, add percentage uncertainties.

Suppose

$$
R=\frac{V}{I},
$$

where

$$
V=(6.0\pm0.2)\ \mathrm{V}
$$

and

$$
I=(2.4\pm0.1)\ \mathrm{A}.
$$

The resistance is

$$
R=\frac{6.0}{2.4}=2.5\ \Omega.
$$

The percentage uncertainty in $V$ is

$$
\frac{0.2}{6.0}\times100\%=3.3\%.
$$

The percentage uncertainty in $I$ is

$$
\frac{0.1}{2.4}\times100\%=4.2\%.
$$

For division, add them:

$$
3.3\%+4.2\%=7.5\%.
$$

So the absolute uncertainty in $R$ is approximately

$$
0.075\times2.5\ \Omega=0.19\ \Omega.
$$

A sensible final answer is

$$
R=(2.5\pm0.2)\ \Omega.
$$

For powers, multiply the percentage uncertainty by the power. If

$$
Q=x^n,
$$

then the percentage uncertainty in $Q$ is approximately $n$ times the percentage uncertainty in $x$.

These are simple uncertainty rules. They are not the whole of statistics, but they are the rules you need for ordinary A-Level physics calculations.

## 10. Scalars and vectors

A scalar has magnitude only. A vector has magnitude and direction.

| Scalar quantities | Vector quantities |
|---|---|
| distance | displacement |
| speed | velocity |
| mass | force |
| time | acceleration |
| energy | momentum |
| temperature | electric field strength |

The distinction matters because direction changes how vectors combine.

If you walk $3\ \mathrm{m}$ east and then $3\ \mathrm{m}$ west, the total distance travelled is

$$
6\ \mathrm{m},
$$

but the displacement is

$$
0\ \mathrm{m}.
$$

Distance is a scalar, so it adds without direction. Displacement is a vector, so opposite directions can cancel.

The same idea explains the difference between speed and velocity. Speed is the rate of change of distance. Velocity is the rate of change of displacement, so it includes direction.

## 11. Adding and subtracting coplanar vectors

Coplanar vectors lie in the same plane. They can be added by a scale diagram or by components.

For a scale diagram:

1. Choose a scale, such as $1\ \mathrm{cm}$ representing $2\ \mathrm{N}$.
2. Draw the first vector in the correct direction.
3. Draw the second vector starting at the head of the first.
4. Draw the resultant from the tail of the first vector to the head of the last vector.
5. Measure the magnitude and direction of the resultant.

This is called the head-to-tail method.

For perpendicular vectors, use Pythagoras and trigonometry. If a vector $P$ of $3.0\ \mathrm{N}$ acts east and a vector $Q$ of $4.0\ \mathrm{N}$ acts north, the resultant has magnitude

$$
R=\sqrt{3.0^2+4.0^2}=5.0\ \mathrm{N}.
$$

The angle above east is

$$
\theta=\tan^{-1}\left(\frac{4.0}{3.0}\right)=53^\circ.
$$

So the resultant is $5.0\ \mathrm{N}$ at $53^\circ$ north of east.

To subtract a vector, add the negative of that vector:

$$
\mathbf{A}-\mathbf{B}=\mathbf{A}+(-\mathbf{B}).
$$

The vector $-\mathbf{B}$ has the same magnitude as $\mathbf{B}$ but points in the opposite direction.

## 12. Resolving a vector into components

Resolving a vector means splitting it into perpendicular components. This is the reverse of vector addition.

If a vector $A$ makes an angle $\theta$ with the positive $x$-direction, then

$$
A_x=A\cos\theta
$$

and

$$
A_y=A\sin\theta.
$$

The component along a chosen direction is found using the angle between the vector and that direction:

$$
\text{component along the direction}=A\cos\theta.
$$

This is often the safest rule. The component next to the angle uses cosine; the perpendicular component uses sine.

Components are useful because they let you treat perpendicular directions separately. Later, projectile motion works because horizontal and vertical motion can be analysed as separate components of one motion.

## 13. A working routine for problems

Use this routine for this chapter:

1. Convert all quantities into SI units.
2. Write down the equation in symbols before substituting values.
3. Check that the units on both sides are homogeneous.
4. Carry units through the calculation.
5. Estimate whether the numerical answer is reasonable.
6. If the quantities are measured, calculate absolute or percentage uncertainty as needed.
7. If vectors are involved, draw a diagram before doing algebra.

This routine may feel slow at first. It saves time later because it catches the common mistakes early: missing powers of ten, wrong directions, and impossible units.

## 14. Common mistakes

- Writing a number without a unit.
- Using $\mathrm{g}$ instead of $\mathrm{kg}$ in an SI calculation.
- Forgetting that $1\ \mathrm{cm^3}=10^{-6}\ \mathrm{m^3}$.
- Treating a unit check as proof that an equation is correct.
- Confusing accuracy with precision.
- Reducing random error by repetition but forgetting that systematic error remains.
- Adding uncertainties with signs. Uncertainties are added as sizes, so they do not cancel.
- Adding vector magnitudes without checking direction.
- Giving a vector answer without a direction.
- Using sine and cosine by memory rather than checking which component is adjacent to the angle.

## Quick self-check

You are ready to move on when you can do these without looking up the method:

- Explain why a physical quantity needs both a numerical magnitude and a unit.
- Recall the SI base units for mass, length, time, current, and temperature.
- Convert between prefixes from pico to tera.
- Express $\mathrm{N}$, $\mathrm{J}$, $\mathrm{W}$, $\mathrm{Pa}$, $\mathrm{C}$, $\mathrm{V}$, and $\Omega$ in base units when needed.
- Check the homogeneity of a physical equation.
- Distinguish random error, systematic error, zero error, precision, and accuracy.
- Convert between absolute and percentage uncertainty.
- Combine uncertainties for sums, differences, products, quotients, and powers.
- Decide whether a quantity is a scalar or a vector.
- Add, subtract, and resolve coplanar vectors.

## Connections

- [[10 Physics/02 Experimental Thinking/Measurement and Data Presentation/00 Overview|Measurement and Data Presentation]]
- [[10 Physics/04 Reference/Math Tools and Formulae|Math Tools and Formulae]]
