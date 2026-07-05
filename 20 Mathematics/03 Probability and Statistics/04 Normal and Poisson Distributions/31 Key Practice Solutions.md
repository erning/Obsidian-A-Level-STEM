---
title: Normal and Poisson Distributions Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/04 Normal and Poisson Distributions/00 Overview|Normal and Poisson Distributions]]"
status: active
tags:
  - mathematics/statistics
  - solutions
---

# Normal and Poisson Distributions Key Practice Solutions

This note gives worked solutions for [[20 Mathematics/03 Probability and Statistics/04 Normal and Poisson Distributions/30 Key Practice Problems|Key Practice Problems]]. Use it to mark modelling, boundaries, and continuity correction as well as numerical answers.

## Problem 1

For $X\sim N(60,5^2)$,

$$
P(X<67)=P\left(Z<\frac{67-60}{5}\right)=P(Z<1.4)=0.919.
$$

For the interval,

$$
P(55<X<67)
=P\left(-1<Z<1.4\right)
=0.761.
$$

## Problem 2

Standardise the upper boundary:

$$
z=\frac{118-100}{12}=1.5.
$$

Therefore

$$
P(X>118)=P(Z>1.5)=0.0668.
$$

## Problem 3

The lower quartile of the standard normal distribution has

$$
z=-0.674.
$$

So

$$
\frac{k-40}{6}=-0.674,
\qquad
k=40+6(-0.674)=36.0
$$

to 3 s.f.

## Problem 4

Since

$$
P(Z<-1)=0.1587,
$$

we have

$$
\frac{32-\mu}{4}=-1.
$$

Thus

$$
\mu=36.
$$

## Problem 5

Use the standard normal values

$$
z_{0.10}=-1.282,
\qquad
z_{0.90}=1.282.
$$

Hence

$$
\frac{18-\mu}{\sigma}=-1.282,
\qquad
\frac{30-\mu}{\sigma}=1.282.
$$

The two percentiles are symmetric, so

$$
\mu=\frac{18+30}{2}=24.
$$

Then

$$
\frac{30-24}{\sigma}=1.282,
\qquad
\sigma=\frac{6}{1.282}=4.68.
$$

## Problem 6

For $X\sim \operatorname{Po}(2.5)$,

$$
P(X=3)=\frac{e^{-2.5}2.5^3}{3!}=0.214.
$$

Also

$$
P(X\le1)=P(X=0)+P(X=1)
=e^{-2.5}(1+2.5)=0.287.
$$

## Problem 7

The mean for $30$ minutes is $3$. If $X$ is the number of emails in
$30$ minutes, then

$$
X\sim \operatorname{Po}(3).
$$

Thus

$$
P(X=2)=\frac{e^{-3}3^2}{2!}=0.224.
$$

The mean for $10$ minutes is $1$. If $Y$ is the number of emails in
$10$ minutes, then

$$
P(Y\ge1)=1-P(Y=0)=1-e^{-1}=0.632.
$$

## Problem 8

Use the complement:

$$
P(X>3)=1-P(X\le3).
$$

For $X\sim \operatorname{Po}(5)$,

$$
P(X\le3)=e^{-5}\left(1+5+\frac{5^2}{2!}+\frac{5^3}{3!}\right).
$$

So

$$
P(X>3)=0.735.
$$

For a Poisson variable,

$$
E(X)=\operatorname{Var}(X)=5.
$$

## Problem 9

In $3$ hours, the mean number of customers is

$$
4\times3=12.
$$

So a suitable model is

$$
X\sim \operatorname{Po}(12).
$$

The mean and variance are both

$$
E(X)=\operatorname{Var}(X)=12.
$$

This uses the assumptions of independent arrivals and an approximately
constant average rate.

## Problem 10

For a Poisson distribution,

$$
P(X=0)=e^{-\lambda}.
$$

So

$$
e^{-\lambda}=0.1353,
\qquad
\lambda\approx2.
$$

Then

$$
P(X=2)=\frac{e^{-2}2^2}{2!}=0.271.
$$

## Problem 11

For $X\sim B(120,0.02)$,

$$
n=120>50,
\qquad
np=2.4<5.
$$

Use

$$
X\approx \operatorname{Po}(2.4).
$$

