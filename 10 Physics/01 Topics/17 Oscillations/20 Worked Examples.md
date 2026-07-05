---
title: Oscillations Worked Examples
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/17 Oscillations/00 Overview|Oscillations]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/waves
  - worked-examples
---

# Oscillations Worked Examples

These examples model the standard CAIE route through simple harmonic motion,
phase, displacement, velocity, acceleration, energy exchange, damping, forced
oscillation, and resonance.

## Source Route

- Syllabus: CAIE Physics 9702 section 17, Oscillations.
- Main subtopics: simple harmonic oscillations, energy in SHM, damped and
  forced oscillations, and resonance.
- Coursebook route: phase, angular frequency, SHM equations, graph
  interpretation, energy transfer, damping, resonance curves, and critical
  damping.

## Example 1: Period, Frequency, Angular Frequency, and Phase

**Prompt.** An oscillator has period $0.80\ \mathrm{s}$. Find its frequency
and angular frequency. A second oscillator reaches maximum displacement
$0.10\ \mathrm{s}$ later. Find the phase difference.

**Solution.**

Frequency:

$$
f=\frac{1}{T}
=\frac{1}{0.80}
=1.25\ \mathrm{Hz}.
$$

Angular frequency:

$$
\omega=2\pi f
=2\pi(1.25)
=7.85\ \mathrm{rad\ s^{-1}}.
$$

Phase difference:

$$
\phi=2\pi\frac{\Delta t}{T}
=2\pi\frac{0.10}{0.80}
=\frac{\pi}{4}\ \mathrm{rad}.
$$

This is one eighth of a cycle, or $45^\circ$.

**What this example trains.** Frequency and angular frequency are not the same
quantity.

## Example 2: Recognising SHM from an Acceleration Graph

**Prompt.** A graph of acceleration $a$ against displacement $x$ is a straight
line through the origin with gradient $-25\ \mathrm{s^{-2}}$. Show that the
motion is SHM, and find $\omega$ and $T$.

**Solution.**

For SHM,

$$
a=-\omega^2x.
$$

An $a$ against $x$ graph must therefore be a straight line through the origin
with negative gradient. The given graph satisfies this condition, so the
motion is SHM.

The gradient is

$$
-\omega^2=-25.
$$

So

$$
\omega=5.0\ \mathrm{rad\ s^{-1}}.
$$

The period is

$$
T=\frac{2\pi}{\omega}
=\frac{2\pi}{5.0}
=1.26\ \mathrm{s}.
$$

**What this example trains.** The negative gradient of an $a$-$x$ graph gives
$-\omega^2$.

## Example 3: Using $x=x_0\sin\omega t$

**Prompt.** An oscillator is described by

$$
x=0.050\sin(4\pi t),
$$

where $x$ is in metres and $t$ is in seconds. Find the amplitude, angular
frequency, period, displacement at $t=0.125\ \mathrm{s}$, and maximum speed.

**Solution.**

Compare with

$$
x=x_0\sin\omega t.
$$

So

$$
x_0=0.050\ \mathrm{m},
\qquad
\omega=4\pi\ \mathrm{rad\ s^{-1}}.
$$

The period is

$$
T=\frac{2\pi}{\omega}
=\frac{2\pi}{4\pi}
=0.50\ \mathrm{s}.
$$

At $t=0.125\ \mathrm{s}$,

$$
\omega t=(4\pi)(0.125)=\frac{\pi}{2}.
$$

Therefore

$$
x=0.050\sin\frac{\pi}{2}=0.050\ \mathrm{m}.
$$

Maximum speed:

$$
v_0=\omega x_0=(4\pi)(0.050)=0.628\ \mathrm{m\ s^{-1}}.
$$

**What this example trains.** The argument $\omega t$ is in radians.

## Example 4: Speed at a Given Displacement

