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

This topic has three different tools. Chi-squared tests compare observed and expected frequencies in frequency tables. Non-parametric tests replace raw measurements by signs or ranks when a normal model is not appropriate. Probability generating functions encode a non-negative integer distribution in a function, so coefficients, moments, and sums can be handled algebraically.

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

The expected frequencies must be large enough for the chi-squared approximation to be reliable. The CAIE rule is to combine classes, rows, or columns where appropriate so that every expected frequency used in the statistic is at least $5$.

The test routine is:

1. State $H_0$ and $H_1$ in words.
2. Calculate expected frequencies under $H_0$.
3. Combine classes, rows, or columns if needed, then recalculate the relevant expected frequencies and degrees of freedom.
4. Calculate $\chi^2=\sum (O-E)^2/E$.
5. Compare with the right-tail critical value, or use a right-tail $p$-value.
6. Conclude in the context of the data.

Because all terms are squared, a chi-squared test does not tell you direction by itself. To describe where the evidence comes from, look back at the largest contributions $(O-E)^2/E$ and whether $O$ is above or below $E$ in those cells.

## 2. Goodness-of-Fit Tests

A goodness-of-fit test asks whether observed frequencies are consistent with a specified theoretical distribution. The hypotheses usually have the form:

$$
H_0:\text{the data follow the stated distribution}.
$$

If the distribution is fully specified, expected frequencies are found by

$$
E_i=Np_i,
$$

where $N$ is the total observed frequency and $p_i$ is the probability of class $i$ under $H_0$.

If a parameter is not given and must be estimated from the same data, that estimation costs a degree of freedom. For a goodness-of-fit test with $k$ classes after any combining and $q$ parameters estimated from the data,

$$
\nu=k-1-q.
$$

For example, fitting a Poisson distribution by estimating $\lambda$ from the sample mean uses $q=1$. If the distribution and all its parameters are stated in the hypothesis, then $q=0$.

Combining should be done before the final statistic and degrees of freedom are fixed. Combine adjacent or natural classes, not arbitrary cells chosen after seeing which observed values are inconvenient. Once classes are combined, both observed and expected frequencies must be combined in the same way.

## 3. Tests for Independence in Contingency Tables

A test for independence uses a contingency table. It asks whether two categorical variables behave independently. Under independence,

$$
E=\frac{\text{row total}\times \text{column total}}{\text{grand total}}.
$$

The expected frequencies are calculated from the row and column totals of the table being tested. For an $r$ by $c$ table,

$$
\nu=(r-1)(c-1).
$$

If rows or columns have to be combined to make expected frequencies at least $5$, use the new number of rows and columns in the degrees-of-freedom formula. Yates' correction is not required in this syllabus.

For an independence test, typical hypotheses are:

$$
H_0:\text{the two categorical variables are independent},
$$

$$
H_1:\text{the two categorical variables are not independent}.
$$

This test uses frequency counts, not percentages. Percentages can help interpret the result afterwards, but the test statistic is built from observed and expected frequencies.

## 4. Non-Parametric Tests

Non-parametric tests are useful when the population cannot reasonably be assumed to follow a normal distribution, or when the data are more naturally signs, ranks, or ordered comparisons.

They are not assumption-free. The sign test uses very little structure, but Wilcoxon tests use rank information and, in this syllabus, require symmetry conditions. Questions avoid tied ranks, observations equal to the tested median, and zero-difference pairs.

### Sign Tests

The sign test uses only whether observations are above or below a hypothesised median, or whether paired differences are positive or negative. It is simple and robust, but it discards magnitude information.

For a single-sample sign test of a population median $m_0$, count how many observations are above $m_0$ and how many are below $m_0$. Under $H_0$, each non-equal observation is equally likely to be above or below $m_0$, so the number of plus signs has distribution

$$
B(n,0.5).
$$

For paired data, first form the differences and count positive and negative differences. A one-sided alternative decides which tail of the binomial distribution is relevant. A two-sided test doubles the smaller tail probability when using an exact binomial calculation.

### Wilcoxon Signed-Rank and Matched-Pairs Tests

The Wilcoxon signed-rank test uses ranks of absolute deviations and their signs. It retains more information than the sign test, but it assumes a symmetric distribution for validity.

For a single-sample test of a median $m_0$, calculate

$$
d_i=x_i-m_0.
$$

Rank the absolute values $|d_i|$, attach the original signs, and add the ranks corresponding to positive differences. The formula-book notation often calls this sum $P$. Under $H_0$, positive and negative ranks should be balanced. For a paired-sample matched-pairs test, use the paired differences in exactly the same way.

For large samples, a normal approximation may be used. If $P$ is the sum of positive ranks for a sample of size $n$, then under $H_0$,

$$
E(P)=\frac{n(n+1)}{4},\qquad
\operatorname{Var}(P)=\frac{n(n+1)(2n+1)}{24}.
$$

Use a continuity correction when applying the normal approximation to a rank statistic.

