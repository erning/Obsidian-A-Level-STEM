---
title: Complex Numbers Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/09 Complex Numbers/00 Overview|Complex Numbers]]"
status: active
tags:
  - mathematics/pure
  - solutions
---

# Complex Numbers Key Practice Solutions

This note gives worked solutions for [[20 Mathematics/01 Pure Mathematics/09 Complex Numbers/30 Key Practice Problems|Complex Numbers Key Practice Problems]]. Use it to check the form chosen, the Argand diagram interpretation, and any branch or argument decisions.

## A. 9709 Core Complex Number Skills

## Problem 1

For

$$
z=3-4i,
$$

the real part is

$$
\operatorname{Re}z=3,
$$

and the imaginary part is

$$
\operatorname{Im}z=-4.
$$

The conjugate is

$$
z^*=3+4i.
$$

The modulus is

$$
|z|=\sqrt{3^2+(-4)^2}=5.
$$

The point $(3,-4)$ is in the fourth quadrant, so the principal argument is

$$
\arg z=-\tan^{-1}\frac{4}{3}\approx -0.927.
$$

## Problem 2

Addition is component-wise:

$$
z+w=(2+3i)+(4-i)=6+2i.
$$

For the product,

$$
zw=(2+3i)(4-i)
=8-2i+12i-3i^2
=11+10i.
$$

For the quotient,

$$
\frac{z}{w}
=\frac{2+3i}{4-i}\cdot\frac{4+i}{4+i}
=\frac{(2+3i)(4+i)}{17}.
$$

The numerator is

$$
(2+3i)(4+i)=8+2i+12i+3i^2=5+14i.
$$

Therefore

$$
\frac{z}{w}=\frac{5}{17}+\frac{14}{17}i.
$$

## Problem 3

Use the quadratic formula:

$$
z=\frac{4\pm\sqrt{(-4)^2-4(1)(13)}}{2}.
$$

So

$$
z=\frac{4\pm\sqrt{-36}}{2}
=\frac{4\pm6i}{2}.
$$

The roots are

$$
z=2+3i,\qquad z=2-3i.
$$

## Problem 4

The polynomial has real coefficients. Since $1+2i$ is a root, $1-2i$ is also
a root.

The conjugate pair gives

$$
(z-(1+2i))(z-(1-2i))
=((z-1)-2i)((z-1)+2i)
=(z-1)^2+4.
$$

So the quadratic factor is

$$
z^2-2z+5.
$$

Factor the cubic:

$$
z^3-5z^2+11z-15=(z^2-2z+5)(z-3).
$$

Therefore the roots are

$$
1+2i,\qquad 1-2i,\qquad 3.
$$

## Problem 5

Let a square root be $x+iy$, with $x,y\in\mathbb R$. Then

$$
(x+iy)^2=5+12i.
$$

Expanding gives

$$
x^2-y^2+2xyi=5+12i.
$$

Therefore

$$
x^2-y^2=5,
\qquad
2xy=12.
$$

Also,

$$
x^2+y^2=|5+12i|=13.
$$

Adding $x^2-y^2=5$ and $x^2+y^2=13$ gives

$$
2x^2=18,
$$

so $x=\pm3$. Since $2xy=12$, $x$ and $y$ have the same sign, so the roots are

$$
3+2i
\quad\text{and}\quad
-3-2i.
$$

## Problem 6

For

$$
z=-1+i\sqrt3,
$$

the modulus is

$$
|z|=\sqrt{(-1)^2+(\sqrt3)^2}=2.
$$

The point $(-1,\sqrt3)$ is in the second quadrant. The principal argument is

$$
\frac{2\pi}{3}.
$$

Thus

$$
z=2\left(\cos\frac{2\pi}{3}+i\sin\frac{2\pi}{3}\right),
$$

and

$$
z=2e^{2\pi i/3}.
$$

## Problem 7

Use Euler form:

$$
4e^{-\pi i/6}
=4\left(\cos\left(-\frac{\pi}{6}\right)
+i\sin\left(-\frac{\pi}{6}\right)\right).
$$

Since

