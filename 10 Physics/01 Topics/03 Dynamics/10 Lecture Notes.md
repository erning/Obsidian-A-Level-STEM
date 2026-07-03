---
title: Dynamics Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/03 Dynamics/00 Overview|Dynamics]]"
status: draft
tags:
  - physics/9702/topic
  - physics/9702/mechanics
  - lecture-notes
---

# Dynamics Lecture Notes

Dynamics is the part of mechanics that explains why motion changes. In
[[10 Physics/01 Topics/02 Kinematics/10 Lecture Notes|kinematics]] you describe
motion using displacement, velocity, acceleration, and graphs. In dynamics you
ask what interactions produce the acceleration, and when it is better to
describe the same interaction through momentum.

The central idea is simple but powerful:

$$
\text{resultant force} \longrightarrow \text{acceleration or change in momentum}
$$

That arrow is not a new formula. It is the habit of thought for this topic:
choose the object or system, identify the real forces, add them as vectors, and
then decide whether to use $F = ma$, $F = \dfrac{\Delta p}{\Delta t}$, or
conservation of momentum.

## Visual guide

![[assets/generated/physics/dynamics.svg]]

Use this diagram as a map of the topic. The left side is the force route:
free-body diagram, resultant force, acceleration. The right side is the
momentum route: momentum, change in momentum, conservation in an isolated
system. A good dynamics solution often starts by deciding which route gives the
cleaner description.

## Source route

This note follows CAIE Physics 9702 section 3, Dynamics:

- 3.1 Momentum and Newton's laws of motion
- 3.2 Non-uniform motion
- 3.3 Linear momentum and its conservation

The matching coursebook route is Chapter 3 for forces and Newton's laws, and
Chapter 6 for momentum and collisions.

## 1. From kinematics to dynamics

Kinematics can tell you that an object has acceleration $2.0\ \text{m s}^{-2}$
to the right. Dynamics asks why that acceleration is present. Is there a pull?
A push? A contact force? Drag? Weight? Does the object interact with another
object strongly enough that momentum is the simpler quantity to track?

Before writing equations, make three decisions.

1. Choose the object or system.
2. Choose a positive direction or coordinate axes.
3. Decide which external forces act on the chosen object or system.

The word "system" matters. If a trolley collides with another trolley, you can
look at one trolley alone, or at both trolleys as one system. Forces between
objects inside the system are internal forces. Forces from outside the system
are external forces. Conservation of momentum is a statement about the total
momentum of a system when the resultant external force is zero or negligible.

## 2. Forces and free-body diagrams

A force is a vector interaction. It can change the motion of an object, change
its shape, or both. Since force is a vector, the direction is part of the
quantity.

In A-Level dynamics, the most common forces are:

| Force | What it means | Usual direction |
| --- | --- | --- |
| Weight | The force on a mass due to a gravitational field | Downwards, toward the attracting body |
| Normal contact force | The force from a surface on an object touching it | Perpendicular to the surface |
| Friction | A contact force that opposes sliding or the tendency to slide | Along the surface, opposite the relative motion or tendency |
| Drag or air resistance | A resistive force from motion through a fluid | Opposite the velocity through the fluid |
| Tension | The pull exerted by a stretched string, rope, or cable | Along the string, away from the object |
| Upthrust | The upward force from a fluid on an immersed object | Upwards |
| Thrust or driving force | A force produced by an engine, motor, or propulsion system | Usually in the intended direction of motion |

A free-body diagram shows only the forces acting on the chosen object. It does
not show forces that the object exerts on other objects. It also should not show
velocity or acceleration arrows unless you clearly mark them separately, since
they are not forces.

The resultant force is the vector sum of the real forces:

$$
\vec{F}_{\text{resultant}} = \sum \vec{F}
$$

The resultant force is not an extra physical force. It is the single vector that
has the same effect as all the real forces together.

## 3. Mass and inertia

Mass is the property of an object that resists a change in motion. This
resistance to change in motion is called inertia. A larger mass needs a larger
resultant force to produce the same acceleration.

