---
title: Matrices and Transformations Key Practice Solutions
subject: Mathematics
syllabus:
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/10 Matrices and Transformations/00 Overview|Matrices and Transformations]]"
status: active
tags:
  - mathematics/pure
  - solutions
---

# Matrices and Transformations Key Practice Solutions

This note gives worked solutions for [[20 Mathematics/01 Pure Mathematics/10 Matrices and Transformations/30 Key Practice Problems|Matrices and Transformations Key Practice Problems]]. Use it to check multiplication order, determinant decisions, and eigenvector matching.

## A. Matrix Algebra and Inverses

## Problem 1

$P$ is $2\times3$ and $R$ is $3\times2$, so $PR$ is defined and is
$2\times2$:

$$
PR=
\begin{pmatrix}1&2&3\\0&-1&4\end{pmatrix}
\begin{pmatrix}2&0\\1&3\\-1&2\end{pmatrix}
=
\begin{pmatrix}1&12\\-5&5\end{pmatrix}.
$$

$RP$ is also defined and is $3\times3$:

$$
RP=
\begin{pmatrix}2&0\\1&3\\-1&2\end{pmatrix}
\begin{pmatrix}1&2&3\\0&-1&4\end{pmatrix}
=
\begin{pmatrix}
2&4&6\\
1&-1&15\\
-1&-4&5
\end{pmatrix}.
$$

## Problem 2

Calculate

$$
AB=
\begin{pmatrix}1&2\\0&1\end{pmatrix}
\begin{pmatrix}2&0\\3&1\end{pmatrix}
=
\begin{pmatrix}8&2\\3&1\end{pmatrix}.
$$

In the other order,

$$
BA=
\begin{pmatrix}2&0\\3&1\end{pmatrix}
\begin{pmatrix}1&2\\0&1\end{pmatrix}
=
\begin{pmatrix}2&4\\3&7\end{pmatrix}.
$$

Since $AB\ne BA$, this shows that matrix multiplication is not generally
commutative.

## Problem 3

The determinant is

$$
\det M=2(4)-(-1)(3)=11.
$$

Since this is non-zero,

$$
M^{-1}
=\frac1{11}
\begin{pmatrix}4&1\\-3&2\end{pmatrix}.
$$

Therefore

$$
\mathbf x=M^{-1}\begin{pmatrix}5\\6\end{pmatrix}
=\frac1{11}
\begin{pmatrix}4&1\\-3&2\end{pmatrix}
\begin{pmatrix}5\\6\end{pmatrix}
=
\begin{pmatrix}\frac{26}{11}\\-\frac3{11}\end{pmatrix}.
$$

## Problem 4

$U$ is upper triangular, so

$$
\det U=1\cdot1\cdot2=2.
$$

Thus $U$ is non-singular. Its inverse is

$$
U^{-1}=
\begin{pmatrix}
1&-2&3\\
0&1&-\frac32\\
0&0&\frac12
\end{pmatrix}.
$$

A check is

$$
UU^{-1}=I.
$$

## Problem 5

To prove that $B^{-1}A^{-1}$ is the inverse of $AB$, multiply:

$$
(AB)(B^{-1}A^{-1})
=A(BB^{-1})A^{-1}
=AIA^{-1}
=I.
$$

Also,

$$
(B^{-1}A^{-1})(AB)
=B^{-1}(A^{-1}A)B
=B^{-1}IB
=I.
$$

Therefore

$$
(AB)^{-1}=B^{-1}A^{-1}.
$$

## B. Transformation Matrices

## Problem 6

Under a $90^\circ$ anticlockwise rotation,

$$
\begin{pmatrix}1\\0\end{pmatrix}
\mapsto
\begin{pmatrix}0\\1\end{pmatrix},
\qquad
\begin{pmatrix}0\\1\end{pmatrix}
\mapsto
\begin{pmatrix}-1\\0\end{pmatrix}.
$$

So the matrix is

$$
R=\begin{pmatrix}0&-1\\1&0\end{pmatrix}.
$$

The image of $(2,-1)$ is

$$
\begin{pmatrix}0&-1\\1&0\end{pmatrix}
\begin{pmatrix}2\\-1\end{pmatrix}
=
\begin{pmatrix}1\\2\end{pmatrix}.
$$

