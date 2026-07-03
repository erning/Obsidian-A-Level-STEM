---
title: Thermodynamics Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/16 Thermodynamics/00 Overview|Thermodynamics]]"
status: draft
tags:
  - physics/9702/topic
  - physics/9702/thermal-physics
  - lecture-notes
---

# Thermodynamics Lecture Notes

Thermodynamics studies energy transfer into, out of, and within a system. In this topic, the system is often a gas in a cylinder, but the same ideas apply to solids, liquids, and other physical systems.

The central habit is to name the system before doing any calculation. Once the system is clear, heating and work are not vague words. They are two ways of transferring energy across the boundary of the system.

## Source Route

- Primary syllabus source: CAIE Physics 9702.
- 16 Thermodynamics
- 16.1 Internal energy
- 16.2 The first law of thermodynamics
- Coursebook route: Physics Coursebook Chapter 19, Internal energy and the first law of thermodynamics.

## Visual Guide

![[assets/generated/physics/thermodynamics.svg]]

Figure: Thermodynamics tracks heating, work, and the resulting change in internal energy.

## 1. System, Boundary, and State

A thermodynamic system is the part of the universe you choose to study. Everything outside it is the surroundings. The system boundary may be a real physical wall, such as the wall of a cylinder, or an imagined boundary drawn around the object you are analysing.

For this topic, the main state quantities are:

- internal energy $U$;
- pressure $p$;
- volume $V$;
- temperature $T$.

Internal energy is a state quantity. This means that its value is determined by the state of the system, not by the path taken to reach that state. Heating and work, by contrast, are processes. They describe energy transfers that happen while the state changes.

This distinction prevents a common error: a system contains internal energy, but it does not "contain heat". Heat is energy transferred because of a temperature difference.

## 2. Internal Energy

The internal energy of a system is the sum of the random distribution of kinetic and potential energies associated with its molecules.

In symbols, this idea is often written conceptually as

$$
U = \sum E_\text{k, random} + \sum E_\text{p, molecular}.
$$

The random kinetic part comes from molecular motion. In a solid, particles vibrate about fixed positions. In a liquid or gas, particles have more freedom to move. The potential part comes from interactions between molecules, especially changes in their separation and arrangement.

A rise in temperature is related to an increase in internal energy. In many cases, this means the molecules have greater random kinetic energy. During a change of state, internal energy can also increase while temperature remains constant, because energy is going into changing molecular arrangement and separation rather than increasing average kinetic energy.

For an ideal gas, intermolecular potential energy is neglected. Its internal energy is therefore associated with molecular kinetic energy. This is why the link between temperature and molecular kinetic energy from [[10 Physics/01 Topics/15 Ideal Gases/00 Overview|Ideal Gases]] is so important.

## 3. Heating and Work

Heating is energy transfer to or from a system because of a temperature difference. If the system is cooler than its surroundings, energy may be transferred to the system by heating. If it is hotter, energy may be transferred from the system to the surroundings.

Work is energy transfer by a force moving through a distance. For a gas, work is commonly done when the gas boundary moves:

- compression: the surroundings push the boundary inwards, so work is done on the gas;
- expansion: the gas pushes the boundary outwards, so work is done by the gas.

Heating and work can both change internal energy, but they are not the same mechanism. Heating depends on temperature difference. Work depends on force and displacement.

## 4. First Law of Thermodynamics

The first law of thermodynamics is conservation of energy applied to a thermodynamic system:

$$
\Delta U = q + W.
$$

In this sign convention:

- $\Delta U$ is the increase in internal energy of the system.
- $q$ is the energy transferred to the system by heating.
- $W$ is the work done on the system.

Positive and negative signs have physical meaning:

- $\Delta U > 0$: the system's internal energy increases.
- $\Delta U < 0$: the system's internal energy decreases.
- $q > 0$: energy is transferred to the system by heating.
- $q < 0$: energy is transferred from the system by heating.
- $W > 0$: work is done on the system.
- $W < 0$: work is done by the system.

Keep this sign convention fixed throughout a problem. If you change convention halfway through, the algebra may still look tidy while the physics becomes wrong.

## 5. Work Done by a Gas at Constant Pressure

Consider a gas in a cylinder with a movable piston of cross-sectional area $A$. If the gas pressure is $p$, the force exerted by the gas on the piston is

$$
F = pA.
$$

If the piston moves outwards by a distance $s$, the increase in volume is

$$
\Delta V = As.
$$

The work done by the gas is

$$
W_\text{by gas} = Fs = pAs = p\Delta V.
$$

This result assumes constant pressure. If $\Delta V > 0$, the gas expands and does positive work on the surroundings.

The first law used in this note uses $W$ for work done on the system. Therefore, for a gas at constant pressure,

$$
W_\text{on gas} = -p\Delta V.
$$

