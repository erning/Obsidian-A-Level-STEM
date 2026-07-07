---
title: Complex Numbers Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/09 Complex Numbers/00 Overview|Complex Numbers]]"
status: active
tags:
  - mathematics/pure
  - lecture-notes
---

# Complex Numbers Lecture Notes

Complex numbers extend the real line into a plane. A complex number can be treated algebraically as $x+iy$ and geometrically as a point or vector in the Argand diagram. The power of the topic comes from choosing the right form: Cartesian form for addition and algebra, polar or exponential form for multiplication, division, powers, roots, and rotation.

## Source Route

- 9709 3.9 Complex numbers
- 9231 2.5 Complex numbers
- Coursebook route: 9709 Pure Mathematics 2 and 3 Chapter 11; 9231 Further Mathematics complex numbers content.

## Visual Guide

![[assets/generated/mathematics/complex-numbers.svg]]

Figure: The guide shows modulus and argument on the Argand diagram. Keep this picture visible whenever a problem mentions $|z|$, $\arg z$, or a locus.

## 1. Cartesian Form and Conjugates

A complex number is written as

$$
z=x+iy,
$$

where $x$ is the real part, $y$ is the imaginary part, and

$$
i^2=-1.
$$

The notation is

$$
\operatorname{Re}z=x,\qquad \operatorname{Im}z=y.
$$

Two complex numbers are equal if and only if both real and imaginary parts are equal.

The conjugate of $z=x+iy$ is

$$
z^*=x-iy.
$$

Conjugation reflects a point in the real axis. It is also useful for division because

$$
zz^*=x^2+y^2.
$$

For example,

$$
\frac{1}{3+2i}=\frac{3-2i}{(3+2i)(3-2i)}=\frac{3-2i}{13}.
$$

## 2. Modulus, Argument, and the Argand Diagram

On the Argand diagram, $z=x+iy$ is represented by the point $(x,y)$. Its modulus is the distance from the origin:

$$
|z|=\sqrt{x^2+y^2}.
$$

Its argument is the angle from the positive real axis:

$$
\arg z=\theta.
$$

The usual principal argument is in an interval such as

$$
-\pi<\theta\le\pi,
$$

unless a question specifies another interval. Do not use $\tan^{-1}\left(\frac{y}{x}\right)$ without checking the quadrant.

## 3. Polar and Exponential Forms

If $|z|=r$ and $\arg z=\theta$, then

$$
z=r(\cos\theta+i\sin\theta).
$$

Using Euler's formula, this can also be written as

$$
z=re^{i\theta}.
$$

Multiplication and division are simple in polar form:

$$
|z_1z_2|=|z_1||z_2|,
\qquad
\arg(z_1z_2)=\arg z_1+\arg z_2,
$$

and

$$
\left|\frac{z_1}{z_2}\right|=\frac{|z_1|}{|z_2|},
\qquad
\arg\left(\frac{z_1}{z_2}\right)=\arg z_1-\arg z_2.
$$

Geometrically, multiplying by $re^{i\theta}$ scales by $r$ and rotates by $\theta$.

## 4. Polynomial Equations and Conjugate Roots

For a polynomial with real coefficients, non-real complex roots occur in conjugate pairs. If $2+3i$ is a root, then $2-3i$ is also a root.

This is useful when solving cubic or quartic equations. If one complex root is given, the conjugate gives another factor. For example, roots $2\pm3i$ correspond to the quadratic factor

$$
(x-(2+3i))(x-(2-3i))
=((x-2)-3i)((x-2)+3i)
=(x-2)^2+9.
$$

For square roots of a complex number in Cartesian form, write

$$
(a+bi)^2=x+iy
$$

and equate real and imaginary parts. This gives the two square roots.

## 5. Powers, de Moivre's Theorem, and Roots

de Moivre's theorem says

$$
(\cos\theta+i\sin\theta)^n=\cos n\theta+i\sin n\theta
$$

for integer $n$, with further extensions in 9231.

If

$$
z=re^{i\theta},
$$

then

$$
z^n=r^ne^{in\theta}.
$$

To find the $n$th roots of

$$
re^{i\theta},
$$

use all equivalent arguments $\theta+2k\pi$:

$$
w=r^{1/n}e^{i(\theta+2k\pi)/n},
\qquad k=0,1,\ldots,n-1.
$$

There are $n$ roots, equally spaced around a circle. The $n$th roots of unity are the roots of

$$
z^n=1.
$$

They lie on the unit circle at angles

$$
\frac{2k\pi}{n},\qquad k=0,1,\ldots,n-1.
$$

In 9231, de Moivre's theorem also supports multiple-angle identities, expressions for powers of $\sin\theta$ and $\cos\theta$, and sums of trigonometric series.

