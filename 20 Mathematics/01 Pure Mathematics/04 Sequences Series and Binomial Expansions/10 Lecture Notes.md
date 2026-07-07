---
title: Sequences, Series and Binomial Expansions Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/04 Sequences Series and Binomial Expansions/00 Overview|Sequences, Series and Binomial Expansions]]"
status: active
tags:
  - mathematics/pure
  - lecture-notes
---

# Sequences, Series and Binomial Expansions Lecture Notes

This topic studies structure in ordered quantities. A sequence records terms in order; a series adds them; a binomial expansion turns a power such as $(a+b)^n$ into a structured sum of terms. The common habit is to identify the pattern before calculating.

Keep the distinction between a term and a sum visible throughout this note. Many errors in this topic come from confusing $u_n$, the $n$th term, with $S_n$, the sum of the first $n$ terms.

## Source Route

- 9709 1.6 Series
- 9709 3.1 Algebra, for non-integer binomial expansions
- 9231 1.3 Summation of series
- Coursebook route: 9709 Pure Mathematics 1 Chapter 6; 9709 Pure Mathematics 2 and 3 Chapter 7; 9231 Further Mathematics content on summation of series.

## Visual Guide

![[assets/generated/mathematics/sequences-series-and-binomial-expansions.svg]]

Figure: The guide compares arithmetic accumulation, geometric growth, and binomial terms. Use it to remember that this topic is about recognising structure before expanding or summing.

## 1. Sequences and Series

A sequence is an ordered list of terms

$$
u_1,u_2,u_3,\ldots.
$$

A series is a sum of terms

$$
u_1+u_2+u_3+\cdots.
$$

The sum of the first $n$ terms is usually written as $S_n$:

$$
S_n=u_1+u_2+\cdots+u_n.
$$

When reading a question, first decide whether it asks for:

- a term such as $u_n$;
- a finite sum such as $S_n$;
- an infinite sum such as $S_\infty$;
- a coefficient or term in a binomial expansion.

## 2. Arithmetic Progressions

An arithmetic progression has a constant difference. If the first term is $a$ and the common difference is $d$, then

$$
u_n=a+(n-1)d.
$$

The sum of the first $n$ terms is

$$
S_n=\frac{n}{2}\left(2a+(n-1)d\right).
$$

If the last term is $l$, then the same sum can be written as

$$
S_n=\frac{n}{2}(a+l).
$$

This second formula says: number of terms multiplied by the average of the first and last terms.

Three numbers $a$, $b$, and $c$ are in arithmetic progression exactly when

$$
2b=a+c.
$$

This condition is often quicker than introducing $d$ explicitly.

## 3. Geometric Progressions

A geometric progression has a constant ratio. If the first term is $a$ and the common ratio is $r$, then

$$
u_n=ar^{n-1}.
$$

The sum of the first $n$ terms is

$$
S_n=\frac{a(1-r^n)}{1-r},\qquad r\ne1.
$$

An equivalent form is

$$
S_n=\frac{a(r^n-1)}{r-1},\qquad r\ne1.
$$

Use whichever version keeps the signs clean.

Three numbers $a$, $b$, and $c$ are in geometric progression exactly when

$$
b^2=ac.
$$

For an infinite geometric series, the sum to infinity exists only when

$$
|r|<1.
$$

Then

$$
S_\infty=\frac{a}{1-r}.
$$

Always check $|r|<1$ before using this formula. If $r=1.2$ or $r=-2$, the terms do not tend to $0$, so the infinite sum cannot settle to a finite value.

## 4. Sigma Notation and Standard Sums

Sigma notation is compact addition:

$$
\sum_{r=1}^{n}u_r=u_1+u_2+\cdots+u_n.
$$

It is linear:

$$
\sum_{r=1}^{n}(au_r+bv_r)=a\sum_{r=1}^{n}u_r+b\sum_{r=1}^{n}v_r.
$$

The standard sums used in 9231 are

$$
\sum_{r=1}^{n}r=\frac{n(n+1)}{2},
$$

$$
\sum_{r=1}^{n}r^2=\frac{n(n+1)(2n+1)}{6},
$$

and

$$
\sum_{r=1}^{n}r^3=\left(\frac{n(n+1)}{2}\right)^2.
$$

These let you sum many polynomial expressions by expanding and collecting powers of $r$.

For example,

$$
\sum_{r=1}^{n}(3r^2-2r+1)
=3\sum_{r=1}^{n}r^2-2\sum_{r=1}^{n}r+\sum_{r=1}^{n}1.
$$

## 5. Method of Differences

The method of differences, also called telescoping, works when a general term can be written as the difference of two consecutive-looking expressions:

$$
u_r=f(r)-f(r+1).
$$

