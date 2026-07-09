---
title: Quantum Physics Lecture Notes
subject: Physics
syllabus: 9702
parent: "[Quantum Physics](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/modern-physics
  - lecture-notes
---

# Quantum Physics Lecture Notes

Quantum physics in this course is not a complete theory of the microscopic world. It is a set of precise ideas needed to explain experiments that classical waves or classical particles cannot explain alone. The topic is held together by one principle: energy and momentum can be transferred in discrete interactions, and the model you use must be chosen from the evidence.

## Source Route

- Primary syllabus source: CAIE Physics 9702.
- 22 Quantum physics
- 22.1 Energy and momentum of a photon
- 22.2 Photoelectric effect
- 22.3 Wave-particle duality
- 22.4 Energy levels in atoms and line spectra
- Coursebook route: Physics Coursebook Chapter 28: quantum physics, photons, photoelectric effect, matter waves, and line spectra.

## Visual Guide

![quantum-physics](../../../assets/generated/physics/quantum-physics.svg)

Figure: Photon energy, threshold frequency, and the work function provide the basic model for the photoelectric effect.

## 1. The Two Models

The wave model explains phenomena such as diffraction, interference, and polarisation. These effects depend on wavelength, phase, path difference, and superposition.

The particle model explains interactions where energy is transferred in separate packets. For electromagnetic radiation, each packet is called a photon. A photon is a quantum of electromagnetic energy.

The important habit is not to ask whether light is really only a wave or only a particle. Instead ask what the experiment shows. Propagation through space is usually described with the wave model. Absorption and emission by matter are often described with the photon model.

## 2. Photon Energy

A photon of frequency $f$ has energy

$$
E = hf,
$$

where $h$ is the Planck constant:

$$
h = 6.63 \times 10^{-34}\,\text{J s}.
$$

For electromagnetic radiation in a vacuum,

$$
c = f \lambda,
$$

so photon energy can also be written as

$$
E = \frac{hc}{\lambda}.
$$

Higher frequency means greater photon energy. Shorter wavelength also means greater photon energy. This is why ultraviolet photons can release electrons from some metal surfaces while visible photons of lower frequency may not, even if the visible light is intense.

## 3. Electronvolts

Photon energies and electron energies are often very small compared with one joule, so the electronvolt is useful. One electronvolt is the energy gained by an electron when it moves through a potential difference of $1\,\text{V}$:

$$
1\,\text{eV} = 1.60 \times 10^{-19}\,\text{J}.
$$

Convert carefully:

$$
E(\text{J}) = E(\text{eV}) \times 1.60 \times 10^{-19},
$$

$$
E(\text{eV}) = \frac{E(\text{J})}{1.60 \times 10^{-19}}.
$$

If a charged particle of charge magnitude $q$ is accelerated through a potential difference $V$, the energy transferred is

$$
E = qV.
$$

For an electron, this often means a kinetic energy of $eV$ if it starts from rest and relativistic effects are not significant.

## 4. Photon Momentum

Although a photon has no rest mass, it has momentum. The photon momentum is related to its energy by

$$
p = \frac{E}{c}.
$$

Using $E = hf$ and $c = f\lambda$ gives

$$
p = \frac{h}{\lambda}.
$$

This is a useful bridge between the photon model and the wave model. Momentum is a particle-like quantity; wavelength is a wave-like quantity. Quantum physics connects them directly.

## 5. The Photoelectric Effect

The photoelectric effect occurs when electromagnetic radiation is incident on a metal surface and electrons are emitted from the surface. The emitted electrons are called photoelectrons.

The key observations are:

- Below a certain frequency, no photoelectrons are emitted, even if the radiation is intense.
- Above that frequency, photoelectrons are emitted immediately.
- Increasing the intensity increases the photoelectric current, provided the frequency is already above the threshold.
- Increasing the intensity does not increase the maximum kinetic energy of the photoelectrons.
- Increasing the frequency increases the maximum kinetic energy of the photoelectrons.

These observations are difficult to explain using only a wave model of light. They are explained naturally if the radiation arrives as photons.

## 6. Work Function And Threshold Frequency

The work function energy $\Phi$ of a metal is the minimum energy required for an electron to escape from the metal surface.

The threshold frequency $f_0$ is the minimum frequency of incident radiation needed to emit photoelectrons:

$$
hf_0 = \Phi.
$$

The threshold wavelength $\lambda_0$ is the longest wavelength that can emit photoelectrons:

$$
\lambda_0 = \frac{c}{f_0} = \frac{hc}{\Phi}.
$$

The word longest matters. Since $E = hc/\lambda$, a shorter wavelength gives a higher photon energy. A wavelength longer than the threshold wavelength gives photons with too little energy to release electrons.

## 7. Einstein's Photoelectric Equation

A single photon interacts with a single electron. The photon transfers all its energy to that electron. Some of the energy is used to release the electron from the metal surface, and the rest becomes kinetic energy.

For the fastest photoelectrons,

$$
hf = \Phi + \frac{1}{2}mv_{\max}^2.
$$

Equivalently,

$$
K_{\max} = hf - \Phi.
$$

This equation explains the observations:

