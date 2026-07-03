---
title: Normal and Poisson Distributions Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/04 Normal and Poisson Distributions/00 Overview|Normal and Poisson Distributions]]"
status: draft
tags:
  - mathematics/statistics
  - lecture-notes
---

# Normal and Poisson Distributions Lecture Notes

The normal distribution models continuous variation around a centre. The Poisson distribution models counts of random events in a fixed interval. They are different kinds of distribution, but they meet through approximation and through linear combinations of random variables.

## Source Route

- 9709 5.5 The normal distribution
- 9709 6.1 The Poisson distribution
- 9709 6.2 Linear combinations of random variables
- Coursebook route: 9709 Probability and Statistics 1 normal distribution chapter; 9709 Probability and Statistics 2 Poisson and linear combinations chapters.

## Visual Guide

![[assets/generated/mathematics/normal-and-poisson-distributions.svg]]

Figure: use the guide to compare continuous normal area with discrete Poisson counts.

## 1. Normal Distribution

If

$$
X\sim N(\mu,\sigma^2),
$$

then $X$ is normally distributed with mean $\mu$ and variance $\sigma^2$. The standard deviation is $\sigma$, not $\sigma^2$.

The normal curve is continuous, bell-shaped, and symmetric about $\mu$. Probabilities are areas under the curve. Since the distribution is continuous,

$$
P(X=a)=0,
$$

so inequalities such as $<$ and $\le$ give the same probability.

## 2. Standardisation and Inverse Questions

The standard normal variable is

$$
Z=\frac{X-\mu}{\sigma},
\qquad Z\sim N(0,1).
$$

Standardisation turns a value of $X$ into a number of standard deviations from the mean. Sketch the curve first, mark the required area, then standardise the boundary value.

For an interval,

$$
P(a<X<b)=P\left(\frac{a-\mu}{\sigma}<Z<\frac{b-\mu}{\sigma}\right).
$$

Inverse probability questions run the process backwards. If a probability is given, first find the corresponding $z$ value, then solve

$$
z=\frac{x-\mu}{\sigma}
$$

for the unknown boundary, mean, or standard deviation.

## 3. Poisson Distribution

The Poisson distribution models counts of random events in a fixed interval of time, distance, area, or volume when events occur independently at an approximately constant average rate.

If

$$
X\sim \operatorname{Po}(\lambda),
$$

then

$$
P(X=r)=\frac{e^{-\lambda}\lambda^r}{r!},
\qquad r=0,1,2,\ldots.
$$

For a Poisson variable,

$$
E(X)=\operatorname{Var}(X)=\lambda.
$$

The parameter must match the interval. If the mean number of calls per hour is $6$, then the mean number in $30$ minutes is $3$, and the mean number in $2$ hours is $12$.

## 4. Linear Combinations

Linear transformations behave predictably:

$$
E(aX+b)=aE(X)+b,\qquad \operatorname{Var}(aX+b)=a^2\operatorname{Var}(X).
$$

If $X$ and $Y$ are independent, then

$$
E(aX+bY)=aE(X)+bE(Y),
$$

and

$$
\operatorname{Var}(aX+bY)=a^2\operatorname{Var}(X)+b^2\operatorname{Var}(Y).
$$

Distribution type may also be preserved:

- if $X$ is normal, then $aX+b$ is normal;
- if independent $X$ and $Y$ are normal, then $aX+bY$ is normal;
- if independent $X$ and $Y$ are Poisson, then $X+Y$ is Poisson with parameter equal to the sum of the parameters.

## 5. Approximations and Continuity Correction

Use the normal approximation to $B(n,p)$ when $n$ is large enough that both

$$
np>5,\qquad nq>5,
$$

where $q=1-p$. Then

$$
B(n,p)\approx N(np,npq).
$$

Use the Poisson approximation to $B(n,p)$ when $n$ is large and $p$ is small, with the syllabus rule of thumb

$$
n>50,\qquad np<5.
$$

Then

$$
B(n,p)\approx \operatorname{Po}(np).
$$

Use the normal approximation to $\operatorname{Po}(\lambda)$ when $\lambda$ is large, approximately $\lambda>15$:

$$
\operatorname{Po}(\lambda)\approx N(\lambda,\lambda).
$$

Whenever a discrete distribution is approximated by a continuous normal distribution, use a continuity correction. For example,

$$
P(X\le 10)\approx P(Y<10.5),
$$

and

$$
P(4\le X\le 10)\approx P(3.5<Y<10.5).
$$

## Worked-Thinking Routine

1. Identify whether the variable is continuous measurement or a count.
2. State the distribution and parameters, including units for rates.
3. Sketch the probability region.
4. For normal questions, standardise boundaries.
5. For Poisson questions, check the interval and adjust $\lambda$ if needed.
6. For approximations, state the condition and apply continuity correction.
7. Interpret the probability in the original context.

## Common Mistakes

- Treating $\sigma^2$ as the standard deviation in $N(\mu,\sigma^2)$.
- Standardising with variance instead of standard deviation.
- Forgetting to scale $\lambda$ when the interval changes.
- Using Poisson for counts that are not plausibly independent or rate-stable.
- Forgetting continuity correction when approximating a discrete distribution by a normal distribution.
- Adding variances for random variables that are not independent.

## Quick Self-Check

- Can you standardise $X$ to $Z$ and reverse the process for inverse questions?
- Can you read normal probabilities as areas?
- Can you decide whether a count is plausibly Poisson?
- Can you adjust a Poisson parameter to a new interval?
- Can you choose the correct approximation and continuity correction?

## Connections

- [[20 Mathematics/03 Probability and Statistics/03 Discrete Random Variables/00 Overview|Discrete Random Variables]]
- [[20 Mathematics/03 Probability and Statistics/06 Sampling Estimation and Hypothesis Tests/00 Overview|Sampling, Estimation and Hypothesis Tests]]

## Study Sequence

1. Practise normal sketches and standardisation.
2. Work inverse normal questions.
3. Learn Poisson probabilities and parameter scaling.
4. Study linear combinations of normal and Poisson variables.
5. Practise binomial, Poisson, and normal approximations with continuity correction.
