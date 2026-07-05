---
title: Complex Numbers Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/09 Complex Numbers/00 Overview|Complex Numbers]]"
status: active
tags:
  - mathematics/pure
  - worked-examples
---

# Complex Numbers Worked Examples

These examples model the CAIE route through complex numbers: Cartesian
calculation, modulus and argument, Argand diagrams, polar and exponential
forms, loci, complex roots, and the 9231 extension to de Moivre's theorem and
roots of unity.

## Source Route

- Syllabus: CAIE Mathematics 9709 section 3.9; CAIE Further Mathematics 9231
  section 2.5.
- Main 9709 subtopics: real and imaginary parts, conjugate, modulus, argument,
  Cartesian operations, conjugate root pairs, Argand diagrams, polar form,
  square roots, geometrical effects, and simple loci.
- Main 9231 extensions: de Moivre's theorem, positive and negative integer
  exponents, rational exponents, multiple-angle identities, powers of
  trigonometric ratios, trigonometric series, and roots of unity.

## Example 1: Cartesian Operations and Division

**Prompt.** Let

$$
z=2+3i,\qquad w=4-i.
$$

Find $z+w$, $zw$, and $\dfrac{z}{w}$ in Cartesian form.

**Solution.**

Addition is component-wise:

$$
z+w=(2+3i)+(4-i)=6+2i.
$$

For multiplication, expand and use $i^2=-1$:

$$
zw=(2+3i)(4-i)=8-2i+12i-3i^2=11+10i.
$$

For division, multiply numerator and denominator by the conjugate of $w$:

$$
\frac{z}{w}
=\frac{2+3i}{4-i}\cdot\frac{4+i}{4+i}
=\frac{(2+3i)(4+i)}{4^2+1^2}.
$$

So

$$
\frac{z}{w}=\frac{5+14i}{17}
=\frac{5}{17}+\frac{14}{17}i.
$$

**What this example trains.** Cartesian form is best for addition,
subtraction, expansion, and division using conjugates.

## Example 2: Modulus, Argument, and Polar Form

**Prompt.** Write $z=-3+4i$ in modulus-argument form.

**Solution.**

The modulus is

$$
|z|=\sqrt{(-3)^2+4^2}=5.
$$

The point $(-3,4)$ is in the second quadrant. The reference angle is

$$
\tan^{-1}\frac{4}{3}.
$$

Therefore the principal argument is

$$
\theta=\pi-\tan^{-1}\frac{4}{3}\approx 2.214.
$$

Hence

$$
z=5(\cos\theta+i\sin\theta),
\qquad
\theta=\pi-\tan^{-1}\frac{4}{3}.
$$

Equivalently,

$$
z=5e^{i\theta}.
$$

**What this example trains.** Always check the quadrant before writing an
argument.

## Example 3: Multiplication and Division in Polar Form

**Prompt.** Let

$$
z_1=2e^{5\pi i/6},
\qquad
z_2=3e^{-2\pi i/3}.
$$

Find $z_1z_2$ and $\dfrac{z_1}{z_2}$ using principal arguments.

**Solution.**

For multiplication, multiply moduli and add arguments:

$$
z_1z_2=6e^{i(5\pi/6-2\pi/3)}
=6e^{i\pi/6}.
$$

For division, divide moduli and subtract arguments:

$$
\frac{z_1}{z_2}
=\frac{2}{3}e^{i(5\pi/6+2\pi/3)}
=\frac{2}{3}e^{3\pi i/2}.
$$

The argument $3\pi/2$ is not in the usual principal interval
$-\pi<\theta\le\pi$. Subtract $2\pi$:

$$
3\pi/2-2\pi=-\pi/2.
$$

So

$$
\frac{z_1}{z_2}=\frac{2}{3}e^{-\pi i/2}.
$$

**What this example trains.** Polar form turns multiplication into scaling and
rotation, but the final argument may need adjustment.

## Example 4: Square Roots in Cartesian Form

**Prompt.** Find the square roots of $5+12i$.

**Solution.**

Let a square root be $x+iy$, where $x$ and $y$ are real. Then

$$
(x+iy)^2=5+12i.
$$

Expanding gives

$$
x^2-y^2+2xyi=5+12i.
$$

Equate real and imaginary parts:

$$
x^2-y^2=5,\qquad 2xy=12.
$$

Also, comparing moduli gives

$$
x^2+y^2=|5+12i|=13.
$$

Add the two equations involving $x^2$ and $y^2$:

$$
2x^2=18,
$$

so $x=\pm3$. Since $2xy=12$, $x$ and $y$ have the same sign, and

$$
y=\pm2.
$$

The square roots are

$$
3+2i
\quad\text{and}\quad
-3-2i.
$$

**What this example trains.** Square roots can be found by equating real and
imaginary parts and using the modulus as a shortcut.

## Example 5: Conjugate Roots of a Real Polynomial

**Prompt.** It is given that $1+2i$ is a root of

$$
z^3-5z^2+11z-15=0.
$$

Find all roots.

**Solution.**

The polynomial has real coefficients, so the non-real root $1+2i$ is paired
with its conjugate:

$$
1-2i.
$$

These two roots give the quadratic factor

$$
(z-(1+2i))(z-(1-2i))
=((z-1)-2i)((z-1)+2i)
=(z-1)^2+4.
$$

So

$$
(z-1)^2+4=z^2-2z+5.
$$

Now divide the cubic by this factor:

$$
z^3-5z^2+11z-15=(z^2-2z+5)(z-3).
$$

Therefore the roots are