## Problem 7

Reflection in $y=x$ swaps the coordinates, so

$$
\begin{pmatrix}1\\0\end{pmatrix}
\mapsto
\begin{pmatrix}0\\1\end{pmatrix},
\qquad
\begin{pmatrix}0\\1\end{pmatrix}
\mapsto
\begin{pmatrix}1\\0\end{pmatrix}.
$$

The matrix is

$$
F=\begin{pmatrix}0&1\\1&0\end{pmatrix}.
$$

Then

$$
F\begin{pmatrix}3\\-2\end{pmatrix}
=
\begin{pmatrix}-2\\3\end{pmatrix}.
$$

## Problem 8

The stretch matrix is

$$
S=\begin{pmatrix}3&0\\0&1\end{pmatrix}.
$$

The reflection in the $x$-axis is

$$
F=\begin{pmatrix}1&0\\0&-1\end{pmatrix}.
$$

The stretch happens first, so the combined matrix is

$$
FS=
\begin{pmatrix}1&0\\0&-1\end{pmatrix}
\begin{pmatrix}3&0\\0&1\end{pmatrix}
=
\begin{pmatrix}3&0\\0&-1\end{pmatrix}.
$$

## Problem 9

A shear with the $x$-axis fixed has form

$$
\begin{pmatrix}1&k\\0&1\end{pmatrix}.
$$

Since $(0,1)$ maps to $(4,1)$, $k=4$. The matrix is

$$
S=\begin{pmatrix}1&4\\0&1\end{pmatrix}.
$$

The image of $(2,3)$ is

$$
\begin{pmatrix}1&4\\0&1\end{pmatrix}
\begin{pmatrix}2\\3\end{pmatrix}
=
\begin{pmatrix}14\\3\end{pmatrix}.
$$

## Problem 10

The determinant is

$$
\det C=1(4)-3(2)=-2.
$$

The area scale factor is

$$
|\det C|=2.
$$

Since $\det C<0$, orientation is reversed.

## Problem 11

Invariant points satisfy

$$
T\begin{pmatrix}x\\y\end{pmatrix}
=
\begin{pmatrix}x\\y\end{pmatrix}.
$$

So

$$
\begin{pmatrix}2x\\x+y\end{pmatrix}
=
\begin{pmatrix}x\\y\end{pmatrix}.
$$

This gives $x=0$. Therefore every point on the $y$-axis is invariant.

For invariant lines through the origin, look for directions mapped to scalar
multiples of themselves. The $y$-axis is invariant because

$$
T\begin{pmatrix}0\\1\end{pmatrix}
=
\begin{pmatrix}0\\1\end{pmatrix}.
$$

Also,

$$
T\begin{pmatrix}1\\1\end{pmatrix}
=
\begin{pmatrix}2\\2\end{pmatrix}
=2\begin{pmatrix}1\\1\end{pmatrix}.
$$

So the invariant lines through the origin are

$$
x=0
\quad\text{and}\quad
y=x.
$$

## C. Systems, Eigenvalues, and Matrix Powers

## Problem 12

The matrix equation is

$$
\begin{pmatrix}
1&1&1\\
2&-1&1\\
1&3&-1
\end{pmatrix}
\begin{pmatrix}x\\y\\z\end{pmatrix}
=
\begin{pmatrix}6\\3\\4\end{pmatrix}.
$$

The coefficient determinant is $8$, so the matrix is non-singular and the
system has a unique solution. Solving gives

$$
x=1,\qquad y=2,\qquad z=3.
$$

Geometrically, the three planes meet at the point $(1,2,3)$.

## Problem 13

For the first system, the second equation is twice the first:

$$
2x+2y+2z=2(x+y+z).
$$

So it adds no new plane. With $x-y=0$, we have $x=y$. Let $x=y=t$. Then

$$
t+t+z=1,
$$

so

$$
z=1-2t.
$$

There are infinitely many solutions:

$$
(x,y,z)=(t,t,1-2t).
$$

For the second system, the left-hand side of the second equation is twice the
left-hand side of the first, but the right-hand side is not twice as large:

$$
2\ne3.
$$

So the system is inconsistent and has no solution.

## Problem 14

