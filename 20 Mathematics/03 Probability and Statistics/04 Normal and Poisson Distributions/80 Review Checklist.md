---
title: Normal and Poisson Distributions Review Checklist
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Normal and Poisson Distributions](00%20Overview.md)"
status: active
tags:
  - mathematics/statistics
  - review-checklist
---

# Normal and Poisson Distributions Review Checklist

Use this after the worked examples and practice problems. Revisit [Normal and Poisson Distributions Lecture Notes](10%20Lecture%20Notes.md) if any item is uncertain.

## Ideas to Recall

- [ ] $X\sim N(\mu,\sigma^2)$ uses variance in the second parameter, while standardisation uses $\sigma$.
- [ ] Normal probabilities are continuous areas, so $P(X=a)=0$.
- [ ] Inverse normal questions turn a given probability into a $z$ value before solving for the unknown boundary or parameter.
- [ ] $X\sim \operatorname{Po}(\lambda)$ has $P(X=r)=\frac{e^{-\lambda}\lambda^r}{r!}$ for $r=0,1,2,\ldots$.
- [ ] For a Poisson variable, $E(X)=\operatorname{Var}(X)=\lambda$.
- [ ] A Poisson rate must be scaled when the time, distance, area, or volume interval changes.
- [ ] $B(n,p)\approx N(np,npq)$ when $np>5$ and $nq>5$.
- [ ] $B(n,p)\approx \operatorname{Po}(np)$ when $n>50$ and $np<5$ approximately.
- [ ] $\operatorname{Po}(\lambda)\approx N(\lambda,\lambda)$ when $\lambda$ is large enough, approximately $\lambda>15$.
- [ ] Independent normal linear combinations remain normal.
- [ ] The sum of independent Poisson variables is Poisson with parameter equal to the sum of parameters.

## Skills to Perform

- [ ] Sketch a normal curve and mark the required area before standardising.
- [ ] Calculate $z=\frac{x-\mu}{\sigma}$ using the standard deviation.
- [ ] Use normal tables or technology for lower tails, upper tails, intervals, and inverse probabilities.
- [ ] Solve for an unknown normal boundary, mean, or standard deviation from a probability statement.
- [ ] Calculate exact Poisson probabilities and cumulative probabilities by summing terms.
- [ ] Use complements for upper-tail Poisson probabilities.
- [ ] Scale a Poisson mean to the interval actually being counted.
- [ ] Choose between exact binomial, Poisson approximation, normal approximation to binomial, and normal approximation to Poisson.
- [ ] Apply continuity correction when a discrete distribution is approximated by a normal distribution.
- [ ] Find means, variances, and distributions for linear transformations and independent linear combinations.

## Common Errors to Avoid

- [ ] Standardising with $\sigma^2$ instead of $\sigma$.
- [ ] Reading $N(50,16)$ as standard deviation $16$.
- [ ] Forgetting to convert an upper-tail probability into a lower-tail percentile for inverse normal work.
- [ ] Using the original Poisson rate after the interval changes.
- [ ] Treating a Poisson model as automatic for every count, without checking independence and an approximately constant rate.
- [ ] Using a normal approximation to a binomial distribution when $np$ or $nq$ is too small.
- [ ] Forgetting the $0.5$ continuity correction for normal approximations to discrete variables.
- [ ] Adding or subtracting standard deviations instead of variances in independent linear combinations.
- [ ] Assuming $aX+bY$ is Poisson for arbitrary coefficients.

## Ready to Move On When

- [ ] I can identify the random variable, its distribution, and its parameter values before calculating.
- [ ] I can move both ways between $X$ and $Z$ for normal questions.
- [ ] I can solve inverse normal questions without losing the tail direction.
- [ ] I can scale a Poisson parameter and explain the modelling assumptions.
- [ ] I can select a syllabus-approved approximation and state why it is justified.
- [ ] I can place the continuity-corrected boundary on the correct side of a discrete event.
- [ ] I can compute the mean and variance of a linear combination and decide whether its distribution is normal, Poisson, or neither.
