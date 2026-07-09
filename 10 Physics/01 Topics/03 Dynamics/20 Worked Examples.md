---
title: Dynamics Worked Examples
subject: Physics
syllabus: 9702
parent: "[Dynamics](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/mechanics
  - worked-examples
---

# Dynamics Worked Examples

These examples model how to decide whether a problem is best handled through
resultant force, momentum change, or momentum conservation.

Take $g=9.81\ \mathrm{m\ s^{-2}}$ where needed.

## Example 1: Resultant Force and Acceleration

**Prompt.** A car of mass $950\ \mathrm{kg}$ has a driving force of
$1800\ \mathrm{N}$ forwards. Resistive forces total $420\ \mathrm{N}$ backwards.
Find the acceleration.

### Solution

Take forwards as positive. The resultant force is

$$
F_{\text{resultant}}=1800-420=1380\ \mathrm{N}.
$$

Use Newton's second law for constant mass:

$$
F_{\text{resultant}}=ma.
$$

So

$$
a=\frac{1380}{950}=1.45\ \mathrm{m\ s^{-2}}.
$$

The acceleration is forwards.

### Check

The acceleration is in the direction of the resultant force, not just in the
direction of the largest named force.

## Example 2: Force Components

**Prompt.** A $12\ \mathrm{kg}$ box is pulled along horizontal ground by a
$75\ \mathrm{N}$ force at $30^\circ$ above the horizontal. Friction is
$18\ \mathrm{N}$. Find the horizontal acceleration.

### Solution

Only the horizontal component of the pull accelerates the box horizontally:

$$
F_x=75\cos30^\circ=65.0\ \mathrm{N}.
$$

Take the direction of motion as positive. The horizontal resultant force is

$$
F_{\text{resultant}}=65.0-18=47.0\ \mathrm{N}.
$$

Therefore

$$
a=\frac{F_{\text{resultant}}}{m}
=\frac{47.0}{12}
=3.91\ \mathrm{m\ s^{-2}}.
$$

### Check

The vertical component of the pull affects the contact force, but it is not a
horizontal accelerating force.

## Example 3: Mass, Weight, and Inertia

**Prompt.** A rover has mass $180\ \mathrm{kg}$. Find its weight on Earth and
on the Moon, taking $g_{\text{Earth}}=9.81\ \mathrm{N\ kg^{-1}}$ and
$g_{\text{Moon}}=1.6\ \mathrm{N\ kg^{-1}}$. Explain whether it is easier to
start the rover moving horizontally on the Moon.

### Solution

Weight is

$$
W=mg.
$$

On Earth,

$$
W=(180)(9.81)=1.77\times 10^3\ \mathrm{N}.
$$

On the Moon,

$$
W=(180)(1.6)=2.9\times 10^2\ \mathrm{N}.
$$

The rover weighs less on the Moon because gravitational field strength is
smaller. Its mass is still $180\ \mathrm{kg}$, so its inertia is unchanged.
Ignoring differences in friction, the same horizontal resultant force would
produce the same horizontal acceleration.

### Check

Weight depends on gravitational field strength. Mass does not change from place
to place.

## Example 4: Drag and Top Speed

**Prompt.** A cyclist and bicycle have total mass $82\ \mathrm{kg}$. The
maximum driving force is $60\ \mathrm{N}$. The drag force is modelled by

$$
D=0.24v^2,
$$

where $D$ is in newtons and $v$ is in $\mathrm{m\ s^{-1}}$. Find the top speed
and the acceleration at $v=10\ \mathrm{m\ s^{-1}}$.

### Solution

At top speed, acceleration is zero, so the resultant force is zero:

$$
D=60\ \mathrm{N}.
$$

Thus

$$
0.24v^2=60.
$$

So

$$
v=\sqrt{\frac{60}{0.24}}=15.8\ \mathrm{m\ s^{-1}}.
$$

At $v=10\ \mathrm{m\ s^{-1}}$,

$$
D=0.24(10)^2=24\ \mathrm{N}.
$$

The resultant force is

$$
60-24=36\ \mathrm{N}.
$$

Therefore

$$
a=\frac{36}{82}=0.44\ \mathrm{m\ s^{-2}}.
$$

### Check

At top speed, the cyclist is still moving, but the resultant force is zero, so
the acceleration is zero.

## Example 5: Impulse and Average Force

**Prompt.** A $0.046\ \mathrm{kg}$ golf ball is initially at rest. A club sends
it away at $52\ \mathrm{m\ s^{-1}}$. The contact time is $1.4\ \mathrm{ms}$.
Find the average force on the ball.

### Solution

Impulse is change in momentum:

$$
F_{\text{average}}\Delta t=\Delta p.
$$

The change in momentum is

$$
\Delta p=m(v-u)
=(0.046)(52-0)
=2.392\ \mathrm{kg\ m\ s^{-1}}.
$$

Convert the time:

$$
1.4\ \mathrm{ms}=1.4\times 10^{-3}\ \mathrm{s}.
$$

So