### Worked Example: de Moivre for a Multiple-Angle Identity

Use

$$
(\cos\theta+i\sin\theta)^3=\cos3\theta+i\sin3\theta.
$$

Expanding the left side gives

$$
\cos^3\theta+3i\cos^2\theta\sin\theta-3\cos\theta\sin^2\theta-i\sin^3\theta.
$$

Equating real and imaginary parts,

$$
\cos3\theta=\cos^3\theta-3\cos\theta\sin^2\theta,
$$

and

$$
\sin3\theta=3\cos^2\theta\sin\theta-\sin^3\theta.
$$

Using $\sin^2\theta=1-\cos^2\theta$ gives

$$
\cos3\theta=4\cos^3\theta-3\cos\theta.
$$

This is the typical 9231 move: expand a complex power, then compare real or imaginary parts.

### Worked Example: Fourth Roots and Their Geometry

To solve $z^4=-16$, write

$$
-16=16e^{i(\pi+2k\pi)}.
$$

The fourth roots are

$$
z=2e^{i(\pi+2k\pi)/4},
\qquad k=0,1,2,3.
$$

Thus the arguments are

$$
\frac{\pi}{4},\quad \frac{3\pi}{4},\quad \frac{5\pi}{4},\quad \frac{7\pi}{4}.
$$

The four roots lie on the circle $|z|=2$, equally spaced by $\frac{\pi}{2}$. This geometric check catches the common error of listing only the principal root.

## 6. Loci in the Argand Diagram

Complex loci are plane geometry written in complex notation.

The expression

$$
|z-a|=r
$$

means the distance from $z$ to the fixed point $a$ is $r$, so the locus is a circle.

The expression

$$
|z-a|=|z-b|
$$

means the point $z$ is equidistant from $a$ and $b$, so the locus is the perpendicular bisector of the segment joining $a$ and $b$.

The expression

$$
\arg(z-a)=\alpha
$$

means the line or ray from fixed point $a$ to $z$ makes angle $\alpha$ with the positive real axis. Pay attention to whether the endpoint is included and whether an inequality shades a region.

### Worked Example: Turn a Locus into Geometry

Find the locus

$$
|z-(1+i)|=|z-3|.
$$

If $z=x+iy$, this says that $(x,y)$ is equidistant from $(1,1)$ and $(3,0)$. The locus is the perpendicular bisector of the segment joining those points.

Expanding confirms the line:

$$
(x-1)^2+(y-1)^2=(x-3)^2+y^2,
$$

so

$$
4x-2y-7=0.
$$

The geometric interpretation should come first; the algebra is a check or a way to give the final Cartesian equation.

## Worked-Thinking Routines

### Choosing a Form

- Use Cartesian form $x+iy$ for addition, subtraction, equality of real and imaginary parts, and polynomial factor work.
- Use polar or exponential form for multiplication, division, powers, roots, and rotations.
- Use the Argand diagram for modulus, argument, and loci.

### Roots

1. Convert the target number to polar or exponential form.
2. Add $2k\pi$ to the argument.
3. Divide arguments by $n$ and take the $n$th root of the modulus.
4. List $k=0,1,\ldots,n-1$.
5. Sketch the roots to check equal spacing.

### Loci

1. Translate $|z-a|$ as a distance from a fixed point.
2. Translate $\arg(z-a)$ as a direction from a fixed point.
3. Sketch before expanding.
4. Apply inequalities as inside/outside or one side of a ray/line.
5. Check any intersections of loci geometrically.

## Common Mistakes

- Confusing $\operatorname{Im}z$ with the term $iy$.
- Confusing modulus with real part.
- Finding an argument from arctangent without checking the quadrant.
- Forgetting conjugate roots for real polynomial coefficients.
- Writing only one root when there should be $n$.
- Using degrees and radians inconsistently in polar form.
- Expanding a locus too early and losing the geometry.

## Quick Self-Check

You are ready to move on when you can:

- Convert between Cartesian, modulus-argument, and exponential forms.
- Explain multiplication as scaling and rotation.
- Divide complex numbers using conjugates.
- Use conjugate-root pairs in real polynomial equations.
- Find square roots and $n$th roots of complex numbers.
- Sketch and interpret simple complex loci.
- State how de Moivre's theorem supports roots and multiple-angle work.

## Connections

- [[20 Mathematics/01 Pure Mathematics/03 Trigonometry and Circular Measure/00 Overview|Trigonometry and Circular Measure]]
- [[20 Mathematics/01 Pure Mathematics/04 Sequences Series and Binomial Expansions/00 Overview|Sequences, Series and Binomial Expansions]]