$$
\cos\left(-\frac{\pi}{6}\right)=\frac{\sqrt3}{2},
\qquad
\sin\left(-\frac{\pi}{6}\right)=-\frac12,
$$

the Cartesian form is

$$
2\sqrt3-2i.
$$

## Problem 8

For multiplication,

$$
z_1z_2
=2e^{5\pi i/6}\cdot3e^{-2\pi i/3}
=6e^{i(5\pi/6-2\pi/3)}
=6e^{\pi i/6}.
$$

For division,

$$
\frac{z_1}{z_2}
=\frac{2}{3}e^{i(5\pi/6+2\pi/3)}
=\frac{2}{3}e^{3\pi i/2}.
$$

The principal argument equivalent to $3\pi/2$ is

$$
3\pi/2-2\pi=-\pi/2.
$$

Therefore

$$
\frac{z_1}{z_2}=\frac{2}{3}e^{-\pi i/2}.
$$

## Problem 9

Multiplication by

$$
2e^{\pi i/3}
$$

scales distances from the origin by $2$ and rotates points anticlockwise by
$\pi/3$.

In Cartesian form,

$$
2e^{\pi i/3}
=2\left(\frac12+i\frac{\sqrt3}{2}\right)
=1+i\sqrt3.
$$

So the image of $1+i$ is

$$
(1+i)(1+i\sqrt3)
=1+i\sqrt3+i+i^2\sqrt3.
$$

Hence

$$
(1+i)(1+i\sqrt3)
=(1-\sqrt3)+i(1+\sqrt3).
$$

## Problem 10

The condition

$$
|z-(2+i)|=3
$$

means the distance from $z$ to the fixed point $2+i$ is $3$.

The locus is the circle with centre $(2,1)$ and radius $3$.

## Problem 11

Let

$$
z=x+iy.
$$

The equation

$$
|z-(1+2i)|=|z-(5-2i)|
$$

means that $z$ is equidistant from $(1,2)$ and $(5,-2)$. So the locus is the
perpendicular bisector of the segment joining those two points.

Algebraically,

$$
(x-1)^2+(y-2)^2=(x-5)^2+(y+2)^2.
$$

Expanding gives

$$
x^2-2x+1+y^2-4y+4
=x^2-10x+25+y^2+4y+4.
$$

Simplifying,

$$
8x-8y-24=0.
$$

Therefore the Cartesian equation is

$$
x-y-3=0.
$$

## Problem 12

The expression $z-(1+i)$ is the vector from $(1,1)$ to the moving point $z$.
The argument condition says that this vector has direction $\pi/4$.

The locus is the ray starting at $(1,1)$ in direction $\pi/4$, excluding the
point $(1,1)$ itself. In Cartesian form,

$$
y=x,\qquad x>1.
$$

The endpoint is excluded because $\arg0$ is undefined.

## Problem 13

On the real axis, $z=x$ with $y=0$. The circle equation is

$$
(x-2)^2+(0-1)^2=3^2.
$$

So

$$
(x-2)^2+1=9,
$$

and

$$
(x-2)^2=8.
$$

Therefore

$$
x=2\pm2\sqrt2.
$$

The intersection points are

$$
z=2+2\sqrt2
\quad\text{and}\quad
z=2-2\sqrt2.
$$

## B. 9231 de Moivre and Roots Extensions

## Problem 14

Write

$$
1+i=\sqrt2\left(\cos\frac{\pi}{4}+i\sin\frac{\pi}{4}\right).
$$

Then, by de Moivre's theorem,

$$
(1+i)^8
=\left(\sqrt2\right)^8
\left(\cos2\pi+i\sin2\pi\right).
$$

Since $\left(\sqrt2\right)^8=16$ and
$\cos2\pi+i\sin2\pi=1$,

$$
(1+i)^8=16.
$$

## Problem 15

Let

$$
c=\cos\theta,\qquad s=\sin\theta.
$$

By de Moivre's theorem,

$$
(c+is)^3=\cos3\theta+i\sin3\theta.
$$

Expand:

$$
(c+is)^3=c^3+3c^2is+3c(is)^2+(is)^3.
$$

Using $i^2=-1$ and $i^3=-i$,

