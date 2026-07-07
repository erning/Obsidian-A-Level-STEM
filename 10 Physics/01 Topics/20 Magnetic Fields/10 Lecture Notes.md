---
title: Magnetic Fields Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/20 Magnetic Fields/00 Overview|Magnetic Fields]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/fields
  - lecture-notes
---

# Magnetic Fields Lecture Notes

Magnetic fields are force fields produced by permanent magnets and by moving charges. They act on moving charges and current-carrying conductors. When the magnetic flux linking a circuit changes, an e.m.f. is induced.

This topic has two large parts. The first is the motor effect: a current or moving charge in a magnetic field can experience a force. The second is electromagnetic induction: motion or changing magnetic flux can produce an e.m.f.

## Source Route

- Primary syllabus source: CAIE Physics 9702.
- 20 Magnetic fields
- 20.1 Concept of a magnetic field
- 20.2 Force on a current-carrying conductor
- 20.3 Force on a moving charge
- 20.4 Magnetic fields due to currents
- 20.5 Electromagnetic induction
- Coursebook route: Physics Coursebook Chapters 24 to 26, magnetic fields, charged particles, Hall effect, and electromagnetic induction.

## Visual Guide

![[assets/generated/physics/magnetic-fields.svg]]

Figure: Magnetic fields connect force directions, circular motion, Hall voltage, flux, and induction.

## 1. Magnetic Field Lines

A magnetic field is a field of force. It can be produced by a permanent magnet or by moving electric charges, usually an electric current.

Magnetic field lines are drawn to show:

- direction of the magnetic field;
- relative strength of the field;
- field pattern around magnets, wires, coils, and solenoids.

By convention, magnetic field lines emerge from a north pole and enter a south pole. The field is strongest where the field lines are closest together.

For current-produced fields:

- around a long straight wire, field lines are concentric circles centred on the wire;
- for a flat circular coil, the field resembles the field of a short bar magnet near the centre;
- inside a long solenoid, the field is approximately uniform and along the axis of the solenoid.

A ferrous core increases the magnetic field in a solenoid because the core becomes magnetised and reinforces the field.

Direction rules are essential. For a straight wire, point the right-hand thumb in the direction of conventional current; the curled fingers show the magnetic field direction. For a solenoid, curl the fingers of the right hand in the direction of conventional current; the thumb points towards the north pole of the solenoid.

## 2. Force on a Current-Carrying Conductor

A current-carrying conductor in a magnetic field may experience a force. The force is greatest when the current is perpendicular to the magnetic field and zero when the current is parallel to the field.

The general equation is

$$
F = BIL\sin\theta,
$$

where:

- $F$ is the force on the conductor;
- $B$ is magnetic flux density;
- $I$ is the current;
- $L$ is the length of conductor in the field;
- $\theta$ is the angle between the current and the magnetic field.

For a conductor at right angles to the field,

$$
F = BIL.
$$

The direction of the force is found using Fleming's left-hand rule:

- First finger: magnetic Field;
- seCond finger: conventional Current;
- thuMb: Motion or force.

The three directions are mutually perpendicular. The rule uses conventional current, so if electrons are moving, the conventional current is in the opposite direction to electron motion.

## 3. Magnetic Flux Density

Magnetic flux density $B$ is defined using the force on a current-carrying conductor placed at right angles to the field:

$$
B = \frac{F}{IL}.
$$

In words, magnetic flux density is the force per unit current per unit length on a straight conductor placed at right angles to the magnetic field.

The unit is the tesla:

$$
1\ \mathrm{T} = 1\ \mathrm{N\ A^{-1}\ m^{-1}}.
$$

A Hall probe or a current balance can be used to measure $B$. A Hall probe gives its maximum reading when the magnetic field is perpendicular to the active face of the probe.

## 4. Force on a Moving Charge

A moving charge in a magnetic field experiences a force if its velocity has a component perpendicular to the magnetic field. The general equation is

$$
F = BQv\sin\theta,
$$

where:

- $Q$ is the charge;
- $v$ is the speed;
- $\theta$ is the angle between velocity and magnetic field.

For motion perpendicular to the field,

$$
F = BQv.
$$

The force is perpendicular to both the velocity and the magnetic field. It does no work on the particle, because it is perpendicular to the motion. Therefore, a magnetic field can change the direction of a charged particle's velocity, but it does not change its speed.

