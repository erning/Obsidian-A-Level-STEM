---
title: Integration Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/06 Integration/00 Overview|Integration]]"
status: active
tags:
  - mathematics/pure
  - worked-examples
---

# Integration Worked Examples

These examples model the standard CAIE route through reverse differentiation,
definite integrals, areas, volumes of revolution, substitution, integration by
parts, partial fractions, trigonometric identities, improper integrals, and the
trapezium rule.

## Source Route

- Syllabus: CAIE Mathematics 9709 sections 1.8, 2.5, and 3.5; CAIE Further
  Mathematics 9231 section 2.4.
- Main subtopics: indefinite and definite integration, constants of
  integration, areas, volumes of revolution, improper integrals, exponential,
  logarithmic and trigonometric forms, substitution, integration by parts,
  partial fractions, trapezium rule, and selected further integration ideas.
- Coursebook route: 9709 Pure Mathematics 1 Chapter 9; 9709 Pure Mathematics
  2 and 3 Chapters 5 and 8; 9231 integration content.

## Example 1: Reverse Chain Rule

**Prompt.** Find

$$
\int (2x+1)^5\,dx.
$$

**Solution.**

The inner derivative of $2x+1$ is $2$, so divide by $2$ after increasing the
power:

$$
\int (2x+1)^5\,dx
=\frac{(2x+1)^6}{6\cdot2}+C.
$$

Therefore

$$
\int (2x+1)^5\,dx=\frac{(2x+1)^6}{12}+C.
$$

**What this example trains.** Reverse the chain rule and always include $C$.

## Example 2: Finding a Curve From Its Gradient

**Prompt.** A curve has

$$
\frac{dy}{dx}=3x^2-4x+1
$$

and passes through $(1,-2)$. Find its equation.

**Solution.**

Integrate:

$$
y=x^3-2x^2+x+C.
$$

Use the point $(1,-2)$:

$$
-2=1-2+1+C.
$$

Thus

$$
C=-2.
$$

The curve is

$$
y=x^3-2x^2+x-2.
$$

**What this example trains.** The constant of integration is determined from a
point or initial condition.

## Example 3: Signed Integral and Geometric Area

**Prompt.** Evaluate

$$
\int_0^3(x^2-4x)\,dx
$$

and state the geometric area between the curve and the $x$-axis on this
interval.

**Solution.**

The definite integral is

$$
\left[\frac{x^3}{3}-2x^2\right]_0^3
=9-18
=-9.
$$

On $0<x<3$, the function $x^2-4x=x(x-4)$ is below the $x$-axis. Therefore the
geometric area is

$$
9.
$$

**What this example trains.** A definite integral is signed; geometric area is
positive.

## Example 4: Area Between Curves

**Prompt.** Find the area between

$$
y=4-x^2
$$

and

$$
y=x+2.
$$

**Solution.**

Find intersections:

$$
4-x^2=x+2.
$$

So

$$
x^2+x-2=0,
$$

giving

$$
x=-2,\ 1.
$$

On this interval, $4-x^2$ is above $x+2$. The area is

$$
\int_{-2}^{1}\left((4-x^2)-(x+2)\right)\,dx
=\int_{-2}^{1}(2-x-x^2)\,dx.
$$

Therefore

$$
\left[2x-\frac{x^2}{2}-\frac{x^3}{3}\right]_{-2}^{1}
=\frac{9}{2}.
$$

**What this example trains.** Sketch or test a point to decide upper curve
minus lower curve.

## Example 5: Volume of Revolution

**Prompt.** The region under

$$
y=\sqrt{x}
$$

from $x=0$ to $x=4$ is rotated about the $x$-axis. Find the volume.

**Solution.**

Use

$$
V=\pi\int_a^b y^2\,dx.
$$

Here $y^2=x$, so

$$
V=\pi\int_0^4 x\,dx.
$$

Thus

