---
title: Trigonometry and Circular Measure Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/03 Trigonometry and Circular Measure/00 Overview|Trigonometry and Circular Measure]]"
status: active
tags:
  - mathematics/pure
  - worked-examples
---

# Trigonometry and Circular Measure Worked Examples

These examples model the standard CAIE route through radians, sector geometry,
trigonometric graphs, equations, identities, reciprocal functions, compound
angles, double angles, and auxiliary-angle form.

## Source Route

- Syllabus: CAIE Mathematics 9709 sections 1.4, 1.5, 2.3, and 3.3.
- Main subtopics: circular measure, trigonometric graphs and equations,
  inverse trigonometric notation, reciprocal functions, compound-angle and
  double-angle formulae, and $a\sin\theta+b\cos\theta$.
- Coursebook route: 9709 Pure Mathematics 1 Chapters 4-5; 9709 Pure
  Mathematics 2 and 3 Chapter 3.

## Example 1: Sector and Segment Area

**Prompt.** A circle has radius $5\text{ cm}$. A sector has angle $1.2$
radians. Find the arc length, the sector area, and the area of the minor
segment cut off by the chord.

**Solution.**

Because the angle is in radians,

$$
s=r\theta=5(1.2)=6\text{ cm}.
$$

The sector area is

$$
A_{\text{sector}}=\frac{1}{2}r^2\theta
=\frac{1}{2}(25)(1.2)
=15\text{ cm}^2.
$$

The triangle formed by the two radii and the chord has area

$$
A_{\text{triangle}}=\frac{1}{2}r^2\sin\theta
=\frac{1}{2}(25)\sin 1.2
=12.5\sin 1.2.
$$

So the minor segment area is

$$
15-12.5\sin 1.2\approx 3.35\text{ cm}^2.
$$

**What this example trains.** Segment area usually means sector area minus
triangle area, with the angle in radians for the sector formulae.

## Example 2: Exact Values and Principal Inverses

**Prompt.** Find

$$
\sin\frac{7\pi}{6},\qquad
\cos\frac{5\pi}{6},\qquad
\tan\frac{3\pi}{4},\qquad
\sin^{-1}\left(-\frac{1}{2}\right).
$$

**Solution.**

Use reference angles and quadrant signs:

$$
\sin\frac{7\pi}{6}=-\frac{1}{2},
$$

$$
\cos\frac{5\pi}{6}=-\frac{\sqrt3}{2},
$$

and

$$
\tan\frac{3\pi}{4}=-1.
$$

For inverse sine, use the principal range

$$
-\frac{\pi}{2}\le y\le\frac{\pi}{2}.
$$

Thus

$$
\sin^{-1}\left(-\frac{1}{2}\right)=-\frac{\pi}{6}.
$$

**What this example trains.** Related angles give exact values, while inverse
trigonometric notation gives a principal value, not all possible angles.

## Example 3: Graph Features

**Prompt.** State the period, range, maxima, and minima of

$$
y=1-\cos 2x.
$$

**Solution.**

The graph of $\cos 2x$ has period

$$
\frac{2\pi}{2}=\pi.
$$

Since $-1\le \cos 2x\le1$,

$$
0\le 1-\cos 2x\le2.
$$

So the range is

$$
0\le y\le2.
$$

The minimum occurs when $\cos 2x=1$, so

$$
x=k\pi,\qquad k\in\mathbb Z.
$$

The maximum occurs when $\cos 2x=-1$, so

$$
x=\frac{\pi}{2}+k\pi,\qquad k\in\mathbb Z.
$$

**What this example trains.** Period and range should be read before sketching
the curve.

## Example 4: Simple Trigonometric Equation

**Prompt.** Solve

$$
2\sin x-1=0,\qquad 0\le x<2\pi.
$$

**Solution.**

First isolate the trigonometric function:

$$
\sin x=\frac{1}{2}.
$$

The reference angle is $\frac{\pi}{6}$. Sine is positive in quadrants I and II,
so

$$
x=\frac{\pi}{6},\frac{5\pi}{6}.
$$

**What this example trains.** A calculator principal value is only the start;
the interval decides the full answer set.

## Example 5: Avoid Losing Solutions

**Prompt.** Solve

$$
\sin 2x=\cos x,\qquad 0\le x<2\pi.
$$

**Solution.**

Use the double-angle identity:

$$
2\sin x\cos x=\cos x.
$$

Bring all terms to one side and factor:

$$
\cos x(2\sin x-1)=0.
$$

So either

$$
\cos x=0
$$

or

$$
\sin x=\frac{1}{2}.
$$

In the interval $0\le x<2\pi$, this gives

$$
x=\frac{\pi}{2},\frac{3\pi}{2}
$$

or

$$
x=\frac{\pi}{6},\frac{5\pi}{6}.
$$

Therefore

$$
x=\frac{\pi}{6},\frac{\pi}{2},\frac{5\pi}{6},\frac{3\pi}{2}.
$$

