---
title: Proof and Mathematical Induction Key Practice Solutions
subject: Mathematics
syllabus:
  - 9231
parent: "[Proof and Mathematical Induction](00%20Overview.md)"
status: active
tags:
  - mathematics/pure
  - solutions
---

# Proof and Mathematical Induction Key Practice Solutions

This note gives worked solutions for [Proof and Mathematical Induction Key Practice Problems](30%20Key%20Practice%20Problems.md). Check that each induction proof has a valid starting case, a clearly stated hypothesis, a real step from $k$ to $k+1$, and a conclusion with the correct range.

## A. Core Induction Structure

### Problem 1

For $n=1$,

$$
1=1^2,
$$

so the result is true.

Assume, for some integer $k\ge1$, that

$$
1+3+\cdots+(2k-1)=k^2.
$$

Then

$$
1+3+\cdots+(2k-1)+(2(k+1)-1)
=k^2+2k+1
=(k+1)^2.
$$

So the result is true for $k+1$. Therefore, by induction,

$$
1+3+\cdots+(2n-1)=n^2
$$

for all positive integers $n$.

### Problem 2

For $n=1$,

$$
\sum_{r=1}^{1}r^2=1
$$

and

$$
\frac{1(2)(3)}{6}=1.
$$

Assume, for some integer $k\ge1$, that

$$
\sum_{r=1}^{k}r^2=\frac{k(k+1)(2k+1)}{6}.
$$

Then

$$
\sum_{r=1}^{k+1}r^2
=\frac{k(k+1)(2k+1)}{6}+(k+1)^2.
$$

So

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

This is

$$
\frac{(k+1)((k+1)+1)(2(k+1)+1)}{6}.
$$

Therefore the formula is true for all positive integers $n$.

### Problem 3

For $n=0$,

$$
\sum_{r=0}^{0}x^r=1
$$

and

$$
\frac{1-x}{1-x}=1,
$$

since $x\ne1$.

Assume, for some integer $k\ge0$, that

$$
\sum_{r=0}^{k}x^r=\frac{1-x^{k+1}}{1-x}.
$$

Then

$$
\sum_{r=0}^{k+1}x^r
=\frac{1-x^{k+1}}{1-x}+x^{k+1}.
$$

Put over the same denominator:

$$
\sum_{r=0}^{k+1}x^r
=\frac{1-x^{k+1}+x^{k+1}(1-x)}{1-x}
=\frac{1-x^{k+2}}{1-x}.
$$

This is the formula with $n=k+1$. Therefore the result is true for all
integers $n\ge0$.

### Problem 4

For $n=1$,

$$
\sum_{r=1}^{1}\frac{1}{r(r+1)}=\frac12
$$

and

$$
\frac{1}{1+1}=\frac12.
$$

Assume

$$
\sum_{r=1}^{k}\frac{1}{r(r+1)}=\frac{k}{k+1}
$$

for some integer $k\ge1$. Then

$$
\sum_{r=1}^{k+1}\frac{1}{r(r+1)}
=\frac{k}{k+1}+\frac{1}{(k+1)(k+2)}.
$$

So

$$
\sum_{r=1}^{k+1}\frac{1}{r(r+1)}
=\frac{k(k+2)+1}{(k+1)(k+2)}
=\frac{(k+1)^2}{(k+1)(k+2)}
=\frac{k+1}{k+2}.
$$

This is the required result for $k+1$. Therefore the formula is true for all
positive integers $n$.

### Problem 5

For $n=1$,

$$
\sum_{r=1}^{1}r^3=1
$$

and

$$
\frac{1^2(2)^2}{4}=1.
$$

Assume

$$
\sum_{r=1}^{k}r^3=\frac{k^2(k+1)^2}{4}.
$$

Then

$$
\sum_{r=1}^{k+1}r^3
=\frac{k^2(k+1)^2}{4}+(k+1)^3.
$$

Factor $(k+1)^2$:

$$
\sum_{r=1}^{k+1}r^3
=(k+1)^2\left(\frac{k^2}{4}+k+1\right).
$$

So

$$
\sum_{r=1}^{k+1}r^3
=(k+1)^2\frac{(k+2)^2}{4}.
$$

This is the required formula for $k+1$. Therefore the result is true for all
positive integers $n$.

