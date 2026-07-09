---
title: Chi-Squared, Non-Parametric Tests and PGF Review Checklist
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Chi-Squared, Non-Parametric Tests and PGF](00%20Overview.md)"
status: active
tags:
  - mathematics/statistics
  - review-checklist
---

# Chi-Squared, Non-Parametric Tests and PGF Review Checklist

Use this after the worked examples and practice problems. Revisit [Chi-Squared, Non-Parametric Tests and PGF Lecture Notes](10%20Lecture%20Notes.md) if any item is uncertain.

## Ideas to Recall

- [ ] Chi-squared tests compare observed and expected frequencies using $\sum\frac{(O-E)^2}{E}$.
- [ ] Chi-squared tests are right-tailed tests.
- [ ] Expected frequencies should be at least $5$ after combining classes, rows, or columns where needed.
- [ ] Goodness-of-fit degrees of freedom are classes minus $1$ minus estimated parameters.
- [ ] Independence-test degrees of freedom are $(r-1)(c-1)$.
- [ ] A sign test uses only directions relative to a median or paired difference of zero.
- [ ] Wilcoxon signed-rank and matched-pairs signed-rank tests use signed ranks and require symmetry.
- [ ] Wilcoxon rank-sum tests compare two independent samples using combined ranks.
- [ ] A PGF is $G_X(t)=E(t^X)=\sum P(X=x)t^x$.
- [ ] The coefficient of $t^x$ in a PGF is $P(X=x)$.
- [ ] $E(X)=G_X'(1)$ and $\operatorname{Var}(X)=G_X''(1)+G_X'(1)-[G_X'(1)]^2$.
- [ ] Independent sums have product PGFs.

## Skills to Perform

- [ ] Calculate expected frequencies in a goodness-of-fit test.
- [ ] Calculate expected frequencies in a contingency table using row and column totals.
- [ ] Combine classes or table categories when expected frequencies are below $5$.
- [ ] Select the correct degrees of freedom for chi-squared tests.
- [ ] Compare a chi-squared statistic with the correct right-tail critical value.
- [ ] Carry out a sign test using a binomial probability.
- [ ] Rank absolute differences for a Wilcoxon signed-rank or matched-pairs signed-rank test.
- [ ] Rank combined observations for a Wilcoxon rank-sum test.
- [ ] Construct a PGF from a probability table.
- [ ] Read probabilities from PGF coefficients.
- [ ] Differentiate a PGF to find mean and variance.
- [ ] Multiply PGFs for sums of independent variables.

## Common Errors to Avoid

- [ ] Using a chi-squared test when expected frequencies are too small and have not been combined.
- [ ] Using a left-tail chi-squared critical value for a right-tail test.
- [ ] Forgetting to subtract estimated parameters in a goodness-of-fit test.
- [ ] Using $(r-1)(c-1)$ for a goodness-of-fit test.
- [ ] Applying Wilcoxon signed-rank tests without the symmetry condition.
- [ ] Including zero differences or tied ranks when the question says they are excluded.
- [ ] Confusing paired data with two independent samples.
- [ ] Reading $P(X=x)$ from the wrong power of $t$.
- [ ] Treating $G_X''(1)$ as $E(X^2)$.
- [ ] Multiplying PGFs for variables that are not independent.

## Ready to Move On When

- [ ] I can decide whether a question is about frequencies, ranks, signs, or PGFs.
- [ ] I can choose between goodness-of-fit and independence tests.
- [ ] I can choose between sign, signed-rank, matched-pairs signed-rank, and rank-sum tests.
- [ ] I can carry out a small exact non-parametric test from signs or ranks.
- [ ] I can construct PGFs for common discrete distributions.
- [ ] I can use PGFs to find probabilities, means, variances, and distributions of independent sums.
