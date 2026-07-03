---
title: Oscillations Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/17 Oscillations/00 Overview|Oscillations]]"
status: draft
tags:
  - physics/9702/topic
  - physics/9702/waves
  - lecture-notes
---

# Oscillations Lecture Notes

Oscillations are repeated motions about an equilibrium position. Simple harmonic motion, or SHM, is the ideal model in which the acceleration is proportional to displacement from equilibrium and directed back towards equilibrium.

The topic is best learned through three representations at the same time: the physical motion, the graphs, and the equations. If these three agree, the signs and phases usually take care of themselves.

## Source Route

- Primary syllabus source: CAIE Physics 9702.
- 17 Oscillations
- 17.1 Simple harmonic oscillations
- 17.2 Energy in simple harmonic motion
- 17.3 Damped and forced oscillations, resonance
- Coursebook route: Physics Coursebook Chapter 18, Oscillations.

## Visual Guide

![[assets/generated/physics/oscillations.svg]]

Figure: SHM connects displacement, velocity, acceleration, energy transfer, damping, and resonance.

## 1. Describing an Oscillation

An oscillating object moves repeatedly about an equilibrium position. The displacement $x$ is measured from that equilibrium position, not from an arbitrary end point.

Important quantities are:

- displacement $x$: signed distance from equilibrium;
- amplitude $x_0$: maximum magnitude of displacement;
- period $T$: time for one complete oscillation;
- frequency $f$: number of complete oscillations per unit time;
- angular frequency $\omega$: phase change per unit time, measured in $\mathrm{rad\ s^{-1}}$;
- phase difference: how far one oscillation is ahead of another in the cycle.

The period and frequency are related by

$$
f = \frac{1}{T}.
$$

One complete oscillation corresponds to a phase change of $2\pi$ radians, so

$$
\omega = 2\pi f = \frac{2\pi}{T}.
$$

For phase difference, compare corresponding points on two oscillations, such as two adjacent maxima. If their time separation is $\Delta t$, then

$$
\phi = 2\pi\frac{\Delta t}{T}
$$

in radians, or

$$
\phi = 360^\circ\frac{\Delta t}{T}
$$

in degrees.

## 2. The Physical Pattern of SHM

In mechanical SHM, the system needs:

- an object with mass;
- an equilibrium position;
- a restoring force directed towards equilibrium;
- a restoring force whose magnitude is proportional to displacement.

This gives the defining condition:

$$
a = -\omega^2 x.
$$

The minus sign is the physics. If the displacement is positive, the acceleration is negative. If the displacement is negative, the acceleration is positive. The acceleration always points back towards equilibrium.

This definition is often more useful than a memorised example. A spring-mass system can be SHM because the spring force is proportional to displacement and directed towards equilibrium. A pendulum is approximately SHM only for small angles, because only then is the restoring acceleration approximately proportional to displacement.

## 3. Displacement as a Function of Time

One solution of

$$
a = -\omega^2x
$$

is

$$
x = x_0\sin\omega t.
$$

This form describes an oscillator that passes through equilibrium at $t = 0$ with positive velocity. The amplitude is $x_0$, and $\omega t$ must be in radians.

The same motion can also be written in a cosine form, for example

$$
x = x_0\cos\omega t,
$$

if the object is at maximum positive displacement at $t = 0$. Sine and cosine forms are not different physics. They are different choices of where the clock starts.

## 4. Velocity and Acceleration

For the sine form

$$
x = x_0\sin\omega t,
$$

the velocity is

$$
v = v_0\cos\omega t,
$$

where

$$
v_0 = \omega x_0.
$$

The speed is maximum at the equilibrium position, where $x = 0$. The speed is zero at the extremes, where $x = \pm x_0$.

Velocity can also be related directly to displacement:

$$
v = \pm \omega\sqrt{x_0^2 - x^2}.
$$

The sign depends on the direction of motion. The equation gives the speed if only the magnitude is needed.

Acceleration follows the defining equation:

$$
a = -\omega^2x.
$$

So acceleration is zero at equilibrium and has maximum magnitude at the extremes:

$$
a_\text{max} = \omega^2x_0.
$$

## 5. Reading SHM Graphs

For SHM, displacement, velocity, and acceleration against time are sinusoidal and have the same period. Their phases differ:

- $x$ is maximum at the extremes.
- $v$ is maximum in magnitude at equilibrium.
- $a$ is maximum in magnitude at the extremes, but opposite in sign to $x$.
- $a$ is in antiphase with $x$.
- $v$ is a quarter cycle out of phase with $x$.

A displacement-time graph gives velocity from gradient:

$$
v = \frac{dx}{dt}.
$$

A velocity-time graph gives acceleration from gradient:

$$
a = \frac{dv}{dt}.
$$

An acceleration-displacement graph is especially powerful. For SHM, it is a straight line through the origin with negative gradient:

$$
\text{gradient} = -\omega^2.
$$

