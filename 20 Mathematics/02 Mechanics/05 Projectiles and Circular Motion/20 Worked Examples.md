---
title: Projectiles and Circular Motion Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Projectiles and Circular Motion](00%20Overview.md)"
status: active
tags:
  - mathematics/mechanics
  - worked-examples
---

# Projectiles and Circular Motion Worked Examples

These examples model the 9231 route through projectile component equations,
trajectory equations, angular speed, centripetal acceleration, horizontal
circles, and vertical circles. Take $g=10\ \mathrm{m\ s^{-2}}$ unless a
question states otherwise.

## Source Route

- CAIE Further Mathematics 9231 section 3.1: projectile motion as constant
  acceleration, horizontal and vertical equations, velocity magnitude and
  direction, range, greatest height, and Cartesian trajectory.
- CAIE Further Mathematics 9231 section 3.3: angular speed, centripetal
  acceleration, horizontal circular motion, and vertical circular motion with
  energy and contact or tension conditions.

## Example 1: Time of Flight, Range, and Greatest Height

**Prompt.** A projectile is launched from horizontal ground at
$20\ \mathrm{m\ s^{-1}}$ at $30^\circ$ above the horizontal. Find its time of
flight, range, and greatest height.

**Solution.**

Resolve the initial velocity:

$$
u_x=20\cos30^\circ,\qquad u_y=20\sin30^\circ=10.
$$

At landing, the vertical displacement is zero:

$$
0=10t-\frac12(10)t^2.
$$

So

$$
0=10t-5t^2=5t(2-t).
$$

The non-zero time is

$$
t=2\ \mathrm{s}.
$$

The range is

$$
R=(20\cos30^\circ)(2)=34.6\ \mathrm{m}\quad \text{to 3 s.f.}
$$

At the greatest height, $v_y=0$:

$$
0=10^2-2(10)h.
$$

Thus

$$
h=5\ \mathrm{m}.
$$

**Check.** The horizontal velocity is constant; only the vertical component is
changed by gravity.

## Example 2: Projectile Landing Below the Launch Point

**Prompt.** A projectile is launched from a cliff $20\ \mathrm{m}$ above the
ground at speed $25\ \mathrm{m\ s^{-1}}$. Its initial velocity components are
$20\ \mathrm{m\ s^{-1}}$ horizontally and $15\ \mathrm{m\ s^{-1}}$ vertically
upwards. Find the time to hit the ground, the horizontal range, and the impact
speed.

**Solution.**

Take the launch point as $y=0$. The ground is at $y=-20$. Vertically,

$$
-20=15t-5t^2.
$$

So

$$
t^2-3t-4=0.
$$

The positive root is

$$
t=4\ \mathrm{s}.
$$

The horizontal range is

$$
x=20(4)=80\ \mathrm{m}.
$$

At impact,

$$
v_x=20,\qquad v_y=15-10(4)=-25.
$$

The impact speed is

$$
\sqrt{20^2+25^2}=32.0\ \mathrm{m\ s^{-1}}\quad \text{to 3 s.f.}
$$

**Check.** The vertical velocity is negative at impact, as the projectile is
moving downwards.

## Example 3: Cartesian Trajectory

**Prompt.** A projectile is launched at $30\ \mathrm{m\ s^{-1}}$ at
$45^\circ$ above the horizontal. Find the Cartesian equation of its trajectory
and its height when $x=45\ \mathrm{m}$.

**Solution.**

Use

$$
y=x\tan\theta-\frac{gx^2}{2u^2\cos^2\theta}.
$$

Here $\theta=45^\circ$, so $\tan\theta=1$ and $\cos^2\theta=\frac12$. Thus

$$
y=x-\frac{10x^2}{2(30^2)(1/2)}
=x-\frac{x^2}{90}.
$$

At $x=45$,

$$
y=45-\frac{45^2}{90}=22.5\ \mathrm{m}.
$$

**Check.** The trajectory is a downward-opening parabola.

## Example 4: Finding Possible Angles of Projection

**Prompt.** A projectile is fired from the origin with speed
$20\ \mathrm{m\ s^{-1}}$ and passes through the point $(30,5)$. Find the
possible angles of projection.

**Solution.**

Let $T=\tan\theta$. Use

$$
y=xT-\frac{gx^2}{2u^2}(1+T^2).
$$

