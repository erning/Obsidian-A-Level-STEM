---
title: Continuous Random Variables Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/05 Continuous Random Variables/00 Overview|Continuous Random Variables]]"
status: active
tags:
  - mathematics/statistics
  - worked-examples
---

# Continuous Random Variables Worked Examples

These examples model the CAIE route through probability density functions,
support intervals, integration for probabilities, expectation, variance,
percentiles, cumulative distribution functions, and simple related variables.

## Source Route

- CAIE Mathematics 9709 section 6.3: continuous random variables, probability
  density functions over a single interval, probabilities by area, mean,
  variance, and percentiles by direct area. Explicit CDF knowledge is not a
  9709 requirement.
- CAIE Further Mathematics 9231 section 4.1: piecewise PDFs, $E(g(X))$, the
  relationship between PDF and CDF, and CDFs of related variables in simple
  cases.

## Example 1: Finding a Density Constant

**Prompt.** A continuous random variable $X$ has density

$$
f(x)=kx,\qquad 0\le x\le2.
$$

Outside this interval, $f(x)=0$. Find $k$ and $P(1<X<2)$.

**Solution.**

A density must have total area $1$:

$$
\int_0^2 kx\,dx=1.
$$

So

$$
k\left[\frac{x^2}{2}\right]_0^2=1,
\qquad
2k=1,
\qquad
k=\frac12.
$$

Now

$$
P(1<X<2)=\int_1^2 \frac{x}{2}\,dx
=\left[\frac{x^2}{4}\right]_1^2
=\frac34.
$$

**Check.** A point probability such as $P(X=1)$ is $0$; probabilities come from
areas over intervals.

## Example 2: A Piecewise Density

**Prompt.** A random variable has density

$$
f(x)=
\begin{cases}
kx, & 0\le x\le1,\\
k(2-x), & 1<x\le2,\\
0, & \text{otherwise}.
\end{cases}
$$

Find $k$ and $P(0.5<X<1.5)$.

**Solution.**

The total area is

$$
\int_0^1 kx\,dx+\int_1^2 k(2-x)\,dx=1.
$$

The two triangular pieces each have area $\frac{k}{2}$, so $k=1$.

For the probability, split the integral at $x=1$:

$$
P(0.5<X<1.5)
=\int_{0.5}^1 x\,dx+\int_1^{1.5}(2-x)\,dx.
$$

Thus

$$
P(0.5<X<1.5)
=0.375+0.375
=0.75.
$$

**Check.** Piecewise densities must be integrated piece by piece.

## Example 3: Expectation and Variance

**Prompt.** Let

$$
f(x)=3x^2,\qquad 0\le x\le1.
$$

Find $E(X)$ and $\operatorname{Var}(X)$.

**Solution.**

First,

$$
E(X)=\int_0^1 x(3x^2)\,dx
=\int_0^1 3x^3\,dx
=\frac34.
$$

Next,

$$
E(X^2)=\int_0^1 x^2(3x^2)\,dx
=\int_0^1 3x^4\,dx
=\frac35.
$$

Therefore

$$
\operatorname{Var}(X)=E(X^2)-[E(X)]^2
=\frac35-\left(\frac34\right)^2
=\frac{3}{80}.
$$

**Check.** Since the density is larger near $1$, the mean $\frac34$ is greater
than the midpoint $\frac12$.

## Example 4: Median and Percentiles by Area

**Prompt.** Let

$$
f(x)=3x^2,\qquad 0\le x\le1.
$$

Find the median and the $90$th percentile.

**Solution.**

For $0\le a\le1$,

$$
P(X<a)=\int_0^a 3x^2\,dx=a^3.
$$

The median $m$ satisfies

$$
P(X<m)=0.5.
$$

So

$$
m^3=0.5,
\qquad
m=\sqrt[3]{0.5}=0.794
$$

to 3 s.f.

For the $90$th percentile $q$,

$$
q^3=0.90,
\qquad
q=\sqrt[3]{0.90}=0.965.
$$

**Check.** Both values are greater than $0.5$ because the density is weighted
towards the right of the interval.

## Example 5: Infinite Support

**Prompt.** A continuous random variable has density

$$
f(x)=\frac{2}{x^3},\qquad x\ge1.
$$

Show that this is a valid density, find $P(X>3)$, and find $E(X)$.

**Solution.**

Check total area:

$$
\int_1^\infty \frac{2}{x^3}\,dx
=\left[-\frac{1}{x^2}\right]_1^\infty
=1.
$$

So the density is valid. For the tail probability,

$$
P(X>3)=\int_3^\infty \frac{2}{x^3}\,dx
=\left[-\frac{1}{x^2}\right]_3^\infty
=\frac19.
$$

For expectation,

$$
E(X)=\int_1^\infty x\frac{2}{x^3}\,dx
=\int_1^\infty \frac{2}{x^2}\,dx
=2.
$$

**Check.** The density has infinite support, so the upper limit must be treated
as a limit.

## Example 6: PDF and CDF

**Prompt.** Let

$$
f(x)=2x,\qquad 0\le x\le1.
$$

Find the cumulative distribution function $F(x)$ and then find
$P(0.3<X<0.8)$.

**Solution.**

For $0\le x\le1$,

$$
F(x)=P(X\le x)=\int_0^x 2t\,dt=x^2.
$$

Including the full support,

$$
F(x)=
\begin{cases}
0, & x<0,\\
x^2, & 0\le x\le1,\\
1, & x>1.
\end{cases}
$$

Therefore

$$
P(0.3<X<0.8)=F(0.8)-F(0.3)=0.64-0.09=0.55.
$$

**Check.** A CDF must start at $0$, increase, and end at $1$.

## Example 7: Expectation of a Function of $X$

**Prompt.** Let $X$ have density

$$
f(x)=2x,\qquad 0\le x\le1.
$$

Find $E(X^2+1)$.

**Solution.**

Use the 9231 result

$$
E(g(X))=\int g(x)f(x)\,dx.
$$

Here $g(x)=x^2+1$, so

$$
E(X^2+1)=\int_0^1 (x^2+1)2x\,dx.
$$

Then

$$
E(X^2+1)=\int_0^1 (2x^3+2x)\,dx
=\left[\frac{x^4}{2}+x^2\right]_0^1
=\frac32.
$$

**Check.** This also equals $E(X^2)+1=\frac12+1$.

## Example 8: CDF of a Related Variable

**Prompt.** Let $X$ have CDF

$$
F_X(x)=
\begin{cases}
0, & x<0,\\
x^2, & 0\le x\le1,\\
1, & x>1.
\end{cases}
$$

Let $Y=X^3$. Find the CDF and PDF of $Y$.

**Solution.**

Since $0\le X\le1$, the related variable also has $0\le Y\le1$. For
$0\le y\le1$,

$$
F_Y(y)=P(Y\le y)=P(X^3\le y).
$$

The cube function is increasing, so

$$
F_Y(y)=P(X\le y^{1/3})=F_X(y^{1/3}).
$$

Therefore

$$
F_Y(y)=(y^{1/3})^2=y^{2/3},
\qquad 0\le y\le1.
$$

Including the support,

$$
F_Y(y)=
\begin{cases}
0, & y<0,\\
y^{2/3}, & 0\le y\le1,\\
1, & y>1.
\end{cases}
$$

Differentiate on $0<y<1$:

$$
f_Y(y)=\frac{2}{3}y^{-1/3}.
$$

**Check.** The range of $Y$ must be written before differentiating.
