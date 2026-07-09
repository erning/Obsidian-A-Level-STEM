---
title: Coordinate Geometry and Graphs Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Coordinate Geometry and Graphs](00%20Overview.md)"
status: active
tags:
  - mathematics/pure
  - worked-examples
---

# Coordinate Geometry and Graphs Worked Examples

These examples model the standard CAIE route through straight lines, circles,
intersections, tangency, and graph transformations of $y=f(x)$.

## Source Route

- Syllabus: CAIE Mathematics 9709 sections 1.2 and 1.3.
- Main subtopics: graph transformations, straight-line equations, distance,
  gradient, midpoint, circles, line-circle problems, and graph intersections.
- Coursebook route: 9709 Pure Mathematics 1 functions and coordinate geometry.

## Example 1: Line Through Two Points

**Prompt.** Find the equation of the line through $A(2,-1)$ and $B(8,3)$.

**Solution.**

The gradient is

$$
m=\frac{3-(-1)}{8-2}=\frac{4}{6}=\frac{2}{3}.
$$

Use point-gradient form through $A(2,-1)$:

$$
y+1=\frac{2}{3}(x-2).
$$

Multiplying by $3$ gives

$$
3y+3=2x-4.
$$

So a general form is

$$
2x-3y-7=0.
$$

Check with $B(8,3)$:

$$
2(8)-3(3)-7=0.
$$

**What this example trains.** Point-gradient form keeps the known point and
gradient visible before expanding.

## Example 2: Perpendicular Line

**Prompt.** Find the line through $B(8,3)$ perpendicular to the line through
$A(2,-1)$ and $B(8,3)$.

**Solution.**

From Example 1, the gradient of $AB$ is

$$
\frac{2}{3}.
$$

The perpendicular gradient is the negative reciprocal:

$$
-\frac{3}{2}.
$$

Using point-gradient form through $B(8,3)$,

$$
y-3=-\frac{3}{2}(x-8).
$$

Equivalently,

$$
3x+2y-30=0.
$$

**What this example trains.** Perpendicular gradients multiply to $-1$, except
for vertical-horizontal special cases.

## Example 3: Circle From Expanded Form

**Prompt.** Find the centre and radius of

$$
x^2+y^2-6x+4y-12=0.
$$

**Solution.**

Move the constant:

$$
x^2-6x+y^2+4y=12.
$$

Complete the squares:

$$
x^2-6x=(x-3)^2-9,
$$

$$
y^2+4y=(y+2)^2-4.
$$

So

$$
(x-3)^2-9+(y+2)^2-4=12.
$$

Hence

$$
(x-3)^2+(y+2)^2=25.
$$

The centre is $(3,-2)$ and the radius is $5$.

**What this example trains.** Completing the square recovers the
centre-radius form.

## Example 4: Circle From a Diameter

**Prompt.** A circle has diameter with endpoints $A(1,2)$ and $B(7,10)$.
Find its equation.

**Solution.**

The centre is the midpoint of the diameter:

$$
\left(\frac{1+7}{2},\frac{2+10}{2}\right)=(4,6).
$$

The diameter length is

$$
AB=\sqrt{(7-1)^2+(10-2)^2}
=\sqrt{36+64}
=10.
$$

So the radius is $5$. The circle is

$$
(x-4)^2+(y-6)^2=25.
$$

**What this example trains.** A diameter gives both centre and radius without
using the general circle equation.

## Example 5: Tangent to a Circle

**Prompt.** The circle with centre $C(3,-2)$ has tangent at $T(6,2)$. Find the
equation of the tangent.

**Solution.**

The gradient of the radius $CT$ is

$$
m_{CT}=\frac{2-(-2)}{6-3}=\frac{4}{3}.
$$

The tangent is perpendicular to the radius, so its gradient is

$$
-\frac{3}{4}.
$$

Using point-gradient form through $T(6,2)$,

$$
y-2=-\frac{3}{4}(x-6).
$$

Equivalently,

$$
3x+4y-26=0.
$$

**What this example trains.** A circle tangent uses the radius-perpendicular
fact at the point of contact.

## Example 6: Line-Circle Intersections

**Prompt.** Find the intersection points of

$$
y=x+1
$$

and

$$
x^2+y^2=25.
$$

**Solution.**

Substitute $y=x+1$ into the circle:

$$
x^2+(x+1)^2=25.
$$

Expand:

$$
2x^2+2x+1=25,
$$

so

$$
x^2+x-12=0.
$$

Factorise:

$$
(x+4)(x-3)=0.
$$

Thus $x=-4$ or $x=3$. Substitute into $y=x+1$:

$$
(-4,-3)\quad\text{and}\quad(3,4).
$$

**What this example trains.** Intersections are simultaneous solutions.

## Example 7: Tangency From a Discriminant

**Prompt.** Find the values of $k$ for which the line $y=x+k$ is tangent to
the circle

$$
x^2+y^2=18.
$$

**Solution.**

Substitute $y=x+k$:

$$
x^2+(x+k)^2=18.
$$

This gives

$$
2x^2+2kx+k^2-18=0.
$$

Tangency means one repeated intersection, so the discriminant is zero:

$$
(2k)^2-4(2)(k^2-18)=0.
$$

Simplify:

$$
4k^2-8k^2+144=0,
$$

so

$$
k^2=36.
$$

Therefore

$$
k=\pm6.
$$

**What this example trains.** For a line and curve, "touches" often translates
to a quadratic with discriminant $0$.

## Example 8: Transforming a Graph and Its Domain

**Prompt.** A point $(2,5)$ lies on $y=f(x)$. The domain of $f$ is
$1\le x\le4$ and the range is $-2\le y\le3$. Describe the point, domain, and
range after the transformation

$$
y=f(x-2)+1.
$$

**Solution.**

The expression $f(x-2)$ translates the graph $2$ units to the right. The
$+1$ translates it $1$ unit upwards.

The point $(2,5)$ becomes

$$
(4,6).
$$

The domain shifts right by $2$:

$$
3\le x\le6.
$$

The range shifts up by $1$:

$$
-1\le y\le4.
$$

**What this example trains.** Horizontal transformations affect the input and
must also update the domain.