The characteristic equation is

$$
\det(A-\lambda I)=
\begin{vmatrix}
4-\lambda&1\\
2&3-\lambda
\end{vmatrix}
=0.
$$

Thus

$$
(4-\lambda)(3-\lambda)-2=0,
$$

so

$$
\lambda^2-7\lambda+10=0.
$$

Therefore

$$
\lambda=5,\qquad \lambda=2.
$$

For $\lambda=5$,

$$
(A-5I)\mathbf e=\mathbf0
$$

gives an eigenvector

$$
\begin{pmatrix}1\\1\end{pmatrix}.
$$

For $\lambda=2$,

$$
(A-2I)\mathbf e=\mathbf0
$$

gives an eigenvector

$$
\begin{pmatrix}1\\-2\end{pmatrix}.
$$

## Problem 15

Use the eigenvectors from problem 14 as the columns of $Q$:

$$
Q=\begin{pmatrix}1&1\\1&-2\end{pmatrix}.
$$

The matching diagonal matrix is

$$
D=\begin{pmatrix}5&0\\0&2\end{pmatrix}.
$$

Then

$$
A=QDQ^{-1}.
$$

The order matters: the first column of $Q$ corresponds to the first diagonal
entry of $D$, and the second column of $Q$ corresponds to the second diagonal
entry of $D$.

## Problem 16

Using diagonalisation,

$$
A^3=QD^3Q^{-1}.
$$

Here

$$
D^3=\begin{pmatrix}125&0\\0&8\end{pmatrix}.
$$

With

$$
Q=\begin{pmatrix}1&1\\1&-2\end{pmatrix},
$$

this gives

$$
A^3=
\begin{pmatrix}86&39\\78&47\end{pmatrix}.
$$

## Problem 17

Since $H$ is upper triangular, its eigenvalues are the diagonal entries:

$$
\lambda=1,\qquad \lambda=2,\qquad \lambda=3.
$$

For $\lambda=1$, solve $(H-I)\mathbf e=\mathbf0$. This gives

$$
\mathbf e=\begin{pmatrix}1\\0\\0\end{pmatrix}
$$

as an eigenvector.

For $\lambda=2$, solve $(H-2I)\mathbf e=\mathbf0$. One eigenvector is

$$
\mathbf e=\begin{pmatrix}1\\1\\0\end{pmatrix}.
$$

For $\lambda=3$, solve $(H-3I)\mathbf e=\mathbf0$. One eigenvector is

$$
\mathbf e=\begin{pmatrix}0\\0\\1\end{pmatrix}.
$$

Any non-zero scalar multiple of these vectors is also an eigenvector.

## Problem 18

Given

$$
A\mathbf e=\lambda\mathbf e,
$$

apply $A$ again:

$$
A^2\mathbf e=A(A\mathbf e)=A(\lambda\mathbf e)=\lambda A\mathbf e
=\lambda^2\mathbf e.
$$

Repeating this argument, or using induction, gives

$$
A^n\mathbf e=\lambda^n\mathbf e
$$

for every positive integer $n$.

## Problem 19

The characteristic equation is

$$
\det(B-\lambda I)=
\begin{vmatrix}
2-\lambda&1\\
1&2-\lambda
\end{vmatrix}
=0.
$$

So

$$
(2-\lambda)^2-1=0,
$$

which gives

$$
\lambda^2-4\lambda+3=0.
$$

By Cayley-Hamilton,

$$
B^2-4B+3I=0.
$$

Multiply by $B^{-1}$:

$$
B-4I+3B^{-1}=0.
$$

Therefore

$$
B^{-1}=\frac{4I-B}{3}
=
\begin{pmatrix}
\frac23&-\frac13\\
-\frac13&\frac23
\end{pmatrix}.
$$

## Problem 20

From problem 19,

$$
B^2=4B-3I.
$$

Then

$$
B^3=B(4B-3I)=4B^2-3B.
$$

Substitute $B^2=4B-3I$:

$$
B^3=4(4B-3I)-3B=13B-12I.
$$

Then

$$
B^4=B(13B-12I)=13B^2-12B.
$$

Again substitute $B^2=4B-3I$:

$$
B^4=13(4B-3I)-12B=40B-39I.
$$