$$
(c+is)^3=(c^3-3cs^2)+i(3c^2s-s^3).
$$

Equating real and imaginary parts gives

$$
\cos3\theta=c^3-3cs^2,
$$

and

$$
\sin3\theta=3c^2s-s^3.
$$

Using $s^2=1-c^2$ and $c^2=1-s^2$,

$$
\cos3\theta=4c^3-3c,
$$

and

$$
\sin3\theta=3s-4s^3.
$$

## Problem 16

Start from

$$
\cos^2\theta=\frac{1+\cos2\theta}{2}.
$$

Then

$$
\cos^4\theta
=\left(\frac{1+\cos2\theta}{2}\right)^2
=\frac{1+2\cos2\theta+\cos^22\theta}{4}.
$$

Also,

$$
\cos^22\theta=\frac{1+\cos4\theta}{2}.
$$

Therefore

$$
\cos^4\theta
=\frac{1+2\cos2\theta+\frac12(1+\cos4\theta)}{4}.
$$

So

$$
\cos^4\theta
=\frac{3+4\cos2\theta+\cos4\theta}{8}.
$$

## Problem 17

The roots of

$$
z^5=1
$$

are the fifth roots of unity:

$$
z=e^{2\pi ik/5},
\qquad k=0,1,2,3,4.
$$

They are the vertices of a regular pentagon on the unit circle.

Let

$$
\omega=e^{2\pi i/5}.
$$

The roots are

$$
1,\omega,\omega^2,\omega^3,\omega^4.
$$

Their sum is

$$
1+\omega+\omega^2+\omega^3+\omega^4
=\frac{1-\omega^5}{1-\omega}=0,
$$

because $\omega^5=1$ and $\omega\ne1$.

## Problem 18

Write

$$
8i=8e^{\pi i/2}.
$$

Equivalent arguments are

$$
\frac{\pi}{2}+2k\pi.
$$

Taking cube roots gives

$$
z=2e^{i(\pi/2+2k\pi)/3},
\qquad k=0,1,2.
$$

The three arguments are

$$
\frac{\pi}{6},\qquad \frac{5\pi}{6},\qquad \frac{3\pi}{2}.
$$

So the roots are

$$
z=\sqrt3+i,\qquad z=-\sqrt3+i,\qquad z=-2i.
$$

## Problem 19

Let

$$
T=\sum_{r=0}^{n-1}e^{ir\theta}.
$$

This is a geometric series with first term $1$ and common ratio
$e^{i\theta}$. Since $0<\theta<2\pi$, the ratio is not $1$. Therefore

$$
T=\frac{1-e^{in\theta}}{1-e^{i\theta}}.
$$

Now

$$
1-e^{in\theta}
=e^{in\theta/2}\left(e^{-in\theta/2}-e^{in\theta/2}\right)
=-2ie^{in\theta/2}\sin\frac{n\theta}{2},
$$

and

$$
1-e^{i\theta}
=e^{i\theta/2}\left(e^{-i\theta/2}-e^{i\theta/2}\right)
=-2ie^{i\theta/2}\sin\frac{\theta}{2}.
$$

Thus

$$
T=e^{i(n-1)\theta/2}
\frac{\sin(n\theta/2)}{\sin(\theta/2)}.
$$

Taking real and imaginary parts gives

$$
\sum_{r=0}^{n-1}\cos r\theta
=
\frac{\sin(n\theta/2)}{\sin(\theta/2)}
\cos\frac{(n-1)\theta}{2},
$$

and

$$
\sum_{r=0}^{n-1}\sin r\theta
=
\frac{\sin(n\theta/2)}{\sin(\theta/2)}
\sin\frac{(n-1)\theta}{2}.
$$

## Problem 20

Use

$$
z^5-1=(z-1)(z^4+z^3+z^2+z+1).
$$

The roots of $z^5=1$ are

$$
e^{2\pi ik/5},
\qquad k=0,1,2,3,4.
$$

The factor $z^4+z^3+z^2+z+1$ excludes the root $z=1$, which corresponds to
$k=0$.

Therefore the solutions are

$$
z=e^{2\pi ik/5},
\qquad k=1,2,3,4.
$$
