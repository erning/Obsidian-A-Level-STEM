---
title: Normal and Poisson Distributions Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Normal and Poisson Distributions](00%20Overview.md)"
status: active
tags:
  - mathematics/statistics
  - worked-examples
---

# Normal and Poisson Distributions Worked Examples

These examples model the CAIE 9709 route through normal probabilities,
inverse normal questions, Poisson probabilities, approximations, continuity
correction, and linear combinations of random variables.

## Source Route

- CAIE Mathematics 9709 section 5.5: normal distribution as a model for a
  continuous random variable, normal tables, standardisation, inverse normal
  questions, and the normal approximation to a binomial distribution.
- CAIE Mathematics 9709 section 6.1: Poisson probabilities, the mean and
  variance of a Poisson variable, Poisson modelling, Poisson approximation to a
  binomial distribution, and normal approximation to a Poisson distribution.
- CAIE Mathematics 9709 section 6.2: expectation, variance, and distribution
  results for linear transformations and independent linear combinations.

## Example 1: Normal Standardisation

**Prompt.** Let $X\sim N(50,6^2)$. Find $P(44<X<60)$ and $P(X>62)$.

**Solution.**

Standardise with the standard deviation $6$, not the variance $36$:

$$
Z=\frac{X-50}{6}.
$$

For the interval,

$$
P(44<X<60)
=P\left(\frac{44-50}{6}<Z<\frac{60-50}{6}\right)
=P(-1<Z<1.67).
$$

Using normal tables or technology,

$$
P(-1<Z<1.67)=\Phi(1.67)-\Phi(-1)=0.794
$$

to 3 s.f. For the upper tail,

$$
P(X>62)=P\left(Z>\frac{62-50}{6}\right)
=P(Z>2)=0.0228.
$$

**Check.** The interval $44<X<60$ covers most of the centre of the curve, so a
probability near $0.8$ is reasonable. The value $62$ is two standard
deviations above the mean, so the upper tail should be small.

## Example 2: Inverse Normal Boundary

**Prompt.** A score $X$ is modelled by $X\sim N(72,8^2)$. Find the mark exceeded
by only $10\%$ of students. Also find the mark below which $5\%$ of students
score.

**Solution.**

If only $10\%$ exceed the mark, then $90\%$ are below it:

$$
P(X<x)=0.90.
$$

The corresponding standard normal value is

$$
z=1.282.
$$

So

$$
\frac{x-72}{8}=1.282,
\qquad
x=72+8(1.282)=82.3.
$$

For the lower $5\%$,

$$
P(X<y)=0.05,
\qquad z=-1.645.
$$

Hence

$$
\frac{y-72}{8}=-1.645,
\qquad
y=72+8(-1.645)=58.8.
$$

**Check.** The $90$th percentile lies above the mean, and the $5$th percentile
lies below the mean.

## Example 3: Finding Normal Parameters

**Prompt.** A measurement $X$ is normally distributed. Given

$$
P(X<35)=0.10,
\qquad
P(X<50)=0.90,
$$

find the mean $\mu$ and standard deviation $\sigma$.

**Solution.**

For a normal distribution, the $10$th and $90$th percentiles have standard
normal values approximately $-1.282$ and $1.282$:

$$
\frac{35-\mu}{\sigma}=-1.282,
\qquad
\frac{50-\mu}{\sigma}=1.282.
$$

Add the two equations:

$$
\frac{85-2\mu}{\sigma}=0,
$$

so

$$
\mu=42.5.
$$

Then

$$
\frac{50-42.5}{\sigma}=1.282,
\qquad
\sigma=\frac{7.5}{1.282}=5.85.
$$

**Check.** The mean is halfway between the symmetric $10$th and $90$th
percentiles.

## Example 4: Poisson Probabilities and Interval Scaling

**Prompt.** Calls arrive at a help desk at a mean rate of $3$ calls per
$20$ minutes. Model the number of calls by a Poisson distribution. Find the
probability of exactly $2$ calls in $20$ minutes, and the probability of at
least $1$ call in $10$ minutes.

**Solution.**

For $20$ minutes, use $\lambda=3$. If $X\sim \operatorname{Po}(3)$, then

$$
P(X=2)=\frac{e^{-3}3^2}{2!}=0.224
$$

to 3 s.f.

