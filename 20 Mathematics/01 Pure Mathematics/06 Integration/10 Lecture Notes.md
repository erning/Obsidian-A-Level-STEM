---
title: Integration Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/06 Integration/00 Overview|Integration]]"
status: draft
tags:
  - mathematics/pure
  - lecture-notes
---

# Integration Lecture Notes

Integration has two connected meanings. As reverse differentiation, it asks for a function whose derivative is known. As accumulation, it measures a total built up over an interval: area, volume, distance, probability, or another accumulated quantity.

The first question is always what the integral represents. An indefinite integral gives a family of functions. A definite integral gives a number. An area or volume problem needs a sketch and correct limits before calculation.

## Source Route

- 9709 1.8 Integration
- 9709 2.5 Integration
- 9709 3.5 Integration
- 9231 2.4 Integration
- Coursebook route: 9709 Pure Mathematics 1 Chapter 9; 9709 Pure Mathematics 2 and 3 Chapters 5 and 8; 9231 Further Mathematics integration content.

## Visual Guide

![[assets/generated/mathematics/integration.svg]]

Figure: The guide shows area under a curve as accumulated change. The geometric picture is essential: limits, signs, and regions matter as much as the antiderivative.

## 1. Indefinite Integration

An indefinite integral is a family of antiderivatives:

$$
\int f(x)\,dx=F(x)+C,
$$

where

$$
F'(x)=f(x).
$$

The constant $C$ is necessary because many functions have the same derivative. For example, $x^2$, $x^2+3$, and $x^2-10$ all have derivative $2x$.

The basic power rule is

$$
\int x^n\,dx=\frac{x^{n+1}}{n+1}+C,\qquad n\ne -1.
$$

The exceptional case is

$$
\int \frac{1}{x}\,dx=\ln|x|+C.
$$

Common 9709 integrals include

$$
\int e^{ax+b}\,dx=\frac{1}{a}e^{ax+b}+C,
$$

$$
\int \frac{1}{ax+b}\,dx=\frac{1}{a}\ln|ax+b|+C,
$$

$$
\int \sin(ax+b)\,dx=-\frac{1}{a}\cos(ax+b)+C,
$$

$$
\int \cos(ax+b)\,dx=\frac{1}{a}\sin(ax+b)+C,
$$

and

$$
\int \sec^2(ax+b)\,dx=\frac{1}{a}\tan(ax+b)+C.
$$

Check indefinite integrals by differentiating the result.

## 2. Definite Integrals and Area

If $F'(x)=f(x)$, then

$$
\int_a^b f(x)\,dx=F(b)-F(a).
$$

This is a signed accumulation. If $f(x)$ is below the $x$-axis, the definite integral is negative. Geometric area is never negative, so split the interval at intercepts if the curve crosses the axis.

For area between two curves, sketch the region and use

$$
\int_a^b \left(\text{upper curve}-\text{lower curve}\right)\,dx.
$$

If the upper and lower curves swap, split the integral at their intersection.

Improper integrals occur when a limit is infinite or the integrand is undefined at an endpoint. Treat them as limits. For example,

$$
\int_1^\infty \frac{1}{x^2}\,dx
=\lim_{b\to\infty}\int_1^b \frac{1}{x^2}\,dx.
$$

## 3. Volumes of Revolution

When a region under $y=f(x)$ is rotated about the $x$-axis, the volume is

$$
V=\pi\int_a^b y^2\,dx.
$$

If a region is rotated about the $y$-axis and expressed using $x$ as a function of $y$, use

$$
V=\pi\int_c^d x^2\,dy.
$$

The square is important: rotating a curve creates circular cross-sections. If the region is between two curves, think in terms of outer radius squared minus inner radius squared.

## 4. Substitution

Substitution reverses the chain rule. It is useful when an integrand contains a composite expression and something proportional to its derivative.

Example:

$$
\int 2x(x^2+1)^5\,dx.
$$

Let

$$
u=x^2+1,\qquad du=2x\,dx.
$$

Then

$$
\int 2x(x^2+1)^5\,dx=\int u^5\,du=\frac{u^6}{6}+C
=\frac{(x^2+1)^6}{6}+C.
$$

For definite integrals, either change the limits into $u$-values or return to $x$ before substituting the original limits. Do not mix a $u$ integrand with $x$ limits.

## 5. Integration by Parts

Integration by parts reverses the product rule:

$$
\int u\frac{dv}{dx}\,dx=uv-\int v\frac{du}{dx}\,dx.
$$

It is useful for products such as $x e^x$, $x\sin 2x$, $x^2e^{-x}$, $\ln x$, and $x\tan^{-1}x$. Choose $u$ to be the part that becomes simpler when differentiated, often a polynomial, logarithm, or inverse trigonometric function.

For $\int \ln x\,dx$, take

$$
u=\ln x,\qquad \frac{dv}{dx}=1.
$$

Then $v=x$, so

$$
\int \ln x\,dx=x\ln x-\int 1\,dx=x\ln x-x+C.
$$

## 6. Partial Fractions and Rational Functions

