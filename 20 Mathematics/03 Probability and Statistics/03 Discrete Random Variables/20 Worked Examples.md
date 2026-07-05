---
title: Discrete Random Variables Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/03 Discrete Random Variables/00 Overview|Discrete Random Variables]]"
status: active
tags:
  - mathematics/statistics
  - worked-examples
---

# Discrete Random Variables Worked Examples

These examples model the 9709 route through probability tables, expectation,
variance, binomial and geometric distributions, cumulative probabilities, and
linear combinations of random variables.

## Source Route

- CAIE Mathematics 9709 section 5.4: probability distribution tables,
  expectation, variance, binomial distribution, geometric distribution, and
  model recognition.
- CAIE Mathematics 9709 section 6.2: expectation and variance of linear
  transformations and independent linear combinations.

## Example 1: Completing a Probability Distribution

**Prompt.** A random variable $X$ has distribution

| $x$ | 0 | 1 | 2 | 3 |
|---:|---:|---:|---:|---:|
| $P(X=x)$ | $k$ | $2k$ | $3k$ | $4k$ |

Find $k$, $E(X)$, and $\operatorname{Var}(X)$.

**Solution.**

Probabilities sum to $1$:

$$
k+2k+3k+4k=1.
$$

So $k=0.1$. Then

$$
E(X)=0(0.1)+1(0.2)+2(0.3)+3(0.4)=2.
$$

Also

$$
E(X^2)=0^2(0.1)+1^2(0.2)+2^2(0.3)+3^2(0.4)=5.
$$

Therefore

$$
\operatorname{Var}(X)=5-2^2=1.
$$

**Check.** The probabilities are all between $0$ and $1$ and sum to $1$.

## Example 2: A Distribution from Coin Tosses

**Prompt.** A fair coin is tossed three times. Let $X$ be the number of heads.
Write the distribution of $X$, and find $E(X)$ and $\operatorname{Var}(X)$.

**Solution.**

There are $8$ equally likely outcomes. The distribution is

| $x$ | 0 | 1 | 2 | 3 |
|---:|---:|---:|---:|---:|
| $P(X=x)$ | $\frac18$ | $\frac38$ | $\frac38$ | $\frac18$ |

Then

$$
E(X)=0\cdot\frac18+1\cdot\frac38+2\cdot\frac38+3\cdot\frac18
=\frac32.
$$

Also

$$
E(X^2)=0+\frac38+\frac{12}{8}+\frac98=3.
$$

Thus

$$
\operatorname{Var}(X)=3-\left(\frac32\right)^2=\frac34.
$$

**Check.** This agrees with $X\sim B(3,1/2)$.

## Example 3: Point and Cumulative Probabilities

**Prompt.** For the distribution

| $x$ | 0 | 1 | 2 | 3 | 4 |
|---:|---:|---:|---:|---:|---:|
| $P(X=x)$ | 0.10 | 0.20 | 0.30 | 0.25 | 0.15 |

find $P(X=2)$, $P(X\le2)$, and $P(X>2)$.

**Solution.**

The point probability is

$$
P(X=2)=0.30.
$$

The cumulative probability is

$$
P(X\le2)=0.10+0.20+0.30=0.60.
$$

The upper tail is

$$
P(X>2)=1-0.60=0.40.
$$

**Check.** $P(X=2)$ and $P(X\le2)$ are different statements.

## Example 4: Binomial Distribution

**Prompt.** Let $X\sim B(8,0.3)$. Find $P(X=2)$, $P(X\ge1)$, $E(X)$, and
$\operatorname{Var}(X)$.

**Solution.**

$$
P(X=2)=\binom82(0.3)^2(0.7)^6=0.296
$$

to 3 s.f. Also

$$
P(X\ge1)=1-P(X=0)=1-(0.7)^8=0.942
$$

to 3 s.f. For a binomial distribution,

$$
E(X)=np=8(0.3)=2.4,
$$

and

$$
\operatorname{Var}(X)=np(1-p)=8(0.3)(0.7)=1.68.
$$

**Check.** The binomial model needs fixed independent trials with constant
success probability.

## Example 5: Geometric Distribution

**Prompt.** Let $X\sim \operatorname{Geo}(0.2)$ in the CAIE convention, where
$X$ is the trial number of the first success. Find $P(X=4)$, $P(X\le3)$, and
$E(X)$.

**Solution.**

$$
P(X=4)=0.2(0.8)^3=0.1024.
$$

The event $X\le3$ means success in the first three trials:

$$
P(X\le3)=1-P(\text{first three trials fail})
=1-(0.8)^3=0.488.
$$

The expectation is

$$
E(X)=\frac{1}{0.2}=5.
$$

**Check.** The first possible value is $1$, not $0$.

## Example 6: Linear Transformation

**Prompt.** A random variable $X$ has $E(X)=4$ and
$\operatorname{Var}(X)=2$. Let $Y=3X-5$. Find $E(Y)$ and
$\operatorname{Var}(Y)$.

**Solution.**

$$
E(Y)=E(3X-5)=3E(X)-5=7.
$$

Variance is not shifted by subtracting $5$, but it is scaled by $3^2$:

$$
\operatorname{Var}(Y)=3^2\operatorname{Var}(X)=18.
$$

**Check.** The variance is not $3(2)-5$.

## Example 7: Independent Linear Combination

**Prompt.** Independent random variables $X$ and $Y$ have
$E(X)=5$, $\operatorname{Var}(X)=3$, $E(Y)=2$, and
$\operatorname{Var}(Y)=4$. Let $Z=2X-Y$. Find $E(Z)$ and
$\operatorname{Var}(Z)$.

**Solution.**

$$
E(Z)=2E(X)-E(Y)=2(5)-2=8.
$$

Independence is needed for the variance result:

$$
\operatorname{Var}(Z)=2^2\operatorname{Var}(X)+(-1)^2\operatorname{Var}(Y).
$$

Thus

$$
\operatorname{Var}(Z)=4(3)+4=16.
$$

**Check.** The minus sign affects the mean, but its square is used in the
variance.

## Example 8: Choosing a Model

**Prompt.** A student answers $10$ independent multiple-choice questions by
guessing. Each question has one correct answer out of four. Which distribution
models the number of correct answers?

**Solution.**

There is a fixed number of trials, $n=10$. Each trial has two outcomes:
correct or not correct. The success probability is constant,

$$
p=\frac14,
$$

and the guesses are independent. Therefore

$$
X\sim B\left(10,\frac14\right).
$$

**Check.** If the question asked for the trial number of the first correct
answer, the geometric model would be the natural one instead.