For $10$ minutes, halve the interval and halve the mean:

$$
\lambda=\frac32=1.5.
$$

If $Y\sim \operatorname{Po}(1.5)$, then

$$
P(Y\ge1)=1-P(Y=0)=1-e^{-1.5}=0.777.
$$

**Check.** A rate must be scaled to the interval being counted.

## Example 5: Poisson Cumulative and Tail Probabilities

**Prompt.** Let $X\sim \operatorname{Po}(4)$. Find $P(X\le2)$, $P(X\ge5)$,
$E(X)$, and $\operatorname{Var}(X)$.

**Solution.**

For the lower cumulative probability,

$$
P(X\le2)=P(X=0)+P(X=1)+P(X=2)
=e^{-4}\left(1+4+\frac{4^2}{2!}\right).
$$

Thus

$$
P(X\le2)=13e^{-4}=0.238.
$$

For the upper tail, use the complement:

$$
P(X\ge5)=1-P(X\le4).
$$

Now

$$
P(X\le4)
=e^{-4}\left(1+4+\frac{4^2}{2!}+\frac{4^3}{3!}
+\frac{4^4}{4!}\right),
$$

so

$$
P(X\ge5)=0.371.
$$

For a Poisson distribution,

$$
E(X)=\operatorname{Var}(X)=4.
$$

**Check.** The mean and variance are both equal to the Poisson parameter.

## Example 6: Poisson Approximation to a Binomial Distribution

**Prompt.** Let $X\sim B(100,0.03)$. Use a Poisson approximation to estimate
$P(X\le2)$.

**Solution.**

The syllabus condition is that $n$ is large and $p$ is small, with
$n>50$ and $np<5$ approximately. Here

$$
n=100,\qquad np=3,
$$

so use

$$
X\approx \operatorname{Po}(3).
$$

Then

$$
P(X\le2)\approx e^{-3}\left(1+3+\frac{3^2}{2!}\right)
=0.423.
$$

**Check.** The approximating Poisson mean is $np$, not $p$.

## Example 7: Normal Approximation to a Binomial Distribution

**Prompt.** Let $X\sim B(80,0.4)$. Use a normal approximation to estimate
$P(X\ge35)$.

**Solution.**

Check the condition:

$$
np=32>5,
\qquad
nq=80(0.6)=48>5.
$$

So

$$
X\approx Y,
\qquad
Y\sim N(32,19.2).
$$

Since $X$ is discrete and $Y$ is continuous, use a continuity correction:

$$
P(X\ge35)\approx P(Y>34.5).
$$

Standardise:

$$
z=\frac{34.5-32}{\sqrt{19.2}}=0.571.
$$

Therefore

$$
P(X\ge35)\approx P(Z>0.571)=0.284.
$$

**Check.** Without the $34.5$ boundary, the approximation would ignore half of
the discrete bar at $35$.

## Example 8: Linear Combinations of Normal and Poisson Variables

**Prompt.** Independent random variables $X$ and $Y$ have

$$
X\sim N(20,4),
\qquad
Y\sim N(10,9).
$$

Let $T=2X-Y$. Find the distribution of $T$ and estimate $P(T>35)$.
Separately, if $A\sim \operatorname{Po}(2.5)$ and
$B\sim \operatorname{Po}(4)$ are independent, find the distribution of
$A+B$ and $P(A+B=5)$.

**Solution.**

For the normal variables,

$$
E(T)=2E(X)-E(Y)=2(20)-10=30.
$$

Because $X$ and $Y$ are independent,

$$
\operatorname{Var}(T)=2^2\operatorname{Var}(X)+(-1)^2\operatorname{Var}(Y)
=4(4)+9=25.
$$

A linear combination of independent normal variables is normal, so

$$
T\sim N(30,25).
$$

Thus

$$
P(T>35)=P\left(Z>\frac{35-30}{5}\right)=P(Z>1)=0.159.
$$

For the Poisson variables, the sum of independent Poisson variables is Poisson:

$$
A+B\sim \operatorname{Po}(2.5+4)=\operatorname{Po}(6.5).
$$

Therefore

$$
P(A+B=5)=\frac{e^{-6.5}6.5^5}{5!}=0.145.
$$

**Check.** Variances add for independent variables even when the coefficient
is negative, because the coefficient is squared.
