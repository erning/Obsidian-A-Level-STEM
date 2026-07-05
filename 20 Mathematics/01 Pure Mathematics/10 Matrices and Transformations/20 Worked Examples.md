---
title: Matrices and Transformations Worked Examples
subject: Mathematics
syllabus:
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/10 Matrices and Transformations/00 Overview|Matrices and Transformations]]"
status: active
tags:
  - mathematics/pure
  - worked-examples
---

# Matrices and Transformations Worked Examples

These examples model the 9231 route through matrix operations, determinants,
inverses, transformations, invariant objects, simultaneous equations,
eigenvalues, diagonalisation, and the Cayley-Hamilton theorem.

## Source Route

- Syllabus: CAIE Further Mathematics 9231 sections 1.4 and 2.2.
- Section 1.4: matrix operations, zero and identity matrices, determinants and
  inverses up to $3\times3$, transformation matrices, composite
  transformations, area scale factor, invariant points, and invariant lines.
- Section 2.2: $3\times3$ systems, consistency, eigenvalues, eigenvectors,
  diagonalisation, matrix powers, and the Cayley-Hamilton theorem.

## Example 1: Multiplication Order

**Prompt.** Let

$$
A=\begin{pmatrix}1&2\\0&1\end{pmatrix},
\qquad
B=\begin{pmatrix}2&0\\3&1\end{pmatrix}.
$$

Find $AB$ and $BA$.

**Solution.**

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

So

$$
AB\ne BA.
$$

**What this example trains.** Matrix multiplication is not generally
commutative.

## Example 2: Determinant, Inverse, and a Matrix Equation

**Prompt.** Let

$$
M=\begin{pmatrix}2&-1\\3&4\end{pmatrix}.
$$

Find $M^{-1}$ and solve

$$
M\mathbf x=\begin{pmatrix}5\\6\end{pmatrix}.
$$

**Solution.**

The determinant is

$$
\det M=2(4)-(-1)(3)=11.
$$

Since $\det M\ne0$, $M$ is non-singular. Its inverse is

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

**What this example trains.** Check the determinant before using an inverse.

## Example 3: Building a Transformation Matrix

**Prompt.** Find the matrix for an anticlockwise rotation through $90^\circ$
about the origin.

**Solution.**

The basis vector

$$
\begin{pmatrix}1\\0\end{pmatrix}
$$

maps to

$$
\begin{pmatrix}0\\1\end{pmatrix},
$$

and

$$
\begin{pmatrix}0\\1\end{pmatrix}
$$

maps to

$$
\begin{pmatrix}-1\\0\end{pmatrix}.
$$

These image vectors are the columns of the transformation matrix:

$$
R=
\begin{pmatrix}
0&-1\\
1&0
\end{pmatrix}.
$$

**What this example trains.** The columns of a $2\times2$ transformation
matrix are the images of the basis vectors.

## Example 4: Composite Transformations

**Prompt.** A stretch parallel to the $x$-axis with scale factor $3$ is followed
by reflection in the $x$-axis. Find the combined matrix.

**Solution.**

The stretch matrix is

$$
S=\begin{pmatrix}3&0\\0&1\end{pmatrix}.
$$

The reflection in the $x$-axis is

$$
F=\begin{pmatrix}1&0\\0&-1\end{pmatrix}.
$$

The stretch happens first, so its matrix is on the right:

$$
FS=
\begin{pmatrix}1&0\\0&-1\end{pmatrix}
\begin{pmatrix}3&0\\0&1\end{pmatrix}
=
\begin{pmatrix}3&0\\0&-1\end{pmatrix}.
$$

**What this example trains.** If transformation $B$ is followed by
transformation $A$, the combined matrix is $AB$.

## Example 5: Area Scale Factor and Orientation

**Prompt.** For

$$
A=\begin{pmatrix}1&3\\2&4\end{pmatrix},
$$

find the area scale factor and state whether orientation is preserved or
reversed.

**Solution.**

The determinant is

$$
\det A=1(4)-3(2)=-2.
$$

The area scale factor is

$$
|\det A|=2.
$$

Since the determinant is negative, orientation is reversed.

**What this example trains.** The determinant gives signed area scale factor;
the absolute value gives area scale factor.

