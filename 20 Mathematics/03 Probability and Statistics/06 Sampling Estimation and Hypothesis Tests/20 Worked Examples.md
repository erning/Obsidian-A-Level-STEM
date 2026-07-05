---
title: Sampling, Estimation and Hypothesis Tests Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/06 Sampling Estimation and Hypothesis Tests/00 Overview|Sampling, Estimation and Hypothesis Tests]]"
status: active
tags:
  - mathematics/statistics
  - worked-examples
---

# Sampling, Estimation and Hypothesis Tests Worked Examples

These examples model the CAIE route through sampling distributions, standard
errors, unbiased estimates, confidence intervals, hypothesis tests, and Type I
and Type II errors.

## Source Route

- CAIE Mathematics 9709 sections 6.4 and 6.5: random sampling, sampling
  distribution of $\bar X$, Central Limit Theorem, unbiased estimates,
  confidence intervals for means and proportions, hypothesis tests using
  binomial, Poisson, and normal models, and Type I and Type II errors.
- CAIE Further Mathematics 9231 section 4.2: small-sample inference using
  $t$-distributions, paired tests, two-sample inference, pooled variance, and
  confidence intervals using $t$ where appropriate.

## Example 1: Sampling Distribution of the Sample Mean

**Prompt.** A population has mean $80$ and standard deviation $12$. A random
sample of size $36$ is taken. Find $E(\bar X)$, $\operatorname{Var}(\bar X)$,
the standard error, and $P(\bar X>84)$ if the population is normal.

**Solution.**

For a random sample,

$$
E(\bar X)=\mu=80,
\qquad
\operatorname{Var}(\bar X)=\frac{\sigma^2}{n}
=\frac{12^2}{36}=4.
$$

The standard error is

$$
\frac{\sigma}{\sqrt n}=\frac{12}{6}=2.
$$

Since the population is normal,

$$
\bar X\sim N(80,4).
$$

Therefore

$$
P(\bar X>84)=P\left(Z>\frac{84-80}{2}\right)
=P(Z>2)=0.0228.
$$

**Check.** The variance of $\bar X$ is smaller than the population variance by
a factor of $n$.

## Example 2: Unbiased Estimates from Raw Data

**Prompt.** A random sample gives the observations

$$
12,\quad 15,\quad 13,\quad 10,\quad 14.
$$

Find the sample mean and the unbiased estimate of the population variance.

**Solution.**

The sample mean is

$$
\bar x=\frac{12+15+13+10+14}{5}=12.8.
$$

The squared deviations from $12.8$ sum to

$$
(12-12.8)^2+(15-12.8)^2+(13-12.8)^2+(10-12.8)^2+(14-12.8)^2=14.8.
$$

The unbiased estimate of the population variance is

$$
s^2=\frac{14.8}{5-1}=3.70.
$$

**Check.** Divide by $n-1$, not $n$, when estimating population variance from
a sample.

## Example 3: Confidence Interval for a Mean

**Prompt.** A random sample of size $64$ has mean $52.3$. The population
standard deviation is known to be $8$. Find a $95\%$ confidence interval for
the population mean.

**Solution.**

Use

$$
\bar x\pm z\frac{\sigma}{\sqrt n}.
$$

For a $95\%$ confidence interval, $z=1.96$. The standard error is

$$
\frac{8}{\sqrt{64}}=1.
$$

So the interval is

$$
52.3\pm 1.96(1),
$$

which gives

$$
(50.34,\ 54.26).
$$

**Interpretation.** This method produces intervals that contain the population
mean in about $95\%$ of repeated random samples.

## Example 4: Confidence Interval for a Proportion

**Prompt.** In a random sample of $500$ voters, $280$ support a proposal. Find
an approximate $95\%$ confidence interval for the population proportion.

**Solution.**

The sample proportion is

$$
\hat p=\frac{280}{500}=0.56.
$$

For a large sample,

