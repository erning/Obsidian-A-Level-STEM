---
title: Matrices and Transformations Key Practice Problems
subject: Mathematics
syllabus:
  - 9231
parent: "[Matrices and Transformations](00%20Overview.md)"
status: active
tags:
  - mathematics/pure
  - practice
---

# Matrices and Transformations Key Practice Problems

Work these without looking at the solutions first. State matrix orders when
they matter, and keep transformation order explicit.

## A. Matrix Algebra and Inverses

1. Let

   $$
   P=\begin{pmatrix}1&2&3\\0&-1&4\end{pmatrix},
   \qquad
   R=\begin{pmatrix}2&0\\1&3\\-1&2\end{pmatrix}.
   $$

   Find $PR$ and $RP$, giving the order of each result.

2. Let

   $$
   A=\begin{pmatrix}1&2\\0&1\end{pmatrix},
   \qquad
   B=\begin{pmatrix}2&0\\3&1\end{pmatrix}.
   $$

   Find $AB$ and $BA$. What does this show?

3. For

   $$
   M=\begin{pmatrix}2&-1\\3&4\end{pmatrix},
   $$

   find $\det M$, $M^{-1}$, and the solution of

   $$
   M\mathbf x=\begin{pmatrix}5\\6\end{pmatrix}.
   $$

4. For

   $$
   U=\begin{pmatrix}
   1&2&0\\
   0&1&3\\
   0&0&2
   \end{pmatrix},
   $$

   find $\det U$ and $U^{-1}$.

5. Let $A$ and $B$ be non-singular square matrices. Explain why

   $$
   (AB)^{-1}=B^{-1}A^{-1}.
   $$

## B. Transformation Matrices

6. Find the matrix for an anticlockwise rotation through $90^\circ$ about the
   origin, and use it to find the image of $(2,-1)$.

7. Find the matrix for reflection in the line $y=x$, and use it to find the
   image of $(3,-2)$.

8. A stretch parallel to the $x$-axis with scale factor $3$ is followed by
   reflection in the $x$-axis. Find the combined matrix.

9. A shear has the $x$-axis fixed and maps $(0,1)$ to $(4,1)$. Find its matrix
   and the image of $(2,3)$.

10. For

    $$
    C=\begin{pmatrix}1&3\\2&4\end{pmatrix},
    $$

    find the area scale factor and state whether orientation is preserved or
    reversed.

11. For

    $$
    T=\begin{pmatrix}2&0\\1&1\end{pmatrix},
    $$

    find the invariant points and the invariant lines through the origin.

## C. Systems, Eigenvalues, and Matrix Powers

12. Solve the system

    $$
    \begin{cases}
    x+y+z=6,\\
    2x-y+z=3,\\
    x+3y-z=4.
    \end{cases}
    $$

    Interpret the result geometrically.

13. Classify each system as having a unique solution, no solution, or
    infinitely many solutions.

    $$
    \begin{cases}
    x+y+z=1,\\
    2x+2y+2z=2,\\
    x-y=0,
    \end{cases}
    $$

    $$
    \begin{cases}
    x+y+z=1,\\
    2x+2y+2z=3,\\
    x-y=0.
    \end{cases}
    $$

14. Find the eigenvalues and corresponding eigenvectors of

    $$
    A=\begin{pmatrix}4&1\\2&3\end{pmatrix}.
    $$

15. Diagonalise the matrix in question 14 by writing $A=QDQ^{-1}$.

16. Use diagonalisation, or another exact matrix method, to find $A^3$ for the
    matrix in question 14.

17. Find the eigenvalues and corresponding eigenvectors of

    $$
    H=\begin{pmatrix}
    1&1&0\\
    0&2&0\\
    0&0&3
    \end{pmatrix}.
    $$

18. If $A\mathbf e=\lambda\mathbf e$ and $\mathbf e\ne\mathbf0$, prove that
    $A^n\mathbf e=\lambda^n\mathbf e$ for positive integers $n$.

19. Use the Cayley-Hamilton theorem to find the inverse of

    $$
    B=\begin{pmatrix}2&1\\1&2\end{pmatrix}.
    $$

20. Use the characteristic equation of the matrix in question 19 to express
    $B^4$ in the form $aB+bI$.
