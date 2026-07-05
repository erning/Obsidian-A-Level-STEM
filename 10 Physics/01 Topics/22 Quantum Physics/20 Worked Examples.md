---
title: Quantum Physics Worked Examples
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/22 Quantum Physics/00 Overview|Quantum Physics]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/modern-physics
  - worked-examples
---

# Quantum Physics Worked Examples

These examples model the standard CAIE route through photons, photoelectric
emission, wave-particle duality, de Broglie wavelength, and atomic line
spectra.

## Source Route

- Syllabus: CAIE Physics 9702 section 22, Quantum physics.
- Main subtopics: energy and momentum of a photon, photoelectric effect,
  wave-particle duality, and energy levels in atoms and line spectra.
- Coursebook route: photons, electronvolts, threshold frequency, work
  function, electron diffraction, matter waves, and emission and absorption
  spectra.

Use these constants unless a question gives different values:

$$
h=6.63 \times 10^{-34}\ \mathrm{J\ s},
$$

$$
c=3.00 \times 10^8\ \mathrm{m\ s^{-1}},
$$

$$
e=1.60 \times 10^{-19}\ \mathrm{C}.
$$

## Example 1: Photon Energy and Momentum

**Prompt.** A photon has wavelength $540\ \mathrm{nm}$. Find its energy in
joules and electronvolts, and find its momentum.

**Solution.**

Convert the wavelength:

$$
540\ \mathrm{nm}=5.40 \times 10^{-7}\ \mathrm{m}.
$$

Photon energy is

$$
E=\frac{hc}{\lambda}.
$$

So

$$
E=
\frac{(6.63 \times 10^{-34})(3.00 \times 10^8)}
{5.40 \times 10^{-7}}
=3.68 \times 10^{-19}\ \mathrm{J}.
$$

Convert to electronvolts:

$$
E=\frac{3.68 \times 10^{-19}}{1.60 \times 10^{-19}}
=2.30\ \mathrm{eV}.
$$

The photon momentum is

$$
p=\frac{E}{c}=\frac{h}{\lambda}.
$$

Therefore

$$
p=
\frac{6.63 \times 10^{-34}}{5.40 \times 10^{-7}}
=1.23 \times 10^{-27}\ \mathrm{kg\ m\ s^{-1}}.
$$

**What this example trains.** Photon energy and momentum connect a particle
quantity to a wave quantity through the wavelength.

## Example 2: Threshold Frequency and Threshold Wavelength

**Prompt.** A metal has work function $2.30\ \mathrm{eV}$. Find the threshold
frequency and threshold wavelength for photoelectric emission.

**Solution.**

First convert the work function to joules:

$$
\Phi=(2.30)(1.60 \times 10^{-19})
=3.68 \times 10^{-19}\ \mathrm{J}.
$$

At the threshold frequency, the photon energy is just equal to the work
function:

$$
hf_0=\Phi.
$$

Hence

$$
f_0=\frac{\Phi}{h}
=\frac{3.68 \times 10^{-19}}{6.63 \times 10^{-34}}
=5.55 \times 10^{14}\ \mathrm{Hz}.
$$

The threshold wavelength is the longest wavelength that can cause emission:

$$
\lambda_0=\frac{c}{f_0}
=\frac{3.00 \times 10^8}{5.55 \times 10^{14}}
=5.41 \times 10^{-7}\ \mathrm{m}.
$$

**What this example trains.** Threshold frequency is a minimum frequency, but
threshold wavelength is a maximum wavelength.

## Example 3: Maximum Kinetic Energy of Photoelectrons

**Prompt.** The metal in Example 2 is illuminated by radiation of frequency
$6.50 \times 10^{14}\ \mathrm{Hz}$. Find the maximum kinetic energy of the
photoelectrons in joules and electronvolts.

**Solution.**

Einstein's photoelectric equation is

$$
hf=\Phi+K_{\max}.
$$

So

$$
K_{\max}=hf-\Phi.
$$

Calculate the photon energy:

$$
hf=(6.63 \times 10^{-34})(6.50 \times 10^{14})
=4.31 \times 10^{-19}\ \mathrm{J}.
$$

Therefore

$$
K_{\max}
=4.31 \times 10^{-19}-3.68 \times 10^{-19}
=6.30 \times 10^{-20}\ \mathrm{J}.
$$

In electronvolts,

$$
K_{\max}
=\frac{6.30 \times 10^{-20}}{1.60 \times 10^{-19}}
=0.394\ \mathrm{eV}.
$$

**What this example trains.** Work function is not optional; it is the energy
used to release the electron before kinetic energy remains.

## Example 4: Intensity and Photoelectric Current