**Prompt.** A body oscillates with amplitude $0.080\ \mathrm{m}$ and period
$1.20\ \mathrm{s}$. Find its maximum speed and its speed when
$x=0.030\ \mathrm{m}$.

**Solution.**

Angular frequency:

$$
\omega=\frac{2\pi}{T}
=\frac{2\pi}{1.20}
=5.24\ \mathrm{rad\ s^{-1}}.
$$

Maximum speed:

$$
v_0=\omega x_0
=(5.24)(0.080)
=0.419\ \mathrm{m\ s^{-1}}.
$$

At displacement $x$,

$$
v=\pm\omega\sqrt{x_0^2-x^2}.
$$

The speed is the magnitude:

$$
|v|
=(5.24)\sqrt{(0.080)^2-(0.030)^2}
=0.388\ \mathrm{m\ s^{-1}}.
$$

The sign would depend on the direction of motion.

**What this example trains.** Speed is maximum at equilibrium, not at maximum
displacement.

## Example 5: Energy in SHM

**Prompt.** A $0.20\ \mathrm{kg}$ mass oscillates with frequency
$2.0\ \mathrm{Hz}$ and amplitude $0.050\ \mathrm{m}$. Find the total energy.
Then find the potential and kinetic energies when $x=0.030\ \mathrm{m}$.

**Solution.**

Angular frequency:

$$
\omega=2\pi f=2\pi(2.0)=12.6\ \mathrm{rad\ s^{-1}}.
$$

Total energy:

$$
E=\frac{1}{2}m\omega^2x_0^2
=
\frac{1}{2}(0.20)(12.6)^2(0.050)^2
=3.95 \times 10^{-2}\ \mathrm{J}.
$$

Potential energy at displacement $x$:

$$
E_p=\frac{1}{2}m\omega^2x^2
=
\frac{1}{2}(0.20)(12.6)^2(0.030)^2
=1.42 \times 10^{-2}\ \mathrm{J}.
$$

Kinetic energy:

$$
E_k=E-E_p
=3.95 \times 10^{-2}-1.42 \times 10^{-2}
=2.53 \times 10^{-2}\ \mathrm{J}.
$$

**What this example trains.** In undamped SHM, total energy is constant but
kinetic and potential energy exchange.

## Example 6: Reading SHM Graphs

**Prompt.** At one instant in SHM, displacement is maximum and positive.
State the velocity and acceleration at that instant.

**Solution.**

At maximum positive displacement,

$$
x=+x_0.
$$

The oscillator is at an extreme, so its velocity is zero:

$$
v=0.
$$

Acceleration is given by

$$
a=-\omega^2x.
$$

Since $x$ is positive, $a$ is negative. The acceleration has maximum magnitude
and is directed back towards equilibrium.

**What this example trains.** Acceleration is opposite in sign to displacement
in SHM.

## Example 7: Damping

**Prompt.** Explain the difference between light damping, critical damping,
and heavy damping.

**Solution.**

Damping is caused by a resistive force that removes energy from an oscillating
system.

In light damping, the system continues to oscillate, but the amplitude
gradually decreases.

In critical damping, the system returns to equilibrium in the shortest time
without oscillating.

In heavy damping, the system also returns without oscillating, but more slowly
than in critical damping.

**What this example trains.** Damping is about energy removal and the shape of
the displacement-time graph.

## Example 8: Resonance and Damping

**Prompt.** Describe resonance and explain the effect of increased damping on
a resonance curve.

**Solution.**

Resonance occurs when an oscillator is forced to oscillate at its natural
frequency. The amplitude is then maximum because energy is transferred from the
driver to the oscillator most efficiently.

On a graph of amplitude against driving frequency, resonance appears as a peak
near the natural frequency.

Increasing damping reduces the maximum amplitude and makes the resonance peak
broader. The frequency at which the maximum occurs can also shift slightly
lower.

**What this example trains.** Resonance is controlled by energy transfer and
damping, not just by the word "large".
