---
title: Vectors Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/08 Vectors/00 Overview|Vectors]]"
status: active
tags:
  - mathematics/pure
  - solutions
---

# Vectors Key Practice Solutions

This note gives worked solutions for [[20 Mathematics/01 Pure Mathematics/08 Vectors/30 Key Practice Problems|Vectors Key Practice Problems]]. Use it to check the method, the vector roles, and the final answer.

## A. Position Vectors and Lines

## Problem 1

The displacement from $A$ to $B$ is final position minus initial position:

$$
\overrightarrow{AB}
=\begin{pmatrix}5\\-1\\9\end{pmatrix}
-\begin{pmatrix}1\\2\\3\end{pmatrix}
=\begin{pmatrix}4\\-3\\6\end{pmatrix}.
$$

Its magnitude is

$$
|\overrightarrow{AB}|=\sqrt{4^2+(-3)^2+6^2}=\sqrt{61}.
$$

A unit vector in the direction of $\overrightarrow{AB}$ is

$$
\frac{1}{\sqrt{61}}\begin{pmatrix}4\\-3\\6\end{pmatrix}.
$$

## Problem 2

The midpoint position vector is the average of the two position vectors:

$$
\frac12\left(
\begin{pmatrix}1\\2\\3\end{pmatrix}
+
\begin{pmatrix}5\\-1\\9\end{pmatrix}
\right)
=
\begin{pmatrix}3\\\frac12\\6\end{pmatrix}.
$$

So the midpoint is $\left(3,\frac12,6\right)$.

## Problem 3

Use one point on the line and the displacement vector from question 1:

$$
\mathbf r=\begin{pmatrix}1\\2\\3\end{pmatrix}
+t\begin{pmatrix}4\\-3\\6\end{pmatrix},
\qquad t\in\mathbb R.
$$

## Problem 4

A point lies on the line if one value of $t$ satisfies all three components:

$$
\begin{pmatrix}9\\-4\\15\end{pmatrix}
=
\begin{pmatrix}1\\2\\3\end{pmatrix}
+t\begin{pmatrix}4\\-3\\6\end{pmatrix}.
$$

From the first component,

$$
9=1+4t,
$$

so $t=2$. Check the other components:

$$
2-3(2)=-4,\qquad 3+6(2)=15.
$$

Therefore the point lies on the line.

## Problem 5

Equate components:

$$
1+2s=3+t,
$$

$$
s=1+2t,
$$

$$
2-s=1.
$$

The third equation gives $s=1$. Then the second gives

$$
1=1+2t,
$$

so $t=0$. The first equation is also satisfied:

$$
1+2(1)=3+0.
$$

The lines intersect at

$$
\begin{pmatrix}3\\1\\1\end{pmatrix}.
$$

## Problem 6

The direction vectors are

$$
\begin{pmatrix}2\\4\\-2\end{pmatrix}
\quad\text{and}\quad
\begin{pmatrix}-1\\-2\\1\end{pmatrix}.
$$

Since

$$
\begin{pmatrix}2\\4\\-2\end{pmatrix}
=-2\begin{pmatrix}-1\\-2\\1\end{pmatrix},
$$

the lines are parallel or identical. Check whether
$\begin{pmatrix}1\\0\\0\end{pmatrix}$ lies on the first line:

$$
\begin{pmatrix}1\\0\\0\end{pmatrix}
=s\begin{pmatrix}2\\4\\-2\end{pmatrix}
$$

would require $2s=1$ and $4s=0$, which is impossible. Therefore the lines are
parallel and distinct.

## Problem 7

The direction vectors

$$
\begin{pmatrix}1\\0\\1\end{pmatrix}
\quad\text{and}\quad
\begin{pmatrix}0\\1\\1\end{pmatrix}
$$

are not scalar multiples, so the lines are not parallel. Test for an
intersection:

$$
s\begin{pmatrix}1\\0\\1\end{pmatrix}
=
\begin{pmatrix}0\\1\\0\end{pmatrix}
+t\begin{pmatrix}0\\1\\1\end{pmatrix}.
$$

The components give

$$
s=0,\qquad 0=1+t,\qquad s=t.
$$

The first two equations give $s=0$ and $t=-1$, but the third would require
$0=-1$. Therefore the lines do not intersect. They are skew.

