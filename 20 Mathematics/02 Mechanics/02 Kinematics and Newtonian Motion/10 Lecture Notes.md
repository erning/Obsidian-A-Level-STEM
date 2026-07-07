---
title: Kinematics and Newtonian Motion Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/02 Mechanics/02 Kinematics and Newtonian Motion/00 Overview|Kinematics and Newtonian Motion]]"
status: active
tags:
  - mathematics/mechanics
  - lecture-notes
---

# Kinematics and Newtonian Motion Lecture Notes

Kinematics describes motion. Newtonian motion explains motion by connecting force and acceleration. Keep those two jobs separate while learning: first describe how position and velocity change, then ask what resultant force would produce that acceleration.

## Source Route

- 9709 4.2 Kinematics of motion in a straight line
- 9709 4.4 Newton's laws of motion
- Coursebook route: 9709 Mechanics kinematics and Newton's laws chapters; linked to Physics kinematics and dynamics.

## Visual Guide

![[assets/generated/mathematics/kinematics-and-newtonian-motion.svg]]

Figure: use the diagram to connect motion graphs, calculus relationships, and the force model.

## 1. Quantities and Sign Conventions

In one-dimensional motion, the first decision is the positive direction. After that, every displacement, velocity, acceleration, and force component must follow that sign convention.

Distance and speed are scalar quantities. They tell you how far or how fast without direction. Displacement, velocity, and acceleration are vector quantities in this syllabus context; in a straight-line problem that means they may be positive or negative.

The basic calculus links are

$$
v=\frac{ds}{dt},\qquad a=\frac{dv}{dt}.
$$

Going the other way,

$$
s=\int v\,dt,\qquad v=\int a\,dt,
$$

with constants of integration found from the initial conditions.

## 2. Motion Graphs

Graphs are not decorations in kinematics. They are another form of the same information.

For a displacement-time graph:

- the gradient is velocity;
- a horizontal tangent means zero velocity at that instant;
- increasing steepness means increasing speed in the positive direction.

For a velocity-time graph:

- the gradient is acceleration;
- the area under the graph is displacement, with area below the time axis counted as negative;
- a crossing of the time axis means the particle changes direction.

Graph questions often become simple once you translate "gradient" and "area" before doing any algebra.

## 3. Constant-Acceleration Formulae

When acceleration is constant, the standard formulae are

$$
v=u+at,
$$

$$
s=ut+\frac12at^2,
$$

$$
v^2=u^2+2as,
$$

and

$$
s=\frac12(u+v)t.
$$

Here $u$ is initial velocity, $v$ is final velocity, $a$ is constant acceleration, $s$ is displacement, and $t$ is time.

These formulae are powerful because they remove calculus, but only when $a$ is constant. If acceleration changes with time, return to $v=ds/dt$ and $a=dv/dt$.

Vertical motion is just constant acceleration with gravity. If upward is positive, a freely moving particle has acceleration $-g$; if downward is positive, it has acceleration $g$. The sign is not a property of gravity alone, but of your coordinate choice.

## 4. From Kinematics to Dynamics

Newton's second law is the bridge from forces to acceleration:

$$
\sum F=ma.
$$

The left side is the resultant force in the chosen direction, not just one convenient force. Before using the equation, draw a force diagram and resolve forces along the direction of motion.

Mass and weight are connected by

$$
W=mg.
$$

Mass is the amount of matter and is measured in kilograms. Weight is a force and is measured in newtons.

In this topic, the usual models are particles of constant mass under constant forces. Forces may include weight, tension, friction, normal contact force, thrust in a rod, or an applied force. If resistance such as air resistance is relevant, the question must specify it.

## 5. Connected Particles

Connected-particle questions test modelling as much as algebra. A light inextensible string gives connected particles the same magnitude of acceleration along the string. A smooth pulley changes the direction of tension without changing its magnitude in the ideal model.

There are two useful viewpoints.

- Treat each particle separately when you need the tension.
- Treat the connected particles as one system when you want to eliminate internal tension.

For example, if two particles are connected by a light string over a smooth pulley, write $\sum F=ma$ for each particle with a consistent direction of motion. The tension appears in both equations and can often be eliminated by adding them.

## 6. Method Choice

Start by identifying which information is given.

- Use constant-acceleration formulae when acceleration is constant and the unknown is one of $u,v,a,s,t$.
- Use graphs when slopes or areas are given or requested.
- Use calculus when velocity or acceleration is given as a function of time.
- Use Newton's second law when forces are given and acceleration is unknown.
- Use the whole-system method when internal tensions are distracting.

## Worked-Thinking Routine

1. State the positive direction.
2. Identify whether the problem is kinematics only, or whether forces are involved.
3. For kinematics, choose graph, formula, or calculus.
4. For dynamics, draw the force diagram before writing $\sum F=ma$.
5. Keep units consistent: metres, seconds, kilograms, newtons.
6. Interpret negative answers as direction information.

## Common Mistakes

- Changing the positive direction halfway through.
- Using distance when the equation requires displacement.
- Treating speed and velocity as interchangeable.
- Using constant-acceleration formulae when acceleration varies.
- Reading height instead of area on a velocity-time graph.
- Writing $F=ma$ for a single force instead of the resultant force.
- Forgetting that connected particles share acceleration magnitude only under the ideal string constraint.

## Quick Self-Check

- Can you explain the difference between distance and displacement?
- Can you read velocity and acceleration from motion graphs?
- Can you decide whether the constant-acceleration formulae are allowed?
- Can you derive $s$ from $v(t)$, or $v$ from $a(t)$?
- Can you draw a force diagram and turn it into $\sum F=ma$?

## Connections

- [[20 Mathematics/02 Mechanics/01 Forces and Equilibrium/00 Overview|Forces and Equilibrium]]
- [[20 Mathematics/02 Mechanics/04 Work Energy Power and Elasticity/00 Overview|Work, Energy, Power and Elasticity]]
- [[10 Physics/01 Topics/02 Kinematics/00 Overview|Physics Kinematics]]
- [[10 Physics/01 Topics/03 Dynamics/00 Overview|Physics Dynamics]]

## Study Sequence

1. Practise sign conventions with short straight-line examples.
2. Translate displacement-time and velocity-time graphs into words.
3. Use constant-acceleration formulae until you can choose the right equation quickly.
4. Rework the same motion with calculus where possible.
5. Add force diagrams and Newton's second law.
6. Finish with connected-particle models.