Partial fractions turn a rational function into simpler pieces that can be integrated using logarithms or inverse trigonometric forms.

For example,

$$
\frac{3x+5}{(x+1)(x+2)}
=\frac{A}{x+1}+\frac{B}{x+2}.
$$

After finding $A$ and $B$, integrate term by term:

$$
\int \frac{A}{x+1}\,dx=A\ln|x+1|+C.
$$

Also recognise the form

$$
\int \frac{f'(x)}{f(x)}\,dx=\ln|f(x)|+C.
$$

For example,

$$
\int \tan x\,dx
=\int \frac{\sin x}{\cos x}\,dx
=-\ln|\cos x|+C.
$$

## 7. Trigonometric Relationships

Trigonometric identities can make an integral possible. Common examples are

$$
\sin^2x=\frac{1-\cos2x}{2},
$$

and

$$
\cos^2x=\frac{1+\cos2x}{2}.
$$

Use these before integrating expressions such as $\sin^2x$ or $\cos^2(2x)$. The method is not "trig for its own sake"; the identity changes the integrand into terms with known antiderivatives.

## 8. Trapezium Rule

The trapezium rule estimates a definite integral from function values. If the interval $[a,b]$ is split into $n$ equal subintervals of width

$$
h=\frac{b-a}{n},
$$

then

$$
\int_a^b y\,dx
\approx
\frac{h}{2}\left(y_0+2y_1+2y_2+\cdots+2y_{n-1}+y_n\right).
$$

A sketch can tell whether the trapezium rule is likely to over-estimate or under-estimate. For a curve bending upward, the trapezia often lie above the curve; for a curve bending downward, they often lie below.

## 9. Further Integration Ideas

In 9231, integration extends beyond routine antiderivatives.

Hyperbolic functions integrate in the same reverse-derivative spirit:

$$
\int \sinh x\,dx=\cosh x+C,
\qquad
\int \cosh x\,dx=\sinh x+C.
$$

Completing the square helps recognise forms such as

$$
\int \frac{1}{x^2+a^2}\,dx,
\qquad
\int \frac{1}{a^2-x^2}\,dx,
\qquad
\int \frac{1}{x^2-a^2}\,dx.
$$

Some of these connect naturally with trigonometric or hyperbolic substitutions.

Reduction formulae relate an integral with parameter $n$ to a similar integral with a smaller parameter, such as an expression for

$$
I_n=\int_0^\pi \sin^n x\,dx
$$

in terms of $I_{n-2}$. The goal is not to memorise every formula, but to learn how integration by parts or differentiation of a product creates a recurrence.

Rectangular estimates connect integration with sums. Approximating area by rectangles can give inequalities and limits involving sums, especially when the rectangle width tends to zero.

Arc length and surface area of revolution also appear:

$$
L=\int_a^b \sqrt{1+\left(\frac{dy}{dx}\right)^2}\,dx
$$

for Cartesian arc length, with related formulae for parametric and polar curves. Surface area of revolution uses a radius multiplied by an arc-length element; always identify the axis of rotation first.

## Worked-Thinking Routines

### Indefinite Integral

1. Look for a direct reverse derivative.
2. Rewrite powers, roots, and reciprocals if useful.
3. Choose substitution, parts, partial fractions, or identities only when the structure suggests it.
4. Add $C$.
5. Differentiate the answer to check.

### Definite Area

1. Sketch the region.
2. Find intersection points or intercepts for limits.
3. Decide whether the integral is signed area or geometric area.
4. Split the region if signs or upper/lower curves change.
5. Keep exact values until the final simplification.

### Technique Choice

- Composite plus derivative nearby: substitution.
- Product where one part simplifies by differentiation: integration by parts.
- Rational function with factorable denominator: partial fractions.
- Powers of trigonometric functions: identities.
- Numeric data or no simple antiderivative: trapezium rule.

## Common Mistakes

- Forgetting the constant of integration.
- Using the power rule for $\int \frac{1}{x}\,dx$.
- Treating signed area as geometric area.
- Reversing upper and lower limits.
- Changing variables in a definite integral but keeping the old limits.
- Using integration by parts with a poor choice of $u$.
- Forgetting the square in a volume of revolution.
- Applying the trapezium rule with the wrong width $h$.

## Quick Self-Check

You are ready to move on when you can:

- Explain integration as both reverse differentiation and accumulation.
- Check an indefinite integral by differentiating.
- Compute definite integrals, areas between curves, and simple improper integrals.
- Set up volumes of revolution with correct limits and radii.
- Choose between substitution, integration by parts, partial fractions, and trigonometric identities.
- Use the trapezium rule and interpret over- or under-estimates from a sketch.
- Recognise the further ideas behind reduction formulae, rectangular estimates, arc length, and surface area.

## Connections

- [[20 Mathematics/01 Pure Mathematics/05 Differentiation/00 Overview|Differentiation]]
- [[20 Mathematics/03 Probability and Statistics/05 Continuous Random Variables/00 Overview|Continuous Random Variables]]