## B. Divisibility and Inequalities

### Problem 6

For $n=1$,

$$
7^1-1=6,
$$

which is divisible by $6$.

Assume

$$
7^k-1=6m
$$

for some integers $k\ge1$ and $m$. Then

$$
7^{k+1}-1=7(7^k-1)+6=7(6m)+6=6(7m+1).
$$

Since $7m+1$ is an integer, $7^{k+1}-1$ is divisible by $6$. Therefore the
result is true for all positive integers $n$.

### Problem 7

For $n=1$,

$$
4^1+15(1)-1=18,
$$

which is divisible by $9$.

Assume

$$
4^k+15k-1=9m
$$

for some integers $k\ge1$ and $m$. Let

$$
A_n=4^n+15n-1.
$$

Then

$$
A_{k+1}=4^{k+1}+15(k+1)-1.
$$

Use

$$
A_{k+1}-4A_k
=4^{k+1}+15k+14-4(4^k+15k-1)
=18-45k.
$$

So

$$
A_{k+1}=4A_k+9(2-5k).
$$

Using $A_k=9m$,

$$
A_{k+1}=36m+9(2-5k)=9(4m+2-5k).
$$

The bracket is an integer, so $A_{k+1}$ is divisible by $9$. Therefore the
result is true for all positive integers $n$.

### Problem 8

For $n=4$,

$$
4!=24>16=2^4.
$$

Assume $k!>2^k$ for some integer $k\ge4$. Then

$$
(k+1)!=(k+1)k!>(k+1)2^k.
$$

Since $k+1>2$,

$$
(k+1)2^k>2\cdot2^k=2^{k+1}.
$$

Therefore $(k+1)!>2^{k+1}$. By induction, $n!>2^n$ for all integers
$n\ge4$.

### Problem 9

For $n=0$,

$$
2^0=1=0+1.
$$

Assume $2^k\ge k+1$ for some integer $k\ge0$. Then

$$
2^{k+1}=2\cdot2^k\ge2(k+1)=2k+2.
$$

Since

$$
2k+2\ge k+2
$$

for $k\ge0$, we have

$$
2^{k+1}\ge(k+1)+1.
$$

Therefore $2^n\ge n+1$ for all integers $n\ge0$.

## C. Recurrences and Matrix Powers

### Problem 10

For $n=1$,

$$
\frac{3^0+1}{2}=1=u_1.
$$

Assume

$$
u_k=\frac{3^{k-1}+1}{2}.
$$

Then

$$
u_{k+1}=3u_k-1
=3\left(\frac{3^{k-1}+1}{2}\right)-1
=\frac{3^k+1}{2}.
$$

This is the required formula for $k+1$. Therefore the formula is true for all
positive integers $n$.

### Problem 11

For $n=1$,

$$
2^1-1=1=v_1.
$$

Assume

$$
v_k=2^k-1.
$$

Then

$$
v_{k+1}=2v_k+1=2(2^k-1)+1=2^{k+1}-1.
$$

Therefore $v_n=2^n-1$ for all positive integers $n$.

### Problem 12

The first few terms are

$$
w_1=1,\qquad w_2=\frac12,\qquad w_3=\frac13.
$$

This suggests

$$
w_n=\frac1n.
$$

For $n=1$, this is true. Assume

$$
w_k=\frac1k
$$

for some integer $k\ge1$. Then

$$
w_{k+1}=\frac{w_k}{w_k+1}
=\frac{1/k}{1/k+1}
=\frac{1}{k+1}.
$$

Therefore $w_n=\dfrac1n$ for all positive integers $n$.

### Problem 13

For $n=1$,

$$
M^1=\begin{pmatrix}1&1\\0&1\end{pmatrix},
$$

so the formula is true.

Assume

$$
M^k=\begin{pmatrix}1&k\\0&1\end{pmatrix}.
$$

Then

$$
M^{k+1}=M^kM
=
\begin{pmatrix}1&k\\0&1\end{pmatrix}
\begin{pmatrix}1&1\\0&1\end{pmatrix}
=
\begin{pmatrix}1&k+1\\0&1\end{pmatrix}.
$$

Therefore the formula is true for all positive integers $n$.

### Problem 14

For $n=1$, the formula gives $D$ itself.