$$
\hat p\pm z\sqrt{\frac{\hat p(1-\hat p)}{n}}
$$

with $z=1.96$. The standard error is

$$
\sqrt{\frac{0.56(0.44)}{500}}=0.0222.
$$

The margin of error is

$$
1.96(0.0222)=0.0435.
$$

So the confidence interval is

$$
(0.516,\ 0.604)
$$

to 3 decimal places.

**Check.** The interval is for the population proportion, not for the number
of people in the sample.

## Example 5: Normal Test for a Population Mean

**Prompt.** A machine is claimed to fill bags with mean mass $100$ g. The
population standard deviation is known to be $6$ g. A random sample of $36$
bags has mean mass $97.8$ g. Test at the $5\%$ significance level whether the
mean mass is lower than claimed.

**Solution.**

Write the hypotheses:

$$
H_0:\mu=100,
\qquad
H_1:\mu<100.
$$

Under $H_0$,

$$
\bar X\sim N\left(100,\frac{6^2}{36}\right).
$$

The test statistic is

$$
z=\frac{97.8-100}{6/\sqrt{36}}=-2.20.
$$

For a lower one-tailed $5\%$ test, the critical value is $-1.645$. Since

$$
-2.20<-1.645,
$$

reject $H_0$. Equivalently, the p-value is approximately $0.0139$.

**Conclusion.** There is evidence at the $5\%$ level that the mean mass is
lower than $100$ g.

## Example 6: Direct Binomial Hypothesis Test

**Prompt.** A candidate claims that $25\%$ of voters support her. In a random
sample of $20$ voters, $9$ support her. Test at the $5\%$ level whether support
is greater than $25\%$.

**Solution.**

Let $X$ be the number of supporters in the sample. The hypotheses are

$$
H_0:p=0.25,
\qquad
H_1:p>0.25.
$$

Under $H_0$,

$$
X\sim B(20,0.25).
$$

The p-value is

$$
P(X\ge9)=0.0409.
$$

Since

$$
0.0409<0.05,
$$

reject $H_0$.

**Conclusion.** There is evidence at the $5\%$ level that support is greater
than $25\%$.

## Example 7: Type I and Type II Errors

**Prompt.** A Poisson count is tested using

$$
H_0:\lambda=3,
\qquad
H_1:\lambda>3.
$$

The critical region is $X\ge7$. Find the probability of a Type I error, and
find the probability of a Type II error if the true value is $\lambda=5$.

**Solution.**

A Type I error means rejecting $H_0$ when $\lambda=3$:

$$
P(\text{Type I})=P(X\ge7\mid X\sim \operatorname{Po}(3)).
$$

So

$$
P(\text{Type I})=0.0335.
$$

A Type II error means not rejecting $H_0$ when $\lambda=5$. Since the critical
region is $X\ge7$, the acceptance region is $X\le6$:

$$
P(\text{Type II})=P(X\le6\mid X\sim \operatorname{Po}(5)).
$$

Thus

$$
P(\text{Type II})=0.762.
$$

**Check.** Type II error probabilities require a specified alternative value.

## Example 8: Small-Sample t Confidence Interval

**Prompt.** A random sample of size $10$ from a normal population has
$\bar x=24.6$ and sample standard deviation $s=3.2$. Find a $95\%$ confidence
interval for the population mean.

**Solution.**

The population variance is unknown and the sample is small, so use a
$t$-distribution with

$$
n-1=9
$$

degrees of freedom. For a $95\%$ confidence interval,

$$
t_{0.975,9}=2.262.
$$

The interval is

$$
\bar x\pm t\frac{s}{\sqrt n}
=24.6\pm 2.262\frac{3.2}{\sqrt{10}}.
$$

The margin is approximately $2.29$, so the interval is

$$
(22.3,\ 26.9)
$$

to 3 significant figures.

**Check.** This is a 9231 small-sample method; 9709 large-sample intervals use
normal critical values.
