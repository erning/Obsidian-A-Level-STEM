---
title: Kinematics and Newtonian Motion Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Kinematics and Newtonian Motion](00%20Overview.md)"
status: active
tags:
  - mathematics/mechanics
  - worked-examples
---

# Kinematics and Newtonian Motion Worked Examples

These examples model the syllabus route through straight-line motion,
motion graphs, calculus links, constant acceleration, Newton's second law,
and connected-particle models. For this Mechanics component, take
$g=10\ \mathrm{m\ s^{-2}}$ unless a question states otherwise.

## Source Route

- CAIE Mathematics 9709 section 4.2: distance, speed, displacement, velocity,
  acceleration, displacement-time graphs, velocity-time graphs, calculus with
  respect to time, and constant-acceleration formulae.
- CAIE Mathematics 9709 section 4.4: Newton's laws for particles of constant
  mass under constant forces, $W=mg$, vertical and inclined-plane motion, and
  connected particles.

## Example 1: Reading a Velocity-Time Graph

**Prompt.** A particle has velocity $4\ \mathrm{m\ s^{-1}}$ at $t=0$ and
$16\ \mathrm{m\ s^{-1}}$ at $t=6$. Its velocity-time graph is a straight line
between these points. Find the acceleration and displacement in the first
$6\ \mathrm{s}$.

**Solution.**

The acceleration is the gradient of the velocity-time graph:

$$
a=\frac{16-4}{6}=2\ \mathrm{m\ s^{-2}}.
$$

The displacement is the area under the velocity-time graph. The area is a
trapezium:

$$
s=\frac12(4+16)(6)=60\ \mathrm{m}.
$$

**Check.** The average velocity is $10\ \mathrm{m\ s^{-1}}$, so in
$6\ \mathrm{s}$ the displacement should be $60\ \mathrm{m}$.

## Example 2: Motion Until Rest

**Prompt.** A particle is moving at $20\ \mathrm{m\ s^{-1}}$ and decelerates
uniformly at $2.5\ \mathrm{m\ s^{-2}}$. Find the time taken to come to rest
and the distance travelled before stopping.

**Solution.**

Take the original direction of motion as positive. Then

$$
u=20,\qquad v=0,\qquad a=-2.5.
$$

Use $v=u+at$:

$$
0=20-2.5t,
$$

so

$$
t=8\ \mathrm{s}.
$$

Use $v^2=u^2+2as$:

$$
0=20^2+2(-2.5)s.
$$

Hence

$$
s=80\ \mathrm{m}.
$$

**Check.** The average speed during uniform deceleration to rest is
$10\ \mathrm{m\ s^{-1}}$, and $10\times 8=80$.

## Example 3: Differentiating a Displacement Function

**Prompt.** A particle has displacement

$$
s=t^3-6t^2+9t
$$

from a fixed origin, where $t$ is in seconds and $s$ is in metres. Find its
velocity and acceleration, and find when it is instantaneously at rest.

**Solution.**

Velocity is the derivative of displacement:

$$
v=\frac{ds}{dt}=3t^2-12t+9.
$$

Acceleration is the derivative of velocity:

$$
a=\frac{dv}{dt}=6t-12.
$$

The particle is instantaneously at rest when $v=0$:

$$
3t^2-12t+9=0.
$$

Divide by $3$:

$$
t^2-4t+3=0.
$$

Thus

$$
t=1\quad \text{or}\quad t=3.
$$

**Check.** The two rest times are turning points of the displacement-time
graph, not necessarily endpoints of the motion.

## Example 4: Integrating a Variable Acceleration

**Prompt.** A particle moves in a straight line with acceleration

$$
a=6-2t.
$$

Given $v=4$ and $s=0$ when $t=0$, find $v(t)$ and the displacement in the
first $4\ \mathrm{s}$.

**Solution.**

Since $a=dv/dt$,

$$
v=\int(6-2t)\,dt=6t-t^2+C.
$$

Using $v(0)=4$ gives $C=4$, so

$$
v=4+6t-t^2.
$$

Since $v=ds/dt$,

