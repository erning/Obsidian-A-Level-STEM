---
title: Chi-Squared, Non-Parametric Tests and PGF Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/07 Chi Squared Nonparametric and PGF/00 Overview|Chi-Squared, Non-Parametric Tests and PGF]]"
status: active
tags:
  - mathematics/statistics
  - lecture-notes
---

# Chi-Squared, Non-Parametric Tests and PGF Lecture Notes

This topic has three different tools. Chi-squared tests compare observed and expected frequencies. Non-parametric tests use signs or ranks when strong distributional assumptions are not appropriate. Probability generating functions encode a discrete distribution in an algebraic form.

## Source Route

- 9231 4.3 Chi-squared tests
- 9231 4.4 Non-parametric tests
- 9231 4.5 Probability generating functions
- Coursebook route: 9231 Further Probability and Statistics content on chi-squared tests, non-parametric tests, and probability generating functions.

## Visual Guide

![[assets/generated/mathematics/chi-squared-non-parametric-tests-and-pgf.svg]]

Figure: use the guide to connect observed-expected differences with the right-tail chi-squared decision.

## 1. Chi-Squared Tests

The chi-squared statistic compares observed frequencies $O$ with expected frequencies $E$:

$$
\chi^2=\sum \frac{(O-E)^2}{E}.
$$

Small differences between $O$ and $E$ give a small statistic. Large differences give a large statistic, so chi-squared tests are right-tailed tests.

The expected frequencies should be large enough for the approximation to be reliable. The CAIE rule is to combine classes, rows, or columns where appropriate so that each expected frequency is at least $5$.

## 2. Goodness of Fit and Independence

A goodness-of-fit test asks whether observed frequencies are consistent with a specified theoretical distribution. The hypotheses usually have the form:

$$
H_0:\text{the data follow the stated distribution}.
$$

The degrees of freedom are usually

$$
\text{number of classes}-1-\text{number of estimated parameters}.
$$

A test for independence uses a contingency table. It asks whether two categorical variables behave independently. Expected frequencies are calculated by

$$
E=\frac{\text{row total}\times \text{column total}}{\text{grand total}}.
$$

For an $r$ by $c$ contingency table, the degrees of freedom are

$$
(r-1)(c-1).
$$

Yates' correction is not required in this syllabus.

## 3. Non-Parametric Tests

Non-parametric tests are useful when the population cannot reasonably be assumed to follow a normal distribution, or when the data are more naturally signs, ranks, or ordered comparisons.

The sign test uses only whether observations are above or below a hypothesised median, or whether paired differences are positive or negative. It is simple and robust, but it discards magnitude information.

The Wilcoxon signed-rank test uses ranks of absolute differences and their signs. It retains more information than the sign test, but it assumes a symmetric distribution for validity.

The Wilcoxon rank-sum test compares two independent samples using the ranks of the combined data. It is used to test for identity of populations when a parametric two-sample normal model is not suitable.

The syllabus avoids tied ranks and zero-difference pairs in these tests, but the concept is worth understanding: the tests replace raw values by signs or ranks, then ask whether those signs or ranks are unusually one-sided.

## 4. Probability Generating Functions

For a discrete random variable $X$ taking non-negative integer values, the probability generating function is

$$
G_X(t)=E(t^X)=\sum_{x=0}^{\infty}P(X=x)t^x.
$$

The coefficient of $t^x$ is $P(X=x)$. This means a PGF stores the whole probability distribution.

Common examples are:

- if $X\sim B(n,p)$, then $G_X(t)=(1-p+pt)^n$;
- if $X\sim \operatorname{Geo}(p)$ with first success on trial $1,2,\ldots$, then

$$
G_X(t)=\frac{pt}{1-(1-p)t};
$$

- if $X\sim \operatorname{Po}(\lambda)$, then

$$
G_X(t)=e^{\lambda(t-1)}.
$$

## 5. Mean, Variance, and Sums from PGFs

The mean and variance can be found from derivatives:

$$
E(X)=G_X'(1),
$$

and

$$
\operatorname{Var}(X)=G_X''(1)+G_X'(1)-[G_X'(1)]^2.
$$

This works because $G_X''(1)$ gives $E[X(X-1)]$, not directly $E(X^2)$.

If $X$ and $Y$ are independent, then

$$
G_{X+Y}(t)=G_X(t)G_Y(t).
$$

This turns sums of independent discrete random variables into multiplication of functions.

## Worked-Thinking Routine

1. Identify the data type: frequencies, ranks, signs, or a discrete distribution.
2. For chi-squared tests, calculate expected frequencies and check they are at least $5$ after any combining.
3. Choose the correct degrees of freedom.
4. For non-parametric tests, identify whether the data are single-sample, paired, or two independent samples.
5. For PGFs, write the distribution in powers of $t$ and read coefficients carefully.
6. Use derivatives at $t=1$ for mean and variance.
7. For sums, check independence before multiplying PGFs.

## Common Mistakes

- Using chi-squared tests with expected frequencies below $5$.
- Forgetting to subtract estimated parameters in a goodness-of-fit degree-of-freedom calculation.
- Using the independence-test degrees of freedom for a goodness-of-fit test.
- Treating non-parametric tests as assumption-free rather than assumption-light.
- Using Wilcoxon signed-rank tests without the symmetry condition.
- Reading PGF coefficients from the wrong power of $t$.
- Treating $G_X''(1)$ as $E(X^2)$.
- Multiplying PGFs for variables that are not independent.

## Quick Self-Check

- Can you distinguish goodness-of-fit and independence tests?
- Can you calculate expected frequencies and degrees of freedom?
- Can you choose between sign, signed-rank, paired, and rank-sum tests?
- Can you construct a PGF from a discrete distribution?
- Can you find mean and variance from a PGF?
- Can you use PGFs for sums of independent variables?

## Connections

- [[20 Mathematics/03 Probability and Statistics/03 Discrete Random Variables/00 Overview|Discrete Random Variables]]
- [[20 Mathematics/03 Probability and Statistics/06 Sampling Estimation and Hypothesis Tests/00 Overview|Sampling, Estimation and Hypothesis Tests]]
- [[20 Mathematics/01 Pure Mathematics/04 Sequences Series and Binomial Expansions/00 Overview|Sequences, Series and Binomial Expansions]]

## Study Sequence

1. Practise chi-squared goodness-of-fit tests.
2. Practise chi-squared independence tests.
3. Learn when non-parametric tests are useful.
4. Compare sign, Wilcoxon signed-rank, matched-pairs signed-rank, and rank-sum tests.
5. Build PGFs for common distributions.
6. Use PGFs for moments and sums.
