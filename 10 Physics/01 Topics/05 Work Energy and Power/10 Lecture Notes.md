---
title: Work, Energy and Power Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/05 Work Energy and Power/00 Overview|Work, Energy and Power]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/mechanics
  - lecture-notes
---

# Work, Energy and Power Lecture Notes

Dynamics explains motion through forces and acceleration. Energy gives another
route. Instead of following every force through every instant, you compare
states: what energy was transferred into the system, what energy left, and how
much energy changed form inside the system.

This topic is built around three questions.

1. How much energy is transferred? That is work done.
2. Where does the energy go? That is conservation of energy and efficiency.
3. How quickly is energy transferred? That is power.

## Visual guide

![[assets/generated/physics/work-energy-and-power.svg]]

The diagram links force, displacement, work done, energy transfer, and power.
Use it as a reminder that energy calculations usually begin by identifying the
initial state, final state, system boundary, and useful energy transfer.

## Source route

This note follows CAIE Physics 9702 section 5, Work, energy and power:

- 5.1 Energy conservation
- 5.2 Gravitational potential energy and kinetic energy

The matching coursebook route is Chapter 5, which develops work done, energy
transfer, gravitational potential energy, kinetic energy, efficiency,
conservation of energy, and power.

## 1. Work done as energy transferred

In physics, work done is a way of measuring energy transferred by a force. Work
is done on a body when a force moves the body in the direction of the force.

If a constant force $F$ moves a body through displacement $s$ in the direction
of the force, then

$$
W = Fs
$$

where $W$ is the work done. The unit of work and energy is the joule:

$$
1\ \text{J} = 1\ \text{N m}
$$

A force of $1\ \text{N}$ moving its point of application through $1\ \text{m}$
in the direction of the force transfers $1\ \text{J}$ of energy.

This definition explains why holding a heavy object still can feel tiring but
does no mechanical work on the object. The force from your hands is large, but
the object has no displacement, so no energy is transferred to the object by
that force.

## 2. Direction matters in work done

Only the component of the force in the direction of displacement does work. If
the force $F$ makes an angle $\theta$ with the displacement $s$, then

$$
W = Fs\cos\theta
$$

This formula covers several important cases:

| Angle between force and displacement | Work done by the force |
| --- | --- |
| $0^\circ$ | positive, $W = Fs$ |
| $90^\circ$ | zero, $W = 0$ |
| $180^\circ$ | negative, $W = -Fs$ |

The tension in the string of an object moving in a horizontal circle is a useful
example. The tension is radial, while the instantaneous displacement is
tangential. The angle is $90^\circ$, so the tension does no work and does not
change the object's kinetic energy.

When a force opposes motion, the work done by that force is negative. Friction
on a sliding object usually does negative work on the object and transfers
mechanical energy into internal energy of the object and surroundings.

## 3. Work done from force-displacement graphs

For a constant force, the work done is the area of a rectangle on a
force-displacement graph:

$$
W = Fs
$$

For a force that changes with displacement, the work done is the area under the
force-displacement graph:

$$
W = \text{area under the } F\text{-}s \text{ graph}
$$

This idea will become especially useful in
[[10 Physics/01 Topics/06 Deformation of Solids/00 Overview|Deformation of Solids]],
where the energy stored in a stretched spring comes from the area under a
force-extension graph.

## 4. Gravitational potential energy

When an object is raised in a gravitational field, work is done against its
weight. Energy is transferred to the object, and the object's gravitational
potential energy increases.

Near the surface of the Earth, where $g$ can be treated as constant, the change
in gravitational potential energy is

$$
\Delta E_p = mg\Delta h
$$

Here $m$ is mass, $g$ is gravitational field strength, and $\Delta h$ is the
vertical height gained. It is the vertical height that matters, not the length
of the path taken.

The derivation comes from work done:

$$
W = Fs
$$

To lift an object slowly at constant speed, the lifting force has magnitude
$mg$. The displacement in the direction of this lifting force is the vertical
height change $\Delta h$. Therefore

$$
\Delta E_p = W = mg\Delta h
$$

This formula assumes a uniform gravitational field. It is suitable for ordinary
heights near the Earth's surface. For very large height changes, such as
satellite motion, $g$ changes significantly and a later gravitational field
model is needed.

## 5. Kinetic energy

Kinetic energy is the energy an object has because it is moving. For a body of
mass $m$ moving at speed $v$,

$$
E_k = \frac{1}{2}mv^2
$$

Kinetic energy depends on speed squared. Doubling speed makes the kinetic
energy four times as large.

The formula can be derived from work done and the equations of motion. Suppose
a constant resultant force $F$ accelerates a body of mass $m$ from rest to speed
$v$ over distance $s$. From kinematics,

$$
v^2 = 2as
$$

Multiply both sides by $\frac{1}{2}m$:

$$
\frac{1}{2}mv^2 = mas
$$

Since $F = ma$,

$$
\frac{1}{2}mv^2 = Fs
$$

The right side is the work done by the resultant force, so the left side is the
kinetic energy gained:

$$
E_k = \frac{1}{2}mv^2
$$

For a change between two non-zero speeds, calculate the change in kinetic
energy from the two kinetic energies:

$$
\Delta E_k = \frac{1}{2}mv^2 - \frac{1}{2}mu^2
$$

Do not square the change in speed.

## 6. Mechanical energy changes

Many mechanics problems involve energy transferring between gravitational
potential energy and kinetic energy.

If a ball falls through height $h$ with negligible air resistance, its loss of
gravitational potential energy becomes gain in kinetic energy:

$$
mg h = \frac{1}{2}mv^2
$$

The mass cancels:

$$
v = \sqrt{2gh}
$$

