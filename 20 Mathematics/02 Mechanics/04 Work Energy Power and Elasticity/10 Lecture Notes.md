---
title: Work, Energy, Power and Elasticity Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/02 Mechanics/04 Work Energy Power and Elasticity/00 Overview|Work, Energy, Power and Elasticity]]"
status: draft
tags:
  - mathematics/mechanics
  - lecture-notes
---

# Work, Energy, Power and Elasticity Lecture Notes

Energy methods replace a step-by-step force analysis with an account of what changes between two states. They are especially useful when the path is complicated but the initial and final positions, speeds, heights, or extensions are clear.

## Source Route

- 9709 4.5 Energy, work and power
- 9231 3.4 Hooke's law
- Coursebook route: 9709 Mechanics energy, work, and power chapters; 9231 Further Mechanics Hooke's law and elastic energy content.

## Visual Guide

![[assets/generated/mathematics/work-energy-power-and-elasticity.svg]]

Figure: use the guide to track energy transfer by work and energy storage in an elastic string or spring.

## 1. Work Done

Work measures energy transferred by a force through a displacement. For a constant force $F$ whose point of application moves a distance $d$ at angle $\theta$ to the force,

$$
W=Fd\cos\theta.
$$

The sign matters:

- if the force helps the motion, the work is positive;
- if the force opposes the motion, the work is negative;
- if the force is perpendicular to the displacement, the work is zero.

For a variable force in one dimension, work is the area under the force-displacement graph:

$$
W=\int F\,dx.
$$

This is the bridge to later variable-force work and to elastic potential energy.

## 2. Kinetic and Gravitational Potential Energy

Kinetic energy is

$$
KE=\frac12mv^2.
$$

Gravitational potential energy changes by

$$
\Delta GPE=mg\Delta h,
$$

where $\Delta h$ is the change in vertical height. The zero level for potential energy can be chosen freely, because only changes in potential energy affect the motion.

The work-energy principle says

$$
\text{work done by the resultant force}=\Delta KE.
$$

Equivalently, track energy stores:

$$
\Delta KE+\Delta GPE=\text{work done by external non-conservative forces}.
$$

If there is no friction, driving force, or other non-conservative work, mechanical energy is conserved:

$$
KE+GPE=\text{constant}.
$$

This can apply even when the path is curved, because energy depends on height and speed rather than on every detail of the path.

## 3. Power

Power is the rate at which work is done:

$$
P=\frac{dW}{dt}.
$$

Average power over a time interval is

$$
\text{average power}=\frac{\text{work done}}{\text{time taken}}.
$$

When a force acts in the direction of motion,

$$
P=Fv.
$$

If the force is not in the direction of motion, use the component of the force in the direction of the velocity.

## 4. Hooke's Law and Elastic Energy

For an elastic string or spring of natural length $l$ and modulus of elasticity $\lambda$, Hooke's law is

$$
T=\frac{\lambda x}{l},
$$

where $x$ is the extension or compression from the natural length. If $k=\lambda/l$, this is the familiar form $T=kx$.

The elastic potential energy stored is

$$
E=\frac{\lambda x^2}{2l}.
$$

This is the area under the force-extension graph. Because the force increases from $0$ to $\lambda x/l$, the average force during stretching is half the final force.

The most common error is using the current length as $x$. The extension is

$$
x=\text{current length}-\text{natural length}.
$$

For a string, the force is tension only when stretched. For a spring, the model may include extension or compression, depending on the situation.

## 5. Choosing Energy or Force Methods

Use energy when a problem asks for speed, height, distance travelled, or maximum extension between two states. Use Newton's second law when the problem asks for acceleration, contact force, tension at a particular instant, or detailed motion during the path.

Many problems need both. For example, use energy to find the speed at a point on a smooth track, then use $\sum F=ma$ at that point to find a normal contact force.

## Worked-Thinking Routine

1. Choose the system and the start and end states.
2. List energy stores: $KE$, $GPE$, and elastic potential energy if present.
3. List external work done, especially by friction, driving forces, or resistance.
4. Write the energy equation before substituting numbers.
5. For elastic problems, compute extension from natural length.
6. Check that every term is in joules and that energy losses have the correct sign.

## Common Mistakes

- Using mechanical energy conservation when friction or resistance does work.
- Forgetting that normal reaction often does no work because it is perpendicular to motion.
- Using total length instead of extension in elastic formulae.
- Mixing force units and energy units.
- Applying $P=Fv$ when $F$ is not the component in the direction of velocity.
- Forgetting that elastic potential energy is quadratic in extension.

## Quick Self-Check

- Can you decide whether a force does positive, negative, or zero work?
- Can you choose a zero level for gravitational potential energy?
- Can you explain when mechanical energy is conserved?
- Can you compute work from a force-displacement graph?
- Can you use $T=\lambda x/l$ and $E=\lambda x^2/(2l)$ without confusing length and extension?

## Connections

- [[20 Mathematics/02 Mechanics/02 Kinematics and Newtonian Motion/00 Overview|Kinematics and Newtonian Motion]]
- [[20 Mathematics/02 Mechanics/05 Projectiles and Circular Motion/00 Overview|Projectiles and Circular Motion]]
- [[20 Mathematics/02 Mechanics/06 Rigid Bodies and Variable Forces/00 Overview|Rigid Bodies and Variable Forces]]
- [[10 Physics/01 Topics/05 Work Energy and Power/00 Overview|Physics Work, Energy and Power]]
- [[10 Physics/01 Topics/06 Deformation of Solids/00 Overview|Physics Deformation of Solids]]

## Study Sequence

1. Start with constant-force work and the sign of work.
2. Practise $KE$, $GPE$, and mechanical energy conservation.
3. Add friction and other external work.
4. Use power as rate of energy transfer.
5. Study Hooke's law and elastic potential energy.
6. Combine energy with Newton's second law where a force at an instant is required.
