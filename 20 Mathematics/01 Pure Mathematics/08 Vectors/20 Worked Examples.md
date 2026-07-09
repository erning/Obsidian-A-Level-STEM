---
title: Vectors Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Vectors](00%20Overview.md)"
status: active
tags:
  - mathematics/pure
  - worked-examples
---

# Vectors Worked Examples

These examples model the standard CAIE route through position vectors,
displacement vectors, vector equations of lines, scalar products, intersections,
planes, vector products, and skew-line distance as a 9231 extension.

## Source Route

- Syllabus: CAIE Mathematics 9709 section 3.7; CAIE Further Mathematics 9231
  section 1.6.
- Main subtopics: vector notation, magnitudes, unit vectors, displacement,
  vector equations of lines, classifying lines, scalar product, projections,
  vector product, planes, line-plane intersections, and skew-line distance.
- Coursebook route: 9709 Pure Mathematics 2 and 3 Chapter 9; 9231 vector
  content.

## Example 1: Displacement, Magnitude, and Unit Vector

**Prompt.** Points $A$ and $B$ have position vectors

$$
\mathbf a=\begin{pmatrix}1\\2\\3\end{pmatrix},
\qquad
\mathbf b=\begin{pmatrix}5\\-1\\9\end{pmatrix}.
$$

Find $\overrightarrow{AB}$, its magnitude, and a unit vector in its direction.

**Solution.**

The displacement from $A$ to $B$ is

$$
\overrightarrow{AB}=\mathbf b-\mathbf a
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

**What this example trains.** A displacement vector is final position minus
initial position.

## Example 2: Vector Equation of a Line

**Prompt.** Find the vector equation of the line through
$A(1,2,3)$ and $B(5,-1,9)$.

**Solution.**

A direction vector is

$$
\overrightarrow{AB}=\begin{pmatrix}4\\-3\\6\end{pmatrix}.
$$

So the line is

$$
\mathbf r=\begin{pmatrix}1\\2\\3\end{pmatrix}
+t\begin{pmatrix}4\\-3\\6\end{pmatrix},
\qquad t\in\mathbb R.
$$

**What this example trains.** A vector line needs one point and one direction
vector.

## Example 3: Intersection of Two Lines

**Prompt.** Determine whether the lines

$$
L_1:\mathbf r=\begin{pmatrix}1\\0\\2\end{pmatrix}
+s\begin{pmatrix}2\\1\\-1\end{pmatrix}
$$

and

$$
L_2:\mathbf r=\begin{pmatrix}3\\1\\1\end{pmatrix}
+t\begin{pmatrix}1\\2\\0\end{pmatrix}
$$

intersect.

**Solution.**

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

so $t=0$. The first equation is then also satisfied:

$$
1+2(1)=3+0.
$$

The lines intersect at

$$
\begin{pmatrix}3\\1\\1\end{pmatrix}.
$$

**What this example trains.** In 3D, all three component equations must be
checked.

## Example 4: Scalar Product and Angle

**Prompt.** Find the angle between

$$
\mathbf a=\begin{pmatrix}1\\2\\2\end{pmatrix}
\quad\text{and}\quad
\mathbf b=\begin{pmatrix}3\\0\\4\end{pmatrix}.
$$

**Solution.**

The scalar product is

$$
\mathbf a\cdot\mathbf b=1(3)+2(0)+2(4)=11.
$$

The magnitudes are

$$
|\mathbf a|=3,\qquad |\mathbf b|=5.
$$

So

$$
\cos\theta=\frac{11}{15}.
$$

Therefore

$$
\theta=\cos^{-1}\frac{11}{15}\approx42.8^\circ.
$$

**What this example trains.** Scalar product connects components with angle.

## Example 5: Foot of a Perpendicular to a Line

**Prompt.** The line is

$$
\mathbf r=\begin{pmatrix}1\\0\\0\end{pmatrix}
+t\begin{pmatrix}1\\2\\2\end{pmatrix}.
$$

Find the foot of the perpendicular from $P(3,1,5)$ to the line.

**Solution.**

A general point on the line is

$$
Q=\begin{pmatrix}1+t\\2t\\2t\end{pmatrix}.
$$

The vector from $Q$ to $P$ is

$$
\overrightarrow{QP}
=\begin{pmatrix}2-t\\1-2t\\5-2t\end{pmatrix}.
$$