$$
F_{\text{average}}
=\frac{2.392}{1.4\times 10^{-3}}
=1.7\times 10^3\ \mathrm{N}.
$$

### Check

The force is large because the momentum change happens in a very short time.

## Example 6: Completely Inelastic Collision

**Prompt.** A $0.80\ \mathrm{kg}$ trolley moving at
$3.0\ \mathrm{m\ s^{-1}}$ collides with a stationary $1.60\ \mathrm{kg}$
trolley. They stick together. Find their common velocity and the kinetic
energy lost.

### Solution

Take the initial direction of the first trolley as positive. Momentum is
conserved during the collision:

$$
m_1u_1+m_2u_2=(m_1+m_2)v.
$$

Substitute:

$$
(0.80)(3.0)+(1.60)(0)=(0.80+1.60)v.
$$

So

$$
v=\frac{2.40}{2.40}=1.0\ \mathrm{m\ s^{-1}}.
$$

Initial kinetic energy:

$$
E_{k,\text{initial}}
=\frac{1}{2}(0.80)(3.0)^2
=3.6\ \mathrm{J}.
$$

Final kinetic energy:

$$
E_{k,\text{final}}
=\frac{1}{2}(2.40)(1.0)^2
=1.2\ \mathrm{J}.
$$

Kinetic energy lost:

$$
3.6-1.2=2.4\ \mathrm{J}.
$$

### Check

Momentum is conserved, but kinetic energy is not conserved because the trolleys
stick together.

## Example 7: Perfectly Elastic Collision

**Prompt.** A $1.0\ \mathrm{kg}$ cart moving at $3.0\ \mathrm{m\ s^{-1}}$
collides elastically in one dimension with a stationary $2.0\ \mathrm{kg}$
cart. Find the final velocities.

### Solution

Take the initial direction of the first cart as positive. Momentum conservation
gives

$$
(1.0)(3.0)=(1.0)v_1+(2.0)v_2.
$$

So

$$
3.0=v_1+2v_2.
$$

For a perfectly elastic collision, relative speed of approach equals relative
speed of separation:

$$
u_1-u_2=v_2-v_1.
$$

Here

$$
3.0-0=v_2-v_1.
$$

So

$$
v_2=v_1+3.0.
$$

Substitute into the momentum equation:

$$
3.0=v_1+2(v_1+3.0).
$$

Thus

$$
3v_1=-3.0,
$$

so

$$
v_1=-1.0\ \mathrm{m\ s^{-1}}.
$$

Then

$$
v_2=2.0\ \mathrm{m\ s^{-1}}.
$$

### Check

The lighter cart rebounds. The relative speed before collision is
$3.0\ \mathrm{m\ s^{-1}}$, and the relative speed after collision is also
$3.0\ \mathrm{m\ s^{-1}}$.

## Example 8: Momentum in Two Dimensions

**Prompt.** A particle initially has momentum
$5.0\ \mathrm{kg\ m\ s^{-1}}$ east. After a collision, one object has momentum
$3.0\ \mathrm{kg\ m\ s^{-1}}$ at $30^\circ$ north of east. Find the momentum of
the other object.

### Solution

Resolve momentum into components. Initial momentum:

$$
p_x=5.0,\qquad p_y=0.
$$

The known final momentum has components

$$
p_{1x}=3.0\cos30^\circ=2.60,
$$

$$
p_{1y}=3.0\sin30^\circ=1.50.
$$

Conservation of momentum in the $x$-direction gives

$$
p_{2x}=5.0-2.60=2.40.
$$

Conservation of momentum in the $y$-direction gives

$$
p_{2y}=0-1.50=-1.50.
$$

The magnitude is

$$
p_2=\sqrt{2.40^2+1.50^2}
=2.83\ \mathrm{kg\ m\ s^{-1}}.
$$

The direction is

$$
\theta=\tan^{-1}\left(\frac{1.50}{2.40}\right)
=32^\circ.
$$

So the second object has momentum

$$
2.83\ \mathrm{kg\ m\ s^{-1}}
$$

at $32^\circ$ south of east.

### Check

The southward component cancels the northward component of the first final
object, so total $y$-momentum remains zero.

## Example 9: Explosion and Recoil

**Prompt.** A stationary object explodes into two fragments. One fragment has
mass $0.12\ \mathrm{kg}$ and moves east at $40\ \mathrm{m\ s^{-1}}$. The other
fragment has mass $0.18\ \mathrm{kg}$. Find the velocity of the second
fragment, and explain the energy change.

### Solution

The initial momentum is zero. Take east as positive. Conservation of momentum
gives

$$
0=(0.12)(40)+(0.18)v.
$$

So

$$
0.18v=-4.8,
$$

and

$$
v=-26.7\ \mathrm{m\ s^{-1}}.
$$

The second fragment moves at

$$
26.7\ \mathrm{m\ s^{-1}}
$$

west.

The total momentum is still zero, but kinetic energy has increased. The kinetic
energy comes from internal energy stored in the object before the explosion.

### Check

Momentum is a vector. Equal total momentum does not mean zero kinetic energy.
