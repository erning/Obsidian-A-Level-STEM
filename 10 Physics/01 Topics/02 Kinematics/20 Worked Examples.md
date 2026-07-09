---
title: Kinematics Worked Examples
subject: Physics
syllabus: 9702
parent: "[Kinematics](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/mechanics
  - worked-examples
---

# Kinematics Worked Examples

These examples model how to choose between definitions, graph methods, and
constant-acceleration equations. Always state the sign convention before using
vector quantities.

Take $g=9.81\ \mathrm{m\ s^{-2}}$ where needed.

## Example 1: Distance, Displacement, Speed, and Velocity

**Prompt.** A runner travels $300\ \mathrm{m}$ east, then turns around and runs
$100\ \mathrm{m}$ west. The total time is $80\ \mathrm{s}$. Find the total
distance, resultant displacement, average speed, and average velocity.

### Solution

Distance is the total path length:

$$
\text{distance}=300+100=400\ \mathrm{m}.
$$

Take east as positive. Displacement is the signed change in position:

$$
\text{displacement}=300-100=200\ \mathrm{m}.
$$

So the resultant displacement is $200\ \mathrm{m}$ east.

Average speed uses distance:

$$
\text{average speed}
=\frac{400}{80}
=5.0\ \mathrm{m\ s^{-1}}.
$$

Average velocity uses displacement:

$$
\text{average velocity}
=\frac{200}{80}
=2.5\ \mathrm{m\ s^{-1}}\ \text{east}.
$$

### Check

The average speed is greater than the magnitude of the average velocity because
some of the path was retraced.

## Example 2: Velocity from a Displacement-Time Graph

**Prompt.** A displacement-time graph has these straight sections:

- from $t=0$ to $t=4.0\ \mathrm{s}$, displacement changes from
  $2.0\ \mathrm{m}$ to $14.0\ \mathrm{m}$;
- from $t=4.0\ \mathrm{s}$ to $t=7.0\ \mathrm{s}$, displacement remains
  $14.0\ \mathrm{m}$;
- from $t=7.0\ \mathrm{s}$ to $t=10.0\ \mathrm{s}$, displacement changes from
  $14.0\ \mathrm{m}$ to $-1.0\ \mathrm{m}$.

Find the velocity in each section.

### Solution

Velocity is the gradient of a displacement-time graph:

$$
v=\frac{\Delta s}{\Delta t}.
$$

For the first section,

$$
v=\frac{14.0-2.0}{4.0-0}
=3.0\ \mathrm{m\ s^{-1}}.
$$

For the second section,

$$
v=\frac{14.0-14.0}{7.0-4.0}
=0.
$$

The object is stationary.

For the third section,

$$
v=\frac{-1.0-14.0}{10.0-7.0}
=-5.0\ \mathrm{m\ s^{-1}}.
$$

### Check

The negative velocity in the final section matches the graph moving downwards
as time increases.

## Example 3: Area Under a Velocity-Time Graph

**Prompt.** A velocity-time graph has three straight sections:

- $0$ to $5.0\ \mathrm{s}$: velocity increases uniformly from
  $0$ to $12\ \mathrm{m\ s^{-1}}$;
- $5.0$ to $9.0\ \mathrm{s}$: velocity is constant at
  $12\ \mathrm{m\ s^{-1}}$;
- $9.0$ to $13.0\ \mathrm{s}$: velocity decreases uniformly from
  $12\ \mathrm{m\ s^{-1}}$ to $-4.0\ \mathrm{m\ s^{-1}}$.

Find the initial acceleration, the total displacement, and the total distance
travelled.

### Solution

The initial acceleration is the gradient of the first section:

$$
a=\frac{12-0}{5.0-0}
=2.4\ \mathrm{m\ s^{-2}}.
$$

Displacement is the signed area under the velocity-time graph.

From $0$ to $5.0\ \mathrm{s}$, the area is a triangle:

$$
\frac{1}{2}(5.0)(12)=30\ \mathrm{m}.
$$

From $5.0$ to $9.0\ \mathrm{s}$, the area is a rectangle:

$$
(4.0)(12)=48\ \mathrm{m}.
$$

From $9.0$ to $13.0\ \mathrm{s}$, the signed area is a trapezium:

$$
\frac{1}{2}(12+(-4.0))(4.0)=16\ \mathrm{m}.
$$

So the total displacement is

$$
30+48+16=94\ \mathrm{m}.
$$

For distance travelled, the part below the time axis must be counted as a
positive distance. In the final section, the velocity reaches zero after
$3.0\ \mathrm{s}$, at $t=12.0\ \mathrm{s}$. The positive triangle from $9.0$ to
$12.0\ \mathrm{s}$ has area

$$
\frac{1}{2}(3.0)(12)=18\ \mathrm{m},
$$

and the negative triangle from $12.0$ to $13.0\ \mathrm{s}$ has magnitude

$$
\frac{1}{2}(1.0)(4.0)=2.0\ \mathrm{m}.
$$

Hence the total distance is

$$
30+48+18+2.0=98\ \mathrm{m}.
$$

### Check

The distance is greater than the displacement because the object reverses
direction during the final section.

## Example 4: Choosing a Constant-Acceleration Equation

**Prompt.** A car is moving at $8.0\ \mathrm{m\ s^{-1}}$. It accelerates at
$1.5\ \mathrm{m\ s^{-2}}$ over a displacement of $70\ \mathrm{m}$. Find its final
velocity and the time taken.

### Solution

The known quantities are

$$
u=8.0\ \mathrm{m\ s^{-1}},
\qquad
a=1.5\ \mathrm{m\ s^{-2}},
\qquad
s=70\ \mathrm{m}.
$$

Time is not initially known, so use

$$
v^2=u^2+2as.
$$

Substitute:

$$
v^2=8.0^2+2(1.5)(70)
=274.
$$

Thus

$$
v=\sqrt{274}=16.6\ \mathrm{m\ s^{-1}}.
$$

Now use

$$
v=u+at
$$

to find the time:

$$
t=\frac{v-u}{a}
=\frac{16.6-8.0}{1.5}
=5.7\ \mathrm{s}.
$$

### Check

The final velocity is larger than the initial velocity because the acceleration
and displacement are in the direction of motion.

## Example 5: Braking with a Sign Convention

**Prompt.** A car travelling at $22\ \mathrm{m\ s^{-1}}$ brakes uniformly to
rest over a distance of $75\ \mathrm{m}$. Find its acceleration and the braking
time.

### Solution

Take the initial direction of motion as positive. Then

$$
u=22\ \mathrm{m\ s^{-1}},
\qquad
v=0,
\qquad
s=75\ \mathrm{m}.
$$

Use

$$
v^2=u^2+2as.
$$

So

$$
0^2=22^2+2a(75).
$$

Therefore

$$
a=-\frac{22^2}{150}
=-3.23\ \mathrm{m\ s^{-2}}.
$$

The negative sign shows that the acceleration is opposite to the chosen
positive direction.

Now use

$$
v=u+at.
$$

Then

$$
t=\frac{v-u}{a}
=\frac{0-22}{-3.23}
=6.8\ \mathrm{s}.
$$

### Check

The acceleration is negative, but the time is positive. The magnitude of the
deceleration is $3.23\ \mathrm{m\ s^{-2}}$.

## Example 6: Throwing a Ball Vertically Upwards

**Prompt.** A ball is thrown vertically upwards from ground level with initial
velocity $14\ \mathrm{m\ s^{-1}}$. Ignore air resistance. Find the maximum
height above the launch point, the time to reach the maximum height, and the
total time before the ball returns to the launch height.

### Solution

Take upward as positive. Then

$$
u=14\ \mathrm{m\ s^{-1}},
\qquad
a=-9.81\ \mathrm{m\ s^{-2}}.
$$

At the maximum height, the vertical velocity is zero:

$$
v=0.
$$

Use

$$
v^2=u^2+2as.
$$

Substitute:

$$
0^2=14^2+2(-9.81)s.
$$

So

$$
s=\frac{14^2}{2(9.81)}
=9.99\ \mathrm{m}.
$$

For the time to the top, use

$$
v=u+at.
$$

Then

$$
0=14-9.81t,
$$

so

$$
t=1.43\ \mathrm{s}.
$$

The motion is symmetrical because the ball returns to the same height with no
air resistance, so the total time is

$$
2(1.43)=2.85\ \mathrm{s}.
$$

### Check

