---
title: Discrete Random Variables Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/03 Discrete Random Variables/00 Overview|Discrete Random Variables]]"
status: draft
tags:
  - mathematics/statistics
  - lecture-notes
---

# Discrete Random Variables Lecture Notes

A random variable turns outcomes into numbers. A discrete random variable can take separate values, so its distribution is described by listing possible values and their probabilities.

## Source Route

- 9709 5.4 Discrete random variables
- 9709 6.2 Linear combinations of random variables
- Coursebook route: 9709 Probability and Statistics 1 chapters on discrete random variables and common discrete distributions.

## Visual Guide

![[assets/generated/mathematics/discrete-random-variables.svg]]

Figure: use the guide to compare probability mass at individual values with cumulative probability.

## 1. Probability Distributions

A probability distribution table for a discrete random variable $X$ lists values $x$ and probabilities $P(X=x)$. It must satisfy

$$
0\le P(X=x)\le 1
$$

for each value, and

$$
\sum P(X=x)=1.
$$

The distinction between point probability and cumulative probability is essential:

$$
P(X=x)
$$

means exactly one value, while

$$
P(X\le x)
$$

adds all probabilities up to that value.

## 2. Expectation and Variance

Expectation is the long-run average value:

$$
E(X)=\sum xP(X=x).
$$

It does not need to be a value that $X$ can actually take. A fair die has expectation $3.5$, even though no face is labelled $3.5$.

Variance measures spread around the expectation:

$$
\operatorname{Var}(X)=E(X^2)-[E(X)]^2,
$$

where

$$
E(X^2)=\sum x^2P(X=x).
$$

The standard deviation is

$$
\sqrt{\operatorname{Var}(X)}.
$$

Always attach interpretation: expectation is the average over many repetitions, and standard deviation gives a typical scale of variation.

## 3. Linear Transformations and Combinations

For a linear transformation,

$$
E(aX+b)=aE(X)+b,
$$

and

$$
\operatorname{Var}(aX+b)=a^2\operatorname{Var}(X).
$$

Adding a constant shifts the centre but does not change spread. Multiplying by $a$ scales deviations by $a$, so variance scales by $a^2$.

For two random variables,

$$
E(aX+bY)=aE(X)+bE(Y).
$$

If $X$ and $Y$ are independent, then

$$
\operatorname{Var}(aX+bY)=a^2\operatorname{Var}(X)+b^2\operatorname{Var}(Y).
$$

The independence condition is needed for the variance result.

## 4. Binomial Distribution

A binomial model is used for the number of successes in a fixed number of independent trials, where each trial has the same success probability $p$. If $X\sim B(n,p)$, then

$$
P(X=r)=\binom nr p^r(1-p)^{n-r},
\qquad r=0,1,\ldots,n.
$$

Its expectation and variance are

$$
E(X)=np,\qquad \operatorname{Var}(X)=np(1-p).
$$

Before using the binomial distribution, check the assumptions: fixed number of trials, two outcomes per trial, constant success probability, and independence.

## 5. Geometric Distribution

In the CAIE notation, $X\sim \operatorname{Geo}(p)$ means $X$ is the trial number on which the first success occurs. The possible values are $1,2,3,\ldots$, and

$$
P(X=r)=p(1-p)^{r-1}.
$$

The expectation is

$$
E(X)=\frac1p.
$$

Use this model when trials repeat independently until the first success and the success probability remains constant.

## 6. Cumulative Probabilities

For a discrete variable, endpoints matter. For example,

$$
P(X\ge 3)=1-P(X\le 2),
$$

not $1-P(X<2)$. Write out the values when in doubt.

For binomial and geometric distributions, cumulative probabilities are often sums of point probabilities:

$$
P(X\le r)=\sum_{k}P(X=k),
$$

over the allowed values $k\le r$.

## Worked-Thinking Routine

1. Define the random variable in words.
2. List its possible values.
3. Build or identify its probability distribution.
4. Check that probabilities sum to $1$.
5. Compute $E(X)$, $E(X^2)$, and $\operatorname{Var}(X)$ if required.
6. For a standard model, check the modelling assumptions before using formulae.
7. Interpret expectation, variance, and probabilities in context.

## Common Mistakes

- Using a distribution without checking its assumptions.
- Confusing $P(X=x)$ with $P(X\le x)$.
- Forgetting that geometric values begin at $1$ in the CAIE convention.
- Treating expectation as a guaranteed outcome.
- Writing $\operatorname{Var}(aX+b)=a\operatorname{Var}(X)+b$.
- Using the variance formula for a sum without independence.

## Quick Self-Check

- Can you define the random variable before calculating?
- Can you check whether a probability distribution is valid?
- Can you compute expectation and variance from a table?
- Can you distinguish binomial and geometric modelling assumptions?
- Can you handle strict and non-strict inequalities for a discrete variable?

## Connections

- [[20 Mathematics/03 Probability and Statistics/02 Counting and Probability/00 Overview|Counting and Probability]]
- [[20 Mathematics/03 Probability and Statistics/04 Normal and Poisson Distributions/00 Overview|Normal and Poisson Distributions]]
- [[20 Mathematics/03 Probability and Statistics/07 Chi Squared Nonparametric and PGF/00 Overview|Chi-Squared, Non-Parametric Tests and PGF]]

## Study Sequence

1. Build probability tables from simple experiments.
2. Practise expectation and variance calculations.
3. Study linear transformations and independent sums.
4. Learn binomial modelling assumptions.
5. Learn geometric modelling assumptions.
6. Finish with cumulative probability and endpoint checks.