For a positive charge, use Fleming's left-hand rule with conventional current in the direction of motion. For a negative charge, the force is in the opposite direction to that predicted for a positive charge moving in the same direction.

If the particle is stationary, $v = 0$, so there is no magnetic force.

## 5. Circular Motion of Charged Particles

If a charged particle enters a uniform magnetic field at right angles, the magnetic force is always perpendicular to its velocity. This force provides centripetal force, so the particle follows a circular path.

For magnitude,

$$
BQv = \frac{mv^2}{r}.
$$

Rearranging gives

$$
r = \frac{mv}{BQ}.
$$

Using momentum $p = mv$,

$$
p = BQr.
$$

This explains the patterns seen in particle tracks:

- greater speed gives a larger radius;
- greater mass gives a larger radius;
- greater charge gives a smaller radius;
- stronger magnetic field gives a smaller radius;
- reversing the sign of the charge reverses the direction of curvature.

If the velocity is not perpendicular to the magnetic field, only the perpendicular component causes circular motion. The component parallel to the field is unchanged, giving helical motion.

## 6. Velocity Selection

A velocity selector uses crossed electric and magnetic fields. Charged particles pass undeflected only if the electric and magnetic forces are equal in magnitude and opposite in direction.

The electric force magnitude is

$$
F_E = QE.
$$

The magnetic force magnitude is

$$
F_B = BQv.
$$

For no deflection,

$$
QE = BQv.
$$

So the selected speed is

$$
v = \frac{E}{B}.
$$

The charge cancels, so the selected speed does not depend on the charge magnitude of the particle. Particles moving faster or slower than this are deflected and do not pass through the exit slit.

## 7. Hall Voltage

The Hall effect occurs when a current-carrying conductor or semiconductor is placed in a magnetic field perpendicular to the current. Moving charge carriers experience a magnetic force and are pushed towards one side of the material. Charge separation creates a potential difference across the material called the Hall voltage.

At equilibrium, the magnetic force on a charge carrier is balanced by the electric force due to the Hall field:

$$
qE_H = Bqv.
$$

So

$$
E_H = Bv.
$$

If the Hall voltage is measured across width $d$,

$$
E_H = \frac{V_H}{d}.
$$

Thus

$$
V_H = Bvd.
$$

The current in the slice is

$$
I = nAvq,
$$

where $n$ is the number density of charge carriers, $A$ is the cross-sectional area, and $q$ is the charge of each carrier. If the cross-section is $A = dt$, where $t$ is the thickness of the slice, then

$$
I = ndtvq.
$$

Substituting for $v$ in the Hall voltage expression gives

$$
V_H = \frac{BI}{ntq}.
$$

This is the Hall voltage formula. It shows why Hall probes use thin semiconductor slices: smaller $t$ and smaller $n$ make the Hall voltage larger and easier to measure. A Hall probe can therefore be calibrated to measure magnetic flux density $B$.

The sign of the Hall voltage also gives information about whether the charge carriers are positive or negative.

## 8. Forces Between Current-Carrying Conductors

Each current-carrying wire produces a magnetic field. A second current-carrying wire placed in that field experiences a magnetic force.

For two parallel wires:

- currents in the same direction attract;
- currents in opposite directions repel.

You can explain this in two equivalent ways. One is to draw the combined magnetic field pattern and see where the field is strengthened or weakened. The other is to treat one wire as producing a magnetic field, then use $F = BIL$ and Fleming's left-hand rule for the force on the other wire.

The forces on the two wires are equal in magnitude and opposite in direction, in accordance with Newton's third law.

## 9. Magnetic Flux and Flux Linkage

Magnetic flux measures how much magnetic field passes through an area. If the magnetic field is perpendicular to the area,

$$
\Phi = BA.
$$

More generally, if $\theta$ is the angle between the magnetic field and the normal to the area,

$$
\Phi = BA\cos\theta.
$$

The unit of magnetic flux is the weber:

$$
1\ \mathrm{Wb} = 1\ \mathrm{T\ m^2}.
$$

For a coil of $N$ turns, the magnetic flux linkage is

$$
N\Phi.
$$

Flux linkage can change if:

- $B$ changes;
- the area $A$ changes;
- the angle $\theta$ changes;
- the number of turns linked by the flux changes.

Electromagnetic induction depends on the rate of change of flux linkage, not just on its value.

