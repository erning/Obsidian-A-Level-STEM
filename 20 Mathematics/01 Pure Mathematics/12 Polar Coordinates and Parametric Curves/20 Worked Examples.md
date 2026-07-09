---
title: Polar Coordinates and Parametric Curves Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Polar Coordinates and Parametric Curves](00%20Overview.md)"
status: active
tags:
  - mathematics/pure
  - worked-examples
---

# Polar Coordinates and Parametric Curves Worked Examples

These examples model the CAIE route through polar coordinates and parametric
curves: coordinate conversion, curve conversion, polar sketch features, polar
area, parametric differentiation, and tangents.

## Source Route

- Syllabus: CAIE Further Mathematics 9231 section 1.5; CAIE Mathematics 9709
  sections 2.4 and 3.4 for parametric differentiation.
- Polar scope: convert between Cartesian and polar forms, sketch simple polar
  curves on stated intervals, identify key features, and use
  $\frac12\int r^2\,d\theta$ for sector area.
- Parametric scope: find and use first derivatives for parametrically defined
  curves, including tangents and normals.

## Example 1: Convert Polar and Cartesian Points

**Prompt.** Convert $(4,2\pi/3)$ to Cartesian coordinates, then find the
principal polar coordinates of $(-\sqrt3,1)$.

**Solution.**

For $(4,2\pi/3)$,

$$
x=r\cos\theta=4\cos\frac{2\pi}{3}=-2,
$$

and

$$
y=r\sin\theta=4\sin\frac{2\pi}{3}=2\sqrt3.
$$

So the Cartesian coordinates are

$$
(-2,2\sqrt3).
$$

For $(-\sqrt3,1)$,

$$
r=\sqrt{(-\sqrt3)^2+1^2}=2.
$$

The point is in the second quadrant and has reference angle $\pi/6$, so

$$
\theta=\frac{5\pi}{6}.
$$

The principal polar coordinates are

$$
\left(2,\frac{5\pi}{6}\right).
$$

**What this example trains.** The quadrant decides the angle, not the tangent
ratio alone.

## Example 2: Convert Equations

**Prompt.** Convert $x^2+y^2=4x$ to polar form, and convert
$r=3\cosec\theta$ to Cartesian form.

**Solution.**

Use

$$
x=r\cos\theta,\qquad y=r\sin\theta,\qquad x^2+y^2=r^2.
$$

Then

$$
x^2+y^2=4x
$$

becomes

$$
r^2=4r\cos\theta.
$$

For $r\ne0$,

$$
r=4\cos\theta.
$$

The pole also lies on both equations, so this polar equation represents the
same circle.

For

$$
r=3\cosec\theta,
$$

multiply by $\sin\theta$:

$$
r\sin\theta=3.
$$

Since $y=r\sin\theta$,

$$
y=3.
$$

**What this example trains.** Use $r^2=x^2+y^2$, $x=r\cos\theta$, and
$y=r\sin\theta$ before trying harder algebra.

## Example 3: Key Features of a Polar Curve

**Prompt.** Describe the key features of

$$
r=2+2\cos\theta,\qquad 0\le\theta\le\pi.
$$

**Solution.**

Since $\cos\theta$ decreases from $1$ to $-1$ on $0\le\theta\le\pi$,

$$
r(0)=4,\qquad r\left(\frac{\pi}{2}\right)=2,\qquad r(\pi)=0.
$$

Also $r\ge0$ on the whole interval. The curve starts on the initial line at
distance $4$, passes through the point with polar coordinates
$(2,\pi/2)$, and reaches the pole at $\theta=\pi$.

For the full curve $0\le\theta<2\pi$, the equation is symmetric about the
initial line because $\cos(-\theta)=\cos\theta$.

**What this example trains.** A polar sketch should show endpoints, pole
behaviour, symmetry, and least or greatest $r$.

## Example 4: Polar Area

**Prompt.** Find the area swept out by

$$
r=2+2\cos\theta
$$

from $\theta=0$ to $\theta=\pi$.

