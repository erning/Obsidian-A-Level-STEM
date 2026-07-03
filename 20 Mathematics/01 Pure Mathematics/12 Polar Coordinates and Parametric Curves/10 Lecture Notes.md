---
title: Polar Coordinates and Parametric Curves Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/12 Polar Coordinates and Parametric Curves/00 Overview|Polar Coordinates and Parametric Curves]]"
status: draft
tags:
  - mathematics/pure
  - lecture-notes
---

# Polar Coordinates and Parametric Curves Lecture Notes

Polar and parametric forms are alternative languages for curves. Polar coordinates describe a point by distance and direction from a pole. Parametric equations describe a curve by allowing both coordinates to depend on a third variable. These forms are useful when $y=f(x)$ hides the geometry or makes the algebra awkward.

## Source Route

- 9231 1.5 Polar coordinates
- 9709 parametric differentiation content
- Coursebook route: 9231 Further Mathematics Coursebook polar coordinate sections; 9709 Pure Mathematics 2 and 3 parametric differentiation sections.

## Visual Guide

![[assets/generated/mathematics/polar-coordinates-and-parametric-curves.svg]]

Figure: The guide compares polar and parametric descriptions of curves. Use it to remember that a curve can be easier to understand in a coordinate system chosen for its shape.

## 1. Polar Coordinates

In Cartesian coordinates, a point is described by $(x,y)$. In polar coordinates, a point is described by

$$
(r,\theta),
$$

where $r$ is the distance from the pole and $\theta$ is the angle from the initial line. In the 9231 convention, $r\ge0$.

The conversion formulae are

$$
x=r\cos\theta,\qquad y=r\sin\theta,
$$

and

$$
r^2=x^2+y^2,\qquad \tan\theta=\frac{y}{x}.
$$

When finding $\theta$, check the quadrant. The tangent ratio alone does not determine the angle.

## 2. Polar Curves

A polar curve is often written as

$$
r=f(\theta).
$$

As $\theta$ changes, the radius changes. To sketch a polar curve, do not try to plot dozens of points. Look for:

- symmetry;
- intersections with the initial line;
- values of $\theta$ where $r=0$;
- least and greatest values of $r$;
- the given angle interval.

Examples:

$$
r=a
$$

is a circle centred at the pole.

The curve

$$
r=a\cos\theta
$$

can be converted by multiplying by $r$:

$$
r^2=ar\cos\theta,
$$

so

$$
x^2+y^2=ax.
$$

This is a circle.

## 3. Area in Polar Coordinates

The area swept out by a polar curve from $\theta=\alpha$ to $\theta=\beta$ is

$$
A=\frac{1}{2}\int_\alpha^\beta r^2\,d\theta.
$$

This comes from the sector area formula $\frac{1}{2}r^2\theta$. The integral adds many small sectors.

Choose limits from the geometry, not from habit. If a curve is traced more than once over an interval, the area integral may double-count. Sketch first.

## 4. Parametric Curves

A parametric curve is described by

$$
x=x(t),\qquad y=y(t).
$$

The parameter $t$ may represent time, but it does not have to. As $t$ changes, the point $(x(t),y(t))$ traces the curve.

Example:

$$
x=\cos t,\qquad y=\sin t
$$

traces the unit circle because

$$
x^2+y^2=1.
$$

Eliminating the parameter can reveal the Cartesian equation, but keep the parameter range. If $x=t+1$ and $y=t^2$, then $y=(x-1)^2$; if $t\ge0$, then $x\ge1$.

## 5. Differentiating Parametric Curves

For

$$
x=x(t),\qquad y=y(t),
$$

the gradient is

$$
\frac{dy}{dx}=\frac{\frac{dy}{dt}}{\frac{dx}{dt}},
\qquad \frac{dx}{dt}\ne0.
$$

For a tangent, first find the parameter value, then the point, then the gradient. Do not treat $\frac{dy}{dt}$ as the gradient of the curve in the $xy$-plane.

The second derivative is

$$
\frac{d^2y}{dx^2}
=\frac{\frac{d}{dt}\left(\frac{dy}{dx}\right)}{\frac{dx}{dt}}.
$$

## 6. Arc Length and Related Further Ideas

Parametric form is useful in integration. For a parametric curve,

$$
\frac{ds}{dt}
=\sqrt{\left(\frac{dx}{dt}\right)^2+\left(\frac{dy}{dt}\right)^2},
$$

so arc length is

$$
L=\int_{t_1}^{t_2}
\sqrt{\left(\frac{dx}{dt}\right)^2+\left(\frac{dy}{dt}\right)^2}\,dt.
$$

Polar arc length and surface area of revolution appear in further integration work. The same rule applies: identify the variable, interval, and geometry before integrating.

## Worked-Thinking Routines

### Polar Sketch

1. Note the angle interval.
2. Test symmetry.
3. Find values where $r=0$.
4. Find least and greatest values of $r$.
5. Mark key angles and sketch the path.

### Polar Area

1. Sketch the region.
2. Choose angle limits from the sketch.
3. Use $A=\frac{1}{2}\int r^2\,d\theta$.
4. Check whether the curve is traced once or more than once.

### Parametric Curve

1. Identify the parameter interval.
2. Find key points by substituting parameter values.
3. Eliminate the parameter only if it helps.
4. Use $\frac{dy/dt}{dx/dt}$ for gradient.
5. Keep parameter restrictions after conversion.

## Common Mistakes

- Using the wrong angle interval.
- Forgetting the convention $r\ge0$ when using polar coordinates.
- Computing $\theta$ from tangent without checking the quadrant.
- Double-counting polar area.
- Eliminating a parameter but forgetting the original range.
- Treating $\frac{dy}{dt}$ as $\frac{dy}{dx}$.
- Assuming the parameter must be time.

## Quick Self-Check

You are ready to move on when you can:

- Convert between Cartesian and polar coordinates.
- Sketch simple polar curves using symmetry and key values.
- Use $\frac{1}{2}\int r^2\,d\theta$ for polar area.
- Interpret and eliminate parametric equations.
- Find tangent gradients for parametric curves.
- Preserve interval restrictions when changing representation.

## Connections

- [[20 Mathematics/01 Pure Mathematics/02 Coordinate Geometry and Graphs/00 Overview|Coordinate Geometry and Graphs]]
- [[20 Mathematics/01 Pure Mathematics/05 Differentiation/00 Overview|Differentiation]]
