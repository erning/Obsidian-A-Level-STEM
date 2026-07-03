---
title: Further Calculus and Differential Equations Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/13 Further Calculus and Differential Equations/00 Overview|Further Calculus and Differential Equations]]"
status: draft
tags:
  - mathematics/pure
  - lecture-notes
---

# Further Calculus and Differential Equations Lecture Notes

Further calculus extends the differentiation and integration toolkit. Differential equations use that toolkit to describe quantities whose rates of change are part of the problem. The goal is not only to solve equations, but to interpret the behaviour of the solution.

## Source Route

- 9709 3.8 Differential equations
- 9231 2.1 Hyperbolic functions
- 9231 2.3 Differentiation
- 9231 2.4 Integration
- 9231 2.6 Differential equations
- Coursebook route: 9709 Pure Mathematics 2 and 3 Chapter 10; 9231 Further Mathematics Coursebook chapters on hyperbolic functions, further calculus, and differential equations.

## Visual Guide

![[assets/generated/mathematics/further-calculus-and-differential-equations.svg]]

Figure: The guide shows a slope field with solution curves. A differential equation gives local slope information; solving it finds curves that follow those slopes.

## 1. Hyperbolic Functions

The hyperbolic functions are defined using exponentials:

$$
\sinh x=\frac{e^x-e^{-x}}{2},
\qquad
\cosh x=\frac{e^x+e^{-x}}{2},
$$

and

$$
\tanh x=\frac{\sinh x}{\cosh x}.
$$

The reciprocal hyperbolic functions are $\operatorname{sech}x$, $\operatorname{cosech}x$, and $\coth x$.

The central identity is

$$
\cosh^2x-\sinh^2x=1.
$$

Hyperbolic functions have identities similar to trigonometric identities, but with sign changes. Their inverse functions also have logarithmic forms, which are often derived from the exponential definitions.

## 2. Further Differentiation and Maclaurin Series

The 9231 differentiation toolkit includes hyperbolic functions, inverse trigonometric functions, inverse hyperbolic functions, and second derivatives for implicit or parametric curves.

A Maclaurin series expands a function around $x=0$:

$$
f(x)=f(0)+xf'(0)+\frac{x^2}{2!}f''(0)+\frac{x^3}{3!}f'''(0)+\cdots.
$$

The work is systematic: differentiate repeatedly, evaluate at $0$, and substitute. Sometimes implicit differentiation is used to find successive derivatives efficiently, for example after rewriting a derivative in terms of $y$.

## 3. Further Integration Techniques

Further integration includes hyperbolic functions, completing the square, trigonometric and hyperbolic substitutions, integration by parts, reduction formulae, rectangular estimates, arc length, and surface area of revolution.

A reduction formula relates an integral with parameter $n$ to another with a smaller parameter. It is usually created by integration by parts or by differentiating a product.

The point of these techniques is method selection. Before calculating, ask what structure is visible: product, composite, rational function, square root of a quadratic, or repeated power.

## 4. Separable Differential Equations

A differential equation relates an unknown function to its derivatives. In 9709, a main type is separable:

$$
\frac{dy}{dx}=g(x)h(y).
$$

Separate variables:

$$
\frac{1}{h(y)}\,dy=g(x)\,dx,
$$

then integrate both sides.

Example:

$$
\frac{dy}{dx}=xy
$$

gives

$$
\frac{1}{y}\,dy=x\,dx.
$$

Integrating,

$$
\ln|y|=\frac{x^2}{2}+C,
$$

so

$$
y=Ae^{x^2/2}
$$

for a non-zero constant $A$, with any special zero solution checked separately if relevant.

Initial conditions choose a particular solution from the general family.

## 5. Modelling with Differential Equations

A rate statement becomes a differential equation. For example, "the rate of change of $y$ is proportional to $y$" becomes

$$
\frac{dy}{dt}=ky.
$$

The constant $k$ must be introduced and later evaluated if data or an initial condition is given.

After solving, interpret the solution in context:

- Is the quantity increasing or decreasing?
- Does it approach a limiting value?
- What does the arbitrary constant mean?
- Does the domain make sense for the model?

## 6. First-Order Linear Differential Equations

In 9231, a first-order linear equation has standard form

$$
\frac{dy}{dx}+P(x)y=Q(x).
$$

The integrating factor is

$$
\mu(x)=e^{\int P(x)\,dx}.
$$

Multiplying the equation by $\mu(x)$ makes the left side a product derivative:

$$
\frac{d}{dx}(\mu y)=\mu Q(x).
$$

Then integrate and solve for $y$.

The most common error is failing to first divide through so that the coefficient of $\frac{dy}{dx}$ is $1$.

## 7. Linear Equations with Constant Coefficients

For a linear differential equation with constant coefficients, the general solution is

$$
\text{general solution}=\text{complementary function}+\text{particular integral}.
$$

The complementary function solves the homogeneous equation. For example,

$$
\frac{d^2y}{dx^2}-3\frac{dy}{dx}+2y=0
$$

has auxiliary equation

$$
\lambda^2-3\lambda+2=0.
$$

Since $\lambda=1,2$, the complementary function is

$$
y=Ae^x+Be^{2x}.
$$

Second-order equations include distinct real roots, repeated real roots, and conjugate complex roots. These cases produce different complementary functions.

The particular integral is chosen to match the forcing term, such as a polynomial, $ae^{bx}$, or $a\cos px+b\sin px$. Substitute the trial form into the differential equation to determine coefficients.

## 8. Substitutions in Differential Equations

Some differential equations become standard only after a given substitution. For example, a substitution such as $x=e^t$ can reduce an equation to one with constant coefficients, and a substitution such as $y=ux$ can reduce certain equations to separable form.

When a substitution is given:

1. Rewrite derivatives carefully.
2. Substitute into the equation.
3. Solve the transformed equation.
4. Convert back to the original variables.

## Worked-Thinking Routines

### Differential Equation from Words

1. Identify the changing quantity and independent variable.
2. Translate "rate of change" into a derivative.
3. Introduce a constant of proportionality if needed.
4. Solve the differential equation.
5. Use initial or boundary conditions.
6. Interpret the result in context.

### Solving a Differential Equation

1. Classify the equation: separable, first-order linear, constant-coefficient linear, or substitution-based.
2. Put it into standard form.
3. Apply the matching method.
4. Include arbitrary constants.
5. Apply conditions for a particular solution.
6. Differentiate and substitute back to check.

## Common Mistakes

- Dropping arbitrary constants.
- Separating variables incorrectly.
- Forgetting special constant solutions.
- Using an integrating factor before putting the equation in standard form.
- Confusing complementary function with particular integral.
- Choosing a particular-integral trial form that duplicates the complementary function without adjusting it.
- Solving symbolically but not interpreting the solution in context.

## Quick Self-Check

You are ready to move on when you can:

- Use hyperbolic definitions and identities.
- Form the first few Maclaurin terms of a function.
- Recognise further integration structures and choose an appropriate method.
- Solve separable differential equations.
- Translate simple rate statements into differential equations.
- Solve first-order linear equations using an integrating factor.
- Solve constant-coefficient linear differential equations using complementary functions and particular integrals.
- Use initial or boundary conditions and check the final solution.

## Connections

- [[20 Mathematics/01 Pure Mathematics/05 Differentiation/00 Overview|Differentiation]]
- [[20 Mathematics/01 Pure Mathematics/06 Integration/00 Overview|Integration]]
- [[10 Physics/01 Topics/17 Oscillations/00 Overview|Physics Oscillations]]