If the graph of $a$ against $x$ is not a straight line through the origin with negative gradient, the motion is not SHM.

## 6. Energy in SHM

In undamped SHM, energy is continually exchanged between kinetic energy and potential energy. The total energy remains constant.

At the equilibrium position:

- displacement is zero;
- speed is maximum;
- kinetic energy is maximum;
- potential energy is minimum.

At either extreme:

- displacement has magnitude $x_0$;
- speed is zero;
- kinetic energy is zero;
- potential energy is maximum.

The total energy of a system undergoing SHM is

$$
E = \frac{1}{2}m\omega^2x_0^2.
$$

For a mass-spring oscillator, this is the maximum elastic potential energy and also the maximum kinetic energy. Since $v_0 = \omega x_0$,

$$
E = \frac{1}{2}mv_0^2.
$$

It is also useful to know the displacement forms:

$$
E_\text{p} = \frac{1}{2}m\omega^2x^2,
$$

and

$$
E_\text{k} = \frac{1}{2}m\omega^2(x_0^2 - x^2).
$$

These show why kinetic energy is largest at $x = 0$ and potential energy is largest at $x = \pm x_0$.

## 7. Damping

Damping occurs when a resistive force removes energy from an oscillating system. As energy is transferred away from the oscillator, the amplitude decreases.

In lightly damped motion, the system continues to oscillate, but the amplitude gradually decreases. The decay is often approximately exponential.

In critical damping, the system returns to equilibrium in the shortest possible time without oscillating. This is useful in systems such as car suspension or door closers.

In heavy damping, the system returns to equilibrium without oscillating, but more slowly than in critical damping.

The key energy statement is simple: damping removes mechanical energy from the oscillator. Since the total oscillation energy is proportional to $x_0^2$, a falling amplitude means a falling total energy.

## 8. Forced Oscillation and Resonance

A free oscillator vibrates at its natural frequency after being disturbed. A forced oscillator is driven by an external periodic force.

Resonance occurs when the forcing frequency is equal to the natural frequency of the system. At resonance:

- the amplitude is maximum;
- energy is transferred from the driver to the oscillator most efficiently;
- the response can be useful or damaging, depending on the system.

Examples help fix the idea. A child on a swing gains amplitude when pushed once per cycle at the right time. A bridge can develop large oscillations if people or wind supply energy at a frequency close to its natural frequency. A tuning circuit selects a radio signal because it responds strongly at a particular frequency.

Damping affects resonance. Greater damping lowers the maximum amplitude and broadens the resonance peak. This is why damping can reduce unwanted large oscillations in structures and vehicles.

## 9. Problem-Solving Routine

For SHM calculations:

1. Define the equilibrium position and the positive direction.
2. Identify $x_0$, $T$, $f$, and $\omega$.
3. Use $\omega = 2\pi f = \frac{2\pi}{T}$.
4. Use $a = -\omega^2x$ to test or model SHM.
5. Choose $x = x_0\sin\omega t$ or $x = x_0\cos\omega t$ based on the initial condition.
6. Use $v = v_0\cos\omega t$ or $v = \pm\omega\sqrt{x_0^2 - x^2}$ for velocity.
7. Check signs using the physical direction of motion.

For energy questions:

1. Decide whether the motion is undamped.
2. Use $E = \frac{1}{2}m\omega^2x_0^2$ for total energy.
3. At equilibrium, treat energy as kinetic.
4. At the extremes, treat energy as potential.
5. If damping is present, total mechanical energy decreases with time.

## 10. Common Traps

- Measuring displacement from an end point instead of from equilibrium.
- Confusing frequency $f$ with angular frequency $\omega$.
- Using degrees when the argument $\omega t$ must be in radians.
- Forgetting that maximum speed occurs at equilibrium, not at maximum displacement.
- Treating $v = \pm\omega\sqrt{x_0^2 - x^2}$ as always positive without checking direction.
- Saying resonance means large amplitude without mentioning forcing frequency and natural frequency.
- Thinking damping only changes amplitude. It also removes energy and changes the resonance response.

## 11. Quick Self-Check

You are ready to move on when you can:

- define displacement, amplitude, period, frequency, angular frequency, and phase difference;
- recognise SHM from $a = -\omega^2x$;
- use $x = x_0\sin\omega t$, $v = v_0\cos\omega t$, and $v = \pm\omega\sqrt{x_0^2 - x^2}$;
- interpret displacement-time, velocity-time, and acceleration-time graphs together;
- describe kinetic and potential energy exchange in SHM;
- use $E = \frac{1}{2}m\omega^2x_0^2$;
- distinguish light damping, critical damping, and heavy damping;
- explain resonance as maximum amplitude when forcing frequency equals natural frequency.

## Connections

- [[10 Physics/01 Topics/07 Waves/00 Overview|Waves]]
- [[20 Mathematics/01 Pure Mathematics/13 Further Calculus and Differential Equations/00 Overview|Further Calculus and Differential Equations]]
