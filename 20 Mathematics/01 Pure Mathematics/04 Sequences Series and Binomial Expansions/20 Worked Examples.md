---
title: Sequences, Series and Binomial Expansions Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Sequences, Series and Binomial Expansions](00%20Overview.md)"
status: active
tags:
  - mathematics/pure
  - worked-examples
---

# Sequences, Series and Binomial Expansions Worked Examples

These examples model the standard CAIE route through arithmetic progressions,
geometric progressions, finite and infinite sums, binomial coefficients,
non-integer binomial expansions, standard sums, and method of differences.

## Source Route

- Syllabus: CAIE Mathematics 9709 sections 1.6 and 3.1; CAIE Further
  Mathematics 9231 section 1.3.
- Main subtopics: arithmetic and geometric progressions, finite and infinite
  geometric sums, positive-integer binomial expansions, non-integer binomial
  expansions with validity conditions, partial fractions, standard sums, and
  telescoping series.
- Coursebook route: 9709 Pure Mathematics 1 Chapter 6; 9709 Pure Mathematics
  2 and 3 Chapter 7; 9231 summation of series.

## Example 1: Arithmetic Progression From Two Terms

**Prompt.** An arithmetic progression has $u_5=18$ and $u_{12}=46$. Find the
first term, the common difference, and $S_{20}$.

**Solution.**

For an arithmetic progression,

$$
u_n=a+(n-1)d.
$$

The two given terms give

$$
a+4d=18
$$

and

$$
a+11d=46.
$$

Subtract:

$$
7d=28,
$$

so

$$
d=4.
$$

Then

$$
a+4(4)=18,
$$

so

$$
a=2.
$$

The sum of the first $20$ terms is

$$
S_{20}=\frac{20}{2}\left(2a+19d\right)
=10(4+76)
=800.
$$

**What this example trains.** Use $u_n$ for terms and $S_n$ for sums; do not
mix the two formulae.

## Example 2: Geometric Progression and Sum to Infinity

**Prompt.** A geometric progression has first term $12$ and common ratio
$-\frac{1}{3}$. Find $u_5$, $S_5$, and $S_\infty$.

**Solution.**

For a geometric progression,

$$
u_n=ar^{n-1}.
$$

So

$$
u_5=12\left(-\frac{1}{3}\right)^4
=\frac{4}{27}.
$$

The finite sum is

$$
S_5=\frac{a(1-r^5)}{1-r}
=\frac{12\left(1-\left(-\frac{1}{3}\right)^5\right)}
{1+\frac{1}{3}}.
$$

This gives

$$
S_5=\frac{244}{27}.
$$

Since

$$
\left|-\frac{1}{3}\right|<1,
$$

the infinite sum exists:

$$
S_\infty=\frac{a}{1-r}
=\frac{12}{1+\frac{1}{3}}
=9.
$$

**What this example trains.** Infinite geometric sums are only valid after
checking $|r|<1$.

## Example 3: Binomial Coefficient Without Full Expansion

**Prompt.** Find the coefficient of $x^2$ in

$$
(3-2x)^6.
$$

**Solution.**

The general term is

$$
T_{r+1}=\binom{6}{r}3^{6-r}(-2x)^r.
$$

For the coefficient of $x^2$, use $r=2$:

$$
\binom{6}{2}3^4(-2)^2
=15\cdot81\cdot4
=4860.
$$

So the coefficient of $x^2$ is

$$
4860.
$$

**What this example trains.** The term containing $x^r$ is the $(r+1)$th
binomial term when the second part contains $x$.

## Example 4: Constant Term With Negative Powers

**Prompt.** Find the constant term in

$$
\left(2x-\frac{1}{x}\right)^6.
$$

**Solution.**

The general term is

$$
T_{r+1}=\binom{6}{r}(2x)^{6-r}\left(-\frac{1}{x}\right)^r.
$$

The power of $x$ is

$$
(6-r)-r=6-2r.
$$

For a constant term,

$$
6-2r=0,
$$

so

$$
r=3.
$$

The constant term is

$$
\binom{6}{3}2^3(-1)^3=-160.
$$

**What this example trains.** Track the power of $x$ first; only then compute
the coefficient.

## Example 5: Non-Integer Binomial Expansion

**Prompt.** Expand

$$
(1-2x)^{-\frac{1}{2}}
$$

up to and including the term in $x^3$, and state the validity condition.

**Solution.**

Use

$$
(1+u)^n
=1+nu+\frac{n(n-1)}{2!}u^2
+\frac{n(n-1)(n-2)}{3!}u^3+\cdots.
$$

Here

$$
n=-\frac{1}{2},\qquad u=-2x.
$$

Therefore

$$
(1-2x)^{-\frac{1}{2}}
=1+x+\frac{3}{2}x^2+\frac{5}{2}x^3+\cdots.
$$

The validity condition is

$$
|-2x|<1,
$$

so

$$
|x|<\frac{1}{2}.
$$

**What this example trains.** For non-integer powers, the expansion is infinite
and the validity condition must be stated.

## Example 6: Rewriting Before Expanding