This is why mass belongs inside Newton's second law. If the same resultant force
acts on two objects, the object with greater mass has smaller acceleration:

$$
a = \frac{F}{m}
$$

Mass is not weight. Mass is a scalar property of the object, measured in
kilograms. Weight is a force due to a gravitational field, measured in newtons.

## 4. Newton's first law

Newton's first law says that an object remains at rest or continues to move with
constant velocity unless acted on by a resultant force.

The important word is resultant. An object can have several forces acting on it
and still have no acceleration if the vector sum is zero. For example, a book at
rest on a horizontal table has weight downwards and a normal contact force
upwards. These two forces can be equal in magnitude, so the resultant force on
the book is zero and the book remains at rest.

The same idea applies to constant velocity. A car moving at steady speed in a
straight line has zero acceleration. Its driving force may be balanced by drag
and other resistive forces. Balanced forces do not mean "no forces"; they mean
"no resultant force."

## 5. Newton's second law in the form $F = ma$

For a body of constant mass, Newton's second law is commonly used as

$$
\vec{F}_{\text{resultant}} = m\vec{a}
$$

The acceleration is always in the same direction as the resultant force. This
does not mean the acceleration is always in the same direction as the velocity.
If a ball is thrown upwards, its velocity is initially upwards, but its
acceleration is downwards because the resultant force is downwards.

The unit of force is the newton:

$$
1\ \text{N} = 1\ \text{kg m s}^{-2}
$$

For one-dimensional motion, choose a positive direction and use signs. If a
positive force is larger than a negative force, the resultant force is positive.
If the resultant force is negative, the acceleration is negative.

For example, suppose a trolley of mass $800\ \text{kg}$ has a driving force
$2400\ \text{N}$ forwards and resistive forces $800\ \text{N}$ backwards. The
resultant force is

$$
F_{\text{resultant}} = 2400 - 800 = 1600\ \text{N}
$$

so the acceleration is

$$
a = \frac{F_{\text{resultant}}}{m}
  = \frac{1600}{800}
  = 2.0\ \text{m s}^{-2}
$$

The sign and direction should be stated: $2.0\ \text{m s}^{-2}$ forwards.

## 6. Weight and gravitational field strength

Weight is the force on a mass due to a gravitational field. Near the surface of
the Earth it is given by

$$
W = mg
$$

where $W$ is weight in newtons, $m$ is mass in kilograms, and $g$ is
gravitational field strength in $\text{N kg}^{-1}$. The same $g$ can also be
written as acceleration of free fall in $\text{m s}^{-2}$, because

$$
1\ \text{N kg}^{-1} = 1\ \text{m s}^{-2}
$$

This equation also explains why, when air resistance is negligible, objects of
different masses fall with the same acceleration. A larger mass has larger
weight, but it also has larger inertia. The ratio is the same:

$$
a = \frac{W}{m} = \frac{mg}{m} = g
$$

## 7. Newton's third law

Newton's third law describes pairs of forces in an interaction. If object A
exerts a force on object B, then object B exerts a force of the same type, equal
in magnitude and opposite in direction, on object A.

A third-law pair has three key features.

- The two forces act on different objects.
- The two forces are equal in magnitude and opposite in direction.
- The two forces are the same type of interaction.

For example, when a hand pushes a wall, the hand exerts a contact force on the
wall and the wall exerts an equal and opposite contact force on the hand.

The weight of a book and the normal contact force from the table on the book are
not a Newton's third-law pair, because they both act on the same object. They
may be equal in magnitude when the book is at rest, but that equality comes from
Newton's first or second law applied to the book, not from Newton's third law.

Third-law pairs are especially important in momentum. During a collision, each
object exerts a force on the other. The forces are equal and opposite, and they
act for the same time interval. Therefore the changes in momentum are equal in
magnitude and opposite in direction.

## 8. Drag, resistive forces, and non-uniform motion