$$
1+2i,\qquad 1-2i,\qquad 3.
$$

**What this example trains.** For real polynomials, non-real roots occur in
conjugate pairs.

## Example 6: Modulus Loci in the Argand Diagram

**Prompt.** Describe the loci

$$
|z-(2+i)|=3
$$

and

$$
|z-(1+2i)|=|z-(5-2i)|.
$$

**Solution.**

The condition

$$
|z-(2+i)|=3
$$

means the distance from $z$ to the fixed point $2+i$ is $3$. The locus is the
circle with centre $(2,1)$ and radius $3$.

For the second locus, let $z=x+iy$. Then

$$
|z-(1+2i)|=|z-(5-2i)|
$$

means

$$
(x-1)^2+(y-2)^2=(x-5)^2+(y+2)^2.
$$

Expanding and simplifying gives

$$
x-y-3=0.
$$

This is the perpendicular bisector of the segment joining $(1,2)$ and
$(5,-2)$.

**What this example trains.** Loci are usually easier to read as geometry
before expanding.

## Example 7: Argument Loci

**Prompt.** Describe the locus

$$
\arg(z-(1+i))=\frac{\pi}{4}.
$$

**Solution.**

The expression $z-(1+i)$ is the vector from the fixed point $(1,1)$ to the
moving point $z$. The argument condition says this vector makes angle
$\pi/4$ with the positive real axis.

Therefore the locus is the ray starting at $(1,1)$ in the direction
$\pi/4$, excluding the starting point because the argument of $0$ is
undefined.

In Cartesian terms the ray is

$$
y=x,\qquad x>1.
$$

**What this example trains.** Argument loci are directed rays or sectors, not
undirected full lines unless the condition says so.

## Example 8: de Moivre's Theorem for a Power

**Prompt.** Evaluate $(1+i)^8$.

**Solution.**

First write $1+i$ in polar form:

$$
1+i=\sqrt2\left(\cos\frac{\pi}{4}+i\sin\frac{\pi}{4}\right).
$$

By de Moivre's theorem,

$$
(1+i)^8
=\left(\sqrt2\right)^8
\left(\cos 2\pi+i\sin 2\pi\right).
$$

Since $\left(\sqrt2\right)^8=16$ and $\cos2\pi+i\sin2\pi=1$,

$$
(1+i)^8=16.
$$

**What this example trains.** Powers are usually simpler after converting to
polar form.

## Example 9: Multiple-Angle Identities from de Moivre

**Prompt.** Use de Moivre's theorem to express $\cos3\theta$ and
$\sin3\theta$ in powers of $\cos\theta$ and $\sin\theta$.

**Solution.**

Let

$$
c=\cos\theta,\qquad s=\sin\theta.
$$

By de Moivre's theorem,

$$
(c+is)^3=\cos3\theta+i\sin3\theta.
$$

Expand the left-hand side:

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

Since $s^2=1-c^2$,

$$
\cos3\theta=4c^3-3c.
$$

Since $c^2=1-s^2$,

$$
\sin3\theta=3s-4s^3.
$$

**What this example trains.** 9231 uses de Moivre's theorem to produce real
trigonometric identities.

## Example 10: General Complex Roots

**Prompt.** Solve

$$
z^3=8i.
$$

**Solution.**

Write the right-hand side in polar form:

$$
8i=8e^{\pi i/2}.
$$

All equivalent arguments are

$$
\frac{\pi}{2}+2k\pi.
$$

Taking cube roots gives

$$
z=2e^{i(\pi/2+2k\pi)/3},
\qquad k=0,1,2.
$$

So the arguments are

$$
\frac{\pi}{6},\qquad \frac{5\pi}{6},\qquad \frac{3\pi}{2}.
$$

Thus

$$
z=\sqrt3+i,\qquad z=-\sqrt3+i,\qquad z=-2i.
$$

**What this example trains.** The $n$th roots are equally spaced by
$2\pi/n$ around a circle.

## Example 11: Trigonometric Series by Complex Exponentials

**Prompt.** For $0<\theta<2\pi$, show that

$$
\sum_{r=0}^{n-1}e^{ir\theta}
=e^{i(n-1)\theta/2}\frac{\sin(n\theta/2)}{\sin(\theta/2)}.
$$

Hence state formulae for

$$
C=\sum_{r=0}^{n-1}\cos r\theta
\quad\text{and}\quad
S=\sum_{r=0}^{n-1}\sin r\theta.
$$

**Solution.**

The complex sum is a geometric series:

$$
T=\sum_{r=0}^{n-1}e^{ir\theta}
=\frac{1-e^{in\theta}}{1-e^{i\theta}}.
$$

Rewrite numerator and denominator symmetrically:

$$
1-e^{in\theta}
=e^{in\theta/2}\left(e^{-in\theta/2}-e^{in\theta/2}\right)
=-2ie^{in\theta/2}\sin\frac{n\theta}{2},
$$

and

$$
1-e^{i\theta}
=-2ie^{i\theta/2}\sin\frac{\theta}{2}.
$$

Therefore

$$
T=e^{i(n-1)\theta/2}
\frac{\sin(n\theta/2)}{\sin(\theta/2)}.
$$

Taking real and imaginary parts gives

$$
C=\frac{\sin(n\theta/2)}{\sin(\theta/2)}
\cos\frac{(n-1)\theta}{2},
$$

and

$$
S=\frac{\sin(n\theta/2)}{\sin(\theta/2)}
\sin\frac{(n-1)\theta}{2}.
$$

**What this example trains.** 9231 complex-number methods can turn
trigonometric sums into geometric series.
