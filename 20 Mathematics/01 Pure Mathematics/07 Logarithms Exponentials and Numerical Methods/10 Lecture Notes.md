---
title: Logarithms, Exponentials and Numerical Methods Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/07 Logarithms Exponentials and Numerical Methods/00 Overview|Logarithms, Exponentials and Numerical Methods]]"
status: draft
tags:
  - mathematics/pure
  - lecture-notes
---

# Logarithms, Exponentials and Numerical Methods Lecture Notes

Logarithms and exponentials describe inverse growth processes. Numerical methods take over when an equation cannot be solved neatly by algebra but can still be located and approximated. The shared habit is to understand the graph before manipulating symbols.

For logarithms, protect the domain. For iteration, protect the accuracy. A correct method can still give a meaningless answer if a logarithm is taken outside its domain or if an iteration is rounded too early.

## Source Route

- 9709 2.2 Logarithmic and exponential functions
- 9709 3.2 Logarithmic and exponential functions
- 9709 2.6 Numerical solution of equations
- 9709 3.6 Numerical solution of equations
- Coursebook route: 9709 Pure Mathematics 2 and 3 Chapters 2 and 6.

## Visual Guide

![[assets/generated/mathematics/logarithms-exponentials-and-numerical-methods.svg]]

Figure: The guide shows exponential and logarithmic graphs as inverses, together with a tangent-based root approximation. Use it to connect algebra, graphs, and numerical approximation.

## 1. Exponentials and Logarithms as Inverses

For $a>0$ and $a\ne1$, the function

$$
y=a^x
$$

has inverse

$$
x=\log_a y.
$$

A logarithm answers the question: to what power must the base be raised?

The natural exponential and natural logarithm are

$$
e^x
\qquad\text{and}\qquad
\ln x.
$$

They satisfy

$$
\ln(e^x)=x
$$

and

$$
e^{\ln x}=x,\qquad x>0.
$$

The graph of $y=e^{kx}$ depends on the sign of $k$. If $k>0$, it grows; if $k<0$, it decays. The graph of $y=\ln x$ has domain $x>0$ and a vertical asymptote at $x=0$.

## 2. Laws of Logarithms

For positive $x$ and $y$,

$$
\log_a(xy)=\log_a x+\log_a y,
$$

$$
\log_a\left(\frac{x}{y}\right)=\log_a x-\log_a y,
$$

and

$$
\log_a(x^n)=n\log_a x.
$$

The laws apply to products, quotients, and powers, not to sums. In particular,

$$
\ln(x+y)\ne \ln x+\ln y.
$$

Before solving a logarithmic equation, write the domain restrictions. For example, $\ln(x-2)$ requires

$$
x>2.
$$

Any proposed solution must be checked against the original logarithms.

## 3. Solving Exponential and Logarithmic Equations

Use logarithms when the unknown appears in an index. For example, to solve

$$
3e^{2x}=15,
$$

divide first:

$$
e^{2x}=5.
$$

Then take natural logarithms:

$$
2x=\ln5,
$$

so

$$
x=\frac{1}{2}\ln5.
$$

For inequalities, remember that $\ln x$ is increasing on $x>0$, so it preserves inequality direction. Exponential functions with base greater than $1$ are increasing; bases between $0$ and $1$ are decreasing. This matters when comparing powers.

## 4. Exponential Models

A common growth or decay model is

$$
N=N_0e^{kt}.
$$

If $k>0$, the quantity grows. If $k<0$, it decays. In a half-life situation, if the half-life is $T$, then

$$
\frac{1}{2}=e^{kT},
$$

so

$$
k=\frac{\ln(1/2)}{T}.
$$

Since $\ln(1/2)<0$, the decay constant is negative. This sign check is a useful way to catch errors.

## 5. Transforming Relationships to Linear Form

Logarithms can turn nonlinear-looking models into straight-line relationships. This lets you estimate constants from a graph.

For a power law

$$
y=kx^n,
$$

take logarithms:

$$
\ln y=\ln k+n\ln x.
$$

This is linear in $\ln x$ and $\ln y$. If you plot $\ln y$ against $\ln x$, the gradient is $n$ and the intercept is $\ln k$.

For an exponential law such as

