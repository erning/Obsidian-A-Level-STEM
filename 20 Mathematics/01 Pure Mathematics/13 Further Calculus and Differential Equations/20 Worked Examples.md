---
title: Further Calculus and Differential Equations Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/13 Further Calculus and Differential Equations/00 Overview|Further Calculus and Differential Equations]]"
status: active
tags:
  - mathematics/pure
  - worked-examples
---

# Further Calculus and Differential Equations Worked Examples

These examples model the syllabus route through hyperbolic functions, further
differentiation and integration, separable equations, first-order linear
equations, constant-coefficient equations, and simple modelling.

## Source Route

- Syllabus: CAIE Mathematics 9709 section 3.8; CAIE Further Mathematics 9231
  sections 2.1, 2.3, 2.4, and 2.6.
- Main 9709 subtopics: formulate and solve separable differential equations,
  use initial conditions, and interpret solutions in context.
- Main 9231 subtopics: hyperbolic functions, inverse functions, Maclaurin
  series, further integration, reduction formulae, arc length, first-order
  linear differential equations, constant-coefficient differential equations,
  substitutions, and model interpretation.

## Example 1: Hyperbolic Identity and Inverse Form

**Prompt.** Prove

$$
\cosh^2x-\sinh^2x=1
$$

and solve $\sinh x=3$.

**Solution.**

Using the definitions,

$$
\cosh x=\frac{e^x+e^{-x}}{2},
\qquad
\sinh x=\frac{e^x-e^{-x}}{2}.
$$

Then

$$
\cosh^2x-\sinh^2x
=\frac{(e^x+e^{-x})^2-(e^x-e^{-x})^2}{4}=1.
$$

To solve $\sinh x=3$, write

$$
\frac{e^x-e^{-x}}{2}=3.
$$

Let $u=e^x$, where $u>0$. Then

$$
u-\frac1u=6,
$$

so

$$
u^2-6u-1=0.
$$

Hence

$$
u=3+\sqrt{10},
$$

and

$$
x=\ln(3+\sqrt{10}).
$$

**What this example trains.** Hyperbolic identities usually follow directly
from exponential definitions.

## Example 2: A Maclaurin Series

**Prompt.** Find the Maclaurin series of $e^x\cos x$ up to and including the
term in $x^3$.

**Solution.**

Use

$$
e^x=1+x+\frac{x^2}{2}+\frac{x^3}{6}+\cdots
$$

and

$$
\cos x=1-\frac{x^2}{2}+\cdots.
$$

Then

$$
e^x\cos x
=\left(1+x+\frac{x^2}{2}+\frac{x^3}{6}+\cdots\right)
\left(1-\frac{x^2}{2}+\cdots\right).
$$

Keeping terms up to $x^3$,

$$
e^x\cos x=1+x-\frac{x^3}{3}+\cdots.
$$

**What this example trains.** Maclaurin work needs only the terms that can
affect the requested order.

## Example 3: A Further Integral

**Prompt.** Evaluate

$$
\int \frac{dx}{\sqrt{9-x^2}}.
$$

**Solution.**

This matches the standard form

$$
\int\frac{dx}{\sqrt{a^2-x^2}}=\sin^{-1}\frac{x}{a}+C.
$$

Here $a=3$, so

$$
\int \frac{dx}{\sqrt{9-x^2}}
=\sin^{-1}\frac{x}{3}+C.
$$

**What this example trains.** Recognise square-root quadratic forms before
trying unnecessary substitution.

## Example 4: A Reduction Formula

**Prompt.** For

$$
I_n=\int_0^{\pi/2}\sin^n x\,dx,
$$

derive the reduction formula

$$
I_n=\frac{n-1}{n}I_{n-2}
$$

for $n\ge2$.

**Solution.**

Write

$$
I_n=\int_0^{\pi/2}\sin^{n-1}x\sin x\,dx.
$$

Use integration by parts with