This result agrees with the kinematics result for motion from rest under
constant acceleration $g$. Energy has given the same physical result without
needing time.

If air resistance, friction, or another dissipative force is significant, not
all the lost gravitational potential energy becomes kinetic energy. Some energy
is transferred to internal energy and sound. The energy is not destroyed, but it
may no longer be useful mechanical energy.

## 7. Conservation of energy

The principle of conservation of energy says that energy cannot be created or
destroyed. It can be transferred from one object to another or converted from
one form to another, but the total energy of a closed system remains constant.

For energy problems, the system boundary is important. If you draw the boundary
around only one object, energy may cross the boundary as work done by external
forces. If you draw the boundary around all interacting objects and their
surroundings, the total energy should be accounted for.

A useful energy equation has this structure:

$$
\text{initial energy} + \text{energy input}
=
\text{final energy} + \text{energy output or losses}
$$

In many ideal mechanics problems, losses are negligible. Then mechanical energy
is conserved:

$$
E_p + E_k = \text{constant}
$$

In real systems, mechanical energy often decreases, but total energy is still
conserved when internal energy, heating, sound, and other transfers are
included.

## 8. Efficiency

Many devices transfer only part of their input energy into the useful output
energy. Efficiency measures this fraction:

$$
\text{efficiency} =
\frac{\text{useful energy output}}{\text{total energy input}}
$$

As a percentage,

$$
\text{percentage efficiency} =
\frac{\text{useful energy output}}{\text{total energy input}} \times 100\%
$$

The same idea can be used with power:

$$
\text{efficiency} =
\frac{\text{useful power output}}{\text{total power input}}
$$

An efficiency of $0.25$ or $25\%$ does not mean the rest of the energy
disappears. It means the remaining $75\%$ is transferred into forms or places
that are not useful for the intended purpose, often internal energy of the
surroundings.

## 9. Power

Power is the rate at which work is done, or the rate at which energy is
transferred:

$$
P = \frac{W}{t}
$$

The unit of power is the watt:

$$
1\ \text{W} = 1\ \text{J s}^{-1}
$$

For example, if a lift motor does $3.6 \times 10^5\ \text{J}$ of work in
$10\ \text{s}$, its output power is

$$
P = \frac{3.6 \times 10^5}{10}
  = 3.6 \times 10^4\ \text{W}
  = 36\ \text{kW}
$$

Power is not the total energy transferred. It is how quickly the transfer
happens.

## 10. Deriving and using $P = Fv$

If a constant force $F$ acts in the direction of motion and the object moves at
speed $v$, then in time $t$ it moves distance

$$
s = vt
$$

The work done is

$$
W = Fs = Fvt
$$

Power is work done per unit time:

$$
P = \frac{W}{t}
  = \frac{Fvt}{t}
  = Fv
$$

So

$$
P = Fv
$$

This equation is useful for steady motion against a resistive force. For a car
travelling at constant speed, the driving force balances the resistive forces.
If the engine delivers constant power, then

$$
F = \frac{P}{v}
$$

As the speed increases, the driving force available from a fixed power becomes
smaller. This helps explain why acceleration decreases as a car speeds up when
the engine power is roughly constant.

## 11. A working routine

Use energy when the problem connects forces, distances, speeds, and height
changes but does not require time.

1. Choose the system and the initial and final states.
2. Write the energy stores or transfers present at each state.
3. Decide whether losses are negligible.
4. Use $W = Fs\cos\theta$ for work done by a force.
5. Use $\Delta E_p = mg\Delta h$ for height changes in a uniform gravitational
   field.
6. Use $E_k = \frac{1}{2}mv^2$ for kinetic energy.
7. Use efficiency if only part of the input becomes useful output.
8. Use power when the rate of energy transfer matters.

Energy methods are especially clean when the path details do not matter. Force
methods are better when acceleration, time, or the detailed motion at each
instant is the main target.

## 12. Common mistakes

- Thinking that a force does work whenever it is present. The force must have a
  component in the direction of displacement.
- Forgetting that $W = Fs$ uses displacement in the direction of the force.
- Using the path length instead of vertical height in $\Delta E_p = mg\Delta h$.
- Calculating $\Delta E_k$ by squaring the change in speed.
- Assuming kinetic energy is conserved in every collision.
- Treating energy lost from mechanical stores as destroyed rather than
  transferred to internal energy, sound, or another store.
- Confusing power with energy.
- Writing efficiency greater than $1$ or greater than $100\%$ for an ordinary
  device.

## Quick self-check

You are ready to move on when you can answer these without notes.

1. What is the difference between work done and force?
2. Why does a force at right angles to the displacement do no work?
3. How do you derive $\Delta E_p = mg\Delta h$?
4. How do you derive $E_k = \frac{1}{2}mv^2$ from an equation of motion?
5. What does conservation of energy mean for a closed system?
6. What does efficiency measure?
7. Why can mechanical energy decrease even though total energy is conserved?
8. How is $P = Fv$ derived from $P = W/t$?

## Connections

- [[10 Physics/01 Topics/03 Dynamics/10 Lecture Notes|Dynamics]] gives the
  force and acceleration route that complements energy methods.
- [[10 Physics/01 Topics/04 Forces Density and Pressure/10 Lecture Notes|Forces, Density and Pressure]]
  introduced force, distance, and force components used here.
- [[10 Physics/01 Topics/06 Deformation of Solids/00 Overview|Deformation of Solids]]
  uses the area under a force-extension graph as stored elastic energy.
- [[20 Mathematics/02 Mechanics/04 Work Energy Power and Elasticity/00 Overview|Work, Energy, Power and Elasticity]]
  gives a mathematical mechanics version of the same ideas.
