---
title: Kinematics and Newtonian Motion Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/02 Mechanics/02 Kinematics and Newtonian Motion/00 Overview|Kinematics and Newtonian Motion]]"
status: active
tags:
  - mathematics/mechanics
  - solutions
---

# Kinematics and Newtonian Motion Key Practice Solutions

This note gives worked solutions for [[20 Mathematics/02 Mechanics/02 Kinematics and Newtonian Motion/30 Key Practice Problems|Kinematics and Newtonian Motion Key Practice Problems]]. Use it to check sign conventions, units, graph interpretation, and force diagrams. Take $g=10\ \mathrm{m\ s^{-2}}$ unless a question states otherwise.

## A. Constant Acceleration and Motion Graphs

### Problem 1

Use

$$
v=u+at.
$$

With $u=5$, $a=2$, and $t=8$,

$$
v=5+2(8)=21\ \mathrm{m\ s^{-1}}.
$$

Use

$$
s=ut+\frac12at^2.
$$

Then

$$
s=5(8)+\frac12(2)(8^2)=104\ \mathrm{m}.
$$

### Problem 2

Take the direction of motion as positive. Then

$$
u=24,\qquad v=0,\qquad a=-3.
$$

From $v=u+at$,

$$
0=24-3t,
$$

so

$$
t=8\ \mathrm{s}.
$$

From $v^2=u^2+2as$,

$$
0=24^2+2(-3)s.
$$

Hence

$$
s=96\ \mathrm{m}.
$$

### Problem 3

Take upward as positive. Then

$$
u=30,\qquad a=-10.
$$

At the greatest height, $v=0$. Use

$$
v^2=u^2+2as.
$$

Thus

$$
0=30^2+2(-10)s,
$$

so

$$
s=45\ \mathrm{m}.
$$

The time to the highest point is found from

$$
0=30-10t,
$$

so $t=3\ \mathrm{s}$. The motion is symmetric under constant gravity, so the
total time back to the point of projection is

$$
6\ \mathrm{s}.
$$

### Problem 4

The displacement is the area under the velocity-time graph. The three areas
are:

$$
\frac12(4)(12)=24,
$$

$$
5(12)=60,
$$

and

$$
\frac12(3)(12)=18.
$$

Therefore the total displacement is

$$
24+60+18=102\ \mathrm{m}.
$$

The acceleration on the first section is

$$
\frac{12-0}{4-0}=3\ \mathrm{m\ s^{-2}}.
$$

The acceleration on the last section is

$$
\frac{0-12}{12-9}=-4\ \mathrm{m\ s^{-2}}.
$$

### Problem 5

Differentiate displacement:

$$
v=\frac{ds}{dt}=3t^2-12t+9.
$$

Set $v=0$:

$$
3t^2-12t+9=0.
$$

So

$$
t^2-4t+3=0,
$$

and

$$
t=1,\qquad t=3.
$$

The displacement from $t=0$ to $t=5$ is

$$
s(5)-s(0)=20-0=20\ \mathrm{m}.
$$

For total distance, use the turning points:

$$
s(0)=0,\qquad s(1)=4,\qquad s(3)=0,\qquad s(5)=20.
$$

Thus the total distance is

$$
|4-0|+|0-4|+|20-0|=28\ \mathrm{m}.
$$

## B. Calculus with Motion

### Problem 6

Displacement is the integral of velocity:

$$
s=\int_0^5(12-3t)\,dt.
$$

Therefore

$$
s=\left[12t-\frac32t^2\right]_0^5=22.5\ \mathrm{m}.
$$

For total distance, find where $v=0$:

$$
12-3t=0 \quad \Rightarrow \quad t=4.
$$

From $t=0$ to $t=4$,

$$
\left[12t-\frac32t^2\right]_0^4=24.
$$

From $t=4$ to $t=5$, the displacement is

$$
22.5-24=-1.5,
$$

so the distance on this part is $1.5\ \mathrm{m}$. The total distance is

$$
24+1.5=25.5\ \mathrm{m}.
$$

### Problem 7

Since $a=dv/dt$,

$$
v=\int(4-2t)\,dt=4t-t^2+C.
$$

Using $v(0)=1$ gives $C=1$, so

$$
v=1+4t-t^2.
$$

Since $v=ds/dt$,

$$
s=\int(1+4t-t^2)\,dt
=t+2t^2-\frac{t^3}{3}+D.
$$

Using $s(0)=3$ gives $D=3$, so

$$
s=3+t+2t^2-\frac{t^3}{3}.
$$

At $t=4$,

$$
s(4)=3+4+2(4^2)-\frac{4^3}{3}
=\frac{53}{3}\ \mathrm{m}.
$$

### Problem 8

Direction changes when velocity changes sign. Solve

$$
t^2-5t+6=0.
$$

Thus

$$
(t-2)(t-3)=0,
$$

so the particle changes direction at

$$
t=2\ \mathrm{s}\quad \text{and}\quad t=3\ \mathrm{s}.
$$

The displacement from $t=0$ to $t=4$ is

$$
\int_0^4(t^2-5t+6)\,dt
=\left[\frac{t^3}{3}-\frac52t^2+6t\right]_0^4
=\frac{16}{3}\ \mathrm{m}.
$$

For total distance, evaluate the position function

$$
S(t)=\frac{t^3}{3}-\frac52t^2+6t.
$$

Then

$$
S(0)=0,\quad S(2)=\frac{14}{3},\quad S(3)=\frac92,\quad S(4)=\frac{16}{3}.
$$

Therefore the total distance is

$$
\left|\frac{14}{3}-0\right|
+\left|\frac92-\frac{14}{3}\right|
+\left|\frac{16}{3}-\frac92\right|
=\frac{17}{3}\ \mathrm{m}.
$$

