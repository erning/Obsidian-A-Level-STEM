---
title: Proof and Mathematical Induction Worked Examples
subject: Mathematics
syllabus:
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/11 Proof and Mathematical Induction/00 Overview|Proof and Mathematical Induction]]"
status: active
tags:
  - mathematics/pure
  - worked-examples
---

# Proof and Mathematical Induction Worked Examples

These examples model the 9231 route through mathematical induction: proving a
given result, proving divisibility, handling recurrences, proving inequalities,
working with matrix powers and derivatives, and forming a conjecture before
proving it.

## Source Route

- Syllabus: CAIE Further Mathematics 9231 section 1.7.
- Main requirements: use mathematical induction to establish a given result;
  recognise when limited trials suggest a conjecture and then prove the
  conjecture by induction.
- Coursebook route: Hodder Further Pure Mathematics 1 Chapter 2 sections 2.4
  and 2.5.

## Example 1: A Summation Formula

**Prompt.** Prove that, for all positive integers $n$,

$$
\sum_{r=1}^{n}r^2=\frac{n(n+1)(2n+1)}{6}.
$$

**Solution.**

Let $P(n)$ be the statement

$$
\sum_{r=1}^{n}r^2=\frac{n(n+1)(2n+1)}{6}.
$$

For $n=1$,

$$
\sum_{r=1}^{1}r^2=1
$$

and

$$
\frac{1(2)(3)}{6}=1.
$$

So $P(1)$ is true.

Assume $P(k)$ is true for some integer $k\ge1$:

$$
\sum_{r=1}^{k}r^2=\frac{k(k+1)(2k+1)}{6}.
$$

Then

$$
\sum_{r=1}^{k+1}r^2
=\sum_{r=1}^{k}r^2+(k+1)^2.
$$

Use the induction hypothesis:

$$
\sum_{r=1}^{k+1}r^2
=\frac{k(k+1)(2k+1)}{6}+(k+1)^2.
$$

Factor and simplify:

$$
\sum_{r=1}^{k+1}r^2
=\frac{(k+1)(k(2k+1)+6(k+1))}{6}
$$

$$
=\frac{(k+1)(2k^2+7k+6)}{6}
$$

$$
=\frac{(k+1)(k+2)(2k+3)}{6}.
$$

This is the required formula for $P(k+1)$:

$$
\frac{(k+1)((k+1)+1)(2(k+1)+1)}{6}.
$$

Therefore, by induction, the formula is true for all positive integers $n$.

**What this example trains.** In a summation proof, the induction step usually
adds the next term.

## Example 2: A Divisibility Result

**Prompt.** Prove that $7^n-1$ is divisible by $6$ for all positive integers
$n$.

**Solution.**

For $n=1$,

$$
7^1-1=6,
$$

which is divisible by $6$.

Assume that $7^k-1$ is divisible by $6$ for some integer $k\ge1$. Then

$$
7^k-1=6m
$$

for some integer $m$.

Now

$$
7^{k+1}-1=7\cdot7^k-1.
$$

Write this in terms of $7^k-1$:

$$
7^{k+1}-1=7(7^k-1)+6.
$$

Using the induction hypothesis,

$$
7^{k+1}-1=7(6m)+6=6(7m+1).
$$

Since $7m+1$ is an integer, $7^{k+1}-1$ is divisible by $6$.

Therefore, by induction, $7^n-1$ is divisible by $6$ for all positive
integers $n$.

**What this example trains.** A divisibility induction must say that the
quotient is an integer.

## Example 3: A Recurrence Formula

**Prompt.** A sequence is defined by

$$
u_{n+1}=3u_n-1,\qquad u_1=1.
$$

Prove that

$$
u_n=\frac{3^{n-1}+1}{2}
$$

for all positive integers $n$.

**Solution.**

For $n=1$,

$$
\frac{3^0+1}{2}=1=u_1.
$$

Assume

$$
u_k=\frac{3^{k-1}+1}{2}
$$

for some integer $k\ge1$.

Using the recurrence,

$$
u_{k+1}=3u_k-1.
$$

Substitute the induction hypothesis:

$$
u_{k+1}=3\left(\frac{3^{k-1}+1}{2}\right)-1.
$$

So

$$
u_{k+1}=\frac{3^k+3-2}{2}
=\frac{3^k+1}{2}.
$$

This is the required formula with $n=k+1$. Therefore the formula is true for
all positive integers $n$.

**What this example trains.** For a recurrence, the induction step starts from
the recurrence definition of the next term.

## Example 4: An Inequality

**Prompt.** Prove that

$$
n!>2^n
$$

for all integers $n\ge4$.

**Solution.**

For $n=4$,

$$
4!=24>16=2^4.
$$

Assume $k!>2^k$ for some integer $k\ge4$.

Then

$$
(k+1)!=(k+1)k!.
$$

Using the induction hypothesis,