So:

- expansion: $\Delta V > 0$, $W_\text{on gas} < 0$;
- compression: $\Delta V < 0$, $W_\text{on gas} > 0$.

This is the cleanest way to avoid confusion between work done by the gas and work done on the gas.

## 6. Reading a $p$-$V$ Graph

On a graph of pressure against volume, the area under the curve represents work done by the gas:

$$
W_\text{by gas} = \int p\,dV.
$$

For constant pressure, this area is a rectangle:

$$
W_\text{by gas} = p\Delta V.
$$

If the gas expands, the area corresponds to work done by the gas. If the gas is compressed, the volume decreases, and work is done on the gas. For the first law sign convention, convert the graph result using

$$
W_\text{on gas} = -W_\text{by gas}.
$$

At A Level, many calculations use constant pressure, so the rectangle area is enough. The graph idea is still useful because it shows that work depends on the path, not just on the initial and final states.

## 7. Standard Processes

### Constant Volume Heating

If a gas is heated in a rigid container, its volume does not change:

$$
\Delta V = 0.
$$

So no boundary work is done:

$$
W = 0.
$$

The first law becomes

$$
\Delta U = q.
$$

All energy transferred to the gas by heating increases its internal energy.

### Expansion While Heated

If a gas is heated and allowed to expand, energy enters by heating, but some energy leaves the system as work done by the gas. In the sign convention of the first law,

$$
W < 0.
$$

So the increase in internal energy is less than the heating input alone:

$$
\Delta U = q + W.
$$

This is why two gases can receive the same heating input but have different temperature rises if one expands and the other cannot.

### Compression Without Heat Transfer

If a gas is compressed quickly, or if the container is well insulated, there may be negligible heat transfer:

$$
q = 0.
$$

Then

$$
\Delta U = W.
$$

Work done on the gas increases its internal energy. For an ideal gas, this usually means an increase in temperature.

### Slow Isothermal Change

In a slow isothermal change, the temperature remains constant. For an ideal gas, internal energy depends only on temperature, so

$$
\Delta U = 0.
$$

The first law becomes

$$
0 = q + W.
$$

If the gas is compressed slowly, work is done on it, so $W > 0$, and energy must leave by heating, so $q < 0$. If the gas expands slowly, $W < 0$, and energy must enter by heating, so $q > 0$.

This is a useful thinking model, even when the problem only asks for the first law and the signs.

## 8. Connecting to Particles

A thermodynamic answer should usually have both an energy statement and a particle statement.

When an object is heated and its temperature rises, the average random kinetic energy of its molecules increases. When a substance melts or boils at constant temperature, the molecular arrangement changes and the potential energy part of internal energy increases. When a gas is compressed, molecules collide with a moving boundary and can rebound with greater kinetic energy.

This particle view keeps the first law from becoming empty algebra. The equation tells you the energy balance. The molecular model tells you what changed inside the system.

## 9. Problem-Solving Routine

For a first-law problem:

1. Define the system.
2. Write the sign convention: $\Delta U = q + W$, with $W$ as work done on the system.
3. Mark whether heating is into or out of the system.
4. Mark whether work is done on or by the system.
5. If a gas changes volume at constant pressure, calculate $W_\text{by gas} = p\Delta V$ first, then convert to $W_\text{on gas}$ if using the first law.
6. Substitute signs carefully.
7. Check the result with a sentence about internal energy and temperature.

For a particle explanation:

1. State whether molecular kinetic energy changes.
2. State whether molecular potential energy changes.
3. Link temperature rise to increased internal energy.
4. For gases, describe boundary motion and molecular collisions if work is involved.

## 10. Common Traps

- Calling internal energy "heat stored in the system".
- Forgetting that internal energy is a state quantity, while heating and work are processes.
- Using $W = p\Delta V$ without saying whether it is work done by the gas or on the gas.
- Treating expansion work as positive in $\Delta U = q + W$ even though $W$ is defined as work done on the system.
- Ignoring work done during expansion or compression.
- Assuming temperature must rise whenever energy is transferred to a substance. During a change of state, internal energy can increase while temperature stays constant.

## 11. Quick Self-Check

You are ready to move on when you can:

- define internal energy as molecular kinetic plus potential energy;
- explain why a temperature rise means an increase in internal energy;
- distinguish energy transferred by heating from work done;
- use $\Delta U = q + W$ with a consistent sign convention;
- calculate constant-pressure gas work using $p\Delta V$;
- explain the difference between work done by a gas and work done on a gas;
- interpret simple $p$-$V$ graph areas as work done by the gas.

## Connections

- [[10 Physics/01 Topics/14 Temperature/00 Overview|Temperature]]
- [[10 Physics/01 Topics/15 Ideal Gases/00 Overview|Ideal Gases]]