### Problem 9

Differentiate:

$$
v=\frac{ds}{dt}=4t-t^2.
$$

Differentiate again:

$$
a=\frac{dv}{dt}=4-2t.
$$

The particle moves in the positive direction while

$$
4t-t^2>0.
$$

This holds for $0<t<4$. The maximum displacement before it stops is at
$t=4$:

$$
s(4)=2(4^2)-\frac{4^3}{3}
=\frac{32}{3}\ \mathrm{m}.
$$

### Problem 10

The particles meet when

$$
2t^2+3t=30+8t-t^2.
$$

So

$$
3t^2-5t-30=0.
$$

Using the quadratic formula,

$$
t=\frac{5\pm\sqrt{385}}{6}.
$$

Reject the negative time, so

$$
t=\frac{5+\sqrt{385}}{6}=4.10\ \mathrm{s}\quad \text{to 3 s.f.}
$$

Substitute into $s_A=2t^2+3t$:

$$
s=46.0\ \mathrm{m}\quad \text{to 3 s.f.}
$$

## C. Newton's Laws for One Particle

### Problem 11

The surface is smooth, so the horizontal resultant force is $42\ \mathrm{N}$.
Newton's second law gives

$$
42=6a.
$$

Thus

$$
a=7\ \mathrm{m\ s^{-2}}.
$$

### Problem 12

The normal contact force is

$$
R=8g=80\ \mathrm{N}.
$$

The frictional force is

$$
F=\mu R=0.25(80)=20\ \mathrm{N}.
$$

The resultant force is

$$
50-20=30\ \mathrm{N}.
$$

Newton's second law gives

$$
30=8a,
$$

so

$$
a=3.75\ \mathrm{m\ s^{-2}}.
$$

### Problem 13

Take upward as positive. The resultant upward force is

$$
70-5g=70-50=20\ \mathrm{N}.
$$

Newton's second law gives

$$
20=5a.
$$

Hence

$$
a=4\ \mathrm{m\ s^{-2}}
$$

upwards.

### Problem 14

Take up the plane as positive. The only component of force along the smooth
plane is the component of weight down the plane:

$$
-mg\sin30^\circ.
$$

Thus

$$
ma=-mg\sin30^\circ,
$$

so

$$
a=-5\ \mathrm{m\ s^{-2}}.
$$

At the stopping point, $v=0$. From $v=u+at$,

$$
0=12-5t,
$$

so

$$
t=2.4\ \mathrm{s}.
$$

Using $v^2=u^2+2as$,

$$
0=12^2+2(-5)s.
$$

Therefore

$$
s=14.4\ \mathrm{m}.
$$

### Problem 15

Take down the plane as positive. The component of weight down the plane is

$$
mg\sin20^\circ.
$$

Friction acts up the plane, with magnitude

$$
\mu R=\mu mg\cos20^\circ.
$$

Newton's second law gives

$$
ma=mg\sin20^\circ-\mu mg\cos20^\circ.
$$

So

$$
a=g(\sin20^\circ-0.15\cos20^\circ).
$$

Hence

$$
a=2.01\ \mathrm{m\ s^{-2}}
$$

down the plane, to 3 s.f.

## D. Connected Particles and Mixed Review

### Problem 16

Let the $6\ \mathrm{kg}$ particle move downward with acceleration $a$. The
$2\ \mathrm{kg}$ particle moves upward with the same magnitude of acceleration.

For the $6\ \mathrm{kg}$ particle:

$$
60-T=6a.
$$

For the $2\ \mathrm{kg}$ particle:

$$
T-20=2a.
$$

Add the equations:

$$
40=8a.
$$

Thus

$$
a=5\ \mathrm{m\ s^{-2}}.
$$

Then

$$
T-20=2(5),
$$

so

$$
T=30\ \mathrm{N}.
$$

### Problem 17

Treat the two particles as one system:

$$
40=(3+5)a.
$$

So

$$
a=5\ \mathrm{m\ s^{-2}}.
$$

Use the $3\ \mathrm{kg}$ particle to find the tension:

$$
T=3a=15\ \mathrm{N}.
$$

### Problem 18

For the whole car-trailer system,

$$
1800-300-150=(900+300)a.
$$

Thus

$$
a=\frac{1350}{1200}=1.125\ \mathrm{m\ s^{-2}}.
$$

Use the trailer alone. If $T$ is the tow-bar tension, then

$$
T-150=300(1.125).
$$

Hence

$$
T=487.5\ \mathrm{N}.
$$

### Problem 19

Let the hanging $3\ \mathrm{kg}$ particle move downward with acceleration
$a$. For the $4\ \mathrm{kg}$ particle on the table,

$$
T=4a.
$$

For the hanging particle,

$$
30-T=3a.
$$

Substitute $T=4a$:

$$
30-4a=3a.
$$

Therefore

$$
a=\frac{30}{7}=4.29\ \mathrm{m\ s^{-2}}\quad \text{to 3 s.f.}
$$

and

$$
T=4a=\frac{120}{7}=17.1\ \mathrm{N}\quad \text{to 3 s.f.}
$$

### Problem 20

The normal contact force on the $4\ \mathrm{kg}$ block is

$$
R=4g=40\ \mathrm{N}.
$$

The frictional force is

$$
F=0.20(40)=8\ \mathrm{N}.
$$

Treat the two particles as one system. The driving force is the hanging
weight, and friction opposes the motion:

$$
60-8=(4+6)a.
$$

So

$$
a=5.2\ \mathrm{m\ s^{-2}}.
$$

Use the $4\ \mathrm{kg}$ block:

$$
T-8=4(5.2).
$$

Therefore

$$
T=28.8\ \mathrm{N}.
$$
