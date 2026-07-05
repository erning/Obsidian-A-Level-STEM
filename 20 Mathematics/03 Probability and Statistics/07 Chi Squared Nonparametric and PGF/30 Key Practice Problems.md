---
title: Chi-Squared, Non-Parametric Tests and PGF Key Practice Problems
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/07 Chi Squared Nonparametric and PGF/00 Overview|Chi-Squared, Non-Parametric Tests and PGF]]"
status: active
tags:
  - mathematics/statistics
  - practice
---

# Chi-Squared, Non-Parametric Tests and PGF Key Practice Problems

Work these without looking at the solutions first. For each test, state the
hypotheses and check the conditions before using a critical value.

## A. Chi-Squared Tests

1. A four-sided spinner is expected to land on each side equally often. In
   $60$ spins the observed frequencies are $12,18,20,10$. Test at the $5\%$
   level whether the spinner is fair.

2. A theoretical distribution predicts probabilities $0.2,0.5,0.3$ in three
   classes. In $100$ observations the observed frequencies are $18,55,27$.
   Carry out a chi-squared goodness-of-fit test at the $5\%$ level.

3. In a goodness-of-fit test there are $6$ classes and one parameter has been
   estimated from the data. State the degrees of freedom. Explain why this is
   not the same as the degrees of freedom for a $2$ by $3$ contingency table.

4. A goodness-of-fit test has observed frequencies $4,6,13,17$ and expected
   frequencies $3,7,12,18$. Combine the first two classes, then carry out the
   test at the $5\%$ level, assuming no parameter has been estimated.

5. The table shows two categorical variables.

   |  | Yes | No | Total |
   |---|---:|---:|---:|
   | Group A | 25 | 15 | 40 |
   | Group B | 15 | 25 | 40 |
   | Total | 40 | 40 | 80 |

   Test at the $5\%$ level whether group and response are independent.

6. The table shows another contingency table.

   |  | Red | Blue | Green | Total |
   |---|---:|---:|---:|---:|
   | Type 1 | 12 | 18 | 20 | 50 |
   | Type 2 | 18 | 12 | 20 | 50 |
   | Total | 30 | 30 | 40 | 100 |

   Test at the $5\%$ level whether type and colour are independent.

## B. Non-Parametric Tests

7. In a single-sample sign test for

   $$
   H_0:m=100,
   \qquad
   H_1:m>100,
   $$

   there are $10$ observations, of which $8$ are above $100$. Use a sign test
   at the $5\%$ level.

8. In a paired-sample sign test for a positive treatment effect, there are
   $8$ non-zero differences, of which $6$ are positive. Use a sign test at the
   $5\%$ level.

9. Six observations have differences from a hypothesised median:

   $$
   4,\quad 5,\quad 2,\quad 6,\quad 3,\quad -1.
   $$

   Use a Wilcoxon signed-rank test at the $5\%$ level for a positive median
   difference. Assume symmetry and no tied absolute differences.

10. Six paired differences, after minus before, are

    $$
    2,\quad 3,\quad 4,\quad 5,\quad 6,\quad -1.
    $$

    Use a Wilcoxon matched-pairs signed-rank test at the $5\%$ level for a
    positive treatment effect. Assume symmetry and no zero or tied absolute
    differences.

11. Two independent samples are

    $$
    A:\ 8,\ 9,\ 11,
    \qquad
    B:\ 2,\ 4,\ 5.
    $$

    Use a one-tailed Wilcoxon rank-sum test at the $5\%$ level to test whether
    population $A$ tends to have larger values than population $B$.

12. Choose a suitable non-parametric test for each situation: a single-sample
    median test with only signs used; paired before-after data with magnitude
    and symmetry reasonable; two independent samples when normality is not
    assumed.

## C. Probability Generating Functions

13. A random variable has distribution

    | $x$ | 0 | 1 | 2 | 3 |
    |---:|---:|---:|---:|---:|
    | $P(X=x)$ | 0.1 | 0.2 | 0.3 | 0.4 |

    Write down its PGF and find $P(X=2)$ and $E(X)$.

14. Let

    $$
    G_X(t)=\frac14(1+t+t^2+t^3).
    $$

    Find $E(X)$ and $\operatorname{Var}(X)$.

15. Let

    $$
    G_X(t)=(0.8+0.2t)^5.
    $$

    Identify the distribution, and find $P(X=1)$, $E(X)$, and
    $\operatorname{Var}(X)$.

16. Let

    $$
    G_X(t)=\frac{0.3t}{1-0.7t}.
    $$

    Identify the distribution, and find $P(X=3)$, $E(X)$, and
    $\operatorname{Var}(X)$.

17. Let

    $$
    G_X(t)=e^{4(t-1)}.
    $$

    Identify the distribution, and find $P(X=2)$, $E(X)$, and
    $\operatorname{Var}(X)$.

18. Independent random variables $X$ and $Y$ have PGFs

    $$
    G_X(t)=(0.6+0.4t)^3,
    \qquad
    G_Y(t)=(0.7+0.3t)^2.
    $$

    Find the PGF of $X+Y$, $E(X+Y)$, and $\operatorname{Var}(X+Y)$.

19. Let

    $$
    G_X(t)=(0.2+0.8t)^2.
    $$

    Expand the PGF and write down the distribution of $X$.

20. Independent random variables $X$ and $Y$ have

    $$
    X\sim \operatorname{Po}(2),
    \qquad
    Y\sim \operatorname{Po}(5).
    $$

    Use PGFs to find the distribution of $X+Y$ and $P(X+Y=6)$.
