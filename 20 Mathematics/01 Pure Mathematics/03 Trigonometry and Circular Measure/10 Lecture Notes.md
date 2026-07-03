---
title: Trigonometry and Circular Measure Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/03 Trigonometry and Circular Measure/00 Overview|Trigonometry and Circular Measure]]"
status: draft
tags:
  - mathematics/pure
  - lecture-notes
---

# Trigonometry and Circular Measure Lecture Notes

Trigonometry is the language of angles, periodic motion, and circular geometry. Circular measure gives this language its natural unit: radians. Once angles are measured by arc length on a circle, the sine, cosine, and tangent functions become coordinate functions on the unit circle, and later become functions that can be differentiated, integrated, and used to model oscillation.

This topic should not be learned as a long list of identities. The aim is to move between four representations: a circle, a graph, an algebraic identity, and an equation over a specified interval.

## Source Route

- 9709 1.4 Circular measure
- 9709 1.5 Trigonometry
- 9709 2.3 Trigonometry
- 9709 3.3 Trigonometry
- Coursebook route: 9709 Pure Mathematics 1 Chapters 4-5; 9709 Pure Mathematics 2 and 3 Chapter 3.

## Visual Guide

![[assets/generated/mathematics/trigonometry-and-circular-measure.svg]]

Figure: The diagram links a point on the unit circle with the sine wave. Use it to remember that trigonometric graphs are not arbitrary curves; they come from circular motion.

## 1. Radian Measure and Circular Geometry

An angle of $1$ radian is the angle at the centre of a circle subtended by an arc equal in length to the radius. If a circle has radius $r$ and central angle $\theta$ measured in radians, then

$$
s=r\theta
$$

for arc length, and

$$
A=\frac{1}{2}r^2\theta
$$

for sector area. These formulae only work directly when $\theta$ is in radians.

A full turn has arc length $2\pi r$, so

$$
360^\circ=2\pi,\qquad 180^\circ=\pi,\qquad 90^\circ=\frac{\pi}{2}.
$$

To convert degrees to radians, multiply by $\frac{\pi}{180}$. To convert radians to degrees, multiply by $\frac{180}{\pi}$.

Circular measure problems often combine a sector with a triangle. The triangle area formula

$$
A=\frac{1}{2}ab\sin C
$$

is a useful companion. For a circular segment, a common strategy is

$$
\text{segment area}=\text{sector area}-\text{triangle area}.
$$

Before substituting into $s=r\theta$ or $A=\frac{1}{2}r^2\theta$, check the angle unit. Many wrong answers in this topic are just degree-radian errors.

## 2. The Unit Circle

On the unit circle, the point reached by an angle $\theta$ has coordinates

$$
(\cos\theta,\sin\theta).
$$

This is the most important picture in trigonometry. Cosine is the $x$-coordinate; sine is the $y$-coordinate; tangent is the ratio

$$
\tan\theta=\frac{\sin\theta}{\cos\theta},
\qquad \cos\theta\ne0.
$$

The unit circle explains signs and symmetry:

| Quadrant | Sign of $\sin\theta$ | Sign of $\cos\theta$ | Sign of $\tan\theta$ |
|---|---|---|---|
| I | $+$ | $+$ | $+$ |
| II | $+$ | $-$ | $-$ |
| III | $-$ | $-$ | $+$ |
| IV | $-$ | $+$ | $-$ |

It also gives the fundamental identity

$$
\sin^2\theta+\cos^2\theta=1.
$$

Dividing by $\cos^2\theta$ gives

$$
1+\tan^2\theta=\sec^2\theta,
$$

and dividing by $\sin^2\theta$ gives

$$
1+\cot^2\theta=\operatorname{cosec}^2\theta.
$$

## 3. Exact Values and Reciprocal Functions

The exact values for $30^\circ$, $45^\circ$, and $60^\circ$ should be automatic. In radians these are $\frac{\pi}{6}$, $\frac{\pi}{4}$, and $\frac{\pi}{3}$.

