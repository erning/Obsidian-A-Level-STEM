---
title: Waves Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/07 Waves/00 Overview|Waves]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/waves
  - lecture-notes
---

# Waves Lecture Notes

A wave is a travelling disturbance that transfers energy without transferring
matter from one place to another. In a water wave, the water surface oscillates
while the wave pattern travels. In a sound wave, air particles oscillate while
energy travels through the air. In an electromagnetic wave, electric and
magnetic fields oscillate while energy travels through space.

The first job in wave physics is to separate two motions:

- the motion of the wave pattern as it travels
- the oscillation of a point in the medium or field

Confusing these two is the source of many mistakes.

## Visual guide

![[assets/generated/physics/waves.svg]]

Use the diagram to locate amplitude, wavelength, period, frequency, phase, and
wave speed on a progressive wave. A displacement-position graph and a
displacement-time graph may look similar, but they answer different questions.

## Source route

This note follows CAIE Physics 9702 section 7, Waves:

- 7.1 Progressive waves
- 7.2 Transverse and longitudinal waves
- 7.3 Doppler effect for sound waves
- 7.4 Electromagnetic spectrum
- 7.5 Polarisation

The matching coursebook route is Chapter 12, which covers progressive waves,
wave quantities, CRO measurements, intensity, wave speed, the Doppler effect,
electromagnetic waves, the electromagnetic spectrum, and polarisation.

## 1. Progressive waves

A progressive wave transfers energy from one place to another. The particles of
a mechanical medium do not travel along with the wave. They oscillate about
equilibrium positions while energy is passed from one part of the medium to the
next.

Mechanical waves need a medium. Sound waves need air, water, or another
material. Waves on a string need the string. Electromagnetic waves do not need a
material medium and can travel through a vacuum.

The word displacement in waves means the displacement of a point on the wave
from its equilibrium position. It is not the distance travelled by the wave.

## 2. Wave quantities

The standard quantities are:

| Quantity | Meaning | Common unit |
| --- | --- | --- |
| Displacement $x$ | Distance of a point from equilibrium, with sign | $\text{m}$ |
| Amplitude $A$ | Maximum displacement from equilibrium | $\text{m}$ |
| Wavelength $\lambda$ | Distance between adjacent points oscillating in phase | $\text{m}$ |
| Period $T$ | Time for one complete oscillation | $\text{s}$ |
| Frequency $f$ | Number of oscillations per unit time | $\text{Hz}$ |
| Wave speed $v$ | Speed at which the wave pattern and energy travel | $\text{m s}^{-1}$ |

Frequency and period are reciprocals:

$$
f = \frac{1}{T}
$$

and

$$
T = \frac{1}{f}
$$

A displacement-position graph shows the shape of the wave at one instant. From
it you can read wavelength and amplitude.

A displacement-time graph shows how one point oscillates as time passes. From
it you can read period, frequency, and amplitude.

## 3. Phase and phase difference

Phase tells you where an oscillation is within its cycle. Two points are in
phase if they move together: same displacement and same direction of motion at
the same time. Points one wavelength apart are in phase.

Two points are in antiphase if their phase difference is $180^\circ$ or
$\pi\ \text{rad}$. When one is at a crest, the other is at a trough.

For two points separated by distance $\Delta x$ on a wave of wavelength
$\lambda$, the phase difference is

$$
\phi = 2\pi \frac{\Delta x}{\lambda}
$$

in radians, or

$$
\phi = 360^\circ \frac{\Delta x}{\lambda}
$$

in degrees.

For two oscillations separated by time $\Delta t$ in a wave of period $T$,

$$
\phi = 2\pi \frac{\Delta t}{T}
$$

Phase language becomes essential in
[[10 Physics/01 Topics/08 Superposition/00 Overview|Superposition]], where
waves meet and combine.

## 4. CRO measurements

A cathode-ray oscilloscope, or CRO, can display a rapidly varying voltage. With
a microphone connected to the input, the voltage trace has the same frequency
as the sound wave detected by the microphone.

The time-base gives the horizontal scale, usually in seconds per division. To
find the period:

$$
T = \text{horizontal divisions for one cycle} \times \text{time-base}
$$

Then

$$
f = \frac{1}{T}
$$

The y-gain gives the vertical scale, usually in volts per division. To find the
amplitude of the trace:

$$
\text{amplitude} =
\text{vertical divisions from centre line to crest} \times \text{y-gain}
$$