At the foot of the perpendicular, $\overrightarrow{QP}$ is perpendicular to the
line direction:

$$
\begin{pmatrix}2-t\\1-2t\\5-2t\end{pmatrix}
\cdot
\begin{pmatrix}1\\2\\2\end{pmatrix}=0.
$$

This gives

$$
14-9t=0,
$$

so

$$
t=\frac{14}{9}.
$$

The foot is

$$
\begin{pmatrix}\frac{23}{9}\\\frac{28}{9}\\\frac{28}{9}\end{pmatrix}.
$$

**What this example trains.** The shortest vector to a line is perpendicular to
the line direction.

## Example 6: Vector Product and Plane Normal

**Prompt.** Let

$$
\mathbf u=\begin{pmatrix}1\\2\\0\end{pmatrix},
\qquad
\mathbf v=\begin{pmatrix}3\\-1\\1\end{pmatrix}.
$$

Find $\mathbf u\times\mathbf v$ and the area of the parallelogram spanned by
$\mathbf u$ and $\mathbf v$.

**Solution.**

The vector product is

$$
\mathbf u\times\mathbf v
=\begin{pmatrix}2\\-1\\-7\end{pmatrix}.
$$

The parallelogram area is

$$
|\mathbf u\times\mathbf v|
=\sqrt{2^2+(-1)^2+(-7)^2}
=3\sqrt6.
$$

**What this example trains.** The vector product gives both an area and a
normal direction.

## Example 7: Plane Equation From a Point and Normal

**Prompt.** Find the Cartesian equation of the plane through $P(1,0,2)$ with
normal vector

$$
\mathbf n=\begin{pmatrix}2\\-1\\-7\end{pmatrix}.
$$

**Solution.**

Use

$$
(\mathbf r-\mathbf p)\cdot\mathbf n=0.
$$

So

$$
\begin{pmatrix}x-1\\y\\z-2\end{pmatrix}
\cdot
\begin{pmatrix}2\\-1\\-7\end{pmatrix}=0.
$$

This gives

$$
2(x-1)-y-7(z-2)=0.
$$

Therefore

$$
2x-y-7z+12=0.
$$

**What this example trains.** A plane in Cartesian form is controlled by a
normal vector.

## Example 8: Line-Plane Intersection

**Prompt.** Find the intersection of

$$
\mathbf r=\begin{pmatrix}0\\1\\2\end{pmatrix}
+t\begin{pmatrix}1\\-1\\3\end{pmatrix}
$$

with the plane

$$
x+2y-z=4.
$$

**Solution.**

Substitute

$$
x=t,\qquad y=1-t,\qquad z=2+3t.
$$

Then

$$
t+2(1-t)-(2+3t)=4.
$$

So

$$
-4t=4,
$$

and

$$
t=-1.
$$

The intersection point is

$$
\begin{pmatrix}-1\\2\\-1\end{pmatrix}.
$$

**What this example trains.** Substitute the parametric line into the plane
equation.

## Example 9: Shortest Distance Between Skew Lines

**Prompt.** Find the shortest distance between

$$
L_1:\mathbf r=s\begin{pmatrix}1\\0\\1\end{pmatrix}
$$

and

$$
L_2:\mathbf r=\begin{pmatrix}0\\1\\0\end{pmatrix}
+t\begin{pmatrix}0\\1\\1\end{pmatrix}.
$$

**Solution.**

The direction vectors are

$$
\mathbf d_1=\begin{pmatrix}1\\0\\1\end{pmatrix},
\qquad
\mathbf d_2=\begin{pmatrix}0\\1\\1\end{pmatrix}.
$$

A common perpendicular direction is

$$
\mathbf d_1\times\mathbf d_2
=\begin{pmatrix}-1\\-1\\1\end{pmatrix}.
$$

Take one point on each line:

$$
P_1=\begin{pmatrix}0\\0\\0\end{pmatrix},
\qquad
P_2=\begin{pmatrix}0\\1\\0\end{pmatrix}.
$$

The shortest distance is

$$
\frac{|(\overrightarrow{P_1P_2})\cdot(\mathbf d_1\times\mathbf d_2)|}
{|\mathbf d_1\times\mathbf d_2|}
=\frac{1}{\sqrt3}.
$$

**What this example trains.** For skew lines, the shortest distance lies along
a direction perpendicular to both lines.
