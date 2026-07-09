---
title: Proof and Mathematical Induction Key Practice Problems
subject: Mathematics
syllabus:
  - 9231
parent: "[Proof and Mathematical Induction](00%20Overview.md)"
status: active
tags:
  - mathematics/pure
  - practice
---

# Proof and Mathematical Induction Key Practice Problems

Work these without looking at the solutions first. In every induction proof,
state the base case, induction hypothesis, induction step, and conclusion.

## A. Core Induction Structure

1. Prove that, for all positive integers $n$,

   $$
   1+3+5+\cdots+(2n-1)=n^2.
   $$

2. Prove that, for all positive integers $n$,

   $$
   \sum_{r=1}^{n}r^2=\frac{n(n+1)(2n+1)}{6}.
   $$

3. For $x\ne1$, prove that, for all integers $n\ge0$,

   $$
   \sum_{r=0}^{n}x^r=\frac{1-x^{n+1}}{1-x}.
   $$

4. Prove that, for all positive integers $n$,

   $$
   \sum_{r=1}^{n}\frac{1}{r(r+1)}=\frac{n}{n+1}.
   $$

5. Prove that, for all positive integers $n$,

   $$
   \sum_{r=1}^{n}r^3=\frac{n^2(n+1)^2}{4}.
   $$

## B. Divisibility and Inequalities

6. Prove that $7^n-1$ is divisible by $6$ for all positive integers $n$.

7. Prove that

   $$
   4^n+15n-1
   $$

   is divisible by $9$ for all positive integers $n$.

8. Prove that

   $$
   n!>2^n
   $$

   for all integers $n\ge4$.

9. Prove that

   $$
   2^n\ge n+1
   $$

   for all integers $n\ge0$.

## C. Recurrences and Matrix Powers

10. A sequence is defined by

    $$
    u_{n+1}=3u_n-1,\qquad u_1=1.
    $$

    Prove that

    $$
    u_n=\frac{3^{n-1}+1}{2}
    $$

    for all positive integers $n$.

11. A sequence is defined by

    $$
    v_{n+1}=2v_n+1,\qquad v_1=1.
    $$

    Prove that

    $$
    v_n=2^n-1
    $$

    for all positive integers $n$.

12. A sequence is defined by

    $$
    w_{n+1}=\frac{w_n}{w_n+1},\qquad w_1=1.
    $$

    Conjecture a formula for $w_n$ from the first few terms and prove it.

13. Let

    $$
    M=\begin{pmatrix}1&1\\0&1\end{pmatrix}.
    $$

    Prove that

    $$
    M^n=\begin{pmatrix}1&n\\0&1\end{pmatrix}
    $$

    for all positive integers $n$.

14. Let

    $$
    D=\begin{pmatrix}2&0\\0&3\end{pmatrix}.
    $$

    Prove that

    $$
    D^n=\begin{pmatrix}2^n&0\\0&3^n\end{pmatrix}
    $$

    for all positive integers $n$.

## D. Derivatives, Conjectures, and Flaws

15. Prove that, for every positive integer $n$,

    $$
    \frac{d^n}{dx^n}(xe^{ax})
    =na^{n-1}e^{ax}+a^nxe^{ax},
    $$

    where $a$ is a constant.

16. Prove that, for every positive integer $n$,

    $$
    \frac{d^n}{dx^n}(e^x\sin x)
    =2^{n/2}e^x\sin\left(x+\frac{n\pi}{4}\right).
    $$

17. Let

    $$
    S_n=\sum_{r=1}^{n}r\cdot r!.
    $$

    Find a conjecture for $S_n$ from the first few values and prove it.

18. A student claims that checking a formula for $n=1,2,3,4$ proves it for all
    positive integers. Explain why this is not a proof, and state what an
    induction proof would still need.

19. A student proves that if

    $$
    2+4+\cdots+2k=k^2+k+2,
    $$

    then

    $$
    2+4+\cdots+2k+2(k+1)=(k+1)^2+(k+1)+2.
    $$

    Explain why this does not prove

    $$
    2+4+\cdots+2n=n^2+n+2
    $$

    for all positive integers $n$.

20. A student writes, "Assume $P(k+1)$ is true. Therefore $P(n)$ is true for
    all positive integers $n$." Explain the flaw and rewrite the induction
    hypothesis correctly.
