---
title: Astronomy and Cosmology Worked Examples
subject: Physics
syllabus: 9702
parent: "[Astronomy and Cosmology](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/applications
  - worked-examples
---

# Astronomy and Cosmology Worked Examples

These examples model the standard CAIE route through luminosity, radiant flux
intensity, standard candles, stellar radii, redshift, Hubble's law, and the Big
Bang model.

## Source Route

- Syllabus: CAIE Physics 9702 section 25, Astronomy and cosmology.
- Main subtopics: standard candles, stellar radii, and Hubble's law and the
  Big Bang theory.
- Coursebook route: luminosity, inverse square law, standard candles, Wien's
  displacement law, Stefan-Boltzmann law, redshift, and cosmic expansion.

Use these constants unless a question gives different values:

$$
c=3.00 \times 10^8\ \mathrm{m\ s^{-1}},
$$

$$
b=2.9 \times 10^{-3}\ \mathrm{m\ K},
$$

$$
\sigma=5.67 \times 10^{-8}\ \mathrm{W\ m^{-2}\ K^{-4}}.
$$

## Example 1: Distance From Luminosity and Flux

**Prompt.** A star has luminosity $3.8 \times 10^{28}\ \mathrm{W}$. The
radiant flux intensity measured at Earth is
$1.2 \times 10^{-10}\ \mathrm{W\ m^{-2}}$. Find the distance to the star.

**Solution.**

Use the inverse square law:

$$
F=\frac{L}{4\pi d^2}.
$$

Rearrange:

$$
d=\sqrt{\frac{L}{4\pi F}}.
$$

Substitute:

$$
d=
\sqrt{
\frac{3.8 \times 10^{28}}
{4\pi(1.2 \times 10^{-10})}
}
=5.0 \times 10^{18}\ \mathrm{m}.
$$

**What this example trains.** Luminosity is the total power emitted; radiant
flux intensity is the power per unit area received at the observer.

## Example 2: Standard Candle Distance

**Prompt.** A Type Ia supernova is treated as a standard candle with known peak
luminosity $5.0 \times 10^{36}\ \mathrm{W}$. Its measured peak radiant flux
intensity is $2.0 \times 10^{-14}\ \mathrm{W\ m^{-2}}$. Estimate its distance.

**Solution.**

A standard candle is useful because its luminosity is known independently of
its observed brightness. Use

$$
d=\sqrt{\frac{L}{4\pi F}}.
$$

Thus

$$
d=
\sqrt{
\frac{5.0 \times 10^{36}}
{4\pi(2.0 \times 10^{-14})}
}
=4.5 \times 10^{24}\ \mathrm{m}.
$$

This distance can be used as an estimate of the distance to the host galaxy.

**What this example trains.** A standard candle is not simply bright; it has a
calibrated intrinsic luminosity.

## Example 3: Temperature From Wien's Displacement Law

**Prompt.** A star has peak wavelength
$5.0 \times 10^{-7}\ \mathrm{m}$. Estimate its surface temperature.

**Solution.**

Wien's displacement law is

$$
\lambda_{\max}T=b.
$$

So

$$
T=\frac{b}{\lambda_{\max}}.
$$

Substitute:

$$
T=
\frac{2.9 \times 10^{-3}}{5.0 \times 10^{-7}}
=5.8 \times 10^3\ \mathrm{K}.
$$

**What this example trains.** Shorter peak wavelength means higher surface
temperature.

## Example 4: Stellar Radius From Luminosity and Temperature

**Prompt.** A star has luminosity $3.8 \times 10^{26}\ \mathrm{W}$ and surface
temperature $5800\ \mathrm{K}$. Estimate its radius.

**Solution.**

Use the Stefan-Boltzmann law:

$$
L=4\pi\sigma r^2T^4.
$$

Rearrange:

$$
r=\sqrt{\frac{L}{4\pi\sigma T^4}}.
$$

Substitute:

$$
r=
\sqrt{
\frac{3.8 \times 10^{26}}
{4\pi(5.67 \times 10^{-8})(5800)^4}
}
=6.9 \times 10^8\ \mathrm{m}.
$$

**What this example trains.** Luminosity depends on both emitting surface area
and temperature.

## Example 5: Redshift and Recession Speed

**Prompt.** A spectral line has laboratory wavelength $656.3\ \mathrm{nm}$.
The same line from a distant galaxy is observed at $660.0\ \mathrm{nm}$.
Estimate the recession speed of the galaxy.

**Solution.**

The wavelength increase is

$$
\Delta\lambda=660.0-656.3=3.7\ \mathrm{nm}.
$$

For small redshifts,

$$
\frac{\Delta\lambda}{\lambda}\approx\frac{v}{c}.
$$

So

$$
v\approx c\frac{\Delta\lambda}{\lambda}
=(3.00 \times 10^8)
\left(\frac{3.7}{656.3}\right)
=1.7 \times 10^6\ \mathrm{m\ s^{-1}}.
$$

The observed wavelength is longer, so the galaxy is receding.

**What this example trains.** Use the fractional wavelength change, not the
absolute wavelength change alone.

## Example 6: Hubble's Law

**Prompt.** Use $H_0=2.3 \times 10^{-18}\ \mathrm{s^{-1}}$ and the recession
speed from Example 5 to estimate the distance to the galaxy.

**Solution.**

Hubble's law is

$$
v\approx H_0d.
$$

Rearrange:

$$
d=\frac{v}{H_0}.
$$

Using $v=1.7 \times 10^6\ \mathrm{m\ s^{-1}}$,

$$
d=
\frac{1.7 \times 10^6}{2.3 \times 10^{-18}}
=7.4 \times 10^{23}\ \mathrm{m}.
$$

**What this example trains.** In this syllabus, Hubble's law calculations use
SI units, so $H_0$ is in $\mathrm{s^{-1}}$.

## Example 7: Hubble Time

**Prompt.** Use $H_0=2.3 \times 10^{-18}\ \mathrm{s^{-1}}$ to estimate the
Hubble time in seconds and years. Take
$1\ \mathrm{year}=3.16 \times 10^7\ \mathrm{s}$.

**Solution.**

The Hubble time is approximately

$$
t\sim\frac{1}{H_0}.
$$

So

$$
t\sim
\frac{1}{2.3 \times 10^{-18}}
=4.35 \times 10^{17}\ \mathrm{s}.
$$

In years,

$$
t=
\frac{4.35 \times 10^{17}}{3.16 \times 10^7}
=1.38 \times 10^{10}\ \mathrm{years}.
$$

This is an order-of-magnitude estimate, not an exact age calculation.

**What this example trains.** Hubble's law leads to a timescale by reversing
the present expansion rate.

## Example 8: Redshift and the Big Bang Model

**Prompt.** Explain how redshift and Hubble's law support the Big Bang model.

**Solution.**

Spectral lines from distant galaxies are observed at longer wavelengths than
their known laboratory values. This redshift indicates that the galaxies are
receding from us.

Hubble's law shows that more distant galaxies have greater recession speeds:

$$
v\approx H_0d.
$$

This pattern is interpreted as expansion of space, not as all galaxies moving
away from Earth through a fixed space. If the expansion is traced backwards,
galaxies were closer together in the past. This leads to the Big Bang model:
the Universe evolved from a much hotter, denser early state and has expanded
since then.

**What this example trains.** Hubble's law supports an expanding Universe; it
does not place Earth at the centre.