$$
u=\sin^{n-1}x,\qquad dv=\sin x\,dx.
$$

Then

$$
du=(n-1)\sin^{n-2}x\cos x\,dx,\qquad v=-\cos x.
$$

The boundary term is zero, so

$$
I_n=(n-1)\int_0^{\pi/2}\sin^{n-2}x\cos^2x\,dx.
$$

Use $\cos^2x=1-\sin^2x$:

$$
I_n=(n-1)(I_{n-2}-I_n).
$$

Thus

$$
nI_n=(n-1)I_{n-2},
$$

so

$$
I_n=\frac{n-1}{n}I_{n-2}.
$$

**What this example trains.** Reduction formulae reduce an integral with
parameter $n$ to a smaller value of the parameter.

## Example 5: A Separable Differential Equation

**Prompt.** Solve

$$
\frac{dy}{dx}=xy,\qquad y(0)=2.
$$

**Solution.**

Separate variables:

$$
\frac1y\,dy=x\,dx.
$$

Integrate:

$$
\ln|y|=\frac{x^2}{2}+C.
$$

So

$$
y=Ae^{x^2/2}.
$$

Use $y(0)=2$:

$$
2=A.
$$

Therefore

$$
y=2e^{x^2/2}.
$$

**What this example trains.** Separable equations need an arbitrary constant
before applying an initial condition.

## Example 6: A First-Order Linear Differential Equation

**Prompt.** Solve

$$
\frac{dy}{dx}+2y=e^{-x}.
$$

**Solution.**

The equation is already in standard form. The integrating factor is

$$
\mu=e^{\int2\,dx}=e^{2x}.
$$

Multiply through:

$$
e^{2x}\frac{dy}{dx}+2e^{2x}y=e^x.
$$

The left side is

$$
\frac{d}{dx}(e^{2x}y).
$$

So

$$
\frac{d}{dx}(e^{2x}y)=e^x.
$$

Integrate:

$$
e^{2x}y=e^x+C.
$$

Therefore

$$
y=e^{-x}+Ce^{-2x}.
$$

**What this example trains.** The integrating factor creates a product
derivative.

## Example 7: Constant-Coefficient Differential Equation

**Prompt.** Solve

$$
\frac{d^2y}{dx^2}-3\frac{dy}{dx}+2y=3e^{3x}.
$$

**Solution.**

The complementary function comes from

$$
m^2-3m+2=0.
$$

Thus

$$
m=1,\qquad m=2,
$$

so

$$
y_c=Ae^x+Be^{2x}.
$$

For the particular integral, try

$$
y_p=ke^{3x}.
$$

Substitution gives

$$
(9k-9k+2k)e^{3x}=3e^{3x},
$$

so

$$
2k=3,\qquad k=\frac32.
$$

Therefore

$$
y=Ae^x+Be^{2x}+\frac32e^{3x}.
$$

**What this example trains.** The general solution is complementary function
plus particular integral.

## Example 8: A Simple Differential Equation Model

**Prompt.** A quantity $T$ cools toward room temperature $20$ according to

$$
\frac{dT}{dt}=-k(T-20).
$$

Given $T(0)=80$ and $T(10)=50$, find $T(t)$.

**Solution.**

Separate variables:

$$
\frac{1}{T-20}\,dT=-k\,dt.
$$

Integrate:

$$
\ln|T-20|=-kt+C.
$$

So

$$
T-20=Ae^{-kt}.
$$

Using $T(0)=80$ gives $A=60$. Hence

$$
T=20+60e^{-kt}.
$$

Using $T(10)=50$,

$$
50=20+60e^{-10k}.
$$

So

$$
e^{-10k}=\frac12,
\qquad
k=\frac{\ln2}{10}.
$$

Therefore

$$
T=20+60e^{-(\ln2)t/10}.
$$

**What this example trains.** Model constants are interpreted after solving,
not guessed before solving.
