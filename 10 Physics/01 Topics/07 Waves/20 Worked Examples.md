---
title: Waves Worked Examples
subject: Physics
syllabus: 9702
parent: "[Waves](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/waves
  - worked-examples
---

# Waves Worked Examples

These examples model the standard CAIE route through progressive waves, wave
quantities, CRO traces, intensity, Doppler shift, the electromagnetic spectrum,
and polarisation.

## Source Route

- Syllabus: CAIE Physics 9702 section 7, Waves.
- Coursebook route: Chapter 12, especially progressive waves, CRO
  measurements, the Doppler effect, electromagnetic waves, and polarisation.

## Example 1: Reading a Displacement-Position Graph

**Prompt.** A wave snapshot has a crest-to-trough vertical distance of
$8.0\ \mathrm{cm}$ and adjacent crests are $0.75\ \mathrm{m}$ apart. Two
points on the wave are separated by $0.25\ \mathrm{m}$ along the direction of
travel. Find the amplitude, wavelength, and phase difference between the two
points.

**Solution.**

Amplitude is measured from the equilibrium line to a crest, so it is half the
crest-to-trough distance:

$$
A=\frac{8.0}{2}=4.0\ \mathrm{cm}.
$$

The wavelength is the distance between adjacent points in phase, such as
adjacent crests:

$$
\lambda=0.75\ \mathrm{m}.
$$

Phase difference from a spatial separation is

$$
\phi=360^\circ\frac{\Delta x}{\lambda}.
$$

Thus

$$
\phi=360^\circ\frac{0.25}{0.75}
=120^\circ.
$$

In radians this is

$$
\phi=2\pi\frac{0.25}{0.75}
=\frac{2\pi}{3}\ \mathrm{rad}.
$$

**What this example trains.** Use a displacement-position graph for amplitude,
wavelength, and spatial phase difference.

## Example 2: Frequency and Amplitude from a CRO Trace

**Prompt.** A CRO trace from a microphone shows one complete cycle occupying
$4.0$ horizontal divisions. The time-base is
$0.50\ \mathrm{ms\ div^{-1}}$. The crest is $2.5$ vertical divisions above the
centre line and the y-gain is $0.20\ \mathrm{V\ div^{-1}}$. Find the period,
frequency, and voltage amplitude of the trace.

**Solution.**

Period:

$$
T=(4.0)(0.50\ \mathrm{ms})
=2.0\ \mathrm{ms}
=2.0\times 10^{-3}\ \mathrm{s}.
$$

Frequency:

$$
f=\frac{1}{T}
=\frac{1}{2.0\times 10^{-3}}
=500\ \mathrm{Hz}.
$$

Voltage amplitude is measured from the centre line to a crest:

$$
V_0=(2.5)(0.20)
=0.50\ \mathrm{V}.
$$

**What this example trains.** The time-base gives period; the y-gain gives
amplitude. Crest-to-trough height would be $2A$.

## Example 3: Deriving and Using $v=f\lambda$

**Prompt.** A sound wave in air has frequency $680\ \mathrm{Hz}$. The speed of
sound is $340\ \mathrm{m\ s^{-1}}$. Derive the wave equation and find the
wavelength.

**Solution.**

A progressive wave travels one wavelength in one period:

$$
v=\frac{\lambda}{T}.
$$

Since

$$
f=\frac{1}{T},
$$

then

$$
v=f\lambda.
$$

Rearrange for wavelength:

$$
\lambda=\frac{v}{f}
=\frac{340}{680}
=0.500\ \mathrm{m}.
$$

**What this example trains.** The wave equation follows from the definitions
of speed, period, frequency, and wavelength.

## Example 4: Intensity and Amplitude

**Prompt.** A progressive wave transmits power $12\ \mathrm{W}$ through an
area of $4.0\ \mathrm{m^2}$ at right angles to its direction of travel. Find
the intensity. If the amplitude is then made three times as large in the same
medium, what is the new intensity?

**Solution.**

Intensity is power per unit area:

$$
I=\frac{P}{A}
=\frac{12}{4.0}
=3.0\ \mathrm{W\ m^{-2}}.
$$

For the same type of progressive wave in the same medium,

$$
I\propto A^2.
$$

If the amplitude is multiplied by $3$, the intensity is multiplied by $3^2=9$:

$$
I_{\text{new}}=9(3.0)
=27\ \mathrm{W\ m^{-2}}.
$$

