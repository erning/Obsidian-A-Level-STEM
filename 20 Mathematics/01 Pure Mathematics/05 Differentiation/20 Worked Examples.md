---
title: Differentiation Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/05 Differentiation/00 Overview|Differentiation]]"
status: active
tags:
  - mathematics/pure
  - worked-examples
---

# Differentiation Worked Examples

These examples model the standard CAIE route through gradient functions, the
chain rule, product and quotient rules, tangents and normals, stationary
points, connected rates, implicit and parametric differentiation, inverse and
hyperbolic derivatives, and Maclaurin series.

## Source Route

- Syllabus: CAIE Mathematics 9709 sections 1.7, 2.4, and 3.4; CAIE Further
  Mathematics 9231 section 2.3.
- Main subtopics: derivative as gradient and rate of change, chain rule,
  product rule, quotient rule, standard derivatives, tangents, normals,
  stationary points, implicit and parametric differentiation, second
  derivatives, inverse and hyperbolic functions, and Maclaurin series.
- Coursebook route: 9709 Pure Mathematics 1 Chapters 7-8; 9709 Pure
  Mathematics 2 and 3 Chapters 4 and 8; 9231 differentiation content.

## Example 1: Chain Rule and a Gradient

**Prompt.** Differentiate

$$
y=(3x^2-5)^4
$$

and find the gradient at $x=1$.

**Solution.**

Use the chain rule. The outer function is a fourth power and the inner
function is $3x^2-5$:

$$
\frac{dy}{dx}=4(3x^2-5)^3\cdot6x.
$$

Thus

$$
\frac{dy}{dx}=24x(3x^2-5)^3.
$$

At $x=1$,

$$
\frac{dy}{dx}=24(1)(-2)^3=-192.
$$

**What this example trains.** A composite function needs the derivative of the
inside, not just the outer power.

## Example 2: Product Rule With a Logarithm

**Prompt.** Differentiate

$$
y=x^2\ln x.
$$

**Solution.**

Use the product rule with

$$
u=x^2,\qquad v=\ln x.
$$

Then

$$
u'=2x,\qquad v'=\frac{1}{x}.
$$

So

$$
\frac{dy}{dx}=2x\ln x+x^2\cdot\frac{1}{x}.
$$

Therefore

$$
\frac{dy}{dx}=2x\ln x+x.
$$

The expression is defined for $x>0$.

**What this example trains.** A standard derivative such as $\frac{d}{dx}\ln x$
still carries its domain.

## Example 3: Quotient Rule

**Prompt.** Differentiate

$$
y=\frac{x^2+1}{x-2}.
$$

**Solution.**

Let

$$
u=x^2+1,\qquad v=x-2.
$$

Then

$$
u'=2x,\qquad v'=1.
$$

The quotient rule gives

$$
\frac{dy}{dx}
=\frac{2x(x-2)-(x^2+1)}{(x-2)^2}.
$$

Simplify the numerator:

$$
2x(x-2)-(x^2+1)=x^2-4x-1.
$$

So

$$
\frac{dy}{dx}=\frac{x^2-4x-1}{(x-2)^2}.
$$

**What this example trains.** The numerator is $u'v-uv'$, in that order.

## Example 4: Tangent and Normal

**Prompt.** Find the tangent and normal to

$$
y=x^3-4x+1
$$

at $x=2$.

**Solution.**

The point is

$$
y=2^3-4(2)+1=1,
$$

so the point is $(2,1)$.

Differentiate:

$$
\frac{dy}{dx}=3x^2-4.
$$

At $x=2$,

$$
\frac{dy}{dx}=8.
$$

The tangent is

$$
y-1=8(x-2).
$$

The normal gradient is $-\frac{1}{8}$, so the normal is

$$
y-1=-\frac{1}{8}(x-2).
$$

**What this example trains.** A line needs both a gradient and a point.

## Example 5: Stationary Points and Classification

**Prompt.** Find and classify the stationary points of

$$
f(x)=x^3-3x^2-9x+4.
$$

**Solution.**

Differentiate:

$$
f'(x)=3x^2-6x-9=3(x-3)(x+1).
$$

Stationary points occur when $f'(x)=0$, so

$$
x=-1,\ 3.
$$

The corresponding values are

$$
f(-1)=9,\qquad f(3)=-23.
$$

Now use the second derivative:

$$
f''(x)=6x-6.
$$

At $x=-1$,

$$
f''(-1)=-12<0,
$$

so $(-1,9)$ is a local maximum.

At $x=3$,

$$
f''(3)=12>0,
$$

so $(3,-23)$ is a local minimum.

**What this example trains.** Solving $f'(x)=0$ locates candidates; a
classification test is still needed.

## Example 6: Connected Rates of Change

**Prompt.** The radius $r$ of a circle is increasing at
$0.2\text{ cm s}^{-1}$. Find the rate of change of the area when
$r=5\text{ cm}$.

