---
title: Medical Physics Worked Examples
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/24 Medical Physics/00 Overview|Medical Physics]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/applications
  - worked-examples
---

# Medical Physics Worked Examples

These examples model the standard CAIE route through ultrasound imaging,
X-ray imaging, CT scanning, and PET scanning.

## Source Route

- Syllabus: CAIE Physics 9702 section 24, Medical physics.
- Main subtopics: production and use of ultrasound, production and use of
  X-rays, and PET scanning.
- Coursebook route: piezoelectric transducers, acoustic impedance, attenuation,
  X-ray tubes, CT reconstruction, radioactive tracers, positron annihilation,
  and detector timing.

Use these constants unless a question gives different values:

$$
h=6.63 \times 10^{-34}\ \mathrm{J\ s},\quad
c=3.00 \times 10^8\ \mathrm{m\ s^{-1}},\quad
e=1.60 \times 10^{-19}\ \mathrm{C}.
$$

## Example 1: Ultrasound Echo Depth

**Prompt.** An ultrasound pulse travels through soft tissue at
$1540\ \mathrm{m\ s^{-1}}$. An echo from a boundary returns
$78\ \mu\mathrm{s}$ after the pulse is sent. Find the depth of the boundary.

**Solution.**

The pulse travels to the boundary and back, so

$$
d=\frac{v\Delta t}{2}.
$$

Convert the time:

$$
78\ \mu\mathrm{s}=78 \times 10^{-6}\ \mathrm{s}.
$$

Then

$$
d=\frac{(1540)(78 \times 10^{-6})}{2}
=6.0 \times 10^{-2}\ \mathrm{m}.
$$

The boundary is about $6.0\ \mathrm{cm}$ below the surface.

**What this example trains.** Echo timing uses a return time, so the factor of
2 is essential.

## Example 2: Acoustic Impedance and Reflection

**Prompt.** At normal incidence, ultrasound meets a boundary between two soft
tissues with acoustic impedances
$Z_1=1.62 \times 10^6\ \mathrm{kg\ m^{-2}\ s^{-1}}$ and
$Z_2=1.48 \times 10^6\ \mathrm{kg\ m^{-2}\ s^{-1}}$. Find the fraction of
the incident intensity reflected.

**Solution.**

The intensity reflection coefficient is

$$
\frac{I_R}{I_0}
=
\left(
\frac{Z_1-Z_2}{Z_1+Z_2}
\right)^2.
$$

Substitute:

$$
\frac{I_R}{I_0}
=
\left(
\frac{1.62 \times 10^6-1.48 \times 10^6}
{1.62 \times 10^6+1.48 \times 10^6}
\right)^2.
$$

Thus

$$
\frac{I_R}{I_0}
=2.04 \times 10^{-3}.
$$

Only about $0.20\%$ of the incident intensity is reflected. Similar acoustic
impedances give weak reflection.

**What this example trains.** Reflection depends on impedance mismatch, not
just on tissue density.

## Example 3: Why Ultrasound Gel Is Needed

**Prompt.** Explain why gel is placed between the ultrasound transducer and
skin.

**Solution.**

Air and skin have very different acoustic impedances. At an air-skin boundary,
the reflection coefficient is close to 1, so almost all ultrasound would be
reflected before entering the body.

Gel removes the air gap and has an acoustic impedance much closer to that of
skin. This reduces reflection at the surface, allowing more ultrasound to enter
the body and return useful echoes from internal boundaries.

**What this example trains.** Coupling gel is not mainly for comfort; it solves
an impedance-mismatch problem.

## Example 4: Ultrasound Attenuation

**Prompt.** Ultrasound of initial intensity $12\ \mathrm{W\ m^{-2}}$ travels
$4.0\ \mathrm{cm}$ through tissue with attenuation coefficient
$35\ \mathrm{m^{-1}}$. Find the intensity after this distance.

**Solution.**

Use

$$
I=I_0e^{-\mu x}.
$$

Convert the distance:

$$
4.0\ \mathrm{cm}=0.040\ \mathrm{m}.
$$

Then