## 10. Electromagnetic Induction

An e.m.f. is induced in a circuit when the magnetic flux linking the circuit changes. Experiments that demonstrate this include:

- moving a magnet into or out of a coil;
- moving a wire through a magnetic field;
- rotating a coil in a magnetic field;
- changing the current in a nearby coil so that the magnetic field changes.

The induced e.m.f. is larger when the flux linkage changes more rapidly. It is increased by stronger magnetic fields, faster motion, greater coil area, and more turns, depending on the arrangement.

Faraday's law states that the magnitude of the induced e.m.f. is equal to the rate of change of magnetic flux linkage:

$$
|\mathcal{E}| = \left|\frac{\Delta(N\Phi)}{\Delta t}\right|.
$$

In differential form, including direction,

$$
\mathcal{E} = -\frac{d(N\Phi)}{dt}.
$$

The minus sign represents Lenz's law.

For a straight conductor of length $L$ moving at speed $v$ perpendicular to a magnetic field,

$$
\mathcal{E} = BLv.
$$

This follows from Faraday's law because the wire sweeps out area at rate $Lv$.

## 11. Lenz's Law

Lenz's law states that the induced e.m.f. is in a direction such that its effects oppose the change producing it.

This is an energy-conservation rule, not just a direction rule. If an induced current helped the change that produced it, the system could gain energy without an external energy input.

Examples:

- If a north pole is pushed towards a coil, the induced current makes the near end of the coil behave like a north pole, opposing the approach.
- If a magnet is pulled away from a coil, the induced current acts to oppose the decrease in flux.
- If a wire is moved through a magnetic field and a current is induced, the magnetic force on the wire opposes the motion that produced the current.

Use Lenz's law by asking: what change in flux is happening, and what induced effect would oppose that change?

## 12. Problem-Solving Routine

For magnetic force:

1. Decide whether the object is a current-carrying conductor or a moving charge.
2. Identify the angle to the magnetic field.
3. Use $F = BIL\sin\theta$ or $F = BQv\sin\theta$.
4. Use Fleming's left-hand rule for direction.
5. Reverse the force direction if the moving particle is negatively charged.

For circular motion:

1. Check that velocity is perpendicular to the field.
2. Set magnetic force equal to centripetal force: $BQv = \frac{mv^2}{r}$.
3. Solve for $r$, $v$, $B$, or $Q/m$ as required.
4. Use the sign of charge to decide curvature direction.

For induction:

1. Identify the circuit or coil whose flux linkage is changing.
2. Write $\Phi = BA\cos\theta$ if geometry matters.
3. Calculate $N\Phi$ and its rate of change.
4. Use Faraday's law for magnitude.
5. Use Lenz's law for direction.
6. Check whether the induced effect opposes the change, not the field itself.

## 13. Common Traps

- Applying magnetic force to a stationary charge.
- Forgetting the $\sin\theta$ factor in magnetic force equations.
- Using electron motion as conventional current without reversing direction.
- Treating magnetic force as doing work on a charged particle.
- Mixing up magnetic flux density $B$ and magnetic flux $\Phi$.
- Using $\Phi = BA$ when the field is not perpendicular to the area.
- Saying Lenz's law opposes the magnetic field rather than the change in flux.
- Forgetting that a ferrous core increases the field in a solenoid.

## 14. Quick Self-Check

You are ready to move on when you can:

- sketch fields for a straight wire, circular coil, and solenoid;
- use $F = BIL\sin\theta$ and Fleming's left-hand rule;
- define magnetic flux density in tesla;
- use $F = BQv\sin\theta$ for moving charges;
- derive $r = \frac{mv}{BQ}$ for circular motion in a magnetic field;
- explain velocity selection using $v = \frac{E}{B}$;
- derive and use $V_H = \frac{BI}{ntq}$ for the Hall voltage;
- explain attraction and repulsion between current-carrying conductors;
- use $\Phi = BA$ and flux linkage $N\Phi$;
- use Faraday's and Lenz's laws for electromagnetic induction.

## Connections

- [[10 Physics/01 Topics/12 Motion in a Circle/00 Overview|Motion in a Circle]]
- [[10 Physics/01 Topics/18 Electric Fields/00 Overview|Electric Fields]]
- [[10 Physics/01 Topics/21 Alternating Currents/00 Overview|Alternating Currents]]