Then

$$
P(X\le2)\approx e^{-2.4}\left(1+2.4+\frac{2.4^2}{2!}\right)=0.570.
$$

## Problem 12

For $X\sim B(100,0.45)$,

$$
np=45>5,
\qquad
nq=55>5.
$$

Use

$$
X\approx Y,
\qquad
Y\sim N(45,24.75).
$$

Since $X<40$ means $X\le39$, apply a continuity correction:

$$
P(X<40)\approx P(Y<39.5).
$$

Then

$$
z=\frac{39.5-45}{\sqrt{24.75}}=-1.11.
$$

So

$$
P(X<40)\approx 0.134.
$$

## Problem 13

For $X\sim \operatorname{Po}(20)$, the parameter is large enough for the
normal approximation:

$$
X\approx Y,
\qquad
Y\sim N(20,20).
$$

Since $X\ge25$, use the continuity correction

$$
P(X\ge25)\approx P(Y>24.5).
$$

Then

$$
z=\frac{24.5-20}{\sqrt{20}}=1.01.
$$

Thus

$$
P(X\ge25)\approx P(Z>1.01)=0.157.
$$

## Problem 14

For $X\sim B(400,0.01)$,

$$
n=400>50,
\qquad
np=4<5.
$$

Use the Poisson approximation

$$
X\approx \operatorname{Po}(4).
$$

Hence

$$
P(X=0)\approx e^{-4}=0.0183.
$$

## Problem 15

For $B(20,0.1)$,

$$
np=2,
\qquad
nq=18.
$$

The normal approximation to a binomial distribution needs both $np>5$ and
$nq>5$. Since $np=2$, the CAIE condition is not satisfied. An exact binomial
calculation is safest for this model. A Poisson approximation is also not
clearly justified by the CAIE rule of thumb because $n$ is not greater than
$50$.

## Problem 16

If $X\sim N(30,9)$ and $Y=2X+5$, then

$$
E(Y)=2(30)+5=65.
$$

Also

$$
\operatorname{Var}(Y)=2^2(9)=36.
$$

So

$$
Y\sim N(65,36).
$$

Therefore

$$
P(Y<70)=P\left(Z<\frac{70-65}{6}\right)
=P(Z<0.833)=0.798.
$$

## Problem 17

For $T=X+2Y$,

$$
E(T)=E(X)+2E(Y)=10+2(6)=22.
$$

Since $X$ and $Y$ are independent,

$$
\operatorname{Var}(T)=\operatorname{Var}(X)+2^2\operatorname{Var}(Y)
=4+4(9)=40.
$$

A linear combination of independent normal variables is normal, so

$$
T\sim N(22,40).
$$

Thus

$$
P(T>30)=P\left(Z>\frac{30-22}{\sqrt{40}}\right)
=P(Z>1.26)=0.103.
$$

## Problem 18

The sum of independent Poisson variables is Poisson:

$$
X+Y\sim \operatorname{Po}(3+4)=\operatorname{Po}(7).
$$

Therefore

$$
P(X+Y=5)=\frac{e^{-7}7^5}{5!}=0.128.
$$

## Problem 19

Expectation is linear:

$$
E(3X-2Y)=3E(X)-2E(Y)=3(2)-2(5)=-4.
$$

For independent random variables, variances add after squaring coefficients:

$$
\operatorname{Var}(3X-2Y)=3^2\operatorname{Var}(X)+(-2)^2\operatorname{Var}(Y)
=9(2)+4(5)=38.
$$

$3X-2Y$ is not Poisson. It can take negative values, and the syllabus Poisson
sum result applies to $X+Y$, not to arbitrary linear combinations.

## Problem 20

For $W=3X-Y$,

$$
E(W)=3E(X)-E(Y)=3(12)-5=31.
$$

Since $X$ and $Y$ are independent,

$$
\operatorname{Var}(W)=3^2\operatorname{Var}(X)+(-1)^2\operatorname{Var}(Y)
=9(4)+1=37.
$$

So

$$
W\sim N(31,37).
$$

Therefore

$$
P(W>35)=P\left(Z>\frac{35-31}{\sqrt{37}}\right)
=P(Z>0.658)=0.255.
$$
