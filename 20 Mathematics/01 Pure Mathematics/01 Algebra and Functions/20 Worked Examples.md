---
title: Algebra and Functions Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/01 Algebra and Functions/00 Overview|Algebra and Functions]]"
status: active
tags:
  - mathematics/pure
  - worked-examples
---

# Algebra and Functions Worked Examples

These examples are designed to show method choice, not just final answers. Try
each one before reading the solution.

## Example 1: Completed Square and Range

Find the minimum value of

$$
f(x) = 2x^2 - 12x + 7.
$$

### Solution

Factor out the coefficient of $x^2$ from the quadratic part:

$$
f(x) = 2(x^2 - 6x) + 7.
$$

Complete the square:

$$
x^2 - 6x = (x-3)^2 - 9.
$$

So

$$
f(x) = 2(x-3)^2 - 18 + 7
= 2(x-3)^2 - 11.
$$

Since $2(x-3)^2 \ge 0$, the minimum value is

$$
-11,
$$

attained at $x=3$.

## Example 2: Discriminant as a Tangency Condition

Find the values of $k$ for which the line

$$
y = x+k
$$

touches the curve

$$
y = x^2 - 3x + 5.
$$

### Solution

At intersection points,

$$
x+k = x^2 - 3x + 5.
$$

Rearrange:

$$
x^2 - 4x + (5-k) = 0.
$$

For tangency, the quadratic has a repeated root, so its discriminant is zero:

$$
(-4)^2 - 4(1)(5-k) = 0.
$$

Thus

$$
16 - 20 + 4k = 0,
$$

so

$$
k = 1.
$$

## Example 3: Composite Function Domain

Let

$$
f(x)=x^2+1, \qquad g(x)=\sqrt{x-5}.
$$

Find the domain of $gf$.

### Solution

The composite function is

$$
gf(x)=g(f(x))=\sqrt{x^2+1-5}
=\sqrt{x^2-4}.
$$

For this expression to be real,

$$
x^2 - 4 \ge 0.
$$

So

$$
(x-2)(x+2) \ge 0.
$$

The domain is

$$
x \le -2 \quad \text{or} \quad x \ge 2.
$$

## Example 4: Inverse Function with Restricted Domain

Let

$$
f(x) = (x-2)^2 + 3, \qquad x \ge 2.
$$

Find $f^{-1}(x)$ and state its domain.

### Solution

Write

$$
y = (x-2)^2 + 3.
$$

Then

$$
y-3 = (x-2)^2.
$$

Since the original domain is $x \ge 2$, we take the positive square root:

$$
\sqrt{y-3}=x-2.
$$

So

$$
x=2+\sqrt{y-3}.
$$

Swap $x$ and $y$:

$$
f^{-1}(x)=2+\sqrt{x-3}.
$$

The domain of $f^{-1}$ is the range of $f$, so

$$
x \ge 3.
$$

## Example 5: Modulus Inequality

Solve

$$
|2x-3| < 7.
$$

### Solution

Use the rule $|A| < b \iff -b < A < b$ for $b>0$:

$$
-7 < 2x-3 < 7.
$$

Add 3 throughout:

$$
-4 < 2x < 10.
$$

Divide by 2:

$$
-2 < x < 5.
$$

## Example 6: Remainder Theorem

The polynomial

$$
f(x)=2x^3+px^2-5x+4
$$

leaves remainder $10$ when divided by $x-2$. Find $p$.

### Solution

By the remainder theorem,

$$
f(2)=10.
$$

Substitute:

$$
2(2^3)+p(2^2)-5(2)+4=10.
$$

So

$$
16+4p-10+4=10.
$$

Hence

$$
4p+10=10,
$$

and

$$
p=0.
$$

## Example 7: Roots and Coefficients

The roots of

$$
x^3 - 4x^2 + 2x + 7 = 0
$$

are $\alpha$, $\beta$, and $\gamma$. Find

$$
\alpha^2+\beta^2+\gamma^2.
$$

### Solution

For a monic cubic,

$$
\alpha+\beta+\gamma=4
$$

and

$$
\alpha\beta+\beta\gamma+\gamma\alpha=2.
$$

Use

$$
\alpha^2+\beta^2+\gamma^2
= (\alpha+\beta+\gamma)^2
-2(\alpha\beta+\beta\gamma+\gamma\alpha).
$$

Therefore

$$
\alpha^2+\beta^2+\gamma^2
=4^2-2(2)=12.
$$

## Example 8: Oblique Asymptote

Find the oblique asymptote of

$$
y=\frac{x^2+3x+5}{x+1}.
$$

### Solution

Divide $x^2+3x+5$ by $x+1$:

$$
x^2+3x+5=(x+1)(x+2)+3.
$$

So

$$
y=x+2+\frac{3}{x+1}.
$$

As $|x|$ becomes large,

$$
\frac{3}{x+1}\to 0.
$$

The oblique asymptote is

$$
y=x+2.
$$

## Example 9: Partial Fractions

Decompose

$$
\frac{5x+1}{(x-1)(x+2)}.
$$

### Solution

Write

$$
\frac{5x+1}{(x-1)(x+2)}
=\frac{A}{x-1}+\frac{B}{x+2}.
$$

Multiply by $(x-1)(x+2)$:

$$
5x+1=A(x+2)+B(x-1).
$$

Set $x=1$:

$$
6=3A,
$$

so $A=2$.

Set $x=-2$:

$$
-9=-3B,
$$

so $B=3$.

Therefore

$$
\frac{5x+1}{(x-1)(x+2)}
=\frac{2}{x-1}+\frac{3}{x+2}.
$$

## Example 10: Range of a Rational Function

Find the range of

$$
y=\frac{x+1}{x^2+1}.
$$

### Solution

Rearrange:

$$
y(x^2+1)=x+1.
$$

So

$$
yx^2-x+(y-1)=0.
$$

For a real $x$ to exist, this quadratic in $x$ must have non-negative
discriminant:

$$
(-1)^2-4y(y-1)\ge 0.
$$

Thus

$$
1-4y^2+4y\ge 0.
$$

Rearrange:

$$
4y^2-4y-1\le 0.
$$

The roots are

$$
y=\frac{1\pm\sqrt{2}}{2}.
$$

Since the quadratic opens upwards, the range is

$$
\frac{1-\sqrt{2}}{2}
\le y \le
\frac{1+\sqrt{2}}{2}.
$$