Non-uniform motion means motion with changing velocity. The acceleration may
change because the resultant force changes.

Resistive forces are forces that oppose motion or relative motion. In this topic
you describe them qualitatively.

Friction is a contact force between surfaces. It acts along the surface and
opposes sliding or the tendency to slide.

Drag is a resistive force from motion through a fluid such as air or water. It
acts opposite to the velocity of the object relative to the fluid. In the simple
model used here, drag increases as speed increases. No coefficient of friction
or coefficient of viscosity is needed for this section.

For a car on a level road, the driving force may initially be larger than the
resistive forces, so the car accelerates. As speed increases, air resistance
increases. The resultant forward force becomes smaller, so the acceleration
decreases. At top speed, the driving force equals the total resistive force.
The resultant force is zero, so the car continues at constant velocity.

## 9. Falling with air resistance and terminal velocity

Consider an object falling downwards through air.

At the instant it is released, its speed is zero, so air resistance is very
small. The main force is weight, so the resultant force is downwards and the
acceleration is close to $g$.

As the object speeds up, air resistance increases upwards. Weight stays nearly
constant, but drag becomes larger. The resultant downward force decreases, so
the downward acceleration decreases.

Eventually the air resistance equals the weight:

$$
D = W
$$

The resultant force is then zero:

$$
F_{\text{resultant}} = W - D = 0
$$

The object continues to move downwards, but now with constant velocity. This
velocity is called terminal velocity.

A parachute changes the situation by greatly increasing drag at a given speed.
When the parachute opens, drag can become larger than weight, so the resultant
force is upwards while the person is still moving downwards. The person slows
down until a new, smaller terminal velocity is reached.

## 10. Linear momentum

Linear momentum is defined as the product of mass and velocity:

$$
\vec{p} = m\vec{v}
$$

Momentum is a vector because velocity is a vector. Its direction is the
direction of the velocity. The SI unit is

$$
\text{kg m s}^{-1}
$$

which is equivalent to $\text{N s}$.

Momentum is useful when an interaction is short and force may change rapidly,
as in collisions or explosions. Instead of trying to describe the detailed force
during the contact, you can compare total momentum before and after.

## 11. Force as rate of change of momentum

Newton's second law can be written in a more general momentum form:

$$
\vec{F}_{\text{resultant}} = \frac{\Delta \vec{p}}{\Delta t}
$$

For a body of constant mass,

$$
\Delta \vec{p} = m\Delta \vec{v}
$$

so

$$
\vec{F}_{\text{resultant}}
  = \frac{m\Delta \vec{v}}{\Delta t}
  = m\vec{a}
$$

This shows that $F = ma$ is the constant-mass version of the momentum law.

The product of force and time is called impulse:

$$
\vec{F}\Delta t = \Delta \vec{p}
$$

Even when the force is not constant, the average force over the contact time can
be used in this relationship. This is why a longer stopping time reduces the
average force for the same change in momentum.

## 12. Conservation of momentum

The principle of conservation of momentum says that the total momentum of a
system remains constant if the resultant external force on the system is zero.

For two objects moving along one line,

$$
m_1u_1 + m_2u_2 = m_1v_1 + m_2v_2
$$

where $u$ values are velocities before the interaction and $v$ values are
velocities after the interaction. The velocities must carry signs. Choosing
right as positive means a leftward velocity is negative.

Momentum is always conserved for a closed system. Kinetic energy may or may not
be conserved.

The condition about external force is essential. If an external impulse is
significant, the total momentum of the chosen system changes. If a collision is
brief and external forces such as friction or weight have very small impulse
during the collision, the momentum of the colliding objects can often be treated
as conserved during that short time.

## 13. Collisions in one dimension

A collision problem is clearest when you draw a before-and-after diagram. Put
mass and velocity on each object. Choose a positive direction and keep it for
the whole solution.

In an inelastic collision, momentum is conserved but kinetic energy is not
conserved. Some kinetic energy is transferred to internal energy, sound, or
deformation. If two objects stick together, they share a common final velocity.
For example,

