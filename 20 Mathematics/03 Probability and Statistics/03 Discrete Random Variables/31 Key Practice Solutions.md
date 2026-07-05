---
title: Discrete Random Variables Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/03 Discrete Random Variables/00 Overview|Discrete Random Variables]]"
status: active
tags:
  - mathematics/statistics
  - solutions
---

# Discrete Random Variables Key Practice Solutions

This note gives worked solutions for [[20 Mathematics/03 Probability and Statistics/03 Discrete Random Variables/30 Key Practice Problems|Discrete Random Variables Key Practice Problems]]. Use it to check probability tables, endpoint inequalities, model assumptions, and variance transformations.

## A. Probability Tables

## Problem 1

$$
E(X)=0(0.2)+1(0.5)+2(0.3)=1.1.
$$

Also

$$
E(X^2)=0+1(0.5)+4(0.3)=1.7.
$$

Therefore

$$
\operatorname{Var}(X)=1.7-1.1^2=0.49.
$$

## Problem 2

Probabilities sum to $1$:

$$
k(1+2+3+4)=1.
$$

Thus $k=0.1$. Then

$$
E(X)=0.1(1^2+2^2+3^2+4^2)=3.
$$

Also

$$
E(X^2)=0.1(1^3+2^3+3^3+4^3)=10.
$$

So

$$
\operatorname{Var}(X)=10-3^2=1.
$$

## Problem 3

Each die has probability $1/6$ of showing a six, so

$$
X\sim B\left(2,\frac16\right).
$$

The distribution is

| $x$ | 0 | 1 | 2 |
|---:|---:|---:|---:|
| $P(X=x)$ | $\frac{25}{36}$ | $\frac{10}{36}$ | $\frac{1}{36}$ |

Hence

$$
E(X)=2\left(\frac16\right)=\frac13,
$$

and

$$
\operatorname{Var}(X)=2\left(\frac16\right)\left(\frac56\right)=\frac{5}{18}.
$$

## Problem 4

$$
P(X\le2)=0.1+0.2+0.4=0.7.
$$

$$
P(X>1)=0.4+0.3=0.7.
$$

## Problem 5

Probabilities sum to $1$:

$$
0.1+0.2+a+0.4=1.
$$

Thus

$$
a=0.3.
$$

Then

$$
E(X)=0(0.1)+1(0.2)+2(0.3)+3(0.4)=2.
$$

## B. Binomial Distribution

## Problem 6

$$
P(X=3)=\binom{10}{3}(0.4)^3(0.6)^7=0.215
$$

to 3 s.f.

## Problem 7

$$
P(X\ge1)=1-P(X=0)=1-(0.6)^{10}=0.994
$$

to 3 s.f.

## Problem 8

$$
E(X)=np=10(0.4)=4.
$$

$$
\operatorname{Var}(X)=np(1-p)=10(0.4)(0.6)=2.4.
$$

## Problem 9

$$
P(Y\le1)=P(Y=0)+P(Y=1).
$$

So

$$
P(Y\le1)=(0.8)^6+\binom61(0.2)(0.8)^5=0.655
$$

to 3 s.f.

## Problem 10

Let $X$ be the number of defective items. A suitable model is

$$
X\sim B(12,0.08).
$$

The assumptions are: there are $12$ fixed trials, each item is defective or not
defective, the probability of a defective item is constant at $0.08$, and the
items are independent.

## C. Geometric Distribution

## Problem 11

For $X\sim \operatorname{Geo}(0.25)$,

$$
P(X=3)=0.25(0.75)^2=0.140625.
$$

Also

$$
E(X)=\frac{1}{0.25}=4.
$$

## Problem 12

$X>5$ means the first five trials fail:

$$
P(X>5)=(0.75)^5=0.237
$$

to 3 s.f.

## Problem 13

$$
P(X\le4)=1-P(X>4)=1-(0.75)^4=0.684
$$

to 3 s.f.

## Problem 14

If $X$ is the attempt number of the first score, then

$$
X\sim \operatorname{Geo}(0.10).
$$

Thus

$$
E(X)=\frac{1}{0.10}=10.
$$

The expected number of attempts is $10$.

## Problem 15

Without replacement, the probability of success changes after each failed
draw. A geometric model requires independent trials with the same success
probability each time, so this situation is not usually geometric.

## D. Linear Transformations and Combinations

## Problem 16

$$
E(Y)=E(4-2X)=4-2E(X)=4-12=-8.
$$

$$
\operatorname{Var}(Y)=(-2)^2\operatorname{Var}(X)=4(5)=20.
$$

## Problem 17

$$
E(X+Y)=3+5=8.
$$

Since $X$ and $Y$ are independent,

$$
\operatorname{Var}(X+Y)=2+7=9.
$$

## Problem 18

$$
E(3X+2Y)=3(3)+2(5)=19.
$$

Since $X$ and $Y$ are independent,

$$
\operatorname{Var}(3X+2Y)=3^2(2)+2^2(7)=46.
$$

## Problem 19

For $X\sim B(20,0.1)$,

$$
E(X)=20(0.1)=2,
$$

and

$$
\operatorname{Var}(X)=20(0.1)(0.9)=1.8.
$$

Since $W=5X$,

$$
E(W)=5(2)=10,
$$

and

$$
\operatorname{Var}(W)=5^2(1.8)=45.
$$

## Problem 20

For $X\sim \operatorname{Geo}(0.2)$,

$$
E(X)=5.
$$

Since $C=2X+5$,

$$
E(C)=2E(X)+5=15.
$$

The expected cost is $15$ dollars.