**What this example trains.** Intensity is proportional to amplitude squared,
not amplitude.

## Example 5: Longitudinal Wave Representation

**Prompt.** A sound wave has adjacent compressions separated by
$0.85\ \mathrm{m}$. Its frequency is $400\ \mathrm{Hz}$. Find the wave speed
and explain why a sine-wave drawing of the sound wave does not mean air
particles move sideways.

**Solution.**

Adjacent compressions are one wavelength apart:

$$
\lambda=0.85\ \mathrm{m}.
$$

Using $v=f\lambda$,

$$
v=(400)(0.85)
=340\ \mathrm{m\ s^{-1}}.
$$

Sound in air is longitudinal: air particles oscillate parallel to the direction
of wave travel. A sine-wave graph represents displacement, pressure variation,
or density variation; it is not a picture of a sideways wave shape.

**What this example trains.** A graph of a longitudinal wave is a
representation, not the physical path of the particles.

## Example 6: Doppler Effect for a Moving Source

**Prompt.** A siren emits sound of frequency $700\ \mathrm{Hz}$. The speed of
sound is $340\ \mathrm{m\ s^{-1}}$. Find the observed frequency for a
stationary observer when the source moves towards the observer at
$20\ \mathrm{m\ s^{-1}}$, and when it moves away at the same speed.

**Solution.**

For a moving source and stationary observer,

$$
f_o=\frac{f_s v}{v\pm v_s}.
$$

Approaching source: use the minus sign because wavefronts are closer together:

$$
f_o=\frac{(700)(340)}{340-20}
=744\ \mathrm{Hz}.
$$

Receding source: use the plus sign because wavefronts are farther apart:

$$
f_o=\frac{(700)(340)}{340+20}
=661\ \mathrm{Hz}.
$$

**What this example trains.** Approaching gives a higher observed frequency;
receding gives a lower observed frequency.

## Example 7: Electromagnetic Spectrum and Frequency

**Prompt.** Light of wavelength $600\ \mathrm{nm}$ travels in free space.
Calculate its frequency and state the region of the electromagnetic spectrum.

**Solution.**

Convert wavelength:

$$
600\ \mathrm{nm}=600\times 10^{-9}\ \mathrm{m}
=6.00\times 10^{-7}\ \mathrm{m}.
$$

For electromagnetic waves in free space,

$$
c=f\lambda.
$$

So

$$
f=\frac{c}{\lambda}
=\frac{3.0\times 10^8}{6.00\times 10^{-7}}
=5.0\times 10^{14}\ \mathrm{Hz}.
$$

The wavelength is between $400\ \mathrm{nm}$ and $700\ \mathrm{nm}$, so it is
visible light.

**What this example trains.** All electromagnetic waves have speed $c$ in free
space; their spectrum region depends on wavelength or frequency.

## Example 8: Malus's Law for One Polarising Filter

**Prompt.** Plane-polarised electromagnetic radiation of intensity
$12\ \mathrm{W\ m^{-2}}$ is incident on a polarising filter. The angle between
the incident plane of polarisation and the transmission axis is $60^\circ$.
Find the transmitted intensity.

**Solution.**

For plane-polarised incident radiation,

$$
I=I_0\cos^2\theta.
$$

Thus

$$
I=(12)\cos^2 60^\circ
=12(0.5)^2
=3.0\ \mathrm{W\ m^{-2}}.
$$

**What this example trains.** Malus's law uses $\cos^2\theta$, not
$\cos\theta$.

## Example 9: A Series of Polarising Filters

**Prompt.** Plane-polarised light of intensity $20\ \mathrm{W\ m^{-2}}$ first
passes through a polarising filter at $30^\circ$ to its plane of polarisation.
It then passes through a second filter whose transmission axis is at
$60^\circ$ to the first filter. Find the final intensity.

**Solution.**

After the first filter:

$$
I_1=20\cos^2 30^\circ
=20(0.75)
=15\ \mathrm{W\ m^{-2}}.
$$

The transmitted light is now plane polarised along the first filter's
transmission axis. Through the second filter:

$$
I_2=I_1\cos^2 60^\circ
=15(0.25)
=3.75\ \mathrm{W\ m^{-2}}.
$$

**What this example trains.** For a series of polarising filters, apply
Malus's law step by step using the angle between successive planes.
