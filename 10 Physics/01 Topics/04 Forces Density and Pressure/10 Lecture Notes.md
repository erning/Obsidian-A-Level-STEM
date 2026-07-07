---
title: Forces, Density and Pressure Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/04 Forces Density and Pressure/00 Overview|Forces, Density and Pressure]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/mechanics
  - lecture-notes
---

# Forces, Density and Pressure Lecture Notes

This topic takes the force ideas from
[[10 Physics/01 Topics/03 Dynamics/10 Lecture Notes|Dynamics]] and uses them in
three new ways. A force can be added to other forces as a vector. A force can
produce a turning effect when its line of action does not pass through a pivot.
A force spread over an area produces pressure, and pressure differences in a
fluid produce upthrust.

The recurring question is: what effect of the force matters here?

- If the object may accelerate, look for the resultant force.
- If the object may rotate, look for the resultant torque or moment.
- If a surface or fluid is involved, look at force per unit area and pressure
  difference.

## Visual guide

![[assets/generated/physics/forces-density-and-pressure.svg]]

Use the diagram as a map. The left side is the rotational route: centre of
gravity, line of action, moment, couple, torque, and equilibrium. The right side
is the fluid route: density, pressure, hydrostatic pressure, and upthrust.

## Source route

This note follows CAIE Physics 9702 section 4, Forces, density and pressure:

- 4.1 Turning effects of forces
- 4.2 Equilibrium of forces
- 4.3 Density and pressure

The matching coursebook route is Chapter 4 for force vectors, components,
centre of gravity, moments, couples, and equilibrium, and Chapter 7 for density,
pressure, hydrostatic pressure, and Archimedes' principle.

## 1. Forces as vectors

Force is a vector quantity. It has magnitude and direction, so forces must be
added by vector addition.

Forces in one straight line can be added with signs. Choose a positive direction
and keep it. If downwards is positive, a weight of $1.0\ \text{N}$ downwards and
air resistance of $0.2\ \text{N}$ upwards give

$$
F_{\text{resultant}} = 1.0 - 0.2 = 0.8\ \text{N}
$$

The positive answer tells you that the resultant force is downwards.

For forces at an angle, draw the vectors head-to-tail or resolve them into
perpendicular components. If a force $F$ makes an angle $\theta$ with the
positive $x$-direction, then

$$
F_x = F\cos\theta
$$

and

$$
F_y = F\sin\theta
$$

The two components are treated independently. This is why a slope problem is
usually easiest when one axis is taken along the slope and the other is normal
to the slope. The component of weight down a slope of angle $\theta$ is

$$
mg\sin\theta
$$

while the normal contact force has no component down the slope.

## 2. Coplanar forces in equilibrium

Coplanar forces act in the same plane. If three coplanar forces keep an object
in equilibrium, their vector sum is zero. Drawn head-to-tail, the three force
vectors form a closed triangle. This is often called a triangle of forces.

The triangle of forces can be used in two directions:

- If the force triangle closes, the resultant force is zero.
- If an object is known to be in equilibrium, the force vectors must close.

This graphical idea is the same as resolving forces into components. If the
object is in equilibrium, then

$$
\sum F_x = 0
$$

and

$$
\sum F_y = 0
$$

These equations say that there is no resultant force in any direction.

## 3. Centre of gravity

An object's weight is the total gravitational force on all parts of the object.
For most mechanics problems, you can represent that total weight as a single
force acting at one point. This point is called the centre of gravity.

For a uniform sphere, the centre of gravity is at the geometrical centre. For a
uniform rod, it is at the midpoint. For an irregular object, it may need to be
found experimentally. A thin lamina can be suspended freely from different
points. Each time it comes to rest, its centre of gravity lies vertically below
the suspension point. Drawing two or more plumb lines locates the centre of
gravity at their intersection.

The centre of gravity is not always inside the material of the object. For
example, the centre of gravity of a curved or hollow object can lie in empty
space. What matters for mechanics is the line of action of the weight.

## 4. Moment of a force

A force can make an object rotate about a point or pivot. The turning effect of
a force is called the moment of the force.

The moment of a force about a point is

$$
M = Fd_\perp
$$

where $F$ is the force and $d_\perp$ is the perpendicular distance from the point
to the line of action of the force.