### Wilcoxon Rank-Sum Test

The Wilcoxon rank-sum test compares two independent samples using the ranks of the combined data. It is used to test for identity of populations when a parametric two-sample normal model is not suitable.

Combine the two samples, rank all observations together, and add the ranks belonging to the smaller sample. If the sample sizes are $m$ and $n$, with $m\le n$, and $R_m$ is the rank sum for the sample of size $m$, then under $H_0$,

$$
E(R_m)=\frac{m(m+n+1)}{2},\qquad
\operatorname{Var}(R_m)=\frac{mn(m+n+1)}{12}.
$$

If the alternative says the first population tends to have larger values, the rank sum for that sample should tend to be large. If it tends to have smaller values, the rank sum should tend to be small. Always connect the tail direction to the sample whose rank sum is being used.

## 5. Probability Generating Functions

For a discrete random variable $X$ taking non-negative integer values, the probability generating function, or PGF, is

$$
G_X(t)=E(t^X)=\sum_{x=0}^{\infty}P(X=x)t^x.
$$

The coefficient of $t^x$ is $P(X=x)$. This means a PGF stores the whole probability distribution. Also,

$$
G_X(1)=1,
$$

provided the probabilities sum to $1$.

Common examples are:

- if $X$ is discrete uniform on $1,2,\ldots,n$, then

$$
G_X(t)=\frac{t+t^2+\cdots+t^n}{n}
=\frac{t(1-t^n)}{n(1-t)};
$$

- if $X\sim B(n,p)$, then $G_X(t)=(1-p+pt)^n$;
- if $X\sim \operatorname{Geo}(p)$ with first success on trial $1,2,\ldots$, then

$$
G_X(t)=\frac{pt}{1-(1-p)t};
$$

- if $X\sim \operatorname{Po}(\lambda)$, then

$$
G_X(t)=e^{\lambda(t-1)}.
$$

If a random variable starts at $0$, the constant term gives $P(X=0)$. If it starts at $1$, there is no constant term. This is a common way to notice whether a geometric distribution is being counted from $0$ or from $1$.

## 6. Mean, Variance, and Sums from PGFs

The mean and variance can be found from derivatives:

$$
E(X)=G_X'(1),
$$

and

$$
\operatorname{Var}(X)=G_X''(1)+G_X'(1)-[G_X'(1)]^2.
$$

This works because

$$
G_X''(1)=E[X(X-1)],
$$

not directly $E(X^2)$. Since

$$
X^2=X(X-1)+X,
$$

we have

$$
E(X^2)=G_X''(1)+G_X'(1).
$$

If $X$ and $Y$ are independent, then

$$
G_{X+Y}(t)=G_X(t)G_Y(t).
$$

This turns sums of independent discrete random variables into multiplication of functions.

Two useful consequences are:

- independent binomial variables with the same success probability add by adding their numbers of trials;
- independent Poisson variables add by adding their means.

For example, if $X\sim \operatorname{Po}(\lambda)$ and $Y\sim \operatorname{Po}(\mu)$ are independent, then

$$
G_{X+Y}(t)=e^{\lambda(t-1)}e^{\mu(t-1)}
=e^{(\lambda+\mu)(t-1)},
$$

so $X+Y\sim \operatorname{Po}(\lambda+\mu)$.

## Worked-Thinking Routine

1. Identify the data type: frequencies, ranks, signs, or a discrete distribution.
2. For chi-squared tests, calculate expected frequencies and check they are at least $5$ after any combining.
3. Choose degrees of freedom after accounting for combined classes or estimated parameters.
4. For non-parametric tests, identify whether the data are single-sample, paired, or two independent samples.
5. For Wilcoxon tests, rank the correct quantities and connect the rank sum to the tail direction.
6. For PGFs, write the distribution in powers of $t$ and read coefficients carefully.
7. Use derivatives at $t=1$ for mean and variance.
8. For sums, check independence before multiplying PGFs.

## Common Mistakes

- Using chi-squared tests with expected frequencies below $5$.
- Forgetting to subtract estimated parameters in a goodness-of-fit degree-of-freedom calculation.
- Using the independence-test degrees of freedom for a goodness-of-fit test.
- Combining chi-squared classes after looking for the most favourable result, instead of combining natural classes before the final test.
- Treating non-parametric tests as assumption-free rather than assumption-light.
- Using Wilcoxon signed-rank tests without the symmetry condition.
- Mixing up paired signed-rank data with independent rank-sum data.
- Reading PGF coefficients from the wrong power of $t$.
- Treating $G_X''(1)$ as $E(X^2)$.
- Multiplying PGFs for variables that are not independent.

## Quick Self-Check

- Can you distinguish goodness-of-fit and independence tests?
- Can you calculate expected frequencies, combine classes correctly, and choose degrees of freedom?
- Can you choose between sign, signed-rank, paired, and rank-sum tests?
- Can you state the Wilcoxon rank-sum and signed-rank routines without confusing the samples?
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