**Solution.**

Use

$$
A=\frac12\int_\alpha^\beta r^2\,d\theta.
$$

Here

$$
A=\frac12\int_0^\pi (2+2\cos\theta)^2\,d\theta.
$$

Expand:

$$
(2+2\cos\theta)^2
=4+8\cos\theta+4\cos^2\theta.
$$

So

$$
A=\frac12\int_0^\pi(4+8\cos\theta+4\cos^2\theta)\,d\theta.
$$

Since

$$
\int_0^\pi\cos\theta\,d\theta=0
$$

and

$$
\int_0^\pi\cos^2\theta\,d\theta=\frac{\pi}{2},
$$

we get

$$
A=\frac12(4\pi+2\pi)=3\pi.
$$

**What this example trains.** Polar area uses $r^2$, and the limits must come
from the part of the curve being traced.

## Example 5: Intersections of Polar Curves

**Prompt.** Find the intersections of

$$
r=2
$$

and

$$
r=4\cos\theta
$$

for $-\pi<\theta\le\pi$.

**Solution.**

At an intersection with the same angle,

$$
2=4\cos\theta.
$$

So

$$
\cos\theta=\frac12.
$$

In the stated interval,

$$
\theta=\frac{\pi}{3}
\quad\text{or}\quad
\theta=-\frac{\pi}{3}.
$$

The intersection points are

$$
\left(2,\frac{\pi}{3}\right)
\quad\text{and}\quad
\left(2,-\frac{\pi}{3}\right).
$$

**What this example trains.** The angle interval decides which polar
descriptions to list.

## Example 6: Eliminate a Parameter

**Prompt.** The curve is

$$
x=t+1,\qquad y=t^2,\qquad t\ge0.
$$

Find its Cartesian equation and range restriction.

**Solution.**

From

$$
x=t+1,
$$

we have

$$
t=x-1.
$$

Substitute into $y=t^2$:

$$
y=(x-1)^2.
$$

Since $t\ge0$,

$$
x\ge1.
$$

So the curve is the right-hand part of the parabola

$$
y=(x-1)^2,\qquad x\ge1.
$$

**What this example trains.** Eliminating a parameter does not remove the
original parameter range.

## Example 7: Tangent to a Parametric Curve

**Prompt.** For

$$
x=t^2+1,\qquad y=t^3-t,
$$

find the tangent at $t=1$.

**Solution.**

The point is

$$
x=2,\qquad y=0.
$$

Differentiate with respect to $t$:

$$
\frac{dx}{dt}=2t,
\qquad
\frac{dy}{dt}=3t^2-1.
$$

Therefore

$$
\frac{dy}{dx}
=\frac{dy/dt}{dx/dt}
=\frac{3t^2-1}{2t}.
$$

At $t=1$,

$$
\frac{dy}{dx}=1.
$$

The tangent through $(2,0)$ with gradient $1$ is

$$
y=x-2.
$$

**What this example trains.** The gradient of a parametric curve is
$\frac{dy/dt}{dx/dt}$, not $\frac{dy}{dt}$.

## Example 8: Stationary and Vertical Tangents

**Prompt.** For

$$
x=t^2,\qquad y=t^3-3t,
$$

find the horizontal and vertical tangents.

**Solution.**

Differentiate:

$$
\frac{dx}{dt}=2t,\qquad \frac{dy}{dt}=3t^2-3.
$$

Horizontal tangents occur when

$$
\frac{dy}{dt}=0,\qquad \frac{dx}{dt}\ne0.
$$

So

$$
3t^2-3=0,
$$

giving

$$
t=\pm1.
$$

The points are

$$
(1,-2)
\quad\text{and}\quad
(1,2).
$$

Vertical tangents occur when

$$
\frac{dx}{dt}=0,\qquad \frac{dy}{dt}\ne0.
$$

So $t=0$, giving the point

$$
(0,0).
$$

**What this example trains.** Check which derivative is zero before naming a
horizontal or vertical tangent.
