---
title: Chi-Squared, Non-Parametric Tests and PGF Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Chi-Squared, Non-Parametric Tests and PGF](00%20Overview.md)"
status: active
tags:
  - mathematics/statistics
  - worked-examples
---

# Chi-Squared, Non-Parametric Tests and PGF Worked Examples

These examples model the 9231 route through chi-squared tests,
non-parametric tests, and probability generating functions.

## Source Route

- CAIE Further Mathematics 9231 section 4.3: fitting theoretical distributions,
  chi-squared goodness-of-fit tests, chi-squared tests for independence,
  expected frequencies, and degrees of freedom.
- CAIE Further Mathematics 9231 section 4.4: sign tests, Wilcoxon signed-rank
  tests, matched-pairs signed-rank tests, and Wilcoxon rank-sum tests.
- CAIE Further Mathematics 9231 section 4.5: PGFs for discrete uniform,
  binomial, geometric and Poisson distributions, moments from PGFs, and sums
  of independent random variables.

## Example 1: Chi-Squared Goodness of Fit

**Prompt.** A die is thrown $100$ times with observed frequencies

| Face | 1 | 2 | 3 | 4 | 5 | 6 |
|---:|---:|---:|---:|---:|---:|---:|
| Observed | 18 | 16 | 20 | 14 | 22 | 10 |

Test at the $5\%$ level whether the die is fair.

**Solution.**

The hypotheses are

$$
H_0:\text{the die is fair},
\qquad
H_1:\text{the die is not fair}.
$$

If the die is fair, each expected frequency is

$$
\frac{100}{6}=16.67.
$$

All expected frequencies are at least $5$, so the chi-squared approximation is
appropriate. The statistic is

$$
\chi^2=\sum \frac{(O-E)^2}{E}=5.60.
$$

There are $6$ classes and no parameter has been estimated, so

$$
\nu=6-1=5.
$$

At the $5\%$ level, the critical value is

$$
\chi^2_{0.95,5}=11.07.
$$

Since $5.60<11.07$, do not reject $H_0$.

**Conclusion.** There is not enough evidence at the $5\%$ level that the die
is unfair.

## Example 2: Chi-Squared Test for Independence

**Prompt.** The table shows preferences for three options in two groups.

|  | Option A | Option B | Option C | Total |
|---|---:|---:|---:|---:|
| Group 1 | 30 | 20 | 10 | 60 |
| Group 2 | 20 | 30 | 40 | 90 |
| Total | 50 | 50 | 50 | 150 |

Test at the $5\%$ level whether group and option are independent.

**Solution.**

The hypotheses are

$$
H_0:\text{group and option are independent},
\qquad
H_1:\text{group and option are not independent}.
$$

Expected frequencies are

$$
E=\frac{\text{row total}\times \text{column total}}{\text{grand total}}.
$$

For Group 1 and Option A,

$$
E=\frac{60\times50}{150}=20.
$$

The expected frequencies are $20,20,20$ in the first row and $30,30,30$ in the
second row. The statistic is

$$
\chi^2=16.67.
$$

For a $2$ by $3$ table,

$$
\nu=(2-1)(3-1)=2.
$$

At the $5\%$ level,

$$
\chi^2_{0.95,2}=5.991.
$$

Since $16.67>5.991$, reject $H_0$.

**Conclusion.** There is evidence at the $5\%$ level that group and option are
not independent.

## Example 3: Single-Sample Sign Test

**Prompt.** The values

$$
55,\quad 52,\quad 61,\quad 60,\quad 57,\quad 49,\quad 53,\quad 58
$$

are a sample from a population with unknown distribution. Test at the $5\%$
level whether the population median is greater than $50$.

**Solution.**

The hypotheses are

$$
H_0:m=50,
\qquad
H_1:m>50.
$$

Compare each observation with $50$. There are $7$ observations above $50$ and
$1$ below $50$.

Under $H_0$, the number $S$ of observations above $50$ has distribution

$$
S\sim B\left(8,\frac12\right).
$$

The p-value is

$$
P(S\ge7)=\frac{\binom87+\binom88}{2^8}
=\frac{9}{256}
=0.0352.
$$

Since $0.0352<0.05$, reject $H_0$.

**Conclusion.** There is evidence at the $5\%$ level that the population median
is greater than $50$.

## Example 4: Wilcoxon Matched-Pairs Signed-Rank Test

**Prompt.** Six paired differences, after minus before, are

$$
4,\quad 5,\quad 2,\quad 6,\quad 3,\quad -1.
$$

Use a Wilcoxon matched-pairs signed-rank test at the $5\%$ level to test whether the median
difference is positive. Assume the differences come from a symmetric
distribution and there are no zero differences or tied absolute differences.

