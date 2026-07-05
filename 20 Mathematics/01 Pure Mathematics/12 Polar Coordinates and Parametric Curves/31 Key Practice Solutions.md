---
title: Polar Coordinates and Parametric Curves Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/12 Polar Coordinates and Parametric Curves/00 Overview|Polar Coordinates and Parametric Curves]]"
status: active
tags:
  - mathematics/pure
  - solutions
---

# Polar Coordinates and Parametric Curves Key Practice Solutions

This note gives worked solutions for [[20 Mathematics/01 Pure Mathematics/12 Polar Coordinates and Parametric Curves/30 Key Practice Problems|Polar Coordinates and Parametric Curves Key Practice Problems]]. Use it to check coordinate conventions, angle intervals, parameter restrictions, and tangent calculations.

## A. Polar Coordinates and Equations

## Problem 1

Use

$$
x=r\cos\theta,\qquad y=r\sin\theta.
$$

Then

$$
x=4\cos\frac{2\pi}{3}=-2,
\qquad
y=4\sin\frac{2\pi}{3}=2\sqrt3.
$$

So the Cartesian coordinates are

$$
(-2,2\sqrt3).
$$

## Problem 2

For $(-\sqrt3,1)$,

$$
r=\sqrt{(-\sqrt3)^2+1^2}=2.
$$

The point is in the second quadrant with reference angle $\pi/6$, so

$$
\theta=\frac{5\pi}{6}.
$$

The principal polar coordinates are

$$
\left(2,\frac{5\pi}{6}\right).
$$

## Problem 3

Adding or subtracting $2\pi$ gives the same point. Two other coordinate pairs
are

$$
\left(3,\frac{13\pi}{6}\right)
\quad\text{and}\quad
\left(3,-\frac{11\pi}{6}\right).
$$

## Problem 4

Use

$$
x^2+y^2=r^2,\qquad x=r\cos\theta.
$$

Then

$$
x^2+y^2=6x
$$

becomes

$$
r^2=6r\cos\theta.
$$

The equivalent polar equation is

$$
r=6\cos\theta.
$$

## Problem 5

Since

$$
y=r\sin\theta,
$$

the line $y=3$ becomes

$$
r\sin\theta=3.
$$

So

$$
r=3\cosec\theta.
$$

## Problem 6

The equation $r=5$ means the distance from the pole is $5$. Since

$$
r^2=x^2+y^2,
$$

the Cartesian form is

$$
x^2+y^2=25.
$$

## Problem 7

Multiply by $r$:

$$
r^2=4r\cos\theta.
$$

Using $r^2=x^2+y^2$ and $r\cos\theta=x$,

$$
x^2+y^2=4x.
$$

Equivalently,

$$
(x-2)^2+y^2=4.
$$

## Problem 8

Use

$$
\sin2\theta=2\sin\theta\cos\theta.
$$

Since

$$
\sin\theta=\frac{y}{r},
\qquad
\cos\theta=\frac{x}{r},
$$

we have

$$
\sin2\theta=\frac{2xy}{r^2}.
$$

Thus

$$
r^2=9\sin2\theta
$$

becomes

$$
r^2=\frac{18xy}{r^2}.
$$

Therefore

$$
(x^2+y^2)^2=18xy.
$$

## B. Polar Sketching, Intersections, and Area

## Problem 9

On $0\le\theta\le\pi$,

$$
r=3+3\cos\theta.
$$

Key values are

$$
r(0)=6,\qquad r\left(\frac{\pi}{2}\right)=3,\qquad r(\pi)=0.
$$

Also $r\ge0$ on this interval. The curve starts on the initial line at distance
$6$, passes through $(3,\pi/2)$, and reaches the pole at $\theta=\pi$.

For the full curve, it is symmetric about the initial line because
$\cos(-\theta)=\cos\theta$.

## Problem 10

Use polar area:

$$
A=\frac12\int_0^{\pi/2}r^2\,d\theta.
$$

With $r=2$,