## B. Scalar Product

## Problem 8

Let

$$
\mathbf a=\begin{pmatrix}1\\2\\2\end{pmatrix},
\qquad
\mathbf b=\begin{pmatrix}3\\0\\4\end{pmatrix}.
$$

Then

$$
\mathbf a\cdot\mathbf b=1(3)+2(0)+2(4)=11,
$$

and

$$
|\mathbf a|=3,\qquad |\mathbf b|=5.
$$

So

$$
\cos\theta=\frac{\mathbf a\cdot\mathbf b}{|\mathbf a||\mathbf b|}
=\frac{11}{15}.
$$

Hence

$$
\theta=\cos^{-1}\frac{11}{15}\approx 42.8^\circ.
$$

## Problem 9

Calculate the scalar product:

$$
\begin{pmatrix}1\\-2\\3\end{pmatrix}
\cdot
\begin{pmatrix}4\\2\\0\end{pmatrix}
=1(4)+(-2)(2)+3(0)=0.
$$

A zero scalar product means the vectors are perpendicular.

## Problem 10

The scalar projection of $\mathbf a$ onto $\mathbf b$ is

$$
\frac{\mathbf a\cdot\mathbf b}{|\mathbf b|}.
$$

Here

$$
\mathbf a=\begin{pmatrix}3\\4\\0\end{pmatrix},
\qquad
\mathbf b=\begin{pmatrix}1\\0\\0\end{pmatrix}.
$$

Therefore

$$
\frac{\mathbf a\cdot\mathbf b}{|\mathbf b|}
=\frac{3}{1}=3.
$$

## Problem 11

A general point on the line is

$$
Q=\begin{pmatrix}1+t\\2t\\2t\end{pmatrix}.
$$

Then

$$
\overrightarrow{QP}
=
\begin{pmatrix}3\\1\\5\end{pmatrix}
-
\begin{pmatrix}1+t\\2t\\2t\end{pmatrix}
=
\begin{pmatrix}2-t\\1-2t\\5-2t\end{pmatrix}.
$$

At the foot of the perpendicular, $\overrightarrow{QP}$ is perpendicular to
the line direction:

$$
\begin{pmatrix}2-t\\1-2t\\5-2t\end{pmatrix}
\cdot
\begin{pmatrix}1\\2\\2\end{pmatrix}=0.
$$

This gives

$$
2-t+2(1-2t)+2(5-2t)=0,
$$

so

$$
14-9t=0,
\qquad
t=\frac{14}{9}.
$$

The foot is

$$
\begin{pmatrix}1+\frac{14}{9}\\2\cdot\frac{14}{9}\\2\cdot\frac{14}{9}\end{pmatrix}
=
\begin{pmatrix}\frac{23}{9}\\\frac{28}{9}\\\frac{28}{9}\end{pmatrix}.
$$

## Problem 12

The angle between two lines is the acute or stated angle between their
direction vectors. Using the same calculation as problem 8,

$$
\cos\theta=\frac{11}{15}.
$$

Therefore

$$
\theta=\cos^{-1}\frac{11}{15}\approx 42.8^\circ.
$$

## C. 9231 Plane and Vector Product Extensions

## Problem 13

Calculate

$$
\begin{pmatrix}1\\2\\0\end{pmatrix}
\times
\begin{pmatrix}3\\-1\\1\end{pmatrix}
=
\begin{pmatrix}
2(1)-0(-1)\\
0(3)-1(1)\\
1(-1)-2(3)
\end{pmatrix}
=
\begin{pmatrix}2\\-1\\-7\end{pmatrix}.
$$

The parallelogram area is the magnitude of the vector product:

$$
\sqrt{2^2+(-1)^2+(-7)^2}=\sqrt{54}=3\sqrt6.
$$

## Problem 14

The plane has normal vector

$$
\mathbf n=\begin{pmatrix}2\\-1\\-7\end{pmatrix}
$$

and passes through $P(1,0,2)$. Use

$$
\mathbf n\cdot(\mathbf r-\mathbf p)=0.
$$

So

$$
2(x-1)-y-7(z-2)=0.
$$

Expanding gives

$$
2x-y-7z+12=0.
$$

## Problem 15