The unit of moment is the newton metre:

$$
\text{N m}
$$

Do not confuse the distance from the pivot to the point where the force is
applied with the perpendicular distance to the line of action. If a force of
magnitude $F$ acts at distance $d$ from the pivot and makes an angle $\theta$
with the lever, then

$$
M = Fd\sin\theta
$$

There are two equivalent ways to see this:

- Use the perpendicular distance $d\sin\theta$ from the pivot to the line of
  action.
- Use the component $F\sin\theta$ that is perpendicular to the lever.

A force whose line of action passes through the pivot has no moment about that
pivot, because $d_\perp = 0$.

## 5. Principle of moments

If an object is in rotational equilibrium, the sum of the clockwise moments
about any point equals the sum of the anticlockwise moments about the same
point:

$$
\sum M_{\text{clockwise}} = \sum M_{\text{anticlockwise}}
$$

This is the principle of moments.

For example, a seesaw has a $20\ \text{N}$ force acting $2.0\ \text{m}$ to the
left of the pivot and a $40\ \text{N}$ force acting $1.0\ \text{m}$ to the right.
The anticlockwise moment is

$$
20 \times 2.0 = 40\ \text{N m}
$$

and the clockwise moment is

$$
40 \times 1.0 = 40\ \text{N m}
$$

The moments are equal, so there is no resultant moment.

When solving moment problems, choose the point about which to take moments
carefully. A good choice often makes an unknown force disappear because its line
of action passes through the chosen point. In a beam problem, taking moments
about the pivot or support often removes the unknown reaction at that support.

## 6. Full equilibrium

An object is in equilibrium only when both conditions are satisfied:

$$
\sum \vec{F} = 0
$$

and

$$
\sum M = 0
$$

No resultant force means no linear acceleration. No resultant moment or torque
means no angular acceleration. One condition alone is not enough.

A pair of equal and opposite forces on a steering wheel can have zero resultant
force but still make the wheel turn. A single upward support force and a
downward weight can cancel translationally, but if their lines of action are not
arranged correctly, the object may rotate.

## 7. Couple and torque of a couple

A couple is a pair of forces that produces rotation only. The two forces in a
couple are:

- equal in magnitude
- parallel but opposite in direction
- separated by a perpendicular distance

The resultant force of a couple is zero, so a couple does not produce linear
acceleration. It does produce a turning effect.

The torque of a couple is

$$
\tau = Fd
$$

where $F$ is one of the forces and $d$ is the perpendicular distance between the
two forces. The unit is $\text{N m}$.

A couple is different from the moment of a single force. The moment of a single
force depends on the point about which it is calculated. The torque of a couple
does not depend on the chosen pivot. It depends only on the force and the
perpendicular separation of the two forces.

## 8. Density

Density is mass per unit volume:

$$
\rho = \frac{m}{V}
$$

where $\rho$ is density, $m$ is mass, and $V$ is volume. The SI unit is

$$
\text{kg m}^{-3}
$$

Density describes how much mass is packed into a given volume. For a given
material under specified conditions, density is treated as a material property.
Water has density approximately

$$
1000\ \text{kg m}^{-3}
$$

which is the same as

$$
1.0\ \text{g cm}^{-3}
$$

Be careful with unit conversion. Since

$$
1\ \text{m}^3 = 10^6\ \text{cm}^3
$$

a density in $\text{g cm}^{-3}$ is multiplied by $1000$ to convert it to
$\text{kg m}^{-3}$.

## 9. Pressure

Pressure is the normal force per unit cross-sectional area:

$$
p = \frac{F}{A}
$$

The word normal means perpendicular to the surface. The unit of pressure is the
pascal:

$$
1\ \text{Pa} = 1\ \text{N m}^{-2}
$$

A large force spread over a large area may produce a small pressure. A smaller
force concentrated on a very small area may produce a large pressure. This is
why a sharp knife cuts more easily than a blunt one, and why snowshoes reduce
the pressure on snow by increasing the contact area.

Pressure in a fluid acts perpendicular to any surface it touches. At a point in
a fluid at rest, pressure has no single direction, even though the force on a
particular surface does have a direction. This is why pressure is a scalar.

## 10. Hydrostatic pressure

Pressure in a fluid increases with depth because deeper fluid has more fluid
above it. The equation for the change in hydrostatic pressure is

