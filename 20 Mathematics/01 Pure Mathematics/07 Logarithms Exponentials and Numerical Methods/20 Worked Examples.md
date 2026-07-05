---
title: Logarithms, Exponentials and Numerical Methods Worked Examples
subject: Mathematics
syllabus:
  - 9709
parent: "[[20 Mathematics/01 Pure Mathematics/07 Logarithms Exponentials and Numerical Methods/00 Overview|Logarithms, Exponentials and Numerical Methods]]"
status: active
tags:
  - mathematics/pure
  - worked-examples
---

# Logarithms, Exponentials and Numerical Methods Worked Examples

These examples model the standard CAIE route through logarithm laws,
exponential equations and inequalities, growth and decay, linear form, root
location, fixed-point iteration, and Newton iteration as an extension.

## Source Route

- Syllabus: CAIE Mathematics 9709 sections 2.2, 3.2, 2.6, and 3.6.
- Main subtopics: laws of logarithms, $e^x$ and $\ln x$ as inverse functions,
  solving exponential equations and inequalities, transforming relationships to
  linear form, locating roots by sign changes, and using fixed-point iteration.
- Coursebook route: 9709 Pure Mathematics 2 and 3 Chapters 2 and 6.

## Example 1: Logarithmic Equation With Domain

**Prompt.** Solve

$$
\ln(x-1)+\ln(x+2)=\ln12.
$$

**Solution.**

First write the domain restrictions:

$$
x-1>0,\qquad x+2>0.
$$

So

$$
x>1.
$$

Combine the logarithms:

$$
\ln\left((x-1)(x+2)\right)=\ln12.
$$

Hence

$$
(x-1)(x+2)=12.
$$

This gives

$$
x^2+x-14=0.
$$

So

$$
x=\frac{-1\pm\sqrt{57}}{2}.
$$

Only the positive-domain value is allowed:

$$
x=\frac{-1+\sqrt{57}}{2}.
$$

**What this example trains.** Logarithm laws are only valid when the original
logarithm arguments are positive.

## Example 2: Exponential Equation

**Prompt.** Solve

$$
3^{2x-1}=5.
$$

**Solution.**

Take natural logarithms:

$$
(2x-1)\ln3=\ln5.
$$

Thus

$$
2x-1=\frac{\ln5}{\ln3}.
$$

Therefore

$$
x=\frac{1}{2}\left(1+\frac{\ln5}{\ln3}\right).
$$

**What this example trains.** When the unknown is in an index, logarithms bring
it down as a multiplier.

## Example 3: Exponential Inequality

**Prompt.** Solve

$$
\left(\frac{1}{2}\right)^x<8.
$$

**Solution.**

Rewrite both sides with base $2$:

$$
2^{-x}<2^3.
$$

Since $2^u$ is increasing,

$$
-x<3.
$$

Therefore

$$
x>-3.
$$

**What this example trains.** Bases between $0$ and $1$ reverse the behaviour
when you rewrite them as powers of a base greater than $1$.

## Example 4: Exponential Decay

**Prompt.** A quantity is modelled by

$$
P=200e^{kt}.
$$

It halves every $6$ time units. Find $k$ and the value after $10$ time units.

**Solution.**

After $6$ time units,

$$
100=200e^{6k}.
$$

So

$$
e^{6k}=\frac{1}{2}.
$$

Taking logarithms gives

$$
6k=\ln\frac{1}{2}.
$$

Hence

$$
k=\frac{\ln(1/2)}{6}.
$$

After $10$ time units,

$$
P=200e^{10k}
=200e^{\frac{10}{6}\ln(1/2)}
=200\left(\frac{1}{2}\right)^{\frac{5}{3}}.
$$

Numerically,

$$
P\approx63.0.
$$

**What this example trains.** A decay constant should be negative, and the
model can be evaluated exactly before rounding.

## Example 5: Linear Form for a Power Law

**Prompt.** A relationship has the form

$$
y=kx^n.
$$

A graph of $\ln y$ against $\ln x$ is a straight line with gradient
$\frac{3}{2}$ and intercept $\ln2$. Find the relationship.

**Solution.**

Taking logarithms gives

$$
\ln y=\ln k+n\ln x.
$$

The gradient is $n$, so

$$
n=\frac{3}{2}.
$$

The intercept is $\ln k$, so

$$
\ln k=\ln2.
$$

Thus $k=2$, and

$$
y=2x^{\frac{3}{2}}.
$$

**What this example trains.** For $y=kx^n$, plot $\ln y$ against $\ln x$;
gradient and intercept have specific meanings.

## Example 6: Linear Form for an Exponential Law

**Prompt.** A graph of $\ln y$ against $x$ is a straight line with gradient
$-0.4$ and intercept $\ln50$. Write $y$ in the form $ke^{bx}$.

**Solution.**

For

$$
y=ke^{bx},
$$

taking logarithms gives

$$
\ln y=\ln k+bx.
$$

The gradient is $b$, so

$$
b=-0.4.
$$

The intercept is $\ln k$, so $k=50$. Hence

$$
y=50e^{-0.4x}.
$$

**What this example trains.** A straight-line graph of $\ln y$ against $x$
models exponential growth or decay.

## Example 7: Locating a Root

**Prompt.** Show that

$$
f(x)=x^3-x-1
$$

has a root between $1$ and $2$.

**Solution.**

Evaluate:

$$
f(1)=1-1-1=-1
$$

and

$$
f(2)=8-2-1=5.
$$

Since $f(1)<0$ and $f(2)>0$, and $f$ is continuous, there is at least one root
between $1$ and $2$.

**What this example trains.** A sign change locates a root, but does not yet
give its decimal value.

## Example 8: Fixed-Point Iteration

**Prompt.** Use

$$
x_{n+1}=\cos x_n,\qquad x_0=0.7,
$$

to approximate the root of $x=\cos x$.

**Solution.**

Iterate without rounding too early:

| $n$ | $x_n$ |
|---|---|
| $0$ | $0.700000$ |
| $1$ | $0.764842$ |
| $2$ | $0.721492$ |
| $3$ | $0.750822$ |
| $4$ | $0.731404$ |
| $5$ | $0.744237$ |
| $6$ | $0.735605$ |

The values are settling toward the fixed point near

$$
x\approx0.739.
$$

**What this example trains.** Iteration is a sequence of approximations; stable
rounding needs more than one value.

## Example 9: Newton Iteration as an Extension

**Prompt.** Starting from $x_0=1.3$, apply Newton iteration twice to

$$
f(x)=x^3-x-1.
$$

**Solution.**

Newton iteration uses

$$
x_{n+1}=x_n-\frac{f(x_n)}{f'(x_n)}.
$$

Here

$$
f'(x)=3x^2-1.
$$

With $x_0=1.3$,

$$
x_1=1.3-\frac{1.3^3-1.3-1}{3(1.3)^2-1}
\approx1.325307.
$$

Then

$$
x_2\approx1.324718.
$$

So the root is approximately

$$
1.3247.
$$

**What this example trains.** Newton iteration uses tangent information and can
converge quickly when the starting value is sensible.
