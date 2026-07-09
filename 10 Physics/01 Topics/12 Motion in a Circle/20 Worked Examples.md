---
title: Motion in a Circle Worked Examples
subject: Physics
syllabus: 9702
parent: "[Motion in a Circle](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/mechanics
  - worked-examples
---

# Motion in a Circle Worked Examples

These examples model the standard CAIE route through radian measure, angular
speed, linear speed, centripetal acceleration, centripetal force, and the real
forces that provide the inward resultant.

## Source Route

- Syllabus: CAIE Physics 9702 section 12, Motion in a circle.
- Main subtopics: kinematics of uniform circular motion and centripetal
  acceleration.
- Coursebook route: radians, angular speed, tangential velocity, centripetal
  force, and physical sources of centripetal force.

## Example 1: Radians and Arc Length

**Prompt.** A point moves along a circular arc of radius $0.80\ \mathrm{m}$.
The angular displacement is $75^\circ$. Find the angular displacement in
radians and the arc length.

**Solution.**

Circular motion formulae use radians. Convert first:

$$
\theta
=75^\circ \times \frac{\pi}{180^\circ}
=1.31\ \mathrm{rad}.
$$

Arc length is

$$
s=r\theta.
$$

So

$$
s=(0.80)(1.31)=1.05\ \mathrm{m}.
$$

The radian definition is built into this equation: an angle in radians is the
arc length divided by the radius.

**What this example trains.** Degrees are not used directly in circular motion
formulae.

## Example 2: Angular Speed from Period and Frequency

**Prompt.** A turntable completes one revolution every $0.40\ \mathrm{s}$.
Find its frequency and angular speed.

**Solution.**

The period is

$$
T=0.40\ \mathrm{s}.
$$

The frequency is

$$
f=\frac{1}{T}
=\frac{1}{0.40}
=2.5\ \mathrm{Hz}.
$$

One full revolution is $2\pi\ \mathrm{rad}$, so

$$
\omega=\frac{2\pi}{T}
=\frac{2\pi}{0.40}
=15.7\ \mathrm{rad\ s^{-1}}.
$$

Equivalently,

$$
\omega=2\pi f=2\pi(2.5)=15.7\ \mathrm{rad\ s^{-1}}.
$$

**What this example trains.** Period, frequency, and angular speed are three
ways to describe the same steady rotation.

## Example 3: Linear Speed on a Rotating Object

**Prompt.** A point on a rotating wheel is $0.18\ \mathrm{m}$ from the centre.
The wheel has angular speed $24\ \mathrm{rad\ s^{-1}}$. Find the linear speed
of the point. Compare it with a point $0.060\ \mathrm{m}$ from the centre.

**Solution.**

For uniform circular motion,

$$
v=r\omega.
$$

For the point near the rim,

$$
v=(0.18)(24)=4.32\ \mathrm{m\ s^{-1}}.
$$

For the point closer to the centre,

$$
v=(0.060)(24)=1.44\ \mathrm{m\ s^{-1}}.
$$

Both points have the same angular speed because they are on the same rigid
wheel. The point further from the centre has a greater linear speed because it
travels a longer arc in the same time.

**What this example trains.** Same $\omega$ does not mean same $v$ when
radius changes.

## Example 4: Centripetal Acceleration and Force

**Prompt.** A $0.050\ \mathrm{kg}$ mass moves in a horizontal circle of radius
$0.12\ \mathrm{m}$ at $300\ \mathrm{rev\ min^{-1}}$. Find $\omega$, $v$,
$a$, and the required inward force.

**Solution.**

Convert revolutions per minute to frequency:

$$
300\ \mathrm{rev\ min^{-1}}
=\frac{300}{60}
=5.0\ \mathrm{Hz}.
$$

Angular speed:

$$
\omega=2\pi f=2\pi(5.0)=31.4\ \mathrm{rad\ s^{-1}}.
$$

Linear speed:

$$
v=r\omega=(0.12)(31.4)=3.77\ \mathrm{m\ s^{-1}}.
$$

Centripetal acceleration:

$$
a=r\omega^2
=(0.12)(31.4)^2
=1.18 \times 10^2\ \mathrm{m\ s^{-2}}.
$$