A parametric plane uses one point and two non-parallel direction vectors:

$$
\mathbf r=
\begin{pmatrix}1\\0\\2\end{pmatrix}
+\lambda\begin{pmatrix}1\\2\\0\end{pmatrix}
+\mu\begin{pmatrix}3\\-1\\1\end{pmatrix},
\qquad \lambda,\mu\in\mathbb R.
$$

The two direction vectors are not scalar multiples, so they define a plane.

## Problem 16

Substitute the line into the plane. On the line,

$$
x=t,\qquad y=1-t,\qquad z=2+3t.
$$

The plane equation $x+2y-z=4$ becomes

$$
t+2(1-t)-(2+3t)=4.
$$

This simplifies to

$$
-4t=4,
$$

so $t=-1$. The intersection point is

$$
\begin{pmatrix}0\\1\\2\end{pmatrix}
-\begin{pmatrix}1\\-1\\3\end{pmatrix}
=
\begin{pmatrix}-1\\2\\-1\end{pmatrix}.
$$

## Problem 17

For the angle $\phi$ between a line and a plane,

$$
\sin\phi=\frac{|\mathbf d\cdot\mathbf n|}{|\mathbf d||\mathbf n|},
$$

where $\mathbf d$ is the line direction and $\mathbf n$ is the plane normal.
Here

$$
\mathbf d=\begin{pmatrix}1\\2\\2\end{pmatrix},
\qquad
\mathbf n=\begin{pmatrix}2\\-1\\2\end{pmatrix}.
$$

Then

$$
\mathbf d\cdot\mathbf n=1(2)+2(-1)+2(2)=4,
$$

and

$$
|\mathbf d|=3,\qquad |\mathbf n|=3.
$$

So

$$
\sin\phi=\frac{4}{9},
$$

and

$$
\phi=\sin^{-1}\frac49\approx 26.4^\circ.
$$

## Problem 18

Write the plane as

$$
x+2y-2z-5=0.
$$

The distance from $(x_0,y_0,z_0)$ to $ax+by+cz+d=0$ is

$$
\frac{|ax_0+by_0+cz_0+d|}{\sqrt{a^2+b^2+c^2}}.
$$

Therefore the distance is

$$
\frac{|1+2(2)-2(3)-5|}{\sqrt{1^2+2^2+(-2)^2}}
=\frac{6}{3}=2.
$$

## Problem 19

For skew lines

$$
\mathbf r=\mathbf a+s\mathbf d_1,
\qquad
\mathbf r=\mathbf b+t\mathbf d_2,
$$

the shortest distance is

$$
\frac{|(\mathbf b-\mathbf a)\cdot(\mathbf d_1\times\mathbf d_2)|}
{|\mathbf d_1\times\mathbf d_2|}.
$$

Here

$$
\mathbf a=\begin{pmatrix}0\\0\\0\end{pmatrix},
\quad
\mathbf b=\begin{pmatrix}0\\1\\0\end{pmatrix},
\quad
\mathbf d_1=\begin{pmatrix}1\\0\\1\end{pmatrix},
\quad
\mathbf d_2=\begin{pmatrix}0\\1\\1\end{pmatrix}.
$$

Now

$$
\mathbf d_1\times\mathbf d_2
=
\begin{pmatrix}-1\\-1\\1\end{pmatrix},
$$

so

$$
(\mathbf b-\mathbf a)\cdot(\mathbf d_1\times\mathbf d_2)
=
\begin{pmatrix}0\\1\\0\end{pmatrix}
\cdot
\begin{pmatrix}-1\\-1\\1\end{pmatrix}
=-1.
$$

Therefore the shortest distance is

$$
\frac{1}{\sqrt3}.
$$

## Problem 20

The planes are

$$
x+y+z=1
$$

and

$$
x-y=0.
$$

From the second plane, $y=x$. Put $x=t$, so $y=t$. Then the first plane gives

$$
t+t+z=1,
$$

so

$$
z=1-2t.
$$

Therefore a vector equation of the line of intersection is

$$
\mathbf r=
\begin{pmatrix}0\\0\\1\end{pmatrix}
+t\begin{pmatrix}1\\1\\-2\end{pmatrix},
\qquad t\in\mathbb R.
$$
