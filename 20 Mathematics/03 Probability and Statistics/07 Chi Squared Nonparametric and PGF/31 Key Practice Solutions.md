---
title: Chi-Squared, Non-Parametric Tests and PGF Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/07 Chi Squared Nonparametric and PGF/00 Overview|Chi-Squared, Non-Parametric Tests and PGF]]"
status: active
tags:
  - mathematics/statistics
  - solutions
---

# Chi-Squared, Non-Parametric Tests and PGF Key Practice Solutions

This note gives worked solutions for [[20 Mathematics/03 Probability and Statistics/07 Chi Squared Nonparametric and PGF/30 Key Practice Problems|Key Practice Problems]]. For tests, check assumptions and state conclusions in context.

## Problem 1

The hypotheses are

$$
H_0:\text{the spinner is fair},
\qquad
H_1:\text{the spinner is not fair}.
$$

The expected frequency in each class is

$$
\frac{60}{4}=15.
$$

The statistic is

$$
\chi^2=\sum\frac{(O-E)^2}{E}
=4.53.
$$

There are $4$ classes, so

$$
\nu=4-1=3.
$$

The $5\%$ critical value is

$$
\chi^2_{0.95,3}=7.815.
$$

Since $4.53<7.815$, do not reject $H_0$. There is not enough evidence that the
spinner is unfair.

## Problem 2

The expected frequencies are

$$
20,\quad 50,\quad 30.
$$

The statistic is

$$
\chi^2=\frac{(18-20)^2}{20}
+\frac{(55-50)^2}{50}
+\frac{(27-30)^2}{30}
=1.00.
$$

There are $3$ classes and no estimated parameter, so

$$
\nu=3-1=2.
$$

The $5\%$ critical value is $5.991$. Since $1.00<5.991$, do not reject
$H_0$. The data are consistent with the stated theoretical distribution.

## Problem 3

For a goodness-of-fit test,

$$
\nu=\text{number of classes}-1-\text{number of estimated parameters}.
$$

Here

$$
\nu=6-1-1=4.
$$

This is not the same as a $2$ by $3$ contingency table. For a test of
independence, the degrees of freedom are

$$
(r-1)(c-1)=(2-1)(3-1)=2.
$$

The two tests use different structures, so their degrees of freedom are found
differently.

## Problem 4

The first two expected frequencies are $3$ and $7$. Since $3<5$, combine the
first two classes. The combined observed and expected frequencies are

$$
O:\ 10,\ 13,\ 17,
\qquad
E:\ 10,\ 12,\ 18.
$$

The statistic is

$$
\chi^2=\frac{(10-10)^2}{10}
+\frac{(13-12)^2}{12}
+\frac{(17-18)^2}{18}
=0.139.
$$

There are now $3$ classes and no estimated parameter, so

$$
\nu=3-1=2.
$$

The $5\%$ critical value is $5.991$. Since $0.139<5.991$, do not reject
$H_0$.

## Problem 5

Under independence, each expected frequency is

$$
\frac{40\times40}{80}=20.
$$

The statistic is

$$
\chi^2=4\left(\frac{5^2}{20}\right)=5.00.
$$

For a $2$ by $2$ table,

$$
\nu=(2-1)(2-1)=1.
$$

The $5\%$ critical value is $3.841$. Since $5.00>3.841$, reject $H_0$. There
is evidence that group and response are not independent.

## Problem 6

The row totals are both $50$, and the column totals are $30,30,40$. The
expected frequencies in each row are

$$
15,\quad 15,\quad 20.
$$

The statistic is

$$
\chi^2=2.40.
$$

The degrees of freedom are

$$
\nu=(2-1)(3-1)=2.
$$

The $5\%$ critical value is $5.991$. Since $2.40<5.991$, do not reject
$H_0$. There is not enough evidence that type and colour are associated.

## Problem 7

Under $H_0$, the number $S$ of observations above $100$ has distribution

$$
S\sim B\left(10,\frac12\right).
$$

The p-value for an upper-tailed sign test is

$$
P(S\ge8)=\frac{\binom{10}{8}+\binom{10}{9}+\binom{10}{10}}{2^{10}}
=0.0547.
$$

Since $0.0547>0.05$, do not reject $H_0$. There is not enough evidence at the
$5\%$ level that the median is greater than $100$.

## Problem 8

Under $H_0$, the number of positive differences has distribution

$$
B\left(8,\frac12\right).
$$

The p-value is

$$
P(S\ge6)=\frac{\binom86+\binom87+\binom88}{2^8}
=0.145.
$$

Since $0.145>0.05$, do not reject $H_0$. There is not enough evidence at the
$5\%$ level of a positive treatment effect.

## Problem 9

The absolute ranks are

| Difference | $4$ | $5$ | $2$ | $6$ | $3$ | $-1$ |
|---:|---:|---:|---:|---:|---:|---:|
| Absolute rank | 4 | 5 | 2 | 6 | 3 | 1 |

The positive rank sum is

$$
W_+=4+5+2+6+3=20.
$$

Under $H_0$, there are $2^6=64$ equally likely sign patterns. Only $2$ have
$W_+\ge20$, so

