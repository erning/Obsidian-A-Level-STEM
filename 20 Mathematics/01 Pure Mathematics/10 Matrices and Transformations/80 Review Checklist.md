---
title: Matrices and Transformations Review Checklist
subject: Mathematics
syllabus:
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/10 Matrices and Transformations/00 Overview|Matrices and Transformations]]"
status: active
tags:
  - mathematics/pure
  - review-checklist
---

# Matrices and Transformations Review Checklist

Use this after the worked examples and practice problems. Revisit [[20 Mathematics/01 Pure Mathematics/10 Matrices and Transformations/10 Lecture Notes|Matrices and Transformations Lecture Notes]] if any item is uncertain.

## Ideas to Recall

- [ ] This is a 9231 topic in the local syllabus route: sections 1.4 and 2.2.
- [ ] Matrix addition and subtraction require the same order; multiplication requires compatible inner dimensions.
- [ ] Matrix multiplication is associative but not generally commutative.
- [ ] The identity matrix leaves a vector unchanged; the zero matrix has all entries zero.
- [ ] A square matrix is singular if its determinant is zero and non-singular if its determinant is non-zero.
- [ ] For transformations, the columns of a $2\times2$ matrix are the images of the basis vectors.
- [ ] If transformation $B$ is followed by transformation $A$, the combined matrix is $AB$.
- [ ] The area scale factor of a two-dimensional matrix transformation is $|\det A|$.
- [ ] Invariant points satisfy $A\mathbf x=\mathbf x$; invariant lines through the origin come from eigenvector directions.
- [ ] Eigenvalues and eigenvectors satisfy $A\mathbf e=\lambda\mathbf e$ with $\mathbf e\ne\mathbf0$.
- [ ] A diagonalisation $A=QDQ^{-1}$ is useful only when the eigenvectors used in $Q$ are independent and match the order of $D$.
- [ ] Cayley-Hamilton says that a square matrix satisfies its own characteristic equation.

## Skills to Perform

- [ ] Determine whether a product is defined and state the order of the result.
- [ ] Multiply matrices accurately and check whether changing the order changes the answer.
- [ ] Evaluate $2\times2$ and $3\times3$ determinants.
- [ ] Find inverses of non-singular $2\times2$ and $3\times3$ matrices.
- [ ] Use $(AB)^{-1}=B^{-1}A^{-1}$ with the order reversed.
- [ ] Build matrices for reflection, rotation, enlargement, stretch, and shear.
- [ ] Compose transformation matrices in the correct order.
- [ ] Use determinants to find area scale factor and orientation change.
- [ ] Find invariant points and invariant lines.
- [ ] Write a $3\times3$ system as a matrix equation and classify its consistency.
- [ ] Find eigenvalues and eigenvectors of $2\times2$ and $3\times3$ matrices with real distinct eigenvalues.
- [ ] Form $QDQ^{-1}$ and use it to calculate powers.
- [ ] Use Cayley-Hamilton to rewrite powers or find an inverse.

## Common Errors to Avoid

- [ ] Multiplying matrices in the wrong order for a composite transformation.
- [ ] Treating $AB$ and $BA$ as interchangeable.
- [ ] Using rows instead of columns when constructing a transformation matrix from basis-vector images.
- [ ] Trying to invert a singular matrix.
- [ ] Forgetting that a negative determinant reverses orientation but the area scale factor is positive.
- [ ] Counting the zero vector as an eigenvector.
- [ ] Pairing an eigenvector column in $Q$ with the wrong diagonal entry in $D$.
- [ ] Assuming a repeated eigenvalue automatically gives enough eigenvectors for diagonalisation.
- [ ] Treating inconsistent and infinitely many solution cases as the same singular case.

## Ready to Move On When

- [ ] I can move between matrix algebra and transformation geometry for the same $2\times2$ matrix.
- [ ] I can decide whether an inverse exists before trying to calculate it.
- [ ] I can describe what a singular coefficient matrix means geometrically for simultaneous equations.
- [ ] I can find eigenvalues and eigenvectors and use them to build a correct diagonalisation.
- [ ] I can use Cayley-Hamilton without expanding high powers directly.