Assume

$$
D^k=\begin{pmatrix}2^k&0\\0&3^k\end{pmatrix}.
$$

Then

$$
D^{k+1}=D^kD
=
\begin{pmatrix}2^k&0\\0&3^k\end{pmatrix}
\begin{pmatrix}2&0\\0&3\end{pmatrix}
=
\begin{pmatrix}2^{k+1}&0\\0&3^{k+1}\end{pmatrix}.
$$

Therefore the formula is true for all positive integers $n$.

## D. Derivatives, Conjectures, and Flaws

### Problem 15

For $n=1$,

$$
\frac{d}{dx}(xe^{ax})=e^{ax}+axe^{ax},
$$

which matches

$$
1\cdot a^0e^{ax}+a^1xe^{ax}.
$$

Assume

$$
\frac{d^k}{dx^k}(xe^{ax})
=ka^{k-1}e^{ax}+a^kxe^{ax}.
$$

Differentiate:

$$
\frac{d^{k+1}}{dx^{k+1}}(xe^{ax})
=ka^ke^{ax}+a^ke^{ax}+a^{k+1}xe^{ax}.
$$

So

$$
\frac{d^{k+1}}{dx^{k+1}}(xe^{ax})
=(k+1)a^ke^{ax}+a^{k+1}xe^{ax}.
$$

Therefore the result is true for every positive integer $n$.

### Problem 16

For $n=1$,

$$
\frac{d}{dx}(e^x\sin x)=e^x(\sin x+\cos x).
$$

Since

$$
\sin x+\cos x=\sqrt2\sin\left(x+\frac{\pi}{4}\right),
$$

the formula is true for $n=1$.

Assume

$$
\frac{d^k}{dx^k}(e^x\sin x)
=2^{k/2}e^x\sin\left(x+\frac{k\pi}{4}\right).
$$

Differentiate:

$$
\frac{d^{k+1}}{dx^{k+1}}(e^x\sin x)
=2^{k/2}e^x
\left[
\sin\left(x+\frac{k\pi}{4}\right)
+\cos\left(x+\frac{k\pi}{4}\right)
\right].
$$

Use $\sin u+\cos u=\sqrt2\sin\left(u+\frac{\pi}{4}\right)$:

$$
\frac{d^{k+1}}{dx^{k+1}}(e^x\sin x)
=2^{(k+1)/2}e^x
\sin\left(x+\frac{(k+1)\pi}{4}\right).
$$

Therefore the result is true for every positive integer $n$.

### Problem 17

Compute the first few values:

$$
S_1=1=2!-1,
$$

$$
S_2=1+2\cdot2!=5=3!-1,
$$

$$
S_3=5+3\cdot3!=23=4!-1.
$$

Conjecture:

$$
S_n=(n+1)!-1.
$$

For $n=1$, this is true. Assume

$$
S_k=(k+1)!-1.
$$

Then

$$
S_{k+1}=S_k+(k+1)(k+1)!.
$$

Using the induction hypothesis,

$$
S_{k+1}=(k+1)!-1+(k+1)(k+1)!.
$$

So

$$
S_{k+1}=(k+2)(k+1)!-1=(k+2)!-1.
$$

Therefore $S_n=(n+1)!-1$ for all positive integers $n$.

### Problem 18

Checking $n=1,2,3,4$ gives evidence only. It does not rule out a
counterexample later.

An induction proof still needs:

1. a true base case;
2. an induction hypothesis, usually $P(k)$ for some integer $k$ in the
   required range;
3. a proof that $P(k)$ implies $P(k+1)$;
4. a conclusion for all integers in the required range.

### Problem 19

The induction step may be valid, but the base case is false. For $n=1$,

$$
2\ne1^2+1+2.
$$

So the induction chain has no true starting point. Therefore the argument does
not prove the formula for all positive integers $n$.

### Problem 20

The flaw is that the student assumes the statement they are supposed to prove
for $k+1$. That is circular.

The induction hypothesis should be:

$$
\text{Assume }P(k)\text{ is true for some integer }k\ge n_0.
$$

Then the induction step must prove

$$
P(k)\implies P(k+1).
$$

Together with a valid base case $P(n_0)$, this proves $P(n)$ for all integers
$n\ge n_0$.
