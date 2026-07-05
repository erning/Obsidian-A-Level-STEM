---
title: Continuous Random Variables Review Checklist
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/05 Continuous Random Variables/00 Overview|Continuous Random Variables]]"
status: active
tags:
  - mathematics/statistics
  - review-checklist
---

# Continuous Random Variables Review Checklist

Use this after the worked examples and practice problems. Revisit [[20 Mathematics/03 Probability and Statistics/05 Continuous Random Variables/10 Lecture Notes|Continuous Random Variables Lecture Notes]] if any item is uncertain.

## Ideas to Recall

- [ ] A probability density function gives probability by area, not by height.
- [ ] For a continuous random variable, $P(X=a)=0$.
- [ ] A valid PDF is non-negative on its support and has total area $1$.
- [ ] 9709 uses PDFs over a single interval and does not require explicit CDF knowledge.
- [ ] 9231 extends the topic to piecewise PDFs, CDFs, $E(g(X))$, and related variables.
- [ ] $E(X)=\int x f(x)\,dx$ over the support.
- [ ] $\operatorname{Var}(X)=E(X^2)-[E(X)]^2$.
- [ ] A median or percentile is found by solving an area equation.
- [ ] A CDF accumulates area from the left and can be differentiated to recover the PDF where differentiable.
- [ ] A related variable needs its own range before its CDF or PDF is written.

## Skills to Perform

- [ ] Write the support before doing any calculation.
- [ ] Use total area $1$ to find an unknown density constant.
- [ ] Calculate interval probabilities by integrating the PDF over the correct interval.
- [ ] Split integrals at breakpoints for piecewise densities.
- [ ] Handle infinite limits as limits, not as ordinary numbers.
- [ ] Calculate $E(X)$, $E(X^2)$, and $\operatorname{Var}(X)$.
- [ ] Find a median or percentile from a direct area equation.
- [ ] Build a CDF from a PDF and use it to evaluate probabilities.
- [ ] Differentiate a CDF to obtain a PDF on the correct support.
- [ ] Use a CDF method for simple related variables such as $Y=X^2$, $Y=X^3$, or $Y=1-X$.

## Common Errors to Avoid

- [ ] Treating $f(x)$ as $P(X=x)$.
- [ ] Forgetting to set the density to $0$ outside its support.
- [ ] Integrating outside the support interval.
- [ ] Dropping limits in expectation and variance integrals.
- [ ] Forgetting to square $X$ when calculating $E(X^2)$.
- [ ] Finding $E(X^2)$ but calling it the variance.
- [ ] Using a CDF formula outside the interval where it is valid.
- [ ] Differentiating a CDF without checking its pieces and support.
- [ ] Writing the range of a related variable incorrectly.

## Ready to Move On When

- [ ] I can explain why density height is not a point probability.
- [ ] I can normalise a density and check non-negativity.
- [ ] I can choose the correct integral limits for probabilities, means, and variances.
- [ ] I can solve percentile questions by area.
- [ ] I can move between PDF and CDF when the syllabus context requires it.
- [ ] I can handle a simple related variable using its CDF and support.