At the top, the velocity is zero but the acceleration is still
$9.81\ \mathrm{m\ s^{-2}}$ downwards.

## Example 7: Determining $g$ from a Graph

**Prompt.** In a falling-ball experiment, a graph of height $h$ against $t^2$
has a best-fit gradient of $4.88\ \mathrm{m\ s^{-2}}$. Explain how this gives
$g$, and state one systematic effect that could make the measured value too
small.

### Solution

For a ball released from rest,

$$
h=\frac{1}{2}gt^2.
$$

This has the straight-line form

$$
y=mx,
$$

where $y=h$, $x=t^2$, and

$$
m=\frac{g}{2}.
$$

So

$$
g=2m=2(4.88)=9.76\ \mathrm{m\ s^{-2}}.
$$

Residual magnetism in the electromagnet could delay the release of the ball.
That would make the measured time too large for a given height. Since

$$
g=\frac{2h}{t^2},
$$

a time that is too large gives a value of $g$ that is too small.

### Check

The result is close to $9.81\ \mathrm{m\ s^{-2}}$, so it is plausible for a
laboratory measurement.

## Example 8: Horizontal Projectile from a Cliff

**Prompt.** A stone is projected horizontally from a cliff with speed
$18\ \mathrm{m\ s^{-1}}$. The cliff is $45\ \mathrm{m}$ high. Ignore air
resistance. Find the time of flight, the horizontal distance from the base of
the cliff, and the velocity just before impact.

### Solution

Separate horizontal and vertical motion. Take downward as positive vertically.

Vertical motion:

$$
s_y=45\ \mathrm{m},
\qquad
u_y=0,
\qquad
a_y=9.81\ \mathrm{m\ s^{-2}}.
$$

Use

$$
s_y=\frac{1}{2}gt^2.
$$

Thus

$$
t=\sqrt{\frac{2s_y}{g}}
=\sqrt{\frac{2(45)}{9.81}}
=3.03\ \mathrm{s}.
$$

Horizontal motion has constant velocity:

$$
x=u_x t=(18)(3.03)=54.5\ \mathrm{m}.
$$

Just before impact, the horizontal component is still

$$
v_x=18\ \mathrm{m\ s^{-1}}.
$$

The vertical component is

$$
v_y=gt=(9.81)(3.03)=29.7\ \mathrm{m\ s^{-1}}
$$

downwards.

The speed is

$$
v=\sqrt{18^2+29.7^2}
=34.7\ \mathrm{m\ s^{-1}}.
$$

The angle below the horizontal is

$$
\theta=\tan^{-1}\left(\frac{29.7}{18}\right)
=59^\circ.
$$

### Check

The horizontal velocity is unchanged because air resistance is ignored. The
vertical velocity has grown from zero because gravity acts vertically.

## Example 9: Projectile Launched at an Angle

**Prompt.** A ball is launched from level ground with speed
$24\ \mathrm{m\ s^{-1}}$ at $35^\circ$ above the horizontal. Ignore air
resistance and assume it lands at the same height. Find the time of flight,
range, and maximum height.

### Solution

Resolve the initial velocity:

$$
u_x=24\cos35^\circ=19.7\ \mathrm{m\ s^{-1}},
$$

$$
u_y=24\sin35^\circ=13.8\ \mathrm{m\ s^{-1}}.
$$

For the whole flight back to the same height, the vertical displacement is
zero. Use

$$
s_y=u_y t-\frac{1}{2}gt^2.
$$

So

$$
0=t\left(u_y-\frac{1}{2}gt\right).
$$

The non-zero time is

$$
t=\frac{2u_y}{g}
=\frac{2(13.8)}{9.81}
=2.81\ \mathrm{s}.
$$

The range is horizontal displacement:

$$
x=u_x t=(19.7)(2.81)=55.2\ \mathrm{m}.
$$

At maximum height, $v_y=0$. Use

$$
v_y^2=u_y^2+2a_y s_y.
$$

Thus

$$
0=(13.8)^2+2(-9.81)s_y,
$$

so

$$
s_y=\frac{13.8^2}{2(9.81)}
=9.66\ \mathrm{m}.
$$

### Check

The same time is used in both directions. The horizontal velocity stays
constant, while the vertical velocity changes uniformly.