$$
(k+1)!>(k+1)2^k.
$$

Since $k\ge4$, $k+1>2$. Hence

$$
(k+1)2^k>2\cdot2^k=2^{k+1}.
$$

Therefore

$$
(k+1)!>2^{k+1}.
$$

By induction, $n!>2^n$ for all integers $n\ge4$.

**What this example trains.** For inequalities, keep the direction valid and
use the starting range.

## Example 5: A Matrix Power

**Prompt.** Let

$$
M=\begin{pmatrix}1&1\\0&1\end{pmatrix}.
$$

Prove that

$$
M^n=\begin{pmatrix}1&n\\0&1\end{pmatrix}
$$

for all positive integers $n$.

**Solution.**

For $n=1$,

$$
M^1=\begin{pmatrix}1&1\\0&1\end{pmatrix},
$$

so the result is true.

Assume that

$$
M^k=\begin{pmatrix}1&k\\0&1\end{pmatrix}
$$

for some integer $k\ge1$.

Then

$$
M^{k+1}=M^kM.
$$

Using the induction hypothesis,

$$
M^{k+1}
=
\begin{pmatrix}1&k\\0&1\end{pmatrix}
\begin{pmatrix}1&1\\0&1\end{pmatrix}
=
\begin{pmatrix}1&k+1\\0&1\end{pmatrix}.
$$

This is the required formula for $n=k+1$. Therefore the formula is true for
all positive integers $n$.

**What this example trains.** Matrix-power induction uses
$M^{k+1}=M^kM$ and then multiplies matrices carefully.

## Example 6: Repeated Differentiation

**Prompt.** Prove that, for every positive integer $n$,

$$
\frac{d^n}{dx^n}(xe^{ax})
=na^{n-1}e^{ax}+a^nxe^{ax},
$$

where $a$ is a constant.

**Solution.**

For $n=1$,

$$
\frac{d}{dx}(xe^{ax})=e^{ax}+axe^{ax}.
$$

The formula gives

$$
1\cdot a^0e^{ax}+a^1xe^{ax}=e^{ax}+axe^{ax},
$$

so the base case is true.

Assume the formula is true for $n=k$:

$$
\frac{d^k}{dx^k}(xe^{ax})
=ka^{k-1}e^{ax}+a^kxe^{ax}.
$$

Differentiate both sides:

$$
\frac{d^{k+1}}{dx^{k+1}}(xe^{ax})
=ka^ke^{ax}+a^ke^{ax}+a^{k+1}xe^{ax}.
$$

So

$$
\frac{d^{k+1}}{dx^{k+1}}(xe^{ax})
=(k+1)a^ke^{ax}+a^{k+1}xe^{ax}.
$$

This is the required formula for $n=k+1$. Therefore the result is true for all
positive integers $n$.

**What this example trains.** Repeated-differentiation induction often proves
the next derivative by differentiating the induction hypothesis.

## Example 7: Conjecture Before Proof

**Prompt.** Let

$$
S_n=\sum_{r=1}^{n}r\cdot r!.
$$

Find a conjecture for $S_n$, then prove it.

**Solution.**

Compute the first few values:

$$
S_1=1\cdot1!=1=2!-1,
$$

$$
S_2=1+2\cdot2!=5=3!-1,
$$

$$
S_3=5+3\cdot3!=23=4!-1.
$$

This suggests

$$
S_n=(n+1)!-1.
$$

For $n=1$, the formula is true because $S_1=1=2!-1$.

Assume

$$
S_k=(k+1)!-1
$$

for some integer $k\ge1$.

Then

$$
S_{k+1}=S_k+(k+1)(k+1)!.
$$

Use the induction hypothesis:

$$
S_{k+1}=(k+1)!-1+(k+1)(k+1)!.
$$

Factor:

$$
S_{k+1}=(k+2)(k+1)!-1.
$$

Since

$$
(k+2)(k+1)!=(k+2)!,
$$

we get

$$
S_{k+1}=(k+2)!-1.
$$

Therefore $S_n=(n+1)!-1$ for all positive integers $n$.

**What this example trains.** Trial values can suggest a formula, but the
formula still needs a proof.

## Example 8: Why a Base Case Matters

**Prompt.** A student shows that if

$$
2+4+\cdots+2k=k^2+k+2,
$$

then

$$
2+4+\cdots+2k+2(k+1)=(k+1)^2+(k+1)+2.
$$

Explain why this does not prove the formula for all positive integers $n$.

**Solution.**

The implication alone is not enough. The base case must also be true.

For $n=1$, the left-hand side is

$$
2,
$$

but the right-hand side is

$$
1^2+1+2=4.
$$

So the base case is false. Even if the implication from $P(k)$ to $P(k+1)$ has
been shown correctly, there is no first true statement to start the chain.

**What this example trains.** A valid induction proof needs both a true base
case and a genuine implication from $P(k)$ to $P(k+1)$.
