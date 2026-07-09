---
title: Continuous Random Variables Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Continuous Random Variables](00%20Overview.md)"
status: active
tags:
  - mathematics/statistics
  - solutions
---

# Continuous Random Variables Key Practice Solutions

This note gives worked solutions for [Key Practice Problems](30%20Key%20Practice%20Problems.md). Mark support intervals and integral limits as carefully as final numerical answers.

## Problem 1

Use total area $1$:

$$
\int_0^4 kx\,dx=1.
$$

So

$$
k\left[\frac{x^2}{2}\right]_0^4=1,
\qquad
8k=1,
\qquad
k=\frac18.
$$

Then

$$
P(1<X<3)=\int_1^3 \frac{x}{8}\,dx
=\left[\frac{x^2}{16}\right]_1^3
=\frac12.
$$

## Problem 2

Find $k$ from

$$
\int_0^2 k(1+x)\,dx=1.
$$

Since

$$
\int_0^2 (1+x)\,dx=\left[x+\frac{x^2}{2}\right]_0^2=4,
$$

we have

$$
k=\frac14.
$$

Now

$$
P(X>1)=\int_1^2 \frac14(1+x)\,dx
=\frac{1}{4}\left[x+\frac{x^2}{2}\right]_1^2
=\frac58.
$$

## Problem 3

Check total area:

$$
\int_0^2 \frac38x^2\,dx
=\frac38\left[\frac{x^3}{3}\right]_0^2
=1.
$$

So it is a valid density. Then

$$
P(X<1)=\int_0^1 \frac38x^2\,dx
=\frac18.
$$

## Problem 4

Use total area:

$$
\int_0^4 c(4-x)\,dx=1.
$$

Since

$$
\int_0^4 (4-x)\,dx=8,
$$

we get

$$
c=\frac18.
$$

Then

$$
P(1<X<3)=\int_1^3 \frac18(4-x)\,dx
=\frac12.
$$

## Problem 5

For the lower half,

$$
P(X<1)=\int_0^1 x\,dx=\frac12.
$$

For the upper tail,

$$
P(X>1.5)=\int_{1.5}^{2}(2-x)\,dx.
$$

Thus

$$
P(X>1.5)=\left[2x-\frac{x^2}{2}\right]_{1.5}^{2}
=\frac18.
$$

## Problem 6

For $f(x)=2x$ on $0\le x\le1$,

$$
E(X)=\int_0^1 x(2x)\,dx
=\int_0^1 2x^2\,dx
=\frac23.
$$

Also

$$
E(X^2)=\int_0^1 x^2(2x)\,dx
=\int_0^1 2x^3\,dx
=\frac12.
$$

Therefore

$$
\operatorname{Var}(X)=\frac12-\left(\frac23\right)^2
=\frac{1}{18}.
$$

## Problem 7

For $f(x)=3x^2$ on $0\le x\le1$,

$$
E(X)=\int_0^1 3x^3\,dx=\frac34.
$$

Also

$$
E(X^2)=\int_0^1 3x^4\,dx=\frac35.
$$

So

$$
\operatorname{Var}(X)=\frac35-\left(\frac34\right)^2
=\frac{3}{80}.
$$

## Problem 8

For $0\le a\le2$,

$$
P(X<a)=\int_0^a \frac12\,dx=\frac{a}{2}.
$$

The median $m$ satisfies

$$
\frac{m}{2}=0.5,
$$

so

$$
m=1.
$$

The $75$th percentile $q$ satisfies

$$
\frac{q}{2}=0.75,
$$

so

$$
q=1.5.
$$

## Problem 9

For $0\le a\le2$,

$$
P(X<a)=\int_0^a \frac38x^2\,dx
=\frac{a^3}{8}.
$$

The median $m$ satisfies

$$
\frac{m^3}{8}=0.5.
$$

So

$$
m^3=4,
\qquad
m=\sqrt[3]{4}=1.59
$$

to 3 s.f.

## Problem 10

Expectation:

$$
E(X)=\int_0^2 x\cdot\frac14(1+x)\,dx
=\frac14\int_0^2 (x+x^2)\,dx.
$$

Hence

$$
E(X)=\frac14\left[\frac{x^2}{2}+\frac{x^3}{3}\right]_0^2
=\frac76.
$$

Next,

$$
E(X^2)=\int_0^2 x^2\cdot\frac14(1+x)\,dx
=\frac14\int_0^2 (x^2+x^3)\,dx
=\frac53.
$$

Therefore

$$
\operatorname{Var}(X)=\frac53-\left(\frac76\right)^2
=\frac{11}{36}.
$$

## Problem 11

Differentiate the CDF on the support:

$$
f(x)=F'(x)=\frac{x}{2},
\qquad 0<x<2.
$$

