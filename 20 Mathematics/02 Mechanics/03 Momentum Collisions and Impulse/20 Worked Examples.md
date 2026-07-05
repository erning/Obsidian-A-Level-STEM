---
title: Momentum, Collisions and Impulse Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/02 Mechanics/03 Momentum Collisions and Impulse/00 Overview|Momentum, Collisions and Impulse]]"
status: active
tags:
  - mathematics/mechanics
  - worked-examples
---

# Momentum, Collisions and Impulse Worked Examples

These examples model the syllabus route through signed momentum, direct
impact, coalescence, impulse, coefficient of restitution, energy checks, and
oblique impact. Treat rightward or the stated line of impact as positive unless
a different direction is declared.

## Source Route

- CAIE Mathematics 9709 section 4.3: linear momentum as a vector quantity and
  conservation of momentum for one-dimensional direct impact, including
  coalescence.
- CAIE Further Mathematics 9231 section 3.6: Newton's experimental law,
  coefficient of restitution, direct and oblique impact of smooth spheres, and
  impact with a fixed smooth surface.

## Example 1: Coalescence in a Direct Impact

**Prompt.** A $2\ \mathrm{kg}$ particle moving at $6\ \mathrm{m\ s^{-1}}$
collides with a stationary $3\ \mathrm{kg}$ particle. They stick together.
Find their common velocity after impact.

**Solution.**

There is no external impulse along the line of motion, so total momentum is
conserved:

$$
2(6)+3(0)=(2+3)v.
$$

Thus

$$
12=5v,
$$

so

$$
v=2.4\ \mathrm{m\ s^{-1}}.
$$

**Check.** The final speed is between $0$ and $6\ \mathrm{m\ s^{-1}}$, as
expected when a moving particle sticks to a stationary one.

## Example 2: Direct Impact with Restitution

**Prompt.** A $2\ \mathrm{kg}$ particle moving at $5\ \mathrm{m\ s^{-1}}$
collides directly with a $1\ \mathrm{kg}$ particle moving in the same direction
at $1\ \mathrm{m\ s^{-1}}$. The coefficient of restitution is $0.5$. Find the
velocities after impact.

**Solution.**

Let the final velocities be $v_1$ for the $2\ \mathrm{kg}$ particle and $v_2$
for the $1\ \mathrm{kg}$ particle. Conservation of momentum gives

$$
2(5)+1(1)=2v_1+v_2.
$$

So

$$
11=2v_1+v_2.
$$

Newton's experimental law gives

$$
v_2-v_1=0.5(5-1)=2.
$$

Solving the two equations,

$$
v_1=3\ \mathrm{m\ s^{-1}},\qquad v_2=5\ \mathrm{m\ s^{-1}}.
$$

**Check.** The particles separate after impact because $v_2>v_1$.

## Example 3: Impulse from a Change in Momentum

**Prompt.** A ball of mass $0.5\ \mathrm{kg}$ moving at
$12\ \mathrm{m\ s^{-1}}$ hits a wall and rebounds at $8\ \mathrm{m\ s^{-1}}$
in the opposite direction. Find the impulse on the ball. If the contact time
is $0.040\ \mathrm{s}$, find the average force on the ball.

**Solution.**

Take the original direction as positive. Then

$$
u=12,\qquad v=-8.
$$

Impulse is change in momentum:

$$
I=m(v-u)=0.5(-8-12)=-10\ \mathrm{N\ s}.
$$

The impulse has magnitude $10\ \mathrm{N\ s}$ and acts opposite to the original
motion.

Average force satisfies

$$
I=Ft.
$$

Thus

$$
F=\frac{-10}{0.040}=-250\ \mathrm{N}.
$$

**Check.** A negative force is expected because the wall reverses the ball's
velocity.

## Example 4: Area Under a Force-Time Graph

**Prompt.** A force on a $6\ \mathrm{kg}$ particle rises uniformly from $0$ to
$40\ \mathrm{N}$ in $2\ \mathrm{s}$, stays at $40\ \mathrm{N}$ until
$t=5\ \mathrm{s}$, then falls uniformly to $0$ at $t=6\ \mathrm{s}$. The
particle initially moves at $3\ \mathrm{m\ s^{-1}}$ in the direction of the
force. Find its final velocity.

**Solution.**

Impulse is the area under the force-time graph:

$$
I=\frac12(2)(40)+(3)(40)+\frac12(1)(40).
$$

Hence

$$
I=40+120+20=180\ \mathrm{N\ s}.
$$

Using $I=m(v-u)$,

$$
180=6(v-3).
$$

So

$$
v=33\ \mathrm{m\ s^{-1}}.
$$

**Check.** The force acts in the same direction as the motion, so the speed
increases.

## Example 5: Explosion as Momentum Conservation

**Prompt.** A body at rest breaks into two parts of masses $2\ \mathrm{kg}$
and $3\ \mathrm{kg}$. The $2\ \mathrm{kg}$ part moves right at
$6\ \mathrm{m\ s^{-1}}$. Find the velocity of the $3\ \mathrm{kg}$ part.

**Solution.**

The original momentum is zero. Let the velocity of the $3\ \mathrm{kg}$ part
be $v$, with right positive. Conservation of momentum gives

$$
0=2(6)+3v.
$$

Thus

$$
v=-4\ \mathrm{m\ s^{-1}}.
$$

The $3\ \mathrm{kg}$ part moves left at $4\ \mathrm{m\ s^{-1}}$.

**Check.** The two momenta are $12$ and $-12\ \mathrm{kg\ m\ s^{-1}}$, so the
total remains zero.

## Example 6: Energy Loss in a Coalescing Collision

**Prompt.** In Example 1, find the kinetic energy lost in the collision.

**Solution.**

Initial kinetic energy is

$$
\frac12(2)(6^2)=36\ \mathrm{J}.
$$

Final kinetic energy is

$$
\frac12(5)(2.4^2)=14.4\ \mathrm{J}.
$$

The kinetic energy lost is

$$
36-14.4=21.6\ \mathrm{J}.
$$

**Check.** Momentum is conserved, but kinetic energy is not conserved because
the particles stick together.

## Example 7: Oblique Impact with a Fixed Smooth Wall

**Prompt.** A smooth sphere hits a fixed smooth wall at speed
$20\ \mathrm{m\ s^{-1}}$. Its velocity makes $30^\circ$ with the normal to the
wall. The coefficient of restitution is $0.6$. Find the speed after impact and
the angle the new velocity makes with the normal.

**Solution.**

Resolve into normal and tangential components. Before impact,

$$
u_n=20\cos30^\circ,\qquad u_t=20\sin30^\circ.
$$

For a fixed smooth wall, the tangential component is unchanged:

$$
v_t=20\sin30^\circ=10.
$$

The normal component reverses and is multiplied in magnitude by $e$:

$$
|v_n|=0.6(20\cos30^\circ)=10.4\quad \text{to 3 s.f.}
$$

The speed after impact is

$$
\sqrt{10.4^2+10^2}=14.4\ \mathrm{m\ s^{-1}}\quad \text{to 3 s.f.}
$$

The angle $\theta$ with the normal satisfies

$$
\tan\theta=\frac{10}{10.4}.
$$

Thus

$$
\theta=43.9^\circ\quad \text{to 3 s.f.}
$$

**Check.** The angle increases because the normal component has been reduced.

## Example 8: Oblique Impact of Identical Smooth Spheres

**Prompt.** Sphere $A$ strikes an identical smooth sphere $B$, initially at
rest. Before impact, the component of $A$'s velocity along the line of centres
is $6\ \mathrm{m\ s^{-1}}$, and its perpendicular component is
$8\ \mathrm{m\ s^{-1}}$. The coefficient of restitution is $0.5$. Find the
components of the velocities after impact.

**Solution.**

Smooth contact gives no impulse perpendicular to the line of centres. Thus
$A$ keeps perpendicular component $8\ \mathrm{m\ s^{-1}}$, and $B$ has
perpendicular component $0$.

Along the line of centres, the masses are equal. Let the after-impact normal
components be $v_A$ and $v_B$. Momentum gives

$$
6=v_A+v_B.
$$

Restitution gives

$$
v_B-v_A=0.5(6)=3.
$$

Solving,

$$
v_A=1.5,\qquad v_B=4.5.
$$

So after impact, $A$ has components $1.5$ along the line of centres and $8$
perpendicular to it, while $B$ has components $4.5$ along the line of centres
and $0$ perpendicular to it.

**Check.** Only the normal components change, which matches the smooth-sphere
model.
