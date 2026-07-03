---
title: Projectiles and Circular Motion Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/02 Mechanics/05 Projectiles and Circular Motion/00 Overview|Projectiles and Circular Motion]]"
status: draft
tags:
  - mathematics/mechanics
  - lecture-notes
---

# Projectiles and Circular Motion Lecture Notes

Projectile motion and circular motion are both two-dimensional models, but they use different organising ideas. A projectile is handled by independent horizontal and vertical components joined by the same time. Circular motion is handled by a radial acceleration directed towards the centre.

## Source Route

- 9231 3.1 Motion of a projectile
- 9231 3.3 Circular motion
- Coursebook route: 9231 Further Mechanics projectile and circular motion content; linked to Physics projectile and circular motion topics.

## Visual Guide

![[assets/generated/mathematics/projectiles-and-circular-motion.svg]]

Figure: use the diagram to compare component motion in projectiles with radial acceleration in circular motion.

## 1. Projectile Model

A projectile is modelled as a particle moving under gravity alone after launch. Air resistance and the size of the object are ignored. With $x$ horizontal and $y$ vertical upwards, acceleration is

$$
a_x=0,\qquad a_y=-g.
$$

If the initial speed is $u$ at angle $\theta$ above the horizontal, then

$$
u_x=u\cos\theta,\qquad u_y=u\sin\theta.
$$

The horizontal and vertical equations are

$$
x=u\cos\theta\,t,
$$

and

$$
y=u\sin\theta\,t-\frac12gt^2.
$$

The same time $t$ appears in both directions. That is the main connection between the horizontal and vertical parts of the motion.

## 2. Time, Height, Range, and Trajectory

At the greatest height, the vertical velocity is zero but the horizontal velocity is usually not zero:

$$
v_y=0,\qquad v_x=u\cos\theta.
$$

For launch and landing at the same height, the time of flight is

$$
T=\frac{2u\sin\theta}{g},
$$

and the range on a horizontal plane is

$$
R=\frac{u^2\sin 2\theta}{g}.
$$

These compact formulae depend on returning to the same vertical level. If launch and landing heights differ, use the component equations rather than forcing the range formula.

Eliminating $t$ gives the Cartesian equation of the trajectory:

$$
y=x\tan\theta-\frac{gx^2}{2u^2\cos^2\theta}.
$$

This is a parabola. The equation is especially useful when the unknown is the angle of projection, the speed of projection, or whether the path passes through a given point.

## 3. Velocity Direction

Velocity is tangent to the path. At time $t$,

$$
v_x=u\cos\theta,\qquad v_y=u\sin\theta-gt.
$$

The speed is

$$
v=\sqrt{v_x^2+v_y^2},
$$

and the direction can be found from

$$
\tan\alpha=\frac{v_y}{v_x}.
$$

Signs matter. A negative $v_y$ means the projectile is moving downwards.

## 4. Uniform Circular Motion

For a particle moving in a circle of radius $r$ with angular speed $\omega$,

$$
v=r\omega.
$$

Even if the speed is constant, the velocity changes direction, so there is acceleration towards the centre:

$$
a=r\omega^2=\frac{v^2}{r}.
$$

There is no extra physical force called "centripetal force". The phrase means the resultant force towards the centre:

$$
\sum F_{\text{towards centre}}=m\frac{v^2}{r}=mr\omega^2.
$$

The real forces may be tension, normal contact force, friction, weight, or a component of one of these.

## 5. Horizontal and Vertical Circles

In a horizontal circle, the radial direction is horizontal. A conical pendulum is a standard example: the vertical component of tension balances weight, and the horizontal component provides centripetal acceleration.

In a vertical circle, the radial direction changes from point to point. At the top of a circle, towards the centre is downward. At the bottom, towards the centre is upward. Draw the radial direction before writing the force equation.

For a particle attached to a light string in a vertical circle:

- at the top, $T+mg=mv^2/r$;
- at the bottom, $T-mg=mv^2/r$.

If the string is just taut at the top, then $T=0$, so the limiting condition is

$$
v^2=gr.
$$

Energy is often paired with circular motion. Use conservation of mechanical energy to relate speeds at different heights, then use the radial force equation at the point of interest.

## Worked-Thinking Routine

1. For projectiles, resolve the initial velocity first.
2. Write horizontal and vertical equations with the same time variable.
3. Use vertical information to find time or height, then return to horizontal distance.
4. For circular motion, draw the centre and the radial direction.
5. Write the resultant force towards the centre, not a new force.
6. Add energy only when speed changes around the circle.

## Common Mistakes

- Giving the projectile a horizontal acceleration when air resistance is ignored.
- Using the range formula when launch and landing heights differ.
- Treating the highest point of a projectile as a point of zero speed.
- Using degrees when angular speed requires radians per second.
- Drawing "centripetal force" as an extra force instead of resolving real forces.
- Forgetting that tension or normal reaction can become zero in vertical-circle problems.

## Quick Self-Check

- Can you derive the trajectory equation by eliminating $t$?
- Can you find speed and direction from velocity components?
- Can you explain why circular motion has acceleration even at constant speed?
- Can you identify the real forces whose resultant is radial?
- Can you combine energy with the radial force equation in a vertical circle?

## Connections

- [[20 Mathematics/02 Mechanics/02 Kinematics and Newtonian Motion/00 Overview|Kinematics and Newtonian Motion]]
- [[20 Mathematics/02 Mechanics/04 Work Energy Power and Elasticity/00 Overview|Work, Energy, Power and Elasticity]]
- [[10 Physics/01 Topics/02 Kinematics/00 Overview|Physics Kinematics]]
- [[10 Physics/01 Topics/12 Motion in a Circle/00 Overview|Physics Motion in a Circle]]

## Study Sequence

1. Practise projectile component equations before using shortcuts.
2. Derive the range and trajectory formulae yourself.
3. Study velocity direction and greatest height.
4. Learn angular speed and centripetal acceleration.
5. Solve horizontal circle models.
6. Add vertical circles with energy and contact or tension conditions.