Measure amplitude from the equilibrium line to a crest or trough, not from
crest to trough. Crest-to-trough height is $2A$.

## 5. The wave equation

A wave travels one wavelength $\lambda$ in one period $T$. Therefore

$$
v = \frac{\lambda}{T}
$$

Since $f = \dfrac{1}{T}$,

$$
v = f\lambda
$$

This equation applies to all progressive waves. The speed is set by the medium
and wave type. For sound in air, the speed depends on conditions such as
temperature. For electromagnetic waves in free space, the speed is

$$
c = 3.0 \times 10^8\ \text{m s}^{-1}
$$

If wave speed is constant, increasing frequency decreases wavelength:

$$
\lambda = \frac{v}{f}
$$

## 6. Transverse and longitudinal waves

In a transverse wave, the oscillations are at right angles to the direction of
wave travel. Waves on a stretched string and electromagnetic waves are
transverse.

In a longitudinal wave, the oscillations are parallel to the direction of wave
travel. Sound in air is longitudinal. It consists of compressions and
rarefactions: regions of higher and lower pressure.

Longitudinal waves are often drawn as sine waves, but the graph represents
particle displacement, pressure variation, or density variation, not a physical
sideways shape of the wave.

## 7. Energy transfer and intensity

A progressive wave transfers energy. The intensity of a wave is the power
transmitted per unit area at right angles to the wave velocity:

$$
I = \frac{P}{A}
$$

The unit is

$$
\text{W m}^{-2}
$$

For a progressive wave of the same type in the same medium, intensity is
proportional to the square of amplitude:

$$
I \propto A^2
$$

If the amplitude doubles, the intensity becomes four times as large. If the
amplitude is halved, the intensity becomes one quarter as large.

Intensity can decrease as a wave travels because the wave spreads out or because
energy is absorbed or scattered.

## 8. Doppler effect for sound waves

The Doppler effect is the change in observed frequency when a source of sound
waves moves relative to a stationary observer.

If the source moves towards the observer, successive wavefronts are closer
together in front of the source. The observed wavelength is shorter and the
observed frequency is higher.

If the source moves away from the observer, successive wavefronts are farther
apart behind the source. The observed wavelength is longer and the observed
frequency is lower.

For a moving source and stationary observer, CAIE uses

$$
f_o = \frac{f_s v}{v \pm v_s}
$$

where $f_o$ is the observed frequency, $f_s$ is the source frequency, $v$ is the
speed of sound in the medium, and $v_s$ is the speed of the source.

Use the plus sign for a receding source:

$$
f_o = \frac{f_s v}{v + v_s}
$$

This gives a lower observed frequency.

Use the minus sign for an approaching source:

$$
f_o = \frac{f_s v}{v - v_s}
$$

This gives a higher observed frequency.

The source frequency is not changed by the motion of the source. The speed of
sound in the medium is also not changed by the motion of the source. What
changes is the spacing of the wavefronts reaching the observer.

## 9. Electromagnetic waves

An electromagnetic wave is an oscillation of electric and magnetic fields. The
electric field and magnetic field oscillate at right angles to each other and at
right angles to the direction of travel. Electromagnetic waves are therefore
transverse waves.

All electromagnetic waves travel at the same speed $c$ in free space:

$$
c = 3.0 \times 10^8\ \text{m s}^{-1}
$$

In free space,

$$
c = f\lambda
$$

Electromagnetic waves do not need a medium. When they enter a material medium,
their speed changes. Their frequency stays the same, so their wavelength changes.

## 10. Electromagnetic spectrum

The principal regions of the electromagnetic spectrum, in order of increasing
frequency and decreasing wavelength, are:

$$
\text{radio} \rightarrow \text{microwave} \rightarrow \text{infrared}
\rightarrow \text{visible} \rightarrow \text{ultraviolet}
\rightarrow \text{X-rays} \rightarrow \gamma\text{-rays}
$$

Approximate wavelength ranges in free space are:

| Region | Approximate wavelength range |
| --- | --- |
| Radio waves | greater than $10^{-1}\ \text{m}$, extending to very long wavelengths |
| Microwaves | $10^{-1}\ \text{m}$ to $10^{-3}\ \text{m}$ |
| Infrared | $10^{-3}\ \text{m}$ to $7 \times 10^{-7}\ \text{m}$ |
| Visible | $7 \times 10^{-7}\ \text{m}$ to $4 \times 10^{-7}\ \text{m}$ |
| Ultraviolet | $4 \times 10^{-7}\ \text{m}$ to $10^{-8}\ \text{m}$ |
| X-rays | $10^{-8}\ \text{m}$ to about $10^{-13}\ \text{m}$ |
| $\gamma$-rays | about $10^{-10}\ \text{m}$ to $10^{-16}\ \text{m}$ |

Visible wavelengths in free space are approximately

$$
400\ \text{nm} \text{ to } 700\ \text{nm}
$$

The boundaries between regions are not sharp. X-rays and gamma-rays overlap in
wavelength; the distinction is usually their origin. X-rays are commonly
produced by rapid deceleration of electrons or electron transitions involving
inner shells, while gamma-rays are produced by nuclear processes.

## 11. Polarisation

Polarisation is associated with transverse waves. A plane-polarised wave has
oscillations in one plane only.

A transverse wave on a rope can be made plane polarised by moving the rope end
up and down in one plane. A polarising filter does a similar job for
electromagnetic waves: it transmits one plane of electric field oscillation more
than others.

Longitudinal waves cannot be plane polarised because their oscillations are
along the direction of travel. There is no transverse plane of vibration to
select. This is why polarisation is evidence that electromagnetic waves are
transverse.

## 12. Malus's law

Malus's law applies when plane-polarised electromagnetic radiation is incident
on a polarising filter. If the angle between the plane of polarisation of the
incident wave and the transmission axis of the filter is $\theta$, then the
transmitted intensity is

$$
I = I_0 \cos^2\theta
$$

where $I_0$ is the incident intensity and $I$ is the transmitted intensity.

Check the limiting cases:

- If $\theta = 0^\circ$, then $I = I_0$.
- If $\theta = 90^\circ$, then $I = 0$.
- If $\theta = 45^\circ$, then $I = \frac{1}{2}I_0$.

This syllabus section does not require calculation of the intensity after a
polarising filter when the incident wave is unpolarised.

## 13. A working routine

Use this routine for wave problems.

1. Decide whether the graph is displacement against position or displacement
   against time.
2. Read amplitude from equilibrium to crest.
3. Read wavelength from a position graph and period from a time graph.
4. Use $f = 1/T$ and $v = f\lambda$.
5. Use phase difference only after identifying whether separation is in space
   or in time.
6. For intensity comparisons, square the amplitude ratio.
7. For Doppler effect, decide whether the source is approaching or receding
   before choosing the sign.
8. For polarisation, check that the incident wave is plane polarised before
   using Malus's law.

## 14. Common mistakes

- Thinking that particles of the medium travel along with a progressive wave.
- Reading wavelength from a displacement-time graph.
- Reading period from a displacement-position graph.
- Measuring amplitude from crest to trough instead of from the centre line.
- Treating intensity as proportional to amplitude rather than amplitude
  squared.
- Using the wrong sign in the moving-source Doppler equation.
- Forgetting that all electromagnetic waves have the same speed in free space.
- Trying to polarise a longitudinal wave.
- Applying Malus's law to unpolarised incident light when the question does not
  require that case.

## Quick self-check

You are ready to move on when you can answer these without notes.

1. What does a progressive wave transfer?
2. What is the difference between the wave speed and the motion of a point in
   the medium?
3. How do you distinguish a displacement-position graph from a
   displacement-time graph?
4. How is $v = f\lambda$ derived?
5. What is the difference between a transverse wave and a longitudinal wave?
6. How does intensity change when amplitude is doubled?
7. Which sign is used in the Doppler equation for an approaching source?
8. Why does polarisation show that electromagnetic waves are transverse?

## Connections

- [[10 Physics/01 Topics/08 Superposition/00 Overview|Superposition]] uses
  phase and displacement to explain interference, diffraction, and stationary
  waves.
- [[10 Physics/01 Topics/17 Oscillations/00 Overview|Oscillations]] studies the
  motion of one vibrating point in more detail.
- [[10 Physics/01 Topics/22 Quantum Physics/00 Overview|Quantum Physics]]
  returns to electromagnetic radiation from a photon point of view.
- [[10 Physics/01 Topics/25 Astronomy and Cosmology/00 Overview|Astronomy and Cosmology]]
  uses wavelength shifts and electromagnetic spectra to study distant objects.
