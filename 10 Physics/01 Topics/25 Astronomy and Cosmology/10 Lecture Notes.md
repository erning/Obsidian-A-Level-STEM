---
title: Astronomy and Cosmology Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/25 Astronomy and Cosmology/00 Overview|Astronomy and Cosmology]]"
status: draft
tags:
  - physics/9702/topic
  - physics/9702/applications
  - lecture-notes
---

# Astronomy and Cosmology Lecture Notes

Astronomy and cosmology turn light into physical information. From the light received at Earth, we infer distances, stellar temperatures, stellar radii, galaxy speeds, and evidence that the Universe is expanding.

The central skill is to separate what a star or galaxy actually emits from what we observe after the radiation has spread across a huge distance.

## Source Route

- Primary syllabus source: CAIE Physics 9702.
- 25 Astronomy and cosmology
- 25.1 Standard candles
- 25.2 Stellar radii
- 25.3 Hubble's law and the Big Bang theory
- Coursebook route: Physics Coursebook Chapter 31: luminosity, standard candles, radiant flux intensity, stellar radii, redshift, Hubble's law, and the Big Bang model.

## Visual Guide

![[assets/generated/physics/astronomy-and-cosmology.svg]]

Figure: Stellar measurements connect luminosity, temperature, radius, redshift, and distance.

## 1. Luminosity

The luminosity $L$ of a star is the total power of radiation emitted by the star. It is not how bright the star looks from Earth.

The unit of luminosity is the watt:

$$
\text{W} = \text{J s}^{-1}.
$$

A very luminous star may look faint if it is very far away. A less luminous star may look bright if it is close. This distinction between intrinsic output and observed flux is the first idea to get secure.

## 2. Radiant Flux Intensity

Radiant flux intensity $F$ is the radiant power passing normally through unit area at the observation point. Its unit is

$$
\text{W m}^{-2}.
$$

If a star emits uniformly in all directions and absorption between the star and the observer is negligible, the radiation spreads out over a sphere of radius $d$. The surface area of that sphere is $4\pi d^2$, so

$$
F = \frac{L}{4\pi d^2}.
$$

This is the inverse square law for radiant flux intensity. If the distance doubles, $F$ falls by a factor of 4. If the distance triples, $F$ falls by a factor of 9.

If $L$ is known and $F$ is measured, the distance is

$$
d = \sqrt{\frac{L}{4\pi F}}.
$$

This equation is one of the main bridges from observation to astronomical distance.

## 3. Standard Candles

A standard candle is an astronomical object of known luminosity. Once its luminosity is known, measuring its radiant flux intensity at Earth allows its distance to be calculated using

$$
F = \frac{L}{4\pi d^2}.
$$

Standard candles are useful because many galaxies are too far away for simple geometric distance methods. If a standard candle can be identified in a galaxy, its distance gives an estimate of the distance to that galaxy.

Two important examples are:

- Cepheid variable stars: their period of brightness variation is related to their average luminosity.
- Type Ia supernovae: their peak luminosities are sufficiently consistent to be used as distance indicators.

The method depends on calibration. A standard candle is useful only because its intrinsic luminosity can be known independently of its observed brightness.

## 4. Stellar Temperature From Wien's Displacement Law

Stars can be modelled approximately as black bodies. A black-body spectrum has a peak wavelength $\lambda_{\max}$, where the emitted intensity is greatest.

Wien's displacement law states that

$$
\lambda_{\max}T = b,
$$

where

$$
b \approx 2.9 \times 10^{-3}\,\text{m K}.
$$

Equivalently,

$$
\lambda_{\max} \propto \frac{1}{T}.
$$

A hotter star has a shorter peak wavelength. Blue-white stars have higher surface temperatures than red stars. If $\lambda_{\max}$ is measured, the surface temperature can be estimated:

$$
T = \frac{b}{\lambda_{\max}}.
$$

Use kelvin for temperature and metres for wavelength unless a question gives a consistent alternative.

## 5. Stellar Luminosity From The Stefan-Boltzmann Law

The luminosity of a star depends on both its surface temperature and its radius. A large cool star can be more luminous than a small hot star because the large star has much more emitting surface area.

The Stefan-Boltzmann law for a spherical star is

$$
L = 4\pi\sigma r^2T^4,
$$

where $r$ is the radius of the star, $T$ is its surface thermodynamic temperature, and $\sigma$ is the Stefan-Boltzmann constant:

$$
\sigma = 5.67 \times 10^{-8}\,\text{W m}^{-2}\,\text{K}^{-4}.
$$

If $L$ and $T$ are known, the radius is

$$
r = \sqrt{\frac{L}{4\pi\sigma T^4}}.
$$

This is the second main bridge from observation to stellar properties.

## 6. Estimating A Stellar Radius

A common route is:

1. Measure the wavelength at peak intensity, $\lambda_{\max}$.
2. Use Wien's displacement law to estimate $T$.
3. Determine $L$ from the observed radiant flux intensity and distance, or from a standard candle calibration.
4. Use the Stefan-Boltzmann law to find $r$.

