---
title: Proof and Mathematical Induction Review Checklist
subject: Mathematics
syllabus:
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/11 Proof and Mathematical Induction/00 Overview|Proof and Mathematical Induction]]"
status: active
tags:
  - mathematics/pure
  - review-checklist
---

# Proof and Mathematical Induction Review Checklist

Use this after the worked examples and practice problems. Revisit [[20 Mathematics/01 Pure Mathematics/11 Proof and Mathematical Induction/10 Lecture Notes|Proof and Mathematical Induction Lecture Notes]] if any item is uncertain.

## Ideas to Recall

- [ ] This is a 9231 topic in the local syllabus route: section 1.7.
- [ ] Checking examples can suggest a conjecture, but it does not prove a universal statement.
- [ ] A valid induction proof needs a true base case and a valid implication from $P(k)$ to $P(k+1)$.
- [ ] The induction hypothesis is $P(k)$ for an arbitrary integer $k$ in the required range, not $P(k+1)$.
- [ ] The starting value matters; some results begin at $n=0$, $n=1$, or another specified integer.
- [ ] Divisibility proofs must show that the quotient is an integer.
- [ ] Inequality proofs must preserve the direction of the inequality at every step.
- [ ] In recurrence proofs, the induction step starts from the recurrence defining the next term.
- [ ] In matrix-power proofs, the induction step usually uses $A^{k+1}=A^kA$.
- [ ] In repeated differentiation, the induction step differentiates the assumed $k$th derivative.

## Skills to Perform

- [ ] State $P(n)$ precisely, including the range of $n$.
- [ ] Prove the base case with the first required value.
- [ ] Write the induction hypothesis explicitly and use it in the step.
- [ ] Derive the target expression for $P(k+1)$ without assuming it.
- [ ] Prove summation identities by adding the next term.
- [ ] Prove divisibility statements by rewriting the next expression using the assumed multiple.
- [ ] Prove recurrence formulae by substituting the induction hypothesis into the recurrence.
- [ ] Prove matrix-power formulae by multiplying by the base matrix in the correct order.
- [ ] Prove repeated-derivative formulae by differentiating the induction hypothesis.
- [ ] Form a conjecture from first cases and then prove it by induction.
- [ ] Identify why a proposed induction proof is invalid.

## Common Errors to Avoid

- [ ] Omitting the base case.
- [ ] Proving only $P(1)$, $P(2)$, and $P(3)$.
- [ ] Assuming $P(k+1)$ instead of deriving it.
- [ ] Forgetting to state that $k$ is an integer in the required range.
- [ ] Starting at the wrong value of $n$.
- [ ] Not using the induction hypothesis anywhere in the step.
- [ ] Treating a false base case as harmless because the implication works.
- [ ] Losing an integer condition in a divisibility proof.
- [ ] Changing the statement being proved halfway through.

## Ready to Move On When

- [ ] I can write a complete induction proof without using template filler.
- [ ] I can explain exactly where the induction hypothesis is used.
- [ ] I can choose the right starting value before doing algebra.
- [ ] I can handle sums, divisibility, recurrences, matrix powers, inequalities, and repeated derivatives.
- [ ] I can diagnose a flawed induction proof and say which logical link failed.