## Example 6: Invariant Points and Lines

**Prompt.** For

$$
A=\begin{pmatrix}2&0\\1&1\end{pmatrix},
$$

find the invariant points and the invariant lines through the origin.

**Solution.**

An invariant point satisfies

$$
A\begin{pmatrix}x\\y\end{pmatrix}
=
\begin{pmatrix}x\\y\end{pmatrix}.
$$

This gives

$$
\begin{pmatrix}2x\\x+y\end{pmatrix}
=
\begin{pmatrix}x\\y\end{pmatrix}.
$$

So $x=0$. Every point on the $y$-axis is invariant.

Invariant lines through the origin have directions that are eigenvectors. The
line $x=0$ is one invariant line. Also,

$$
A\begin{pmatrix}1\\1\end{pmatrix}
=
\begin{pmatrix}2\\2\end{pmatrix}
=2\begin{pmatrix}1\\1\end{pmatrix},
$$

so the line $y=x$ is also invariant.

**What this example trains.** Invariant points satisfy $A\mathbf x=\mathbf x$;
invariant lines through the origin come from eigenvector directions.

## Example 7: A 3 by 3 Determinant and Inverse

**Prompt.** Find the determinant and inverse of

$$
U=\begin{pmatrix}
1&2&0\\
0&1&3\\
0&0&2
\end{pmatrix}.
$$

**Solution.**

Since $U$ is upper triangular, its determinant is the product of its diagonal
entries:

$$
\det U=1\cdot1\cdot2=2.
$$

So $U$ is non-singular. Solving $U\mathbf x=\mathbf e_1$,
$U\mathbf x=\mathbf e_2$, and $U\mathbf x=\mathbf e_3$ gives the columns of
$U^{-1}$:

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

**What this example trains.** The inverse columns are solutions of matrix
equations with identity-matrix columns on the right.

## Example 8: A 3 by 3 Linear System

**Prompt.** Solve

$$
\begin{cases}
x+y+z=6,\\
2x-y+z=3,\\
x+3y-z=4.
\end{cases}
$$

**Solution.**

Write the system as

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

The determinant of the coefficient matrix is

$$
8,
$$

so the system has a unique solution. Solving gives

$$
\begin{pmatrix}x\\y\\z\end{pmatrix}
=
\begin{pmatrix}1\\2\\3\end{pmatrix}.
$$

**What this example trains.** A non-singular coefficient matrix gives one
common point of the three planes.

## Example 9: Eigenvalues, Eigenvectors, and Diagonalisation

**Prompt.** Diagonalise

$$
A=\begin{pmatrix}4&1\\2&3\end{pmatrix}.
$$

**Solution.**

The characteristic equation is

$$
\det(A-\lambda I)=
\begin{vmatrix}
4-\lambda&1\\
2&3-\lambda
\end{vmatrix}
=0.
$$

So

$$
(4-\lambda)(3-\lambda)-2=0,
$$

which simplifies to

$$
\lambda^2-7\lambda+10=0.
$$

Thus

$$
\lambda=5,\qquad \lambda=2.
$$

For $\lambda=5$, an eigenvector is

$$
\begin{pmatrix}1\\1\end{pmatrix}.
$$

For $\lambda=2$, an eigenvector is

$$
\begin{pmatrix}1\\-2\end{pmatrix}.
$$

Therefore

$$
Q=\begin{pmatrix}1&1\\1&-2\end{pmatrix},
\qquad
D=\begin{pmatrix}5&0\\0&2\end{pmatrix},
$$

and

$$
A=QDQ^{-1}.
$$

**What this example trains.** The order of eigenvectors in $Q$ must match the
order of eigenvalues in $D$.

## Example 10: Cayley-Hamilton for an Inverse

**Prompt.** Use the Cayley-Hamilton theorem to find the inverse of

$$
B=\begin{pmatrix}2&1\\1&2\end{pmatrix}.
$$

**Solution.**

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

or

$$
\lambda^2-4\lambda+3=0.
$$

By the Cayley-Hamilton theorem,

$$
B^2-4B+3I=0.
$$

Since $B$ is non-singular, multiply by $B^{-1}$:

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

**What this example trains.** Cayley-Hamilton can turn a characteristic
equation into a formula for an inverse or a power.
