---
title: Nuclear Physics Worked Examples
subject: Physics
syllabus: 9702
parent: "[Nuclear Physics](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/modern-physics
  - worked-examples
---

# Nuclear Physics Worked Examples

These examples model the standard CAIE route through nuclear equations, mass
defect, binding energy, binding energy per nucleon, fission, fusion, activity,
half-life, and exponential decay.

## Source Route

- Syllabus: CAIE Physics 9702 section 23, Nuclear physics.
- Main subtopics: mass defect and nuclear binding energy, and radioactive
  decay.
- Coursebook route: balanced nuclear equations, mass-energy equivalence,
  binding-energy-per-nucleon graph, fission, fusion, random decay, activity,
  half-life, and decay graphs.

Use these constants unless a question gives different values:

$$
c=3.00 \times 10^8\ \mathrm{m\ s^{-1}},
$$

$$
1\ \mathrm{u}=1.66 \times 10^{-27}\ \mathrm{kg},
$$

$$
1\ \mathrm{MeV}=1.60 \times 10^{-13}\ \mathrm{J}.
$$

## Example 1: Balancing A Nuclear Equation

**Prompt.** Complete the alpha decay equation

$$
{}^{238}_{92}\mathrm{U}
\rightarrow
{}^{A}_{Z}\mathrm{Th}
+
{}^{4}_{2}\mathrm{He}.
$$

**Solution.**

Balance nucleon number:

$$
238=A+4,
$$

so

$$
A=234.
$$

Balance proton number:

$$
92=Z+2,
$$

so

$$
Z=90.
$$

The completed equation is

$$
{}^{238}_{92}\mathrm{U}
\rightarrow
{}^{234}_{90}\mathrm{Th}
+
{}^{4}_{2}\mathrm{He}.
$$

**What this example trains.** Nuclear equations are checked by conservation of
nucleon number and proton number.

## Example 2: Mass Defect and Binding Energy

**Prompt.** A helium-4 nucleus has mass
$6.645 \times 10^{-27}\ \mathrm{kg}$. Use
$m_p=1.673 \times 10^{-27}\ \mathrm{kg}$ and
$m_n=1.675 \times 10^{-27}\ \mathrm{kg}$ to find its mass defect, binding
energy, and binding energy per nucleon.

**Solution.**

A helium-4 nucleus has two protons and two neutrons. The mass of the separated
nucleons is

$$
2m_p+2m_n
=2(1.673 \times 10^{-27})+2(1.675 \times 10^{-27})
=6.696 \times 10^{-27}\ \mathrm{kg}.
$$

The mass defect is

$$
\Delta m
=6.696 \times 10^{-27}-6.645 \times 10^{-27}
=5.10 \times 10^{-29}\ \mathrm{kg}.
$$

The binding energy is

$$
E_b=\Delta m c^2
=(5.10 \times 10^{-29})(3.00 \times 10^8)^2
=4.59 \times 10^{-12}\ \mathrm{J}.
$$

In MeV,

$$
E_b=\frac{4.59 \times 10^{-12}}{1.60 \times 10^{-13}}
=28.7\ \mathrm{MeV}.
$$

The binding energy per nucleon is

$$
\frac{28.7}{4}=7.17\ \mathrm{MeV\ per\ nucleon}.
$$

**What this example trains.** Binding energy is the energy required to separate
the nucleus, not energy stored inside it waiting to be released.

## Example 3: Energy Released From A Mass Decrease

**Prompt.** In a nuclear reaction, the total rest mass decreases by
$0.190\ \mathrm{u}$. Calculate the energy released in joules and MeV.

**Solution.**

Convert the mass decrease to kilograms:

$$
\Delta m=(0.190)(1.66 \times 10^{-27})
=3.15 \times 10^{-28}\ \mathrm{kg}.
$$

The energy released is

$$
E=\Delta m c^2
=(3.15 \times 10^{-28})(3.00 \times 10^8)^2
=2.84 \times 10^{-11}\ \mathrm{J}.
$$

Convert to MeV:

$$
E=\frac{2.84 \times 10^{-11}}{1.60 \times 10^{-13}}
=177\ \mathrm{MeV}.
$$