$$
P(W_+\ge20)=\frac{2}{64}=0.03125.
$$

Since $0.03125<0.05$, reject $H_0$. There is evidence of a positive median
difference.

## Problem 10

The absolute ranks are

| Difference | $2$ | $3$ | $4$ | $5$ | $6$ | $-1$ |
|---:|---:|---:|---:|---:|---:|---:|
| Absolute rank | 2 | 3 | 4 | 5 | 6 | 1 |

The positive rank sum is

$$
W_+=2+3+4+5+6=20.
$$

Again,

$$
P(W_+\ge20)=\frac{2}{64}=0.03125.
$$

Since $0.03125<0.05$, reject $H_0$. There is evidence of a positive treatment
effect.

## Problem 11

The combined ranks are

| Value | 2 | 4 | 5 | 8 | 9 | 11 |
|---:|---:|---:|---:|---:|---:|---:|
| Rank | 1 | 2 | 3 | 4 | 5 | 6 |

Sample $A$ has rank sum

$$
R_A=4+5+6=15.
$$

There are $\binom63=20$ possible rank sets for $A$ under $H_0$. Only
$\{4,5,6\}$ gives $R_A\ge15$, so

$$
P(R_A\ge15)=\frac{1}{20}=0.05.
$$

At the $5\%$ level, reject $H_0$. There is evidence that population $A$ tends
to have larger values than population $B$.

## Problem 12

- For a single-sample median test using only signs, use the sign test.
- For paired before-after data where magnitudes are useful and symmetry is
  reasonable, use the Wilcoxon matched-pairs signed-rank test.
- For two independent samples where normality is not assumed, use the
  Wilcoxon rank-sum test.

## Problem 13

The PGF is

$$
G_X(t)=0.1+0.2t+0.3t^2+0.4t^3.
$$

The coefficient of $t^2$ is $0.3$, so

$$
P(X=2)=0.3.
$$

Differentiate:

$$
G_X'(t)=0.2+0.6t+1.2t^2.
$$

Therefore

$$
E(X)=G_X'(1)=0.2+0.6+1.2=2.0.
$$

## Problem 14

Differentiate:

$$
G_X'(t)=\frac14(1+2t+3t^2),
\qquad
G_X''(t)=\frac14(2+6t).
$$

Then

$$
E(X)=G_X'(1)=\frac{6}{4}=1.5.
$$

Also

$$
G_X''(1)=2.
$$

So

$$
\operatorname{Var}(X)=G_X''(1)+G_X'(1)-[G_X'(1)]^2
=2+1.5-(1.5)^2=1.25.
$$

## Problem 15

The PGF

$$
G_X(t)=(0.8+0.2t)^5
$$

is the PGF of

$$
X\sim B(5,0.2).
$$

The probability of one success is

$$
P(X=1)=\binom51(0.2)(0.8)^4=0.410.
$$

The mean and variance are

$$
E(X)=5(0.2)=1,
\qquad
\operatorname{Var}(X)=5(0.2)(0.8)=0.8.
$$

## Problem 16

The PGF

$$
G_X(t)=\frac{0.3t}{1-0.7t}
$$

is the PGF of a geometric distribution with $p=0.3$, where $X$ is the trial
number of the first success.

Thus

$$
P(X=3)=0.3(0.7)^2=0.147.
$$

The mean and variance are

$$
E(X)=\frac{1}{0.3}=3.33,
$$

and

$$
\operatorname{Var}(X)=\frac{0.7}{0.3^2}=7.78.
$$

## Problem 17

The PGF

$$
G_X(t)=e^{4(t-1)}
$$

is the PGF of

$$
X\sim \operatorname{Po}(4).
$$

So

$$
P(X=2)=\frac{e^{-4}4^2}{2!}=0.147.
$$

For a Poisson variable,

$$
E(X)=\operatorname{Var}(X)=4.
$$

## Problem 18

For independent random variables, PGFs multiply:

$$
G_{X+Y}(t)=(0.6+0.4t)^3(0.7+0.3t)^2.
$$

The means add:

$$
E(X+Y)=3(0.4)+2(0.3)=1.8.
$$

The variances add:

$$
\operatorname{Var}(X+Y)=3(0.4)(0.6)+2(0.3)(0.7)
=0.72+0.42=1.14.
$$

The sum is not binomial in general because the two binomial variables have
different success probabilities.

## Problem 19

Expand the PGF:

$$
G_X(t)=(0.2+0.8t)^2
=0.04+0.32t+0.64t^2.
$$

So the distribution is

| $x$ | 0 | 1 | 2 |
|---:|---:|---:|---:|
| $P(X=x)$ | 0.04 | 0.32 | 0.64 |

## Problem 20

The PGFs are

$$
G_X(t)=e^{2(t-1)},
\qquad
G_Y(t)=e^{5(t-1)}.
$$

Since $X$ and $Y$ are independent,

$$
G_{X+Y}(t)=e^{2(t-1)}e^{5(t-1)}
=e^{7(t-1)}.
$$

Therefore

$$
X+Y\sim \operatorname{Po}(7).
$$

So

$$
P(X+Y=6)=\frac{e^{-7}7^6}{6!}=0.149.
$$