Substitute $x=30$, $y=5$, $u=20$, and $g=10$:

$$
5=30T-\frac{10(30^2)}{2(20^2)}(1+T^2).
$$

So

$$
5=30T-11.25(1+T^2).
$$

This simplifies to

$$
9T^2-24T+13=0.
$$

Hence

$$
T=\frac{4\pm\sqrt3}{3}.
$$

Therefore

$$
\theta=62.4^\circ\quad \text{or}\quad 37.1^\circ
$$

to 3 s.f.

**Check.** Two angles are possible because a low path and a high path can pass
through the same point.

## Example 5: Uniform Circular Motion

**Prompt.** A $2\ \mathrm{kg}$ particle moves in a circle of radius
$3\ \mathrm{m}$ at constant speed $6\ \mathrm{m\ s^{-1}}$. Find its angular
speed and the resultant force towards the centre.

**Solution.**

Use $v=r\omega$:

$$
\omega=\frac{v}{r}=\frac{6}{3}=2\ \mathrm{rad\ s^{-1}}.
$$

The centripetal acceleration is

$$
\frac{v^2}{r}=\frac{6^2}{3}=12\ \mathrm{m\ s^{-2}}.
$$

The resultant force towards the centre is

$$
F=m\frac{v^2}{r}=2(12)=24\ \mathrm{N}.
$$

**Check.** This $24\ \mathrm{N}$ must be supplied by real forces; it is not a
new extra force.

## Example 6: Conical Pendulum

**Prompt.** A $0.5\ \mathrm{kg}$ particle is attached to a light string of
length $2\ \mathrm{m}$ and moves in a horizontal circle. The string makes
$60^\circ$ with the vertical. Find the tension and angular speed.

**Solution.**

Vertical equilibrium gives

$$
T\cos60^\circ=mg=5.
$$

Thus

$$
T=10\ \mathrm{N}.
$$

The radius of the circle is $2\sin60^\circ$. Horizontally,

$$
T\sin60^\circ=m\omega^2(2\sin60^\circ).
$$

Cancel $\sin60^\circ$:

$$
T=2m\omega^2.
$$

So

$$
10=2(0.5)\omega^2,
$$

and

$$
\omega=\sqrt{10}=3.16\ \mathrm{rad\ s^{-1}}.
$$

**Check.** The vertical component of tension balances weight, while the
horizontal component supplies the radial acceleration.

## Example 7: Tension in a Vertical Circle

**Prompt.** A $0.5\ \mathrm{kg}$ particle attached to a light string of length
$1\ \mathrm{m}$ moves in a vertical circle. Its speed at the top is
$4\ \mathrm{m\ s^{-1}}$. Find the tension at the top and, assuming no energy
loss, the tension at the bottom.

**Solution.**

At the top, towards the centre is downward:

$$
T+mg=m\frac{v^2}{r}.
$$

So

$$
T+5=0.5(16),
$$

giving

$$
T=3\ \mathrm{N}.
$$

From top to bottom the particle drops $2\ \mathrm{m}$, so

$$
v_b^2=4^2+2(10)(2)=56.
$$

At the bottom, towards the centre is upward:

$$
T_b-mg=m\frac{v_b^2}{r}.
$$

Thus

$$
T_b-5=0.5(56),
$$

so

$$
T_b=33\ \mathrm{N}.
$$

**Check.** The bottom tension is larger because the speed is larger and weight
acts away from the centre there.

## Example 8: Minimum Speed for a Complete Vertical Circle

**Prompt.** A particle on a light string of length $2\ \mathrm{m}$ moves in a
vertical circle. Find the minimum speed at the bottom for the string to remain
taut throughout the circle.

**Solution.**

At the limiting top point, the tension is zero:

$$
mg=m\frac{v_t^2}{r}.
$$

So

$$
v_t^2=gr=20.
$$

From bottom to top the particle rises by $2r=4\ \mathrm{m}$. Energy gives

$$
\frac12mv_b^2=\frac12mv_t^2+mg(4).
$$

Cancel $m$ and multiply by $2$:

$$
v_b^2=v_t^2+80=100.
$$

Therefore

$$
v_b=10\ \mathrm{m\ s^{-1}}.
$$

**Check.** The standard result is $v_b^2=5gr$, and here $5gr=100$.