$$
A=\frac12\int_0^{\pi/2}4\,d\theta
=2\cdot\frac{\pi}{2}
=\pi.
$$

## Problem 11

The area is

$$
A=\frac12\int_0^\pi(2+2\cos\theta)^2\,d\theta.
$$

Expand:

$$
(2+2\cos\theta)^2=4+8\cos\theta+4\cos^2\theta.
$$

Therefore

$$
A=\frac12\left(4\pi+0+4\cdot\frac{\pi}{2}\right)=3\pi.
$$

## Problem 12

At an intersection,

$$
2=4\cos\theta.
$$

So

$$
\cos\theta=\frac12.
$$

For $-\pi<\theta\le\pi$,

$$
\theta=\frac{\pi}{3}
\quad\text{or}\quad
\theta=-\frac{\pi}{3}.
$$

The intersections are

$$
\left(2,\frac{\pi}{3}\right)
\quad\text{and}\quad
\left(2,-\frac{\pi}{3}\right).
$$

## Problem 13

Use

$$
\cos\left(\theta-\frac{\pi}{4}\right)
=\frac{1}{\sqrt2}\cos\theta+\frac{1}{\sqrt2}\sin\theta.
$$

Then

$$
r\cos\left(\theta-\frac{\pi}{4}\right)=3
$$

becomes

$$
\frac{r\cos\theta+r\sin\theta}{\sqrt2}=3.
$$

Since $r\cos\theta=x$ and $r\sin\theta=y$,

$$
x+y=3\sqrt2.
$$

## C. Parametric Curves and Differentiation

## Problem 14

From $x=t+1$,

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

## Problem 15

From

$$
x=t^2,\qquad y=t^3,
$$

we get

$$
y^2=t^6
$$

and

$$
x^3=t^6.
$$

So

$$
y^2=x^3.
$$

Since $x=t^2$,

$$
x\ge0.
$$

## Problem 16

Differentiate with respect to $t$:

$$
\frac{dx}{dt}=2t,
\qquad
\frac{dy}{dt}=3t^2-1.
$$

Therefore

$$
\frac{dy}{dx}=\frac{3t^2-1}{2t},
\qquad t\ne0.
$$

## Problem 17

At $t=1$,

$$
x=2,\qquad y=0.
$$

From problem 16,

$$
\frac{dy}{dx}=\frac{3t^2-1}{2t}.
$$

At $t=1$, the gradient is

$$
1.
$$

The tangent is

$$
y=x-2.
$$

## Problem 18

At $t=1$, the tangent gradient is $1$, so the normal gradient is $-1$. The
normal passes through $(2,0)$, so

$$
y=-(x-2).
$$

Thus

$$
y=2-x.
$$

## Problem 19

For

$$
x=t^2,\qquad y=t^3-3t,
$$

we have

$$
\frac{dx}{dt}=2t,
\qquad
\frac{dy}{dt}=3t^2-3.
$$

Horizontal tangents occur when $\frac{dy}{dt}=0$ and
$\frac{dx}{dt}\ne0$:

$$
3t^2-3=0,
$$

so

$$
t=\pm1.
$$

The points are

$$
(1,-2)
\quad\text{and}\quad
(1,2).
$$

Vertical tangents occur when $\frac{dx}{dt}=0$ and
$\frac{dy}{dt}\ne0$. This gives $t=0$, so the point is

$$
(0,0).
$$

## Problem 20

From problem 16,

$$
\frac{dy}{dx}=\frac{3t^2-1}{2t}
=\frac32t-\frac{1}{2t}.
$$

Differentiate with respect to $t$:

$$
\frac{d}{dt}\left(\frac{dy}{dx}\right)
=\frac32+\frac{1}{2t^2}.
$$

Then

$$
\frac{d^2y}{dx^2}
=
\frac{\frac{d}{dt}\left(\frac{dy}{dx}\right)}{\frac{dx}{dt}}
=
\frac{\frac32+\frac{1}{2t^2}}{2t}.
$$

At $t=1$,

$$
\frac{d^2y}{dx^2}=1.
$$
