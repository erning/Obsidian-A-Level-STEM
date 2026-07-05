---
title: Sampling, Estimation and Hypothesis Tests Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/06 Sampling Estimation and Hypothesis Tests/00 Overview|Sampling, Estimation and Hypothesis Tests]]"
status: active
tags:
  - mathematics/statistics
  - solutions
---

# Sampling, Estimation and Hypothesis Tests Key Practice Solutions

This note gives worked solutions for [[20 Mathematics/03 Probability and Statistics/06 Sampling Estimation and Hypothesis Tests/30 Key Practice Problems|Key Practice Problems]]. For tests, mark the hypotheses, test direction, calculation, and conclusion in context.

## Problem 1

The population is all customers whose waiting times the supermarket wants to
study. The parameter is the true population mean waiting time.

The sample is the first $30$ customers after opening on a Monday. The statistic
is the sample mean waiting time from those $30$ observations.

The sampling method may be unsatisfactory because early Monday customers may
not be representative of customers at other times or on other days. This is
not a random sample from the full population of interest.

## Problem 2

For a random sample,

$$
E(\bar X)=40,
\qquad
\operatorname{Var}(\bar X)=\frac{10^2}{25}=4.
$$

The standard error is

$$
\frac{10}{\sqrt{25}}=2.
$$

If the population is normal,

$$
\bar X\sim N(40,4).
$$

Therefore

$$
P(\bar X>43)=P\left(Z>\frac{43-40}{2}\right)
=P(Z>1.5)=0.0668.
$$

## Problem 3

The sample mean is

$$
\bar x=\frac{7+9+10+6+8}{5}=8.
$$

The squared deviations are

$$
1,\quad 1,\quad 4,\quad 4,\quad 0,
$$

which sum to $10$. Therefore the unbiased estimate of the population variance
is

$$
s^2=\frac{10}{5-1}=2.5.
$$

## Problem 4

The standard error is

$$
\frac{5}{\sqrt{100}}=0.5.
$$

For a $95\%$ confidence interval, use $z=1.96$:

$$
18.4\pm1.96(0.5).
$$

So the interval is

$$
(17.42,\ 19.38).
$$

## Problem 5

The sample proportion is

$$
\hat p=\frac{72}{120}=0.6.
$$

For a $90\%$ confidence interval, use $z=1.645$. The standard error is

$$
\sqrt{\frac{0.6(0.4)}{120}}=0.0447.
$$

The margin is

$$
1.645(0.0447)=0.0736.
$$

Therefore the interval is

$$
(0.526,\ 0.674)
$$

to 3 decimal places.

## Problem 6

The hypotheses are

$$
H_0:\mu=50,
\qquad
H_1:\mu>50.
$$

The standard error is

$$
\frac{8}{\sqrt{64}}=1.
$$

The test statistic is

$$
z=\frac{52.1-50}{1}=2.10.
$$

For an upper one-tailed $5\%$ test, the critical value is $1.645$. Since
$2.10>1.645$, reject $H_0$. The p-value is approximately $0.0179$.

There is evidence at the $5\%$ level that the population mean is greater than
$50$.

## Problem 7

The hypotheses are

$$
H_0:\mu=100,
\qquad
H_1:\mu\ne100.
$$

The standard error is

$$
\frac{12}{\sqrt{36}}=2.
$$

The test statistic is

$$
z=\frac{95-100}{2}=-2.50.
$$

For a two-tailed $5\%$ test, the critical values are $\pm1.96$. Since
$|z|=2.50>1.96$, reject $H_0$. The p-value is approximately $0.0124$.

There is evidence at the $5\%$ level that the population mean is different
from $100$.

## Problem 8

Let $X$ be the number of defective items. The hypotheses are

$$
H_0:p=0.4,
\qquad
H_1:p<0.4.
$$

Under $H_0$,

$$
X\sim B(15,0.4).
$$

The p-value is

$$
P(X\le3)=0.0905.
$$

Since $0.0905>0.05$, do not reject $H_0$.

There is not enough evidence at the $5\%$ level that the defect probability is
less than $0.4$.

## Problem 9

Under $H_0$,

$$
X\sim \operatorname{Po}(2).
$$

The p-value is

$$
P(X\ge6)=0.0166.
$$

Since $0.0166<0.05$, reject $H_0$.

There is evidence at the $5\%$ level that $\lambda>2$.

## Problem 10

Let $X$ be the number of heads. The hypotheses are

$$
H_0:p=\frac12,
\qquad
H_1:p>\frac12.
$$

Under $H_0$,

$$
X\sim B\left(200,\frac12\right).
$$

Use the normal approximation:

$$
X\approx Y,\qquad Y\sim N(100,50).
$$

With continuity correction,

$$
P(X\ge116)\approx P(Y>115.5).
$$

Then

$$
z=\frac{115.5-100}{\sqrt{50}}=2.19.
$$

The p-value is approximately

$$
P(Z>2.19)=0.0142.
$$

Since $0.0142<0.05$, reject $H_0$. There is evidence that the coin is biased
towards heads.

## Problem 11

