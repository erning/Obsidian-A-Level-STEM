---
title: Sampling, Estimation and Hypothesis Tests Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/06 Sampling Estimation and Hypothesis Tests/00 Overview|Sampling, Estimation and Hypothesis Tests]]"
status: draft
tags:
  - mathematics/statistics
  - lecture-notes
---

# Sampling, Estimation and Hypothesis Tests Lecture Notes

Statistical inference uses a sample to say something uncertain but controlled about a population. The central idea is that a statistic such as $\bar X$ varies from sample to sample, and we use its sampling distribution to build intervals or tests.

## Source Route

- 9709 6.4 Sampling and estimation
- 9709 6.5 Hypothesis tests
- 9231 4.2 Inference using normal and t-distributions
- Coursebook route: 9709 Probability and Statistics 2 sampling, estimation, and hypothesis testing chapters; 9231 further inference content.

## Visual Guide

![[assets/generated/mathematics/sampling-estimation-and-hypothesis-tests.svg]]

Figure: use the guide to connect sampling distributions, confidence intervals, and rejection regions.

## 1. Population, Sample, and Sampling Distribution

A population is the whole group or process of interest. A sample is the observed subset. A parameter, such as a population mean $\mu$ or population proportion $p$, describes the population. A statistic, such as $\bar X$ or $\hat p$, is calculated from the sample.

Random sampling matters because it lets the statistic have a meaningful probability distribution. If the sample is biased, a neat formula cannot rescue the inference.

For a sample of size $n$ from a population with mean $\mu$ and variance $\sigma^2$,

$$
E(\bar X)=\mu,\qquad \operatorname{Var}(\bar X)=\frac{\sigma^2}{n}.
$$

The standard error of $\bar X$ is

$$
\frac{\sigma}{\sqrt n}.
$$

The Central Limit Theorem says that for large samples, the sampling distribution of $\bar X$ is approximately normal, even when the original population is not exactly normal.

## 2. Estimation and Confidence Intervals

An estimator is a rule for estimating a parameter. The sample mean estimates $\mu$. The usual unbiased estimate of population variance from raw data is

$$
s^2=\frac{\sum (x-\bar x)^2}{n-1}.
$$

A confidence interval gives a range of plausible parameter values. If the population variance is known, or if a large-sample normal approximation is appropriate, a confidence interval for a population mean has the form

$$
\bar x\pm z\frac{\sigma}{\sqrt n}.
$$

For a large-sample population proportion,

$$
\hat p\pm z\sqrt{\frac{\hat p(1-\hat p)}{n}}.
$$

A confidence level is about the long-run method, not about one fixed interval after it has been calculated. A 95% method produces intervals that contain the true parameter about 95% of the time in repeated sampling.

## 3. Hypothesis Test Structure

A hypothesis test asks whether the sample result is unusually far from what the null hypothesis predicts.

The null hypothesis $H_0$ is the model being tested. The alternative hypothesis $H_1$ states the direction or kind of departure:

- one-tailed: $H_1:\mu>\mu_0$ or $H_1:\mu<\mu_0$;
- two-tailed: $H_1:\mu\ne\mu_0$.

The significance level $\alpha$ is the probability of rejecting $H_0$ when $H_0$ is true. The rejection region, also called the critical region, is the set of test statistic values that lead to rejection.

A $p$-value is the probability, assuming $H_0$ is true, of obtaining the observed result or something at least as extreme in the direction of $H_1$. If $p<\alpha$, reject $H_0$.

## 4. Choosing a Test

The method depends on the statistic and the model.

- For a single observation from a binomial or Poisson population, use direct probabilities or a suitable normal approximation.
- For a population mean with known variance, or a large sample, use a normal test statistic.
- For a small sample from a normal population with unknown variance, use a $t$-test.
- For paired data, reduce to the differences and use a paired $t$-test when the differences are modelled as normal.
- For two independent normal samples with unknown but equal variances, use a pooled 2-sample $t$-test where appropriate.
- For differences of means with known variances or large samples, a normal distribution may be appropriate.

For a normal test of a mean with known $\sigma$,

$$
Z=\frac{\bar X-\mu_0}{\sigma/\sqrt n}.
$$

For a one-sample $t$-test with sample standard deviation $s$,

$$
T=\frac{\bar X-\mu_0}{s/\sqrt n},
$$

with $n-1$ degrees of freedom.

## 5. Type I and Type II Errors

A Type I error is rejecting $H_0$ when $H_0$ is true. Its probability is the significance level, if the rejection region is set exactly to $\alpha$.

A Type II error is not rejecting $H_0$ when $H_1$ is true. To calculate it, assume a particular alternative parameter value, then find the probability that the test statistic falls in the acceptance region under that alternative.

These errors are not just vocabulary. They describe the trade-off between being too quick to reject and being too slow to detect a real change.

## Worked-Thinking Routine

1. Identify the population, parameter, sample statistic, and model assumptions.
2. Decide whether the task is estimation or testing.
3. For intervals, choose the standard error and critical value.
4. For tests, write $H_0$ and $H_1$ in symbols and words.
5. Select the distribution of the test statistic under $H_0$.
6. Use a rejection region or $p$-value consistently.
7. State the conclusion in context without saying $H_0$ has been proved.

## Common Mistakes

- Treating a biased sampling method as if it were random.
- Confusing population standard deviation, sample standard deviation, and standard error.
- Saying a fixed confidence interval has a 95% probability of containing the parameter.
- Writing hypotheses after seeing the calculation.
- Confusing one-tailed and two-tailed alternatives.
- Saying the null hypothesis is proved.
- Interpreting the significance level as the probability that $H_0$ is true.
- Using a normal test when a small-sample $t$-test is required.

## Quick Self-Check

- Can you distinguish parameter, statistic, estimator, and estimate?
- Can you explain why $\operatorname{Var}(\bar X)=\sigma^2/n$?
- Can you construct and interpret a confidence interval?
- Can you choose between normal, binomial, Poisson, and $t$ tests?
- Can you define Type I and Type II errors for a specific context?

## Connections

- [[20 Mathematics/03 Probability and Statistics/04 Normal and Poisson Distributions/00 Overview|Normal and Poisson Distributions]]
- [[20 Mathematics/03 Probability and Statistics/07 Chi Squared Nonparametric and PGF/00 Overview|Chi-Squared, Non-Parametric Tests and PGF]]

## Study Sequence

1. Review samples, populations, and random sampling.
2. Study the sampling distribution of $\bar X$.
3. Build confidence intervals for means and proportions.
4. Practise the structure of hypothesis tests.
5. Add binomial, Poisson, normal, and $t$ tests.
6. Finish with Type I and Type II error calculations.