**What this example trains.** Do not divide by a trigonometric factor unless
you have separately checked when it is zero.

## Example 6: Simplifying With a Pythagorean Identity

**Prompt.** Simplify

$$
\frac{1-\cos^2x}{1-\sin^2x}.
$$

**Solution.**

Use

$$
1-\cos^2x=\sin^2x
$$

and

$$
1-\sin^2x=\cos^2x.
$$

So, where $\cos x\ne0$,

$$
\frac{1-\cos^2x}{1-\sin^2x}
=\frac{\sin^2x}{\cos^2x}
=\tan^2x.
$$

**What this example trains.** A simplification is only valid on values where
the original denominator is defined.

## Example 7: Exact Evaluation by a Compound Angle

**Prompt.** Find the exact value of $\sin 75^\circ$.

**Solution.**

Write

$$
75^\circ=45^\circ+30^\circ.
$$

Then

$$
\sin 75^\circ
=\sin(45^\circ+30^\circ)
$$

$$
=\sin45^\circ\cos30^\circ+\cos45^\circ\sin30^\circ.
$$

Substitute exact values:

$$
\sin 75^\circ
=\frac{\sqrt2}{2}\cdot\frac{\sqrt3}{2}
+\frac{\sqrt2}{2}\cdot\frac{1}{2}
=\frac{\sqrt6+\sqrt2}{4}.
$$

**What this example trains.** Compound-angle formulae turn unfamiliar exact
angles into known exact values.

## Example 8: Reciprocal Functions in an Equation

**Prompt.** Solve

$$
\tan\theta+\cot\theta=4,\qquad 0<\theta<\pi.
$$

**Solution.**

Let

$$
t=\tan\theta.
$$

Since $\cot\theta=\frac{1}{\tan\theta}$, the equation becomes

$$
t+\frac{1}{t}=4.
$$

Multiply by $t$, with $t\ne0$:

$$
t^2-4t+1=0.
$$

Hence

$$
t=2\pm\sqrt3.
$$

These are both positive. In $0<\theta<\pi$, positive tangent values lie in
quadrant I. Since

$$
\tan\frac{\pi}{12}=2-\sqrt3
$$

and

$$
\tan\frac{5\pi}{12}=2+\sqrt3,
$$

the solutions are

$$
\theta=\frac{\pi}{12},\frac{5\pi}{12}.
$$

**What this example trains.** Reciprocal functions often reduce to an algebraic
equation in $\tan\theta$, $\sin\theta$, or $\cos\theta$.

## Example 9: Auxiliary-Angle Form

**Prompt.** Write

$$
3\sin\theta+4\cos\theta
$$

in the form $R\sin(\theta+\alpha)$, where $R>0$ and $0<\alpha<\frac{\pi}{2}$.
Then state its maximum and minimum values.

**Solution.**

Expand the target form:

$$
R\sin(\theta+\alpha)=R\sin\theta\cos\alpha+R\cos\theta\sin\alpha.
$$

Compare coefficients with $3\sin\theta+4\cos\theta$:

$$
R\cos\alpha=3,\qquad R\sin\alpha=4.
$$

Therefore

$$
R=\sqrt{3^2+4^2}=5
$$

and

$$
\tan\alpha=\frac{4}{3}.
$$

So

$$
3\sin\theta+4\cos\theta
=5\sin(\theta+\alpha),
\qquad \alpha=\tan^{-1}\frac{4}{3}.
$$

Since sine ranges from $-1$ to $1$, the maximum value is $5$ and the minimum
value is $-5$.

**What this example trains.** Auxiliary-angle form turns a linear combination
of sine and cosine into one shifted graph.

## Example 10: Solving With Auxiliary-Angle Form

**Prompt.** Solve

$$
3\sin\theta+4\cos\theta=2,\qquad 0\le\theta<2\pi.
$$

**Solution.**

From Example 9,

$$
3\sin\theta+4\cos\theta=5\sin(\theta+\alpha),
\qquad \alpha=\tan^{-1}\frac{4}{3}.
$$

So

$$
\sin(\theta+\alpha)=\frac{2}{5}.
$$

Let

$$
\beta=\sin^{-1}\frac{2}{5}.
$$

Since $0\le\theta<2\pi$, the angle $\theta+\alpha$ lies in

$$
\alpha\le\theta+\alpha<2\pi+\alpha.
$$

The two values in this shifted interval are

$$
\theta+\alpha=\pi-\beta
$$

and

$$
\theta+\alpha=2\pi+\beta.
$$

Therefore

$$
\theta=\pi-\beta-\alpha,\qquad 2\pi+\beta-\alpha.
$$

Numerically,

$$
\theta\approx1.80,\ 5.77.
$$

**What this example trains.** The auxiliary angle changes the interval for the
new angle; solve within that shifted interval before subtracting $\alpha$.
