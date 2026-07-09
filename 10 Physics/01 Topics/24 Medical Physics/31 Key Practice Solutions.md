---
title: Medical Physics Key Practice Solutions
subject: Physics
syllabus: 9702
parent: "[Medical Physics](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/applications
  - solutions
---

# Medical Physics Key Practice Solutions

Use these solutions to check the physical chain, unit conversions, attenuation
models, and final answers for [Key Practice Problems](30%20Key%20Practice%20Problems.md).

## A. Ultrasound

1. A piezoelectric crystal changes shape when a p.d. is applied across it. An
   alternating p.d. makes it vibrate and generate ultrasound. The reverse
   effect also occurs: returning ultrasound changes the crystal shape and
   generates an e.m.f., so the same transducer can receive echoes.

2. The echo time is a return time, so

   $$
   d=\frac{v\Delta t}{2}.
   $$

   Convert $52\ \mu\mathrm{s}=52 \times 10^{-6}\ \mathrm{s}$:

   $$
   d=\frac{(1540)(52 \times 10^{-6})}{2}
   =4.0 \times 10^{-2}\ \mathrm{m}.
   $$

   The boundary is $4.0\ \mathrm{cm}$ deep.

3. An A-scan shows echoes as spikes on a voltage-time graph; spike position
   gives depth and spike height indicates reflected intensity. A B-scan builds
   a two-dimensional image from many echo measurements, with brightness linked
   to echo strength.

4. Specific acoustic impedance is

   $$
   Z=\rho v.
   $$

   Thus

   $$
   Z=(1050)(1540)
   =1.62 \times 10^6\ \mathrm{kg\ m^{-2}\ s^{-1}}.
   $$

5. Use

   $$
   \frac{I_R}{I_0}
   =
   \left(
   \frac{Z_1-Z_2}{Z_1+Z_2}
   \right)^2.
   $$

   Hence

   $$
   \frac{I_R}{I_0}
   =
   \left(
   \frac{1.62 \times 10^6-1.48 \times 10^6}
   {1.62 \times 10^6+1.48 \times 10^6}
   \right)^2
   =2.04 \times 10^{-3}.
   $$

6. Gel removes the air gap between transducer and skin. Air and skin have a
   very large acoustic impedance mismatch, so most ultrasound would be
   reflected at an air-skin boundary. Gel has an impedance closer to skin and
   lets more ultrasound enter the body.

7. Use

   $$
   I=I_0e^{-\mu x}.
   $$

   Convert $6.0\ \mathrm{cm}=0.060\ \mathrm{m}$:

   $$
   I=5.0e^{-(25)(0.060)}
   =1.12\ \mathrm{W\ m^{-2}}.
   $$

8. Higher-frequency ultrasound has a shorter wavelength, so it can resolve
   smaller details. It is also attenuated more strongly, so it has poorer
   penetration. Lower frequency penetrates better but gives lower resolution.

## B. X-Rays and CT

9. Electrons are emitted from a heated cathode and accelerated through a large
   p.d. toward a metal target. When they hit the target and decelerate rapidly,
   some of their kinetic energy is emitted as X-ray photons. Most energy is
   transferred as thermal energy to the target.

10. The minimum wavelength is found from

    $$
    eV=\frac{hc}{\lambda_{\min}}.
    $$

    Therefore

    $$
    \lambda_{\min}=\frac{hc}{eV}
    =
    \frac{(6.63 \times 10^{-34})(3.00 \times 10^8)}
    {(1.60 \times 10^{-19})(6.0 \times 10^4)}
    =2.07 \times 10^{-11}\ \mathrm{m}.
    $$

11. Aluminium filters remove low-energy X-ray photons. These photons are likely
    to be absorbed in the patient without reaching the detector, so they add
    dose without improving the image.

12. Use

    $$
    I=I_0e^{-\mu x}.
    $$

    Since $\mu$ is in $\mathrm{cm^{-1}}$, keep $x$ in centimetres:

    $$
    I=100e^{-(0.35)(4.0)}
    =24.7\ \mathrm{W\ m^{-2}}.
    $$

13. Contrast is the difference in detector signal between different tissues or
    structures. In X-ray imaging, it mainly comes from different attenuation
    coefficients and thicknesses.

14. CT takes many X-ray measurements through the same section from different
    angles. A computer combines them to reconstruct a two-dimensional slice.
    The process is repeated along an axis, and the slices are combined to form
    a three-dimensional image.

15. A benefit is that X-ray or CT imaging can show internal structures such as
    bone or dense tissue without surgery. A risk is exposure to ionising
    radiation, which can damage tissue and increase cancer risk.

## C. PET and Method Comparison

16. A tracer is a substance containing radioactive nuclei that can be introduced
    into the body and absorbed by the tissue being studied. A beta-plus emitter
    is used because it emits positrons, which later annihilate with electrons
    to produce gamma photons for detection.

17. The positron is the antiparticle of the electron. When it meets an electron
    in tissue, annihilation occurs. Mass-energy and momentum are conserved, and
    two gamma-ray photons are produced travelling in approximately opposite
    directions.

18. Each gamma-ray photon has energy

    $$
    E_{\gamma}=m_ec^2.
    $$

    Thus

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

19. If two detectors on opposite sides of the patient detect gamma photons at
    nearly the same time, the scanner treats them as coming from the same
    annihilation event. The line joining the detectors is a line of response.

20. The radioactive tracer is absorbed by tissue according to biological
    activity. More annihilation events and detected photon pairs from a region
    indicate higher tracer concentration there. The computer reconstructs this
    distribution from many lines of response.

21. Ultrasound contrast comes mainly from reflection at boundaries with
    different acoustic impedances. X-ray contrast comes from different
    attenuation of X-rays. PET contrast comes from tracer concentration and
    uptake in tissue.

22. Foetal imaging: ultrasound, because it uses non-ionising sound waves and
    works well for soft tissue. Broken bone: X-ray or CT, because bone strongly
    attenuates X-rays and gives good contrast. Active tissue uptake: PET,
    because it images tracer concentration and function.

23. PET does not photograph the tracer directly. It detects pairs of gamma-ray
    photons produced after positron-electron annihilation in tissue and
    reconstructs tracer concentration from their arrival times.

24. Ultrasound does not use ionising radiation. X-ray and CT use ionising
    radiation from outside the body. PET uses a radioactive tracer inside the
    body and detects ionising gamma radiation, so exposure and benefit must be
    considered.