**What this example trains.** A decrease in total rest mass corresponds to
energy released.

## Example 4: Using The Binding-Energy-Per-Nucleon Graph

**Prompt.** Explain why both fusion of light nuclei and fission of heavy nuclei
can release energy.

**Solution.**

The binding-energy-per-nucleon graph rises steeply for light nuclei, reaches a
maximum near iron and nickel, and then decreases slowly for very heavy nuclei.

Fusion of light nuclei can produce a nucleus with a larger binding energy per
nucleon. The products are more tightly bound, so the total rest mass is lower
and energy is released.

Fission of a very heavy nucleus can produce medium-mass fragments with larger
binding energy per nucleon than the original heavy nucleus. Again, the products
are more tightly bound, the total rest mass is lower, and energy is released.

**What this example trains.** Fusion and fission release energy when the
products move towards greater binding energy per nucleon.

## Example 5: Activity, Decay Constant, and Half-Life

**Prompt.** A radioactive sample contains $3.0 \times 10^{12}$ undecayed
nuclei. Its decay constant is $2.0 \times 10^{-4}\ \mathrm{s^{-1}}$. Find the
activity and half-life.

**Solution.**

Activity is

$$
A=\lambda N.
$$

Therefore

$$
A=(2.0 \times 10^{-4})(3.0 \times 10^{12})
=6.0 \times 10^8\ \mathrm{Bq}.
$$

The half-life is

$$
t_{1/2}=\frac{0.693}{\lambda}
=\frac{0.693}{2.0 \times 10^{-4}}
=3.47 \times 10^3\ \mathrm{s}.
$$

This is

$$
\frac{3.47 \times 10^3}{60}=57.8\ \mathrm{min}.
$$

**What this example trains.** Activity depends on both the decay constant and
the number of undecayed nuclei.

## Example 6: Half-Life Fraction Method

**Prompt.** A sample has initial activity $800\ \mathrm{Bq}$ and half-life
$6.0\ \mathrm{h}$. Find the activity after $18\ \mathrm{h}$.

**Solution.**

The number of half-lives is

$$
n=\frac{18}{6.0}=3.
$$

After $n$ half-lives,

$$
\frac{A}{A_0}=\left(\frac{1}{2}\right)^n.
$$

So

$$
A=800\left(\frac{1}{2}\right)^3
=100\ \mathrm{Bq}.
$$

**What this example trains.** If the time is an exact multiple of the
half-life, the fraction method is usually simpler than the exponential form.

## Example 7: Exponential Decay and Background Count

**Prompt.** A detector records $360\ \mathrm{counts\ min^{-1}}$ from a source
and background. The background count rate is
$40\ \mathrm{counts\ min^{-1}}$. After two half-lives, find the expected
recorded count rate.

**Solution.**

First subtract background:

$$
R_0=360-40=320\ \mathrm{counts\ min^{-1}}.
$$

After two half-lives, the corrected count rate is

$$
R=320\left(\frac{1}{2}\right)^2
=80\ \mathrm{counts\ min^{-1}}.
$$

The detector still records background, so add it back:

$$
R_{\text{recorded}}=80+40=120\ \mathrm{counts\ min^{-1}}.
$$

**What this example trains.** Half-life applies to the corrected count rate
from the source, not to the background count.

## Example 8: Linearising A Decay Graph

**Prompt.** A graph of $\ln R$ against time $t$ in minutes has gradient
$-0.035\ \mathrm{min^{-1}}$. Find the decay constant and half-life.

**Solution.**

For exponential decay,

$$
R=R_0e^{-\lambda t}.
$$

Taking logarithms gives

$$
\ln R=\ln R_0-\lambda t.
$$

So the gradient of a graph of $\ln R$ against $t$ is $-\lambda$. Hence

$$
\lambda=0.035\ \mathrm{min^{-1}}.
$$

The half-life is

$$
t_{1/2}=\frac{0.693}{\lambda}
=\frac{0.693}{0.035}
=19.8\ \mathrm{min}.
$$

**What this example trains.** Linearising decay data turns the decay constant
into the magnitude of the straight-line gradient.