$$
V=\pi\left[\frac{x^2}{2}\right]_0^4=8\pi.
$$

**What this example trains.** Volumes of revolution use $y^2$, not $y$.

## Example 6: Substitution

**Prompt.** Find

$$
\int 2x(x^2+1)^5\,dx.
$$

**Solution.**

Let

$$
u=x^2+1.
$$

Then

$$
du=2x\,dx.
$$

So

$$
\int 2x(x^2+1)^5\,dx=\int u^5\,du
=\frac{u^6}{6}+C.
$$

Returning to $x$ gives

$$
\frac{(x^2+1)^6}{6}+C.
$$

**What this example trains.** Substitution works when the derivative of the
inside is present.

## Example 7: Integration by Parts

**Prompt.** Find

$$
\int x e^{2x}\,dx.
$$

**Solution.**

Choose

$$
u=x,\qquad \frac{dv}{dx}=e^{2x}.
$$

Then

$$
\frac{du}{dx}=1,\qquad v=\frac{1}{2}e^{2x}.
$$

Using integration by parts,

$$
\int x e^{2x}\,dx
=\frac{x}{2}e^{2x}-\int \frac{1}{2}e^{2x}\,dx.
$$

Thus

$$
\int x e^{2x}\,dx
=\frac{x}{2}e^{2x}-\frac{1}{4}e^{2x}+C.
$$

**What this example trains.** Choose $u$ as the part that becomes simpler when
differentiated.

## Example 8: Partial Fractions

**Prompt.** Find

$$
\int \frac{3x+5}{(x+1)(x+2)}\,dx.
$$

**Solution.**

Write

$$
\frac{3x+5}{(x+1)(x+2)}
=\frac{A}{x+1}+\frac{B}{x+2}.
$$

Then

$$
3x+5=A(x+2)+B(x+1).
$$

Comparing coefficients gives

$$
A=2,\qquad B=1.
$$

So

$$
\int \frac{3x+5}{(x+1)(x+2)}\,dx
=2\ln|x+1|+\ln|x+2|+C.
$$

**What this example trains.** Partial fractions turn a rational function into
logarithmic integrals.

## Example 9: Trigonometric Identity

**Prompt.** Evaluate

$$
\int_0^{\frac{\pi}{2}}\sin^2x\,dx.
$$

**Solution.**

Use

$$
\sin^2x=\frac{1-\cos2x}{2}.
$$

Then

$$
\int_0^{\frac{\pi}{2}}\sin^2x\,dx
=\int_0^{\frac{\pi}{2}}\frac{1-\cos2x}{2}\,dx.
$$

So

$$
=\left[\frac{x}{2}-\frac{\sin2x}{4}\right]_0^{\frac{\pi}{2}}
=\frac{\pi}{4}.
$$

**What this example trains.** A trigonometric identity can change the integrand
into a directly integrable form.

## Example 10: Trapezium Rule

**Prompt.** Use the trapezium rule with four strips to estimate

$$
\int_0^2(x^2+1)\,dx.
$$

State whether the estimate is likely to be an over-estimate or under-estimate.

**Solution.**

Here

$$
h=\frac{2-0}{4}=\frac{1}{2}.
$$

The $x$-values are $0,\frac{1}{2},1,\frac{3}{2},2$. The corresponding
$y=x^2+1$ values are

$$
1,\ \frac{5}{4},\ 2,\ \frac{13}{4},\ 5.
$$

The trapezium rule gives

$$
\frac{h}{2}\left(y_0+2y_1+2y_2+2y_3+y_4\right)
=\frac{1}{4}\left(1+2\cdot\frac{5}{4}+2(2)+2\cdot\frac{13}{4}+5\right).
$$

Thus the estimate is

$$
\frac{19}{4}.
$$

Since $y=x^2+1$ bends upward, the trapezia lie above the curve, so this is an
over-estimate.

**What this example trains.** Use the correct strip width and use the sketch to
interpret the direction of error.