$$
\Delta p = \rho g \Delta h
$$

This equation gives a pressure difference, not necessarily the total pressure.
If the top surface is open to the atmosphere, the total pressure at depth
$\Delta h$ is

$$
p_{\text{total}} = p_{\text{atmospheric}} + \rho g\Delta h
$$

The derivation comes directly from density and pressure. Consider a vertical
column of fluid of cross-sectional area $A$ and height $\Delta h$. Its volume is

$$
V = A\Delta h
$$

Its mass is

$$
m = \rho A\Delta h
$$

Its weight is

$$
W = mg = \rho g A\Delta h
$$

The pressure difference caused by this weight is force per unit area:

$$
\Delta p = \frac{W}{A}
         = \frac{\rho g A\Delta h}{A}
         = \rho g\Delta h
$$

At the same depth in the same connected fluid at rest, the pressure is the same.
If it were not, fluid would flow sideways until the pressure difference
disappeared.

## 11. Upthrust and Archimedes' principle

An object in a fluid has a larger pressure on its lower surface than on its
upper surface, because the lower surface is deeper. The upward force on the
lower surface is therefore larger than the downward force on the upper surface.
The resultant upward force is called upthrust.

For an object of volume $V$ fully immersed in a fluid of density $\rho$, the
upthrust is

$$
F = \rho gV
$$

This is Archimedes' principle in equation form. The upthrust equals the weight
of the fluid displaced by the object.

If an object is floating, only the submerged part displaces fluid, so $V$ is the
submerged volume. A floating object is in equilibrium when

$$
\text{upthrust} = \text{weight}
$$

If upthrust is greater than weight, the object accelerates upwards. If weight is
greater than upthrust, it accelerates downwards.

For an object hung from a newton meter and then submerged, the meter reading
decreases because upthrust supports part of the object's weight:

$$
\text{apparent weight} = W - F_{\text{upthrust}}
$$

## 12. A working routine

Use the type of physical effect to choose the method.

1. For translation, draw a force diagram and find the resultant force.
2. For equilibrium with angled forces, resolve into components or draw a force
   triangle.
3. For rotation, draw the pivot, the line of action, and the perpendicular
   distance before calculating a moment.
4. For a couple, use one force and the perpendicular distance between the two
   forces.
5. For density, identify mass and volume with consistent units.
6. For pressure, use the normal force and the area over which it acts.
7. For fluids, decide whether the question asks for pressure difference, total
   pressure, or upthrust.

## 13. Common mistakes

- Using the distance along a lever instead of the perpendicular distance to the
  line of action.
- Checking $\sum \vec{F} = 0$ but forgetting $\sum M = 0$.
- Treating a couple as if it had a resultant force.
- Mixing $\text{g cm}^{-3}$ and $\text{kg m}^{-3}$ without converting units.
- Using total force when pressure requires force per unit area.
- Forgetting that hydrostatic pressure $\rho g\Delta h$ is a pressure
  difference.
- Using the total volume of a floating object instead of the submerged volume
  when calculating upthrust.

## Quick self-check

You are ready to move on when you can answer these without notes.

1. What is meant by the line of action of a force?
2. Why does a force through the pivot have zero moment about that pivot?
3. What two conditions are needed for equilibrium?
4. What is the difference between the moment of a force and the torque of a
   couple?
5. Why is pressure a scalar even though it is defined using force?
6. How is $\Delta p = \rho g\Delta h$ derived from density and pressure?
7. Why does an immersed object experience upthrust?
8. Which volume should be used in $F = \rho gV$ for a floating object?

## Connections

- [[10 Physics/01 Topics/03 Dynamics/10 Lecture Notes|Dynamics]] gives the
  force and acceleration ideas used here.
- [[10 Physics/01 Topics/05 Work Energy and Power/00 Overview|Work, Energy and Power]]
  uses force with displacement rather than force with perpendicular distance.
- [[10 Physics/01 Topics/06 Deformation of Solids/00 Overview|Deformation of Solids]]
  uses force and area again when defining stress.
- [[20 Mathematics/02 Mechanics/01 Forces and Equilibrium/00 Overview|Forces and Equilibrium]]
  develops the mathematical treatment of resolving forces and moments.