The probability is

$$
P(0.5<X<1.5)=F(1.5)-F(0.5).
$$

So

$$
P(0.5<X<1.5)=\frac{1.5^2}{4}-\frac{0.5^2}{4}
=\frac12.
$$

## Problem 12

For $0\le x\le1$,

$$
F(x)=\int_0^x \frac13\,dt=\frac{x}{3}.
$$

For $1<x\le2$,

$$
F(x)=\frac13+\int_1^x \frac23\,dt
=\frac13+\frac23(x-1)
=\frac{2x-1}{3}.
$$

Thus

$$
F(x)=
\begin{cases}
0, & x<0,\\
\frac{x}{3}, & 0\le x\le1,\\
\frac{2x-1}{3}, & 1<x\le2,\\
1, & x>2.
\end{cases}
$$

Then

$$
P(0.5<X<1.5)=F(1.5)-F(0.5)
=\frac23-\frac16
=\frac12.
$$

## Problem 13

Use total area:

$$
\int_0^2 kx\,dx+\int_2^4 k(4-x)\,dx=1.
$$

Each triangular half has area $2k$, so

$$
4k=1,
\qquad
k=\frac14.
$$

Now

$$
P(1<X<3)
=\int_1^2 \frac{x}{4}\,dx+\int_2^3 \frac{4-x}{4}\,dx.
$$

This gives

$$
P(1<X<3)=\frac38+\frac38=\frac34.
$$

## Problem 14

On $0<x<1$,

$$
f(x)=F'(x)=3x^2.
$$

The median $m$ satisfies

$$
F(m)=0.5.
$$

So

$$
m^3=0.5,
\qquad
m=\sqrt[3]{0.5}=0.794
$$

to 3 s.f.

## Problem 15

For the upper tail,

$$
P(X>4)=\int_4^\infty \frac{1}{x^2}\,dx
=\left[-\frac{1}{x}\right]_4^\infty
=\frac14.
$$

For the interval,

$$
P(1<X<3)=\int_1^3 \frac{1}{x^2}\,dx
=\left[-\frac{1}{x}\right]_1^3
=\frac23.
$$

## Problem 16

Use linearity of expectation:

$$
E(1+3X)=1+3E(X).
$$

For $f(x)=2x$,

$$
E(X)=\frac23.
$$

Therefore

$$
E(1+3X)=1+3\left(\frac23\right)=3.
$$

## Problem 17

For $0\le y\le1$,

$$
F_Y(y)=P(Y\le y)=P(X^2\le y).
$$

Since $0\le X\le1$,

$$
F_Y(y)=P(X\le \sqrt{y}).
$$

The CDF of $X$ is $F_X(x)=x^2$ on $0\le x\le1$, so

$$
F_Y(y)=F_X(\sqrt{y})=y.
$$

Thus

$$
F_Y(y)=
\begin{cases}
0, & y<0,\\
y, & 0\le y\le1,\\
1, & y>1.
\end{cases}
$$

Therefore

$$
f_Y(y)=1,
\qquad 0<y<1.
$$

## Problem 18

For $0\le y\le1$,

$$
F_Y(y)=P(Y\le y)=P(X^3\le y).
$$

Since the cube function is increasing,

$$
F_Y(y)=P(X\le y^{1/3})=F_X(y^{1/3}).
$$

Hence

$$
F_Y(y)=(y^{1/3})^2=y^{2/3},
\qquad 0\le y\le1.
$$

So

$$
F_Y(y)=
\begin{cases}
0, & y<0,\\
y^{2/3}, & 0\le y\le1,\\
1, & y>1.
\end{cases}
$$

Differentiating,

$$
f_Y(y)=\frac{2}{3}y^{-1/3},
\qquad 0<y<1.
$$

## Problem 19

For $0\le y\le1$,

$$
F_Y(y)=P(Y\le y)=P(1-X\le y).
$$

This is

$$
F_Y(y)=P(X\ge 1-y).
$$

Since $F_X(x)=x^3$ for $0\le x\le1$,

$$
F_Y(y)=1-F_X(1-y)=1-(1-y)^3.
$$

So

$$
F_Y(y)=
\begin{cases}
0, & y<0,\\
1-(1-y)^3, & 0\le y\le1,\\
1, & y>1.
\end{cases}
$$

Differentiating,

$$
f_Y(y)=3(1-y)^2,
\qquad 0<y<1.
$$

## Problem 20

Since $0\le X\le1$,

$$
X^2<0.25
$$

is equivalent to

$$
X<0.5.
$$

Thus

$$
P(X^2<0.25)=\int_0^{0.5}2x\,dx
=0.25.
$$

Also

$$
E(X^2)=\int_0^1 x^2(2x)\,dx
=\frac12.
$$