- If $hf < \Phi$, no electron can escape.
- If $hf = \Phi$, an electron can just escape with zero maximum kinetic energy.
- If $hf > \Phi$, the excess energy appears as kinetic energy.
- Greater intensity means more photons per second, so more electrons per second can be emitted.
- Greater intensity at the same frequency does not change $hf$, so it does not change $K_{\max}$.

In graph form, a plot of $K_{\max}$ against $f$ is a straight line:

$$
K_{\max} = hf - \Phi.
$$

The gradient is $h$, the intercept on the energy axis is $-\Phi$, and the frequency-axis intercept is $f_0$.

## 8. Wave-Particle Duality

The photoelectric effect provides evidence that electromagnetic radiation has a particulate nature. Diffraction and interference provide evidence that electromagnetic radiation has a wave nature.

This is wave-particle duality. It does not mean that you should draw a photon as a tiny classical ball and a full wave at the same time. It means that different experiments reveal different aspects of the same physical entity.

For electromagnetic radiation:

- Interaction with matter is often described using photons.
- Propagation, diffraction, and interference are described using waves.

## 9. Matter Waves And Electron Diffraction

De Broglie proposed that a moving particle has an associated wavelength:

$$
\lambda = \frac{h}{p}.
$$

For a non-relativistic particle of mass $m$ and speed $v$,

$$
\lambda = \frac{h}{mv}.
$$

Electron diffraction provides evidence for the wave nature of particles. In an electron diffraction tube, electrons are accelerated and then passed through a thin crystalline material such as graphite. The screen shows diffraction rings. Such rings are wave behaviour, because they depend on the electron wavelength being comparable with spacings between atomic layers.

Increasing the accelerating voltage gives electrons more kinetic energy and greater momentum. Since $\lambda = h/p$, the de Broglie wavelength decreases. The diffraction pattern therefore becomes less spread out.

For everyday objects, the de Broglie wavelength is far too small to observe because their momentum is large. For electrons, the wavelength can be comparable with atomic spacings, so diffraction becomes measurable.

## 10. Discrete Energy Levels

Electrons in isolated atoms can have only certain discrete energy levels. They cannot have energies between the allowed levels. This is called quantisation of energy.

An electron in a low energy level can absorb a photon only if the photon energy matches the difference between two allowed levels. The electron then moves to a higher energy level.

An electron in a higher energy level can make a transition to a lower energy level. The atom emits a photon whose energy equals the energy difference:

$$
hf = \Delta E.
$$

If the levels are labelled $E_{\text{high}}$ and $E_{\text{low}}$,

$$
hf = E_{\text{high}} - E_{\text{low}}.
$$

Use a positive energy difference. Energy levels are often drawn as negative values, with zero corresponding to a free electron, so the subtraction order matters.

## 11. Emission And Absorption Line Spectra

A hot low-pressure gas emits light at specific wavelengths. This gives an emission line spectrum: bright lines on a dark background. Each line corresponds to a photon emitted when an electron falls from a higher level to a lower level.

White light passing through a cool gas can produce an absorption line spectrum: dark lines on a continuous spectrum. Photons with exactly the right energy are absorbed by electrons, lifting them to higher energy levels. The re-emitted photons leave in many directions, so less light of those wavelengths continues in the original direction.

Different elements have different energy level spacings. Therefore they emit and absorb different sets of wavelengths. This is why line spectra can be used to identify elements.

## 12. Problem Routines

For photon calculations:

1. Identify whether the given quantity is frequency, wavelength, energy, or momentum.
2. Use $E = hf$ or $E = hc/\lambda$.
3. Convert between joules and electronvolts only when needed.
4. Use $p = E/c$ or $p = h/\lambda$ for photon momentum.

For photoelectric problems:

1. Compare $hf$ with $\Phi$.
2. If $hf < \Phi$, no photoelectrons are emitted.
3. If photoelectrons are emitted, use $K_{\max} = hf - \Phi$.
4. Link intensity to number of photons per second, not to energy per photon.

For energy level problems:

1. Draw the two levels and the transition arrow.
2. Take the positive energy difference.
3. Set $hf = \Delta E$.
4. Convert to wavelength using $c = f\lambda$ if required.

## 13. Common Traps

- Saying that intensity below the threshold frequency can eventually release electrons.
- Treating intensity as energy per photon.
- Forgetting to convert eV to J before using SI formulae.
- Using the wrong sign when subtracting negative energy levels.
- Treating the work function as optional in the photoelectric equation.
- Explaining electron diffraction with a particle-only model.
- Assuming wave-particle duality means two classical pictures are literally happening side by side.

## 14. Quick Self-Check

You have the topic if you can do these without notes:

- Explain why photoelectric emission supports the photon model of electromagnetic radiation.
- Use $E = hf$, $E = hc/\lambda$, and $p = E/c$ correctly.
- Distinguish threshold frequency from threshold wavelength.
- Explain why increasing intensity increases photoelectric current but not maximum kinetic energy.
- Use $\lambda = h/p$ to reason about electron diffraction.
- Explain how emission and absorption line spectra arise from discrete energy levels.

## Connections

- [Waves](../07%20Waves/00%20Overview.md)
- [Superposition](../08%20Superposition/00%20Overview.md)
- [Particle Physics](../11%20Particle%20Physics/00%20Overview.md)
- [Nuclear Physics](../23%20Nuclear%20Physics/00%20Overview.md)