$$
s=\int(4+6t-t^2)\,dt
=4t+3t^2-\frac{t^3}{3}+D.
$$

Using $s(0)=0$ gives $D=0$. Therefore, at $t=4$,

$$
s=4(4)+3(4^2)-\frac{4^3}{3}
=\frac{128}{3}\ \mathrm{m}.
$$

**Check.** The acceleration changes with time, so constant-acceleration
formulae are not allowed here.

## Example 5: Newton's Second Law on a Rough Horizontal Surface

**Prompt.** An $8\ \mathrm{kg}$ block is pulled along a rough horizontal
surface by a horizontal force of $50\ \mathrm{N}$. The coefficient of friction
is $0.20$. Find its acceleration.

**Solution.**

The normal contact force is

$$
R=8g=80\ \mathrm{N}.
$$

The frictional force is

$$
F=\mu R=0.20(80)=16\ \mathrm{N}.
$$

The resultant force in the direction of motion is

$$
50-16=34\ \mathrm{N}.
$$

Using Newton's second law,

$$
34=8a,
$$

so

$$
a=4.25\ \mathrm{m\ s^{-2}}.
$$

**Check.** The acceleration is less than $50/8$ because friction reduces the
resultant force.

## Example 6: Motion Down a Smooth Incline

**Prompt.** A $4\ \mathrm{kg}$ particle is released from rest on a smooth plane
inclined at $30^\circ$ to the horizontal. Find its acceleration down the plane
and the time taken to travel $10\ \mathrm{m}$.

**Solution.**

The component of weight down the plane is

$$
mg\sin30^\circ.
$$

Newton's second law down the plane gives

$$
mg\sin30^\circ=ma.
$$

Thus

$$
a=g\sin30^\circ=5\ \mathrm{m\ s^{-2}}.
$$

Starting from rest,

$$
s=\frac12at^2.
$$

So

$$
10=\frac12(5)t^2.
$$

Hence

$$
t=2\ \mathrm{s}.
$$

**Check.** The mass cancels because both the driving force and inertia are
proportional to the mass.

## Example 7: Connected Particles over a Smooth Pulley

**Prompt.** Particles of masses $3\ \mathrm{kg}$ and $5\ \mathrm{kg}$ are
connected by a light inextensible string over a smooth pulley. The heavier
particle moves downward. Find the acceleration and the tension.

**Solution.**

Let the $5\ \mathrm{kg}$ particle move downward with acceleration $a$, so the
$3\ \mathrm{kg}$ particle moves upward with the same magnitude of acceleration.

For the $5\ \mathrm{kg}$ particle:

$$
5g-T=5a.
$$

For the $3\ \mathrm{kg}$ particle:

$$
T-3g=3a.
$$

Add the equations to eliminate $T$:

$$
2g=8a.
$$

Thus

$$
a=2.5\ \mathrm{m\ s^{-2}}.
$$

Then

$$
T-30=3(2.5),
$$

so

$$
T=37.5\ \mathrm{N}.
$$

**Check.** The acceleration is less than $g$, and the tension lies between the
two weights $30\ \mathrm{N}$ and $50\ \mathrm{N}$.

## Example 8: A Car Towing a Trailer

**Prompt.** A car of mass $800\ \mathrm{kg}$ tows a trailer of mass
$200\ \mathrm{kg}$ along a straight horizontal road. The driving force is
$1500\ \mathrm{N}$. The resistances on the car and trailer are
$300\ \mathrm{N}$ and $100\ \mathrm{N}$ respectively. Find the acceleration
and the tension in the tow-bar.

**Solution.**

Treat the car and trailer as one system to find the acceleration:

$$
1500-300-100=(800+200)a.
$$

Hence

$$
a=1.10\ \mathrm{m\ s^{-2}}.
$$

Now use the trailer alone. Let $T$ be the tow-bar tension. For the trailer,

$$
T-100=200(1.10).
$$

Therefore

$$
T=320\ \mathrm{N}.
$$

**Check.** The tow-bar tension is an internal force for the whole system, so
it should not appear in the whole-system equation.
