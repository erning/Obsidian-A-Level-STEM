---
title: Matrices and Transformations Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/10 Matrices and Transformations/00 Overview|Matrices and Transformations]]"
status: draft
tags:
  - mathematics/pure
  - lecture-notes
---

# Matrices and Transformations Lecture Notes

Matrices organise linear operations. They can store coefficients in simultaneous equations, represent geometric transformations, and describe directions that remain aligned under a transformation. The same matrix should be read both algebraically and geometrically.

## Source Route

- 9231 1.4 Matrices
- 9231 2.2 Matrices
- Coursebook route: 9231 Further Mathematics Coursebook matrix and transformation chapters; Hodder FP1/FP2 matrix chapters.

## Visual Guide

![[assets/generated/mathematics/matrices-and-transformations.svg]]

Figure: The guide shows a matrix transformation acting on a square grid. Watch where the basis vectors go; their images become the columns of the transformation matrix.

## 1. Matrix Operations

Matrices can be added or subtracted only when they have the same order. Matrix multiplication is defined when the number of columns in the first matrix equals the number of rows in the second.

Matrix multiplication is not generally commutative:

$$
AB\ne BA
$$

in general.

The identity matrix $I$ leaves vectors unchanged, and the zero matrix has all entries zero. The identity matrix plays the role of $1$ in matrix multiplication:

$$
AI=IA=A.
$$

## 2. Matrices as Transformations

A $2\times2$ matrix

$$
A=\begin{pmatrix}a&b\\c&d\end{pmatrix}
$$

maps a vector by

$$
A\begin{pmatrix}x\\y\end{pmatrix}
=
\begin{pmatrix}ax+by\\cx+dy\end{pmatrix}.
$$

The columns of $A$ are the images of the basis vectors:

$$
A\begin{pmatrix}1\\0\end{pmatrix}
=\text{first column of }A,
\qquad
A\begin{pmatrix}0\\1\end{pmatrix}
=\text{second column of }A.
$$

This is the easiest way to build transformation matrices from geometry.

Common transformations include rotations, reflections, enlargements, stretches, and shears. For example, anticlockwise rotation through angle $\theta$ is

$$
\begin{pmatrix}
\cos\theta&-\sin\theta\\
\sin\theta&\cos\theta
\end{pmatrix}.
$$

If the transformation represented by $B$ is followed by the transformation represented by $A$, the combined matrix is

$$
AB.
$$

The rightmost matrix acts first.

## 3. Determinants and Inverses

For

$$
A=\begin{pmatrix}a&b\\c&d\end{pmatrix},
$$

the determinant is

$$
\det A=ad-bc.
$$

If $\det A\ne0$, the matrix is non-singular and has inverse

$$
A^{-1}=\frac{1}{ad-bc}
\begin{pmatrix}d&-b\\-c&a\end{pmatrix}.
$$

If $\det A=0$, the matrix is singular and has no inverse. Geometrically, a singular $2\times2$ transformation collapses area to a line or point.

For non-singular matrices,

$$
(AB)^{-1}=B^{-1}A^{-1}.
$$

The order reverses because the inverse transformation must undo the last step first.

The area scale factor of a two-dimensional transformation is

$$
|\det A|.
$$

The sign of the determinant also tells whether orientation is preserved or reversed.

## 4. Invariant Points and Lines

An invariant point satisfies

$$
A\mathbf x=\mathbf x.
$$

This is equivalent to

$$
(A-I)\mathbf x=\mathbf0.
$$

An invariant line is mapped onto itself as a set. A line through the origin with direction vector $\mathbf v$ is invariant when $A\mathbf v$ is parallel to $\mathbf v$. This idea leads naturally to eigenvectors.

## 5. Linear Systems

A system of three linear equations in three unknowns can be written as

$$
A\mathbf x=\mathbf b.
$$

If $A$ is non-singular, there is a unique solution:

$$
\mathbf x=A^{-1}\mathbf b.
$$

If $A$ is singular, the system may be inconsistent or may have infinitely many solutions. Geometrically, three planes may meet at a point, in a line, or not share a common point.

## 6. Eigenvalues and Eigenvectors

An eigenvector is a non-zero vector whose direction is unchanged by a matrix transformation. If

$$
A\mathbf e=\lambda\mathbf e,
$$

then $\lambda$ is an eigenvalue and $\mathbf e$ is an eigenvector.

To find eigenvalues, solve the characteristic equation

$$
\det(A-\lambda I)=0.
$$

For each eigenvalue, solve

$$
(A-\lambda I)\mathbf e=\mathbf0
$$

to find eigenvectors.

Eigenvectors are invariant directions. Eigenvalues are scale factors along those directions.

## 7. Diagonalisation and the Characteristic Equation

When a square matrix has enough independent eigenvectors, it can be written as

$$
A=QDQ^{-1},
$$

where the columns of $Q$ are eigenvectors and $D$ is a diagonal matrix of eigenvalues.

This is useful because powers become simple:

$$
A^n=QD^nQ^{-1}.
$$

The Cayley-Hamilton theorem says that a square matrix satisfies its own characteristic equation. For a $2\times2$ or $3\times3$ matrix, this can help compute powers or inverses without repeated multiplication.

## Worked-Thinking Routines

### Transformation Matrix

1. Find where $\begin{pmatrix}1\\0\end{pmatrix}$ goes.
2. Find where $\begin{pmatrix}0\\1\end{pmatrix}$ goes.
3. Put those image vectors as the columns of the matrix.
4. For composite transformations, multiply in the order "second matrix on the left".
5. Test the matrix on a simple point or shape.

### Inverse or Determinant

1. Compute the determinant first.
2. If it is zero, stop and interpret singularity.
3. If non-zero, calculate the inverse.
4. Check by multiplying back to $I$ if needed.

### Eigenstructure

1. Form $\det(A-\lambda I)=0$.
2. Solve for eigenvalues.
3. Substitute each eigenvalue into $(A-\lambda I)\mathbf e=\mathbf0$.
4. Interpret eigenvectors as invariant directions.
5. Use diagonalisation only when the eigenvectors are independent.

## Common Mistakes

- Assuming matrix multiplication is commutative.
- Writing composite transformations in the wrong order.
- Confusing rows and columns when building a transformation matrix.
- Trying to invert a singular matrix.
- Forgetting that the area scale factor is $|\det A|$.
- Treating the zero vector as an eigenvector.
- Building $Q$ with eigenvectors in an order that does not match the eigenvalues in $D$.

## Quick Self-Check

You are ready to move on when you can:

- Multiply matrices and explain why the order matters.
- Build a $2\times2$ transformation matrix from basis-vector images.
- Interpret determinant as invertibility and area scale factor.
- Find an inverse when it exists.
- Solve a matrix equation and interpret singular cases.
- Find eigenvalues and eigenvectors.
- Use diagonalisation to compute powers of a matrix.

## Connections

- [[20 Mathematics/01 Pure Mathematics/08 Vectors/00 Overview|Vectors]]
- [[20 Mathematics/01 Pure Mathematics/02 Coordinate Geometry and Graphs/00 Overview|Coordinate Geometry and Graphs]]