| $\theta$ | $\sin\theta$ | $\cos\theta$ | $\tan\theta$ |
|---|---|---|---|
| $\frac{\pi}{6}$ | $\frac{1}{2}$ | $\frac{\sqrt3}{2}$ | $\frac{1}{\sqrt3}$ |
| $\frac{\pi}{4}$ | $\frac{\sqrt2}{2}$ | $\frac{\sqrt2}{2}$ | $1$ |
| $\frac{\pi}{3}$ | $\frac{\sqrt3}{2}$ | $\frac{1}{2}$ | $\sqrt3$ |

Related angles use the same reference angle with a sign chosen from the quadrant. For example, $150^\circ$ has reference angle $30^\circ$ and lies in quadrant II, so

$$
\cos150^\circ=-\frac{\sqrt3}{2}.
$$

The reciprocal functions are

$$
\operatorname{cosec}\theta=\frac{1}{\sin\theta},\qquad
\sec\theta=\frac{1}{\cos\theta},\qquad
\cot\theta=\frac{1}{\tan\theta}.
$$

They are undefined where their denominators are zero. This is why their graphs have vertical asymptotes.

## 4. Graphs of Trigonometric Functions

The graphs of $y=\sin x$ and $y=\cos x$ have period $2\pi$ and range

$$
-1\le y\le 1.
$$

The graph of $y=\tan x$ has period $\pi$ and is undefined at

$$
x=\frac{\pi}{2}+k\pi,\qquad k\in\mathbb Z.
$$

Transformations use the same principles as in [[20 Mathematics/01 Pure Mathematics/02 Coordinate Geometry and Graphs/00 Overview|Coordinate Geometry and Graphs]]. For instance:

- $y=3\sin x$ has amplitude $3$.
- $y=1-\cos 2x$ has period $\pi$ because $\cos 2x$ completes a cycle twice as fast.
- $y=\tan x+4$ is the tangent graph translated upward by $4$.

When sketching trigonometric graphs, mark the period, intercepts, maxima, minima, and asymptotes before drawing the curve.

## 5. Inverse Trigonometric Notation

The notations $\sin^{-1}x$, $\cos^{-1}x$, and $\tan^{-1}x$ mean principal inverse trigonometric values, not reciprocals. For example,

$$
\sin^{-1}\left(\frac{1}{2}\right)=\frac{\pi}{6}
$$

as a principal value, even though $\sin x=\frac{1}{2}$ has many solutions.

Do not confuse

$$
\sin^{-1}x
$$

with

$$
\frac{1}{\sin x}.
$$

The second expression is $\operatorname{cosec}x$.

## 6. Solving Trigonometric Equations

Solving a trigonometric equation is not finished when a calculator gives one angle. The full task is to find all solutions in the stated interval.

A reliable routine is:

1. Simplify the equation into a known trigonometric function where possible.
2. Find a reference angle.
3. Use the unit circle or graph to decide which quadrants fit the sign.
4. Add or subtract periods until all solutions in the interval are found.
5. Substitute back if the algebra involved squaring or multiplying by a trigonometric expression.

Example: solve

$$
\sin x=\frac{1}{2},\qquad 0\le x<2\pi.
$$

The reference angle is $\frac{\pi}{6}$. Sine is positive in quadrants I and II, so

$$
x=\frac{\pi}{6},\frac{5\pi}{6}.
$$

For equations involving $\tan x$, remember its period is $\pi$, not $2\pi$.

## 7. Proving and Using Identities

An identity is an equation that is true for all allowed values of the variable. The best way to prove one is usually to transform one side into the other, or to transform both sides into a common expression.

Useful tactics:

- Convert everything to $\sin$ and $\cos$.
- Use $\sin^2\theta+\cos^2\theta=1$ to replace a pair of squares.
- Use $1+\tan^2\theta=\sec^2\theta$ or $1+\cot^2\theta=\operatorname{cosec}^2\theta$ when secant, cosecant, or cotangent appears.
- Factor or collect terms before applying an identity.

Avoid changing both sides in a way that assumes the result. Work in a clear chain of equivalences, or state when you are simplifying the left-hand side only.

## 8. Compound-Angle Formulae

The compound-angle formulae connect trigonometric functions of $A+B$ and $A-B$ to functions of $A$ and $B$:

$$
\sin(A+B)=\sin A\cos B+\cos A\sin B,
$$

$$
\sin(A-B)=\sin A\cos B-\cos A\sin B,
$$

$$
\cos(A+B)=\cos A\cos B-\sin A\sin B,
$$