Required inward force:

$$
F=ma=(0.050)(118)=5.9\ \mathrm{N}.
$$

The force is directed towards the centre of the circle.

**What this example trains.** Convert rpm before using angular speed formulae.

## Example 5: Friction as the Centripetal Force

**Prompt.** A $900\ \mathrm{kg}$ car travels at $15\ \mathrm{m\ s^{-1}}$
around a flat circular bend of radius $50\ \mathrm{m}$. Find the centripetal
acceleration and the frictional force needed.

**Solution.**

The acceleration is

$$
a=\frac{v^2}{r}
=\frac{15^2}{50}
=4.5\ \mathrm{m\ s^{-2}}.
$$

The inward resultant force is

$$
F=ma=(900)(4.5)=4.05 \times 10^3\ \mathrm{N}.
$$

On a flat road, this inward force is supplied by friction between the tyres and
the road. It is not an extra force called "centripetal force"; it is the
frictional force acting as the inward resultant.

**What this example trains.** Always name the real force that supplies the
centripetal role.

## Example 6: Maximum Speed on a Flat Bend

**Prompt.** A car moves around a flat bend of radius $40\ \mathrm{m}$. The
maximum frictional force available is $0.60mg$. Estimate the maximum speed
before slipping begins.

**Solution.**

For a flat bend, friction provides the inward force. At the limiting speed,

$$
\frac{mv^2}{r}=0.60mg.
$$

The mass cancels:

$$
\frac{v^2}{r}=0.60g.
$$

So

$$
v=\sqrt{0.60gr}
=\sqrt{(0.60)(9.81)(40)}
=15.3\ \mathrm{m\ s^{-1}}.
$$

The result is independent of the car's mass in this simplified model.

**What this example trains.** The available inward force sets the maximum
speed for a given radius.

## Example 7: Vertical Circle with Constant Speed

**Prompt.** A $0.20\ \mathrm{kg}$ mass moves at constant speed
$4.0\ \mathrm{m\ s^{-1}}$ in a vertical circle of radius $0.50\ \mathrm{m}$.
Find the string tension at the top and bottom of the circle.

**Solution.**

The required inward resultant has magnitude

$$
\frac{mv^2}{r}
=\frac{(0.20)(4.0)^2}{0.50}
=6.4\ \mathrm{N}.
$$

At the top, inward is downward. Both tension and weight act downward, so

$$
T_{\text{top}}+mg=\frac{mv^2}{r}.
$$

Therefore

$$
T_{\text{top}}
=6.4-(0.20)(9.81)
=4.4\ \mathrm{N}.
$$

At the bottom, inward is upward. Tension acts upward and weight acts downward,
so

$$
T_{\text{bottom}}-mg=\frac{mv^2}{r}.
$$

Therefore

$$
T_{\text{bottom}}
=6.4+(0.20)(9.81)
=8.4\ \mathrm{N}.
$$

The tension is larger at the bottom because it must both provide the inward
resultant and overcome the weight.

**What this example trains.** "Towards the centre" changes direction around
the circle, so the force equation changes with position.

## Example 8: Constant Speed, Changing Velocity

**Prompt.** A satellite moves at constant speed in a circular orbit. State
which quantities stay constant and which change: speed, velocity, kinetic
energy, momentum, acceleration, and resultant force.

**Solution.**

The speed is constant by definition of uniform circular motion. The kinetic
energy is also constant because

$$
E_k=\frac{1}{2}mv^2.
$$

Velocity changes because its direction changes continuously. Momentum also
changes because

$$
\vec{p}=m\vec{v}
$$

and $\vec{v}$ changes direction.

Centripetal acceleration has constant magnitude if $v$ and $r$ are constant:

$$
a=\frac{v^2}{r}.
$$

Its direction changes continuously because it always points towards the centre.
The resultant force has the same behaviour: constant magnitude if $m$, $v$,
and $r$ are constant, but changing direction.

The inward force does no work in uniform circular motion because it is
perpendicular to the instantaneous displacement.

**What this example trains.** Constant speed is not the same as constant
velocity or equilibrium.