**Solution.**

Rank the absolute differences:

| Difference | $4$ | $5$ | $2$ | $6$ | $3$ | $-1$ |
|---:|---:|---:|---:|---:|---:|---:|
| Absolute rank | 4 | 5 | 2 | 6 | 3 | 1 |

The positive rank sum is

$$
W_+=4+5+2+6+3=20.
$$

The negative rank sum is

$$
W_-=1.
$$

For a one-tailed test in the positive direction, use large $W_+$. Under the
null hypothesis, all sign patterns are equally likely. There are $2^6=64$
patterns, and only $2$ have $W_+\ge20$. Therefore

$$
P(W_+\ge20)=\frac{2}{64}=0.03125.
$$

Since $0.03125<0.05$, reject $H_0$.

**Conclusion.** There is evidence that the median difference is positive.

## Example 5: Constructing a PGF and Finding Moments

**Prompt.** A random variable has distribution

| $x$ | 0 | 1 | 2 |
|---:|---:|---:|---:|
| $P(X=x)$ | 0.2 | 0.5 | 0.3 |

Find its PGF, $E(X)$, and $\operatorname{Var}(X)$.

**Solution.**

The PGF is

$$
G_X(t)=0.2+0.5t+0.3t^2.
$$

Differentiate:

$$
G_X'(t)=0.5+0.6t,
\qquad
G_X''(t)=0.6.
$$

Then

$$
E(X)=G_X'(1)=1.1.
$$

For variance,

$$
\operatorname{Var}(X)=G_X''(1)+G_X'(1)-[G_X'(1)]^2.
$$

So

$$
\operatorname{Var}(X)=0.6+1.1-(1.1)^2=0.49.
$$

**Check.** $G_X''(1)$ is $E[X(X-1)]$, not $E(X^2)$.

## Example 6: PGF of a Sum of Independent Poisson Variables

**Prompt.** Independent random variables $X$ and $Y$ have

$$
X\sim \operatorname{Po}(2),
\qquad
Y\sim \operatorname{Po}(3).
$$

Use PGFs to find the distribution of $X+Y$ and $P(X+Y=4)$.

**Solution.**

The PGFs are

$$
G_X(t)=e^{2(t-1)},
\qquad
G_Y(t)=e^{3(t-1)}.
$$

For independent variables,

$$
G_{X+Y}(t)=G_X(t)G_Y(t)
=e^{2(t-1)}e^{3(t-1)}
=e^{5(t-1)}.
$$

This is the PGF of

$$
X+Y\sim \operatorname{Po}(5).
$$

Therefore

$$
P(X+Y=4)=\frac{e^{-5}5^4}{4!}=0.175.
$$

**Check.** PGFs multiply for sums only when the variables are independent.

## Example 7: Binomial PGF

**Prompt.** Let $X\sim B(4,0.3)$. Use its PGF to find $P(X=2)$, $E(X)$, and
$\operatorname{Var}(X)$.

**Solution.**

The binomial PGF is

$$
G_X(t)=(0.7+0.3t)^4.
$$

The coefficient of $t^2$ is

$$
\binom42(0.3)^2(0.7)^2=0.2646.
$$

So

$$
P(X=2)=0.2646.
$$

For a binomial distribution,

$$
E(X)=np=4(0.3)=1.2,
$$

and

$$
\operatorname{Var}(X)=np(1-p)=4(0.3)(0.7)=0.84.
$$

These same values can be obtained from $G_X'(1)$ and $G_X''(1)$.

## Example 8: Wilcoxon Rank-Sum Test

**Prompt.** Two independent samples are

$$
A:\ 8,\ 9,\ 11,
\qquad
B:\ 2,\ 4,\ 5.
$$

Use a one-tailed Wilcoxon rank-sum test at the $5\%$ level to test whether
population $A$ tends to have larger values than population $B$.

**Solution.**

Rank all six observations together:

| Value | 2 | 4 | 5 | 8 | 9 | 11 |
|---:|---:|---:|---:|---:|---:|---:|
| Rank | 1 | 2 | 3 | 4 | 5 | 6 |

The rank sum for sample $A$ is

$$
R_A=4+5+6=15.
$$

There are $\binom63=20$ possible sets of ranks for sample $A$ under the null
hypothesis. Only the set $\{4,5,6\}$ gives $R_A\ge15$, so

$$
P(R_A\ge15)=\frac{1}{20}=0.05.
$$

At the $5\%$ level, reject $H_0$.

**Conclusion.** There is evidence that population $A$ tends to have larger
values than population $B$.