$$
\cos(A-B)=\cos A\cos B+\sin A\sin B,
$$

$$
\tan(A+B)=\frac{\tan A+\tan B}{1-\tan A\tan B},
$$

$$
\tan(A-B)=\frac{\tan A-\tan B}{1+\tan A\tan B}.
$$

These formulae are for structure, not just memorisation. They allow exact evaluation, simplification, and equation solving. For example, $\sin 75^\circ$ can be written as $\sin(45^\circ+30^\circ)$ and evaluated exactly.

## 9. Double-Angle Formulae

Set $B=A$ in the compound-angle formulae to get

$$
\sin 2A=2\sin A\cos A,
$$

$$
\cos 2A=\cos^2A-\sin^2A,
$$

and

$$
\tan 2A=\frac{2\tan A}{1-\tan^2A}.
$$

The cosine formula has two especially useful alternatives:

$$
\cos 2A=2\cos^2A-1
$$

and

$$
\cos 2A=1-2\sin^2A.
$$

Choose the version that matches the expression you already have. If the expression contains only $\sin^2A$, use $1-2\sin^2A$. If it contains only $\cos^2A$, use $2\cos^2A-1$.

## 10. The Form $a\sin\theta+b\cos\theta$

Expressions such as

$$
a\sin\theta+b\cos\theta
$$

can be written as a single shifted sine or cosine. In sine form,

$$
a\sin\theta+b\cos\theta=R\sin(\theta+\alpha),
$$

where

$$
R=\sqrt{a^2+b^2},\qquad R\cos\alpha=a,\qquad R\sin\alpha=b.
$$

This is useful because a single sine function is easy to sketch and solve. For example, its maximum is $R$ and its minimum is $-R$.

The same expression can also be written as

$$
R\cos(\theta-\beta),
$$

with constants chosen by expanding the right-hand side and matching coefficients.

## Worked-Thinking Routines

### Circular Measure

1. Convert any angle in degrees to radians.
2. Decide whether the problem needs arc length, sector area, triangle area, or a combination.
3. Draw the sector and label $r$, $\theta$, and any chord or triangle sides.
4. Substitute with units.
5. Check whether the answer is a length, area, or angle.

### Trigonometric Equations

1. Simplify the equation with identities.
2. Find reference values from exact values or inverse trigonometric notation.
3. Use the unit circle or graph to locate all solutions in the interval.
4. Watch for period changes caused by $2x$, $x-\alpha$, or similar arguments.
5. Check for lost or extra solutions.

### Identities

1. Identify the most complicated side.
2. Convert reciprocal functions if needed.
3. Replace paired squares using a Pythagorean identity.
4. Use compound-angle or double-angle formulae only when the argument structure suggests them.
5. End with the exact expression required.

## Common Mistakes

- Using $s=r\theta$ with $\theta$ in degrees.
- Writing $\sin^{-1}x$ when you mean $\operatorname{cosec}x$.
- Solving a trigonometric equation but keeping only the calculator's principal value.
- Forgetting the period of $\tan x$ is $\pi$.
- Dropping solutions when the angle is $2x$ or $x-\alpha$.
- Dividing by $\sin x$ or $\cos x$ without checking whether it could be zero.
- Choosing the wrong sign for a related angle.
- Using a compound-angle formula with the signs reversed.

## Quick Self-Check

You are ready to move on when you can:

- Explain why radians make $s=r\theta$ and $A=\frac{1}{2}r^2\theta$ simple.
- Use the unit circle to determine signs and exact values.
- Sketch $y=\sin x$, $y=\cos x$, $y=\tan x$, and simple transformations of them.
- Solve trigonometric equations over a specified interval.
- Prove basic identities by clean algebraic steps.
- Use reciprocal, compound-angle, and double-angle identities in context.
- Rewrite $a\sin\theta+b\cos\theta$ as one shifted sine or cosine.

## Connections

- [[20 Mathematics/01 Pure Mathematics/05 Differentiation/00 Overview|Differentiation]]
- [[20 Mathematics/01 Pure Mathematics/06 Integration/00 Overview|Integration]]
- [[20 Mathematics/01 Pure Mathematics/09 Complex Numbers/00 Overview|Complex Numbers]]