The physical interpretation is important. A star with high $T$ but low $L$ must have a small radius. A star with low $T$ but high $L$ must have a large radius.

## 7. Spectral Lines And Redshift

Atoms produce emission and absorption lines at known wavelengths. If the same spectral lines from a distant galaxy are observed at longer wavelengths than their laboratory values, the spectrum is redshifted.

Redshift does not mean that every line literally becomes red. It means that wavelengths have increased.

For a source moving away from an observer at non-relativistic speed, the fractional wavelength change is approximately

$$
\frac{\Delta\lambda}{\lambda} \approx \frac{v}{c},
$$

where $v$ is the recession speed and $c$ is the speed of light.

Since frequency decreases when wavelength increases, a signed frequency change would be negative for redshift. In many A Level calculations the frequency form is used in magnitude:

$$
\left|\frac{\Delta f}{f}\right| \approx \frac{v}{c}.
$$

Use the same units for $\Delta\lambda$ and $\lambda$. If both are in nanometres, the ratio is still dimensionless.

## 8. Hubble's Law

Hubble's law states that the recession speed $v$ of a galaxy is approximately proportional to its distance $d$:

$$
v \approx H_0d.
$$

$H_0$ is the Hubble constant. In SI units, its unit is

$$
\text{s}^{-1}.
$$

On a graph of recession speed against distance, the gradient is $H_0$.

Hubble's law is not saying that Earth is at the centre of the Universe. The modern interpretation is that space itself is expanding, so distant galaxies recede from one another. An observer in another galaxy would also see distant galaxies receding.

## 9. Expanding Universe And The Big Bang Model

Redshift shows that light from distant galaxies has been stretched to longer wavelengths. Hubble's law adds that more distant galaxies have greater recession speeds. Together, these observations support the idea that the Universe is expanding.

If the expansion is traced backward in time, distances between galaxies were smaller in the past. This leads to the Big Bang model: the Universe evolved from an extremely hot, dense early state and has been expanding and cooling since.

A rough timescale comes from the Hubble time:

$$
t \sim \frac{1}{H_0}.
$$

This estimate is only a model-dependent approximation, but it gives the correct order of magnitude for the age of the Universe. A value of $H_0$ around $2.4 \times 10^{-18}\,\text{s}^{-1}$ gives a timescale of order $10^{17}$ to $10^{18}\,\text{s}$, or billions of years.

The cosmic microwave background is further supporting evidence: radiation from all directions has a spectrum corresponding to a temperature of about $2.7\,\text{K}$, consistent with an expanding Universe that has cooled over time.

## 10. Problem Routines

For luminosity and distance:

1. Identify whether the given power is luminosity $L$ or observed radiant flux intensity $F$.
2. Use $F = L/(4\pi d^2)$.
3. Rearrange to find the unknown.
4. Check that $F$ has units $\text{W m}^{-2}$ and $L$ has units $\text{W}$.

For standard candles:

1. Explain how the object's luminosity is known.
2. Measure or use the observed radiant flux intensity.
3. Calculate distance using the inverse square law.
4. Treat the distance to the standard candle as the distance to its host galaxy if appropriate.

For stellar radii:

1. Use Wien's law to find $T$ from $\lambda_{\max}$.
2. Use Stefan-Boltzmann to connect $L$, $r$, and $T$.
3. Interpret the result by comparing size and temperature.

For redshift and Hubble's law:

1. Identify the laboratory wavelength and observed wavelength.
2. Compute $\Delta\lambda/\lambda$.
3. Use $v/c \approx \Delta\lambda/\lambda$ for non-relativistic recession speeds.
4. Use $v \approx H_0d$ to connect speed and distance.

## 11. Common Traps

- Using the word brightness without saying whether you mean luminosity or radiant flux intensity.
- Forgetting the $4\pi d^2$ in the inverse square law.
- Treating a standard candle as an object that merely looks bright.
- Using Celsius instead of kelvin in Wien's law or Stefan-Boltzmann law.
- Thinking that redshift means every spectral line turns red.
- Applying the simple redshift equation without recognising it is for small speeds compared with $c$.
- Interpreting Hubble's law as expansion away from Earth rather than expansion of space.

## 12. Quick Self-Check

You have the topic if you can do these without notes:

- Define luminosity and radiant flux intensity and state their units.
- Explain how a standard candle gives the distance to a galaxy.
- Use $F = L/(4\pi d^2)$ to connect luminosity, flux, and distance.
- Use Wien's displacement law to estimate stellar surface temperature.
- Use $L = 4\pi\sigma r^2T^4$ to estimate stellar radius.
- Use redshift and Hubble's law to explain why the Universe is thought to be expanding.

## Connections

- [[10 Physics/01 Topics/07 Waves/00 Overview|Waves]]
- [[10 Physics/01 Topics/08 Superposition/00 Overview|Superposition]]
- [[10 Physics/01 Topics/22 Quantum Physics/00 Overview|Quantum Physics]]