**Prompt.** Radiation of frequency above the threshold frequency shines on a
metal surface. Explain what happens to the photoelectric current and the
maximum kinetic energy when the intensity is doubled but the frequency is
unchanged.

**Solution.**

Increasing intensity at the same frequency increases the number of photons
arriving per second. If the frequency is already above the threshold frequency,
more photons can release more electrons per second, so the photoelectric
current increases.

The energy of each photon is still

$$
E=hf.
$$

Since $f$ has not changed, the energy per photon has not changed. The maximum
kinetic energy remains

$$
K_{\max}=hf-\Phi.
$$

So the current increases, but the maximum kinetic energy does not.

**What this example trains.** Intensity controls the photon arrival rate;
frequency controls the energy per photon.

## Example 5: Stopping Potential

**Prompt.** The maximum kinetic energy of photoelectrons is
$1.44 \times 10^{-19}\ \mathrm{J}$. Find the stopping potential.

**Solution.**

The stopping potential $V_s$ is the potential difference needed to reduce the
maximum kinetic energy of an electron to zero:

$$
eV_s=K_{\max}.
$$

Therefore

$$
V_s=\frac{K_{\max}}{e}
=\frac{1.44 \times 10^{-19}}{1.60 \times 10^{-19}}
=0.900\ \mathrm{V}.
$$

**What this example trains.** Stopping potential is a direct way to measure
maximum kinetic energy in electronvolts.

## Example 6: De Broglie Wavelength of An Electron

**Prompt.** An electron is accelerated from rest through a potential difference
of $150\ \mathrm{V}$. Estimate its de Broglie wavelength. Use
$m_e=9.11 \times 10^{-31}\ \mathrm{kg}$.

**Solution.**

The kinetic energy gained by the electron is

$$
E=eV=(1.60 \times 10^{-19})(150)
=2.40 \times 10^{-17}\ \mathrm{J}.
$$

For a non-relativistic electron,

$$
E=\frac{p^2}{2m}.
$$

So

$$
p=\sqrt{2mE}.
$$

Substitute:

$$
p=
\sqrt{2(9.11 \times 10^{-31})(2.40 \times 10^{-17})}
=6.61 \times 10^{-24}\ \mathrm{kg\ m\ s^{-1}}.
$$

The de Broglie wavelength is

$$
\lambda=\frac{h}{p}
=\frac{6.63 \times 10^{-34}}{6.61 \times 10^{-24}}
=1.00 \times 10^{-10}\ \mathrm{m}.
$$

This is comparable with atomic spacings, so electron diffraction can be
observed.

**What this example trains.** Matter-wave effects become observable when the
de Broglie wavelength is comparable with the spacing in the diffracting
structure.

## Example 7: Energy Levels and Emitted Wavelength

**Prompt.** In a hydrogen atom, an electron falls from the
$-3.40\ \mathrm{eV}$ level to the $-13.6\ \mathrm{eV}$ level. Find the
energy and wavelength of the emitted photon.

**Solution.**

Use the positive energy difference:

$$
\Delta E=(-3.40)-(-13.6)=10.2\ \mathrm{eV}.
$$

Convert to joules:

$$
\Delta E=(10.2)(1.60 \times 10^{-19})
=1.63 \times 10^{-18}\ \mathrm{J}.
$$

For the emitted photon,

$$
hf=\Delta E
$$

and

$$
\lambda=\frac{hc}{\Delta E}.
$$

Thus

$$
\lambda=
\frac{(6.63 \times 10^{-34})(3.00 \times 10^8)}
{1.63 \times 10^{-18}}
=1.22 \times 10^{-7}\ \mathrm{m}.
$$

**What this example trains.** Energy levels may be negative, but emitted
photon energy is the positive difference between the two levels.

## Example 8: Emission and Absorption Spectra

**Prompt.** Explain why a low-pressure gas can produce both emission and
absorption line spectra, and why these spectra identify the element.

**Solution.**

In an isolated atom, electrons have discrete allowed energy levels. In an
emission spectrum, an electron falls from a higher level to a lower level and
emits a photon with energy

$$
hf=E_{\text{high}}-E_{\text{low}}.
$$

Only certain energy differences are allowed, so only certain photon
wavelengths are emitted. The result is bright lines on a dark background.

In an absorption spectrum, photons from continuous white light are absorbed
only if their energies match allowed upward transitions. Those wavelengths are
removed from the transmitted light, producing dark lines on a continuous
background.

Different elements have different allowed energy levels, so the pattern of
lines is characteristic of the element.

**What this example trains.** Line spectra are direct evidence for discrete
energy levels in atoms.