Then

$$
\sum_{r=1}^{n}u_r
=\left(f(1)-f(2)\right)+\left(f(2)-f(3)\right)+\cdots+\left(f(n)-f(n+1)\right),
$$

so most middle terms cancel, leaving

$$
S_n=f(1)-f(n+1).
$$

Partial fractions often create this structure. For instance,

$$
\frac{1}{r(r+1)}=\frac{1}{r}-\frac{1}{r+1}.
$$

Therefore

$$
\sum_{r=1}^{n}\frac{1}{r(r+1)}
=1-\frac{1}{n+1}.
$$

If the remaining term tends to $0$ as $n\to\infty$, you can also find a sum to infinity.

## 6. Binomial Expansion for Positive Integer Powers

For a positive integer $n$,

$$
(a+b)^n=\sum_{r=0}^{n}\binom{n}{r}a^{n-r}b^r.
$$

The binomial coefficient is

$$
\binom{n}{r}=\frac{n!}{r!(n-r)!}.
$$

The term involving $b^r$ is the $(r+1)$th term:

$$
T_{r+1}=\binom{n}{r}a^{n-r}b^r.
$$

The index shift is important. When $r=0$, you are at the first term. When a question asks for the coefficient of $x^k$, identify which value of $r$ produces $x^k$ instead of expanding everything.

Example: the term in $x^2$ in $(1+x)^5$ comes from $r=2$:

$$
\binom{5}{2}x^2=10x^2.
$$

## 7. Non-Integer Binomial Expansions

For non-integer powers, the expansion becomes infinite:

$$
(1+x)^n
=1+nx+\frac{n(n-1)}{2!}x^2
+\frac{n(n-1)(n-2)}{3!}x^3+\cdots.
$$

The validity condition is

$$
|x|<1.
$$

For example,

$$
(1-3x)^{-2}
$$

is expanded by replacing $x$ with $-3x$, so the validity condition is

$$
|-3x|<1,
$$

or

$$
|x|<\frac{1}{3}.
$$

For an expression such as $(a+x)^n$, factor out $a$ first:

$$
(a+x)^n=a^n\left(1+\frac{x}{a}\right)^n.
$$

The validity condition becomes

$$
\left|\frac{x}{a}\right|<1.
$$

Non-integer binomial expansions are often used for approximation. The smaller $|x|$ is, the faster the terms usually decrease. State how many terms you are using and keep the validity condition visible.

## Worked-Thinking Routines

### Progressions

1. Decide whether the pattern has a constant difference or a constant ratio.
2. Identify $a$, $d$ or $r$, and what the question asks for.
3. Use $u_n$ for a term and $S_n$ for a sum.
4. For an infinite geometric sum, check $|r|<1$ first.
5. Substitute back into the original wording to check the result.

### Sigma Sums

1. Write out the first few terms if the pattern is not obvious.
2. Expand polynomial expressions in $r$.
3. Use linearity and standard sums.
4. For rational terms, try partial fractions and look for telescoping.
5. Check whether the final expression is for $S_n$ or $S_\infty$.

### Binomial Expansions

1. Identify whether the power is a positive integer.
2. If it is a positive integer, use the finite binomial theorem.
3. If it is not a positive integer, rewrite the expression in the form $(1+x)^n$.
4. State the validity condition.
5. Find the required term or coefficient without unnecessary expansion.

## Common Mistakes

- Confusing $u_n$ with $S_n$.
- Using an infinite geometric sum when $|r|\ge1$.
- Treating $r=1$ as allowed in the geometric finite-sum formula.
- Mixing the $(r+1)$th binomial term with the $r$th term.
- Forgetting that non-integer binomial expansions are infinite.
- Omitting the validity condition for a non-integer binomial expansion.
- Expanding a whole binomial when only one coefficient is needed.
- Missing cancellations in a telescoping series.

## Quick Self-Check

You are ready to move on when you can:

- Tell from a pattern whether it is arithmetic, geometric, or neither.
- Derive and use $u_n$ and $S_n$ for arithmetic and geometric progressions.
- Explain why $S_\infty=\frac{a}{1-r}$ requires $|r|<1$.
- Use sigma notation and the standard sums for $r$, $r^2$, and $r^3$.
- Recognise a telescoping series after partial fractions.
- Find a specified coefficient in a binomial expansion without expanding every term.
- State and use the validity condition for a non-integer binomial expansion.

## Connections

- [[20 Mathematics/01 Pure Mathematics/11 Proof and Mathematical Induction/00 Overview|Proof and Mathematical Induction]]
- [[20 Mathematics/01 Pure Mathematics/13 Further Calculus and Differential Equations/00 Overview|Further Calculus and Differential Equations]]
