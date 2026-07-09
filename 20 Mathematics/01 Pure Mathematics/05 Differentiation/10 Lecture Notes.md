---
title: Differentiation Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Differentiation](00%20Overview.md)"
status: active
tags:
  - mathematics/pure
  - lecture-notes
---

# Differentiation Lecture Notes

Differentiation measures local change. On a graph, the derivative is the gradient of the tangent. In a model, it is an instantaneous rate of change. Algebraically, differentiation turns a function into a new function that describes how the original one is changing.

The central question is always: what is changing with respect to what? Write the variable of differentiation explicitly, especially in rates, implicit equations, and parametric equations.

## Source Route

- 9709 1.7 Differentiation
- 9709 2.4 Differentiation
- 9709 3.4 Differentiation
- 9231 2.3 Differentiation
- Coursebook route: 9709 Pure Mathematics 1 Chapters 7-8; 9709 Pure Mathematics 2 and 3 Chapters 4 and 8; 9231 Further Mathematics differentiation content.

## Visual Guide

![differentiation](../../../assets/generated/mathematics/differentiation.svg)

Figure: The diagram shows a tangent gradient becoming a derivative function. The point is not only to calculate $f'(x)$, but to understand what $f'(x)$ says about the graph of $f$.

## 1. What a Derivative Means

For $y=f(x)$, the derivative at $x$ can be written as

$$
\frac{dy}{dx}=f'(x).
$$

Informally, it is the limit of gradients of chords as the two points become very close:

$$
f'(x)=\lim_{h\to0}\frac{f(x+h)-f(x)}{h}.
$$

This definition explains the two main interpretations:

- Geometric interpretation: $f'(a)$ is the gradient of the tangent to $y=f(x)$ at $x=a$.
- Rate interpretation: if $y$ depends on $x$, then $\frac{dy}{dx}$ is the instantaneous rate at which $y$ changes as $x$ changes.

The second derivative is

$$
\frac{d^2y}{dx^2}=f''(x),
$$

which measures how the gradient itself is changing.

## 2. Basic Rules

The power rule is

$$
\frac{d}{dx}x^n=nx^{n-1}
$$

for the powers used in the course. Together with constant multiples, sums, and differences, this gives

$$
\frac{d}{dx}(3x^4-5x^2+7)=12x^3-10x.
$$

The main structural rules are:

| Structure | Rule |
|---|---|
| Constant multiple | $\frac{d}{dx}[ku]=k\frac{du}{dx}$ |
| Sum or difference | $\frac{d}{dx}(u\pm v)=\frac{du}{dx}\pm\frac{dv}{dx}$ |
| Composite function | $\frac{d}{dx}f(g(x))=f'(g(x))g'(x)$ |
| Product | $\frac{d}{dx}(uv)=u'v+uv'$ |
| Quotient | $\frac{d}{dx}\left(\frac{u}{v}\right)=\frac{u'v-uv'}{v^2}$ |

Choose the rule from the structure:

- A power of a bracket usually needs the chain rule.
- Two large factors usually need the product rule.
- A quotient with variable numerator and denominator usually needs the quotient rule.
- A quotient such as $\frac{1}{(2x+1)^3}$ may be cleaner as $(2x+1)^{-3}$ followed by the chain rule.

## 3. Standard Derivatives

For 9709, the standard derivatives include:

$$
\frac{d}{dx}e^x=e^x,\qquad
\frac{d}{dx}\ln x=\frac{1}{x},
$$

$$
\frac{d}{dx}\sin x=\cos x,\qquad
\frac{d}{dx}\cos x=-\sin x,
$$

$$
\frac{d}{dx}\tan x=\sec^2x,
$$

and

$$
\frac{d}{dx}\tan^{-1}x=\frac{1}{1+x^2}.
$$

For trigonometric derivatives, angles are in radians. If a question uses degrees in a context involving calculus, convert or interpret carefully.

For 9231, the toolkit extends to inverse trigonometric and hyperbolic functions. The inverse trigonometric functions need $|x|\le 1$ (and the derivatives diverge at $|x|=1$):

$$
\frac{d}{dx}\sin^{-1}x=\frac{1}{\sqrt{1-x^2}},
\qquad
\frac{d}{dx}\cos^{-1}x=-\frac{1}{\sqrt{1-x^2}},
$$

$$
\frac{d}{dx}\sinh x=\cosh x,\qquad
\frac{d}{dx}\cosh x=\sinh x,\qquad
\frac{d}{dx}\tanh x=\operatorname{sech}^2x.
$$

The common inverse hyperbolic derivatives are

$$
\frac{d}{dx}\sinh^{-1}x=\frac{1}{\sqrt{x^2+1}},\qquad x\in\mathbb{R},
$$

$$
\frac{d}{dx}\cosh^{-1}x=\frac{1}{\sqrt{x^2-1}},\qquad x>1,
$$

and

$$
\frac{d}{dx}\tanh^{-1}x=\frac{1}{1-x^2},\qquad |x|<1.
$$

Always keep domain restrictions in mind when using inverse functions and logarithms.

## 4. Tangents and Normals

At $x=a$, the point on the curve is

$$
(a,f(a)),
$$

and the tangent gradient is

$$
f'(a).
$$

The tangent equation is usually written using point-gradient form:

$$
y-f(a)=f'(a)(x-a).
$$

The normal is perpendicular to the tangent. If the tangent gradient is $m$, then the normal gradient is

$$
-\frac{1}{m},
$$

provided $m\ne0$. If the tangent is horizontal, the normal is vertical. If the tangent is vertical, the normal is horizontal, though vertical tangents are more common in implicit or parametric work.