$$
I=12e^{-(35)(0.040)}
=12e^{-1.40}
=2.96\ \mathrm{W\ m^{-2}}.
$$

**What this example trains.** The units of $\mu$ and $x$ must match so that
$\mu x$ is dimensionless.

## Example 5: Minimum X-Ray Wavelength

**Prompt.** Electrons in an X-ray tube are accelerated through
$80\ \mathrm{kV}$. Calculate the minimum wavelength of the X-rays produced.

**Solution.**

The maximum photon energy occurs if all the electron kinetic energy becomes
one photon:

$$
eV=\frac{hc}{\lambda_{\min}}.
$$

So

$$
\lambda_{\min}=\frac{hc}{eV}.
$$

Substitute $V=8.0 \times 10^4\ \mathrm{V}$:

$$
\lambda_{\min}
=
\frac{(6.63 \times 10^{-34})(3.00 \times 10^8)}
{(1.60 \times 10^{-19})(8.0 \times 10^4)}
=1.55 \times 10^{-11}\ \mathrm{m}.
$$

**What this example trains.** Higher accelerating p.d. gives greater maximum
photon energy and therefore a smaller minimum wavelength.

## Example 6: X-Ray Attenuation and Contrast

**Prompt.** X-rays pass through $2.0\ \mathrm{cm}$ of soft tissue with
$\mu=0.20\ \mathrm{cm^{-1}}$ and through $2.0\ \mathrm{cm}$ of bone with
$\mu=0.80\ \mathrm{cm^{-1}}$. Find $I/I_0$ for each and explain the image
contrast.

**Solution.**

Use

$$
\frac{I}{I_0}=e^{-\mu x}.
$$

For soft tissue,

$$
\frac{I}{I_0}=e^{-(0.20)(2.0)}
=e^{-0.40}
=0.670.
$$

For bone,

$$
\frac{I}{I_0}=e^{-(0.80)(2.0)}
=e^{-1.60}
=0.202.
$$

Less X-ray intensity reaches the detector behind bone, so bone gives a
different detector signal from soft tissue. That difference is contrast.

**What this example trains.** X-ray contrast comes from different attenuation
coefficients and thicknesses.

## Example 7: CT Compared With A Single X-Ray Image

**Prompt.** Explain why CT scanning gives more depth information than a single
X-ray image.

**Solution.**

A single X-ray image is a shadow image. Structures at different depths are
superimposed on the same detector, so a dense object in front of another
structure can obscure it.

In CT, many X-ray measurements are taken from different angles through the same
section. A computer combines these measurements to reconstruct a two-dimensional
slice. The process is repeated along an axis, and the slices are combined to
form a three-dimensional image.

CT still uses ionising radiation, so the extra information has to be weighed
against dose.

**What this example trains.** CT is reconstruction from many projections, not
just a sharper single X-ray photograph.

## Example 8: PET Photon Energy and Reconstruction

**Prompt.** In PET scanning, a positron annihilates with an electron. Calculate
the energy of each gamma-ray photon using
$m_e=9.11 \times 10^{-31}\ \mathrm{kg}$. Then explain how the scanner uses the
photons.

**Solution.**

When the electron-positron pair annihilates and the initial kinetic energy is
small, two gamma-ray photons are produced. Each photon has energy

$$
E_{\gamma}=m_ec^2.
$$

Therefore

$$
E_{\gamma}
=(9.11 \times 10^{-31})(3.00 \times 10^8)^2
=8.20 \times 10^{-14}\ \mathrm{J}.
$$

In electronvolts,

$$
E_{\gamma}
=\frac{8.20 \times 10^{-14}}{1.60 \times 10^{-19}}
=5.12 \times 10^5\ \mathrm{eV}
=512\ \mathrm{keV}.
$$

The two photons travel in approximately opposite directions. Detectors around
the patient record pairs of photons arriving at nearly the same time. The line
joining the two detectors is a line of response, and many such lines are
processed to reconstruct tracer concentration in the tissue.

**What this example trains.** PET images tracer distribution by coincidence
detection of gamma photons, not by taking an ordinary photograph.