**Prompt.** Expand

$$
(4+x)^{-2}
$$

up to and including the term in $x^3$.

**Solution.**

Factor out $4$ first:

$$
(4+x)^{-2}
=4^{-2}\left(1+\frac{x}{4}\right)^{-2}
=\frac{1}{16}\left(1+\frac{x}{4}\right)^{-2}.
$$

Now use

$$
(1+u)^{-2}=1-2u+3u^2-4u^3+\cdots.
$$

With $u=\frac{x}{4}$,

$$
(4+x)^{-2}
=\frac{1}{16}-\frac{x}{32}+\frac{3x^2}{256}-\frac{x^3}{256}+\cdots.
$$

The validity condition is

$$
\left|\frac{x}{4}\right|<1,
$$

or

$$
|x|<4.
$$

**What this example trains.** Non-integer binomial expansions need the form
$(1+u)^n$, not just any binomial expression.

## Example 7: Standard Sums

**Prompt.** Find

$$
\sum_{r=1}^{n}(3r^2-2r+1).
$$

**Solution.**

Use linearity:

$$
\sum_{r=1}^{n}(3r^2-2r+1)
=3\sum_{r=1}^{n}r^2-2\sum_{r=1}^{n}r+\sum_{r=1}^{n}1.
$$

Substitute the standard sums:

$$
=3\cdot\frac{n(n+1)(2n+1)}{6}
-2\cdot\frac{n(n+1)}{2}
+n.
$$

Simplifying gives

$$
\sum_{r=1}^{n}(3r^2-2r+1)
=\frac{n(2n^2+n+1)}{2}.
$$

**What this example trains.** Expand and collect into standard sums before
trying to simplify.

## Example 8: Method of Differences

**Prompt.** Find

$$
\sum_{r=1}^{n}\frac{1}{r(r+1)}
$$

and hence find the sum to infinity.

**Solution.**

Use partial fractions:

$$
\frac{1}{r(r+1)}=\frac{1}{r}-\frac{1}{r+1}.
$$

So

$$
S_n=
\left(1-\frac{1}{2}\right)
+\left(\frac{1}{2}-\frac{1}{3}\right)
+\cdots
+\left(\frac{1}{n}-\frac{1}{n+1}\right).
$$

All middle terms cancel:

$$
S_n=1-\frac{1}{n+1}
=\frac{n}{n+1}.
$$

As $n\to\infty$,

$$
S_n\to1.
$$

So the sum to infinity is

$$
1.
$$

**What this example trains.** Write enough terms to see the cancellation.

## Example 9: A Telescoping Sum With Delayed Cancellation

**Prompt.** Find

$$
\sum_{r=1}^{n}\frac{2}{(r+1)(r+3)}
$$

and its sum to infinity.

**Solution.**

Decompose:

$$
\frac{2}{(r+1)(r+3)}
=\frac{1}{r+1}-\frac{1}{r+3}.
$$

Therefore

$$
S_n=
\left(\frac{1}{2}-\frac{1}{4}\right)
+\left(\frac{1}{3}-\frac{1}{5}\right)
+\cdots
+\left(\frac{1}{n+1}-\frac{1}{n+3}\right).
$$

The surviving terms are

$$
S_n=\frac{1}{2}+\frac{1}{3}-\frac{1}{n+2}-\frac{1}{n+3}.
$$

Thus

$$
S_n=\frac{5}{6}-\frac{1}{n+2}-\frac{1}{n+3}.
$$

As $n\to\infty$, the last two terms tend to $0$, so

$$
S_\infty=\frac{5}{6}.
$$

**What this example trains.** Telescoping sums do not always leave only the
first and last term; delayed cancellation can leave several boundary terms.

## Example 10: Partial Fractions Before a Binomial Expansion

**Prompt.** Expand

$$
\frac{1}{(1-x)(2+x)}
$$

up to and including the term in $x^2$, and state the validity condition.

**Solution.**

First decompose:

$$
\frac{1}{(1-x)(2+x)}
=\frac{A}{1-x}+\frac{B}{2+x}.
$$

Then

$$
1=A(2+x)+B(1-x).
$$

Comparing coefficients gives

$$
A=B=\frac{1}{3}.
$$

So

$$
\frac{1}{(1-x)(2+x)}
=\frac{1}{3}\left(\frac{1}{1-x}+\frac{1}{2+x}\right).
$$

Now

$$
\frac{1}{1-x}=1+x+x^2+\cdots
$$

and

$$
\frac{1}{2+x}
=\frac{1}{2}\left(1+\frac{x}{2}\right)^{-1}
=\frac{1}{2}\left(1-\frac{x}{2}+\frac{x^2}{4}+\cdots\right).
$$

Hence

$$
\frac{1}{(1-x)(2+x)}
=\frac{1}{2}+\frac{x}{4}+\frac{3x^2}{8}+\cdots.
$$

The two series require $|x|<1$ and $|x|<2$, so the combined validity condition
is

$$
|x|<1.
$$

**What this example trains.** Partial fractions can turn one awkward rational
function into binomial expansions with clear validity conditions.