## 5. Stationary Points and Graph Shape

A stationary point occurs when

$$
f'(x)=0.
$$

It may be a local maximum, a local minimum, or a stationary point of inflection. There are two standard tests.

The sign-change test looks at the sign of $f'(x)$ on each side:

| Change in $f'(x)$ | Interpretation |
|---|---|
| $+$ to $-$ | Local maximum |
| $-$ to $+$ | Local minimum |
| No sign change | Stationary point of inflection or another flat contact |

The second-derivative test uses $f''(a)$:

| Value | Interpretation |
|---|---|
| $f''(a)>0$ | Usually local minimum |
| $f''(a)<0$ | Usually local maximum |
| $f''(a)=0$ | Inconclusive |

Increasing and decreasing intervals come directly from the first derivative:

$$
f'(x)>0 \Rightarrow f(x)\text{ is increasing},
$$

$$
f'(x)<0 \Rightarrow f(x)\text{ is decreasing}.
$$

When sketching a graph, combine intercepts, asymptotes, stationary points, and derivative signs.

## 6. Optimisation and Rates of Change

Optimisation problems usually follow this pattern:

1. Define the quantity to maximise or minimise.
2. Express it as a function of one variable.
3. Differentiate.
4. Solve $f'(x)=0$.
5. Use a sign test, second derivative, or endpoint comparison to justify the maximum or minimum.
6. Answer in the context of the problem.

Connected rates of change use the chain rule between variables. If $A$ depends on $r$ and $r$ depends on $t$, then

$$
\frac{dA}{dt}=\frac{dA}{dr}\frac{dr}{dt}.
$$

In these questions, write units beside the rates. A negative rate usually means the quantity is decreasing, not that the calculation has failed.

## 7. Implicit Differentiation

An implicit equation mixes $x$ and $y$ in one relation, such as

$$
x^2+y^2=xy+7.
$$

Differentiate both sides with respect to $x$. Every time you differentiate a function of $y$, multiply by $\frac{dy}{dx}$.

For example,

$$
x^2+y^2=25
$$

gives

$$
2x+2y\frac{dy}{dx}=0,
$$

so

$$
\frac{dy}{dx}=-\frac{x}{y}.
$$

For a second derivative, differentiate the expression for $\frac{dy}{dx}$ again with respect to $x$, remembering that $y$ is still a function of $x$.

## 8. Parametric Differentiation

If a curve is given by

$$
x=x(t),\qquad y=y(t),
$$

then

$$
\frac{dy}{dx}=\frac{\frac{dy}{dt}}{\frac{dx}{dt}},
\qquad \frac{dx}{dt}\ne0.
$$

The second derivative is not simply

$$
\frac{d^2y/dt^2}{d^2x/dt^2}.
$$

Instead,

$$
\frac{d^2y}{dx^2}
=\frac{\frac{d}{dt}\left(\frac{dy}{dx}\right)}{\frac{dx}{dt}}.
$$

For tangents and normals, find the parameter value first, then calculate the point and gradient.

## 9. Maclaurin Series

In 9231, differentiation also builds Maclaurin series. A Maclaurin series expands a function around $x=0$:

$$
f(x)=f(0)+xf'(0)+\frac{x^2}{2!}f''(0)+\frac{x^3}{3!}f'''(0)+\cdots.
$$

The first few terms often give a local approximation near $x=0$. The work is mostly organised differentiation: find successive derivatives, evaluate them at $0$, and substitute into the series.

## Worked-Thinking Routines

### Differentiating an Explicit Function

1. Identify the main structure: sum, product, quotient, or composite.
2. Rewrite awkward roots and reciprocals as powers if that helps.
3. Apply the rule carefully, especially the inner derivative in the chain rule.
4. Simplify only as far as it helps the next step.
5. Check dimensions, signs, and domains.

### Tangent or Normal

1. Find the point on the curve.
2. Differentiate to find the tangent gradient.
3. Use point-gradient form for the tangent.
4. Use the negative reciprocal for the normal when appropriate.
5. Check special cases such as horizontal tangents.

### Stationary Point

1. Solve $f'(x)=0$.
2. Find the corresponding $y$-values.
3. Classify using sign changes or $f''(x)$.
4. If $f''(x)=0$, use another method.
5. Interpret the result on the graph or in context.

## Common Mistakes

- Applying the chain rule but forgetting the derivative of the inner function.
- Reversing the numerator in the quotient rule.
- Treating $f'(x)=0$ as automatically meaning a maximum or minimum.
- Using the second-derivative test when $f''(a)=0$ and still drawing a conclusion.
- Finding a tangent gradient but forgetting the point needed for the line.
- Treating $\frac{dy}{dt}$ as $\frac{dy}{dx}$ in parametric questions.
- Forgetting that $y$ is a function of $x$ in implicit differentiation.
- Ignoring domain restrictions for $\ln x$ and inverse functions.

## Quick Self-Check

You are ready to move on when you can:

- Explain derivative as both tangent gradient and instantaneous rate of change.
- Choose the correct rule from the structure of a function.
- Differentiate powers, exponentials, logarithms, trigonometric functions, and composites.
- Write tangent and normal equations.
- Locate and classify stationary points.
- Solve optimisation and connected-rate problems.
- Differentiate implicit and parametric relations, including second derivatives where needed.
- Use derivatives to form the first few terms of a Maclaurin series.

## Connections

- [Integration](../06%20Integration/00%20Overview.md)
- [Kinematics and Newtonian Motion](../../02%20Mechanics/02%20Kinematics%20and%20Newtonian%20Motion/00%20Overview.md)