$$
y=ka^x,
$$

take logarithms:

$$
\ln y=\ln k+x\ln a.
$$

This is linear in $x$ and $\ln y$. The gradient is $\ln a$ and the intercept is $\ln k$.

The same idea works for

$$
y=ke^{bx},
$$

where

$$
\ln y=\ln k+bx.
$$

Before using logarithms on data, check that all $x$ or $y$ values being logged are positive.

## 6. Locating Roots Numerically

A root of $f(x)=0$ is an $x$-value where the graph meets the $x$-axis. If $f$ is continuous and $f(a)$ and $f(b)$ have opposite signs, then there is at least one root in the interval $(a,b)$.

This sign-change test locates a root but does not by itself give its decimal value. It is often the first step before iteration.

Graphical thinking is important. The equation

$$
f(x)=0
$$

can also be written as an intersection problem, such as

$$
g(x)=h(x).
$$

Different rearrangements can lead to different numerical methods.

## 7. Fixed-Point Iteration

If an equation can be rearranged as

$$
x=F(x),
$$

then a fixed-point iteration uses

$$
x_{n+1}=F(x_n).
$$

Starting from $x_0$, compute $x_1$, $x_2$, $x_3$, and so on. If the values settle toward a number $\alpha$, then $\alpha$ is a fixed point and is a root of the original rearranged equation.

Not every rearrangement converges. A different rearrangement of the same equation may converge faster, converge to a different root, or fail to converge. This is why the syllabus expects the understanding that an iteration may fail.

Use enough working precision during iteration and round only at the end. To justify an answer to a given number of decimal places, show enough successive approximations to make the rounding stable.

## 8. Newton Iteration as an Extension

Newton iteration is not the only numerical method, but it is a useful way to understand the tangent picture in the visual guide. It uses the tangent at the current point to estimate where the graph crosses the $x$-axis:

$$
x_{n+1}=x_n-\frac{f(x_n)}{f'(x_n)}.
$$

It often converges quickly when the starting value is close to the desired root, but it can fail if the starting value is poor, if $f'(x_n)$ is close to zero, or if the graph has awkward shape near the root.

## Worked-Thinking Routines

### Logarithmic or Exponential Equation

1. Write the domain restrictions.
2. Simplify before taking logarithms.
3. Use log laws only for products, quotients, and powers.
4. Solve algebraically.
5. Substitute into the original equation to check.

### Linearising Data

1. Identify the proposed model, such as $y=kx^n$ or $y=ka^x$.
2. Take logarithms and rearrange into $Y=mX+c$.
3. Decide what to plot on each axis.
4. Read the gradient and intercept.
5. Convert back from $\ln k$ or $\ln a$ to $k$ or $a$.

### Numerical Root

1. Use a graph or sign change to locate a root.
2. Choose or use the given rearrangement $x=F(x)$.
3. Start from a sensible value near the root.
4. Iterate with sufficient precision.
5. Check the result in the original equation and state the accuracy.

## Common Mistakes

- Taking logarithms of non-positive expressions.
- Applying log laws to sums.
- Forgetting that $e^{\ln x}=x$ requires $x>0$.
- Losing the sign of the decay constant.
- Plotting $\ln y$ against $x$ when the linear form requires $\ln y$ against $\ln x$.
- Assuming every rearrangement gives a convergent iteration.
- Rounding intermediate iterations too early.
- Reporting a numerical root without checking it in the original equation.

## Quick Self-Check

You are ready to move on when you can:

- Explain why $e^x$ and $\ln x$ are inverse functions.
- Use logarithm laws while respecting domain restrictions.
- Solve exponential and logarithmic equations and inequalities.
- Build and interpret exponential growth or decay models.
- Transform $y=kx^n$, $y=ka^x$, and $y=ke^{bx}$ into linear forms.
- Locate a root graphically or by sign change.
- Use fixed-point iteration and recognise that convergence is not automatic.
- Use Newton iteration as a tangent-based extension when appropriate.

## Connections

- [[10 Physics/01 Topics/19 Capacitance/00 Overview|Physics Capacitance]]
- [[10 Physics/01 Topics/23 Nuclear Physics/00 Overview|Physics Nuclear Physics]]