**Solution.**

The area is

$$
A=\pi r^2.
$$

Differentiate with respect to $r$:

$$
\frac{dA}{dr}=2\pi r.
$$

Use the chain rule:

$$
\frac{dA}{dt}=\frac{dA}{dr}\frac{dr}{dt}.
$$

At $r=5$ and $\frac{dr}{dt}=0.2$,

$$
\frac{dA}{dt}=2\pi(5)(0.2)=2\pi.
$$

The area is increasing at

$$
2\pi\text{ cm}^2\text{ s}^{-1}.
$$

**What this example trains.** Write what is changing with respect to what, and
carry units through the chain rule.

## Example 7: Implicit Differentiation

**Prompt.** The curve

$$
x^2+y^2=xy+7
$$

passes through $(3,1)$. Find $\frac{dy}{dx}$ and the tangent at this point.

**Solution.**

Differentiate both sides with respect to $x$:

$$
2x+2y\frac{dy}{dx}=y+x\frac{dy}{dx}.
$$

Collect the $\frac{dy}{dx}$ terms:

$$
(2y-x)\frac{dy}{dx}=y-2x.
$$

Hence

$$
\frac{dy}{dx}=\frac{y-2x}{2y-x}.
$$

At $(3,1)$,

$$
\frac{dy}{dx}=\frac{1-6}{2-3}=5.
$$

The tangent is

$$
y-1=5(x-3).
$$

**What this example trains.** Every differentiated $y$ term brings a factor of
$\frac{dy}{dx}$.

## Example 8: Parametric Differentiation

**Prompt.** A curve is defined by

$$
x=t^2+1,\qquad y=t^3-t.
$$

Find $\frac{dy}{dx}$ and $\frac{d^2y}{dx^2}$ at $t=2$.

**Solution.**

First differentiate with respect to $t$:

$$
\frac{dx}{dt}=2t,\qquad \frac{dy}{dt}=3t^2-1.
$$

So

$$
\frac{dy}{dx}
=\frac{\frac{dy}{dt}}{\frac{dx}{dt}}
=\frac{3t^2-1}{2t}.
$$

At $t=2$,

$$
\frac{dy}{dx}=\frac{11}{4}.
$$

For the second derivative,

$$
\frac{d^2y}{dx^2}
=\frac{\frac{d}{dt}\left(\frac{dy}{dx}\right)}{\frac{dx}{dt}}.
$$

Since

$$
\frac{dy}{dx}=\frac{3t}{2}-\frac{1}{2t},
$$

we have

$$
\frac{d}{dt}\left(\frac{dy}{dx}\right)
=\frac{3}{2}+\frac{1}{2t^2}.
$$

Thus, at $t=2$,

$$
\frac{d^2y}{dx^2}
=\frac{\frac{3}{2}+\frac{1}{8}}{4}
=\frac{13}{32}.
$$

**What this example trains.** The second derivative is found by differentiating
$\frac{dy}{dx}$ with respect to $t$, then dividing by $\frac{dx}{dt}$.

## Example 9: Inverse and Hyperbolic Derivatives

**Prompt.** Differentiate

$$
y=\tan^{-1}(2x)+\sinh(3x).
$$

**Solution.**

Use the chain rule on both terms:

$$
\frac{d}{dx}\tan^{-1}(2x)
=\frac{2}{1+4x^2},
$$

and

$$
\frac{d}{dx}\sinh(3x)=3\cosh(3x).
$$

Therefore

$$
\frac{dy}{dx}=\frac{2}{1+4x^2}+3\cosh(3x).
$$

**What this example trains.** Standard inverse and hyperbolic derivatives still
need the chain rule when the argument is not just $x$.

## Example 10: Maclaurin Series From Derivatives

**Prompt.** Find the Maclaurin series for

$$
f(x)=\ln(1+2x)
$$

up to and including the term in $x^3$.

**Solution.**

First evaluate the function and its derivatives at $0$:

$$
f(0)=0.
$$

The first derivative is

$$
f'(x)=\frac{2}{1+2x},
$$

so

$$
f'(0)=2.
$$

The second derivative is

$$
f''(x)=-\frac{4}{(1+2x)^2},
$$

so

$$
f''(0)=-4.
$$

The third derivative is

$$
f'''(x)=\frac{16}{(1+2x)^3},
$$

so

$$
f'''(0)=16.
$$

Use

$$
f(x)=f(0)+xf'(0)+\frac{x^2}{2!}f''(0)+\frac{x^3}{3!}f'''(0)+\cdots.
$$

Therefore

$$
\ln(1+2x)=2x-2x^2+\frac{8}{3}x^3+\cdots.
$$

**What this example trains.** A Maclaurin series is organised differentiation
followed by substitution into the series formula.