$$
m_1u_1 + m_2u_2 = (m_1 + m_2)v
$$

In a perfectly elastic collision, both total momentum and total kinetic energy
are conserved:

$$
m_1u_1 + m_2u_2 = m_1v_1 + m_2v_2
$$

and

$$
\frac{1}{2}m_1u_1^2 + \frac{1}{2}m_2u_2^2
=
\frac{1}{2}m_1v_1^2 + \frac{1}{2}m_2v_2^2
$$

For a perfectly elastic collision in one dimension, the relative speed of
approach equals the relative speed of separation. In words, the speed at which
the objects move towards each other before the collision equals the speed at
which they move apart after the collision.

Be careful with the phrase "kinetic energy is not conserved." Total energy is
still conserved. It is kinetic energy that has changed into other forms.

## 14. Momentum in two dimensions

Momentum is a vector, so conservation of momentum applies separately in
perpendicular directions. In a two-dimensional collision, choose axes, usually
$x$ and $y$, resolve each momentum into components, and write one conservation
equation for each direction:

$$
\sum p_x \text{ before} = \sum p_x \text{ after}
$$

$$
\sum p_y \text{ before} = \sum p_y \text{ after}
$$

If an object of momentum $p$ moves at angle $\theta$ above the positive
$x$-direction, its components are

$$
p_x = p\cos\theta
$$

and

$$
p_y = p\sin\theta
$$

The same sign discipline from one-dimensional motion still applies. Components
pointing left or down may be negative depending on your axes.

## 15. A working routine for dynamics problems

Use this routine when a problem feels messy.

1. Choose the object or system.
2. Draw a free-body diagram if forces are involved.
3. Choose positive directions or axes.
4. Decide whether the force route or momentum route is simpler.
5. For the force route, write $\sum F = ma$ in the chosen direction.
6. For the momentum route, write momentum before equals momentum after only if
   the resultant external impulse is zero or negligible.
7. Carry units and signs through the calculation.
8. Check the result against the physical situation.

The last step is not cosmetic. If a car has a forward driving force but your
answer gives backward acceleration, the signs or force balance need checking.
If two objects collide and your final momentum is not equal to the initial
momentum in a closed system, the algebra or sign convention is wrong.

## 16. Common mistakes

- Treating velocity as a force.
- Drawing forces that the object exerts on other objects in its free-body
  diagram.
- Forgetting that balanced forces can occur while an object is moving at
  constant velocity.
- Using $F = ma$ with one force instead of the resultant force.
- Saying weight and normal contact force are a Newton's third-law pair.
- Ignoring direction in momentum problems.
- Conserving kinetic energy in every collision.
- Using conservation of momentum without checking the system and external
  impulse.

## Quick self-check

You are ready to move on when you can answer these without notes.

1. What is the difference between mass and weight?
2. Why does zero resultant force mean zero acceleration, not necessarily zero
   velocity?
3. How do you decide whether two forces form a Newton's third-law pair?
4. Why does drag lead to terminal velocity for a falling object?
5. Why is momentum a vector quantity?
6. What condition is needed for conservation of momentum?
7. What extra condition makes a collision perfectly elastic?
8. How do you handle a momentum problem in two dimensions?

## Connections

- [[10 Physics/01 Topics/02 Kinematics/10 Lecture Notes|Kinematics]] gives the
  displacement, velocity, and acceleration language used here.
- [[10 Physics/01 Topics/04 Forces Density and Pressure/00 Overview|Forces, Density and Pressure]]
  develops force ideas that become important for pressure and fluids.
- [[10 Physics/01 Topics/05 Work Energy and Power/00 Overview|Work, Energy and Power]]
  explains energy transfers that complement momentum conservation.
- [[20 Mathematics/02 Mechanics/03 Momentum Collisions and Impulse/00 Overview|Momentum, Collisions and Impulse]]
  gives a mathematics route through the same collision ideas.