For a large sample, use the sample standard deviation to estimate the standard
error:

$$
\frac{s}{\sqrt n}=\frac{4}{10}=0.4.
$$

The hypotheses are

$$
H_0:\mu=15,
\qquad
H_1:\mu>15.
$$

The test statistic is

$$
z=\frac{15.7-15}{0.4}=1.75.
$$

The p-value is

$$
P(Z>1.75)=0.0401.
$$

Since $0.0401<0.05$, reject $H_0$. There is evidence that the population mean
is greater than $15$.

## Problem 12

A Type I error is rejecting $H_0$ when $p=0.2$:

$$
P(\text{Type I})=P(X\ge5\mid X\sim B(10,0.2)).
$$

Thus

$$
P(\text{Type I})=0.0328.
$$

A Type II error at $p=0.4$ means not rejecting $H_0$ when $p=0.4$. Since the
critical region is $X\ge5$, the acceptance region is $X\le4$:

$$
P(\text{Type II})=P(X\le4\mid X\sim B(10,0.4))=0.633.
$$

## Problem 13

A Type I error is rejecting $H_0$ when $\lambda=3$:

$$
P(\text{Type I})=P(X=0\mid X\sim \operatorname{Po}(3))=e^{-3}=0.0498.
$$

A Type II error at $\lambda=1$ means not rejecting $H_0$ when $\lambda=1$.
The critical region is $X=0$, so the acceptance region is $X\ge1$:

$$
P(\text{Type II})=P(X\ge1\mid X\sim \operatorname{Po}(1))=1-e^{-1}=0.632.
$$

## Problem 14

Under $H_0$, the standard error is

$$
\frac{10}{\sqrt{25}}=2.
$$

The Type I error probability is

$$
P(\bar X>104\mid \mu=100)
=P\left(Z>\frac{104-100}{2}\right)
=P(Z>2)=0.0228.
$$

If the true mean is $106$, the Type II error is the probability of not
rejecting $H_0$:

$$
P(\bar X\le104\mid \mu=106)
=P\left(Z\le\frac{104-106}{2}\right)
=P(Z\le -1)=0.159.
$$

## Problem 15

For $X\sim B(12,0.5)$,

$$
P(X\ge9)=0.0730,
$$

which is too large for a $5\%$ test. But

$$
P(X\ge10)=0.0193.
$$

Therefore the smallest critical region of the form $X\ge c$ with significance
level at most $5\%$ is

$$
X\ge10.
$$

The actual significance level is $0.0193$, or about $1.93\%$.

## Problem 16

The hypotheses are

$$
H_0:\mu=100,
\qquad
H_1:\mu>100.
$$

Use a $t$-test because the population is normal, the sample is small, and the
population variance is unknown. The degrees of freedom are $8$.

The test statistic is

$$
t=\frac{102.4-100}{4.5/\sqrt9}=1.60.
$$

For an upper one-tailed $5\%$ test with $8$ degrees of freedom,

$$
t_{0.95,8}=1.860.
$$

Since $1.60<1.860$, do not reject $H_0$. There is not enough evidence at the
$5\%$ level that the mean is greater than $100$.

## Problem 17

Use a $t$ interval with $11$ degrees of freedom. For a $95\%$ interval,

$$
t_{0.975,11}=2.201.
$$

The interval is

$$
31.5\pm2.201\frac{2.4}{\sqrt{12}}.
$$

The margin is approximately $1.52$, so the confidence interval is

$$
(30.0,\ 33.0)
$$

to 3 significant figures.

## Problem 18

For a paired test, work with the differences. The hypotheses are

$$
H_0:\mu_d=0,
\qquad
H_1:\mu_d>0.
$$

The test statistic is

$$
t=\frac{1.6-0}{2.0/\sqrt8}=2.26.
$$

The degrees of freedom are $7$. For an upper one-tailed $5\%$ test,

$$
t_{0.95,7}=1.895.
$$

Since $2.26>1.895$, reject $H_0$. There is evidence at the $5\%$ level that
the mean difference is positive.

## Problem 19

The pooled estimate is

$$
s_p^2=\frac{(n_1-1)s_1^2+(n_2-1)s_2^2}{n_1+n_2-2}.
$$

Substitute the values:

$$
s_p^2=\frac{5(4.0)+7(6.5)}{6+8-2}
=\frac{65.5}{12}
=5.46.
$$

This pooled estimate is used in a 2-sample $t$ procedure when a common
population variance is assumed.

## Problem 20

The hypotheses are

$$
H_0:\mu_A-\mu_B=0,
\qquad
H_1:\mu_A-\mu_B>0.
$$

The standard error of $\bar X_A-\bar X_B$ is

$$
\sqrt{\frac{10^2}{50}+\frac{12^2}{60}}
=\sqrt{4.4}
=2.10.
$$

The test statistic is

$$
z=\frac{82-78}{2.10}=1.91.
$$

The p-value is approximately

$$
P(Z>1.91)=0.0283.
$$

Since $0.0283<0.05$, reject $H_0$. There is evidence at the $5\%$ level that
population $A$ has a larger mean than population $B$.
