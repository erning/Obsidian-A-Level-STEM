---
title: Particle Physics Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/11 Particle Physics/00 Overview|Particle Physics]]"
status: draft
tags:
  - physics/9702/topic
  - physics/9702/modern-physics
  - lecture-notes
---

# Particle Physics Lecture Notes

Particle physics begins with a change in scale. Instead of treating matter as continuous, we ask what atoms, nuclei, and subatomic particles are made of, and what evidence supports those models. The main tools in this topic are scattering evidence, nuclear equations, and conservation laws.

There is not much algebra compared with mechanics or circuits. The skill is careful bookkeeping: nucleon number, proton number, charge, particle type, and energy must all make sense before and after a nuclear process.

## Source Route

- Primary syllabus source: CAIE Physics 9702, Topic 11 Particle physics.
- Main subtopics: atoms, nuclei and radiation; fundamental particles.
- Coursebook route: atomic structure, radioactive radiation, radioactive decay equations, antiparticles, neutrinos, leptons, hadrons, and quarks.
- Useful earlier knowledge: charge, electric force, conservation of energy, electromagnetic radiation, and scientific models.

## Visual Guide

![[assets/generated/physics/particle-physics.svg]]

The visual guide is a classification map. Use it to keep the levels separate: atoms contain nuclei and electrons; nuclei contain protons and neutrons; protons and neutrons are hadrons made from quarks.

## 1. Evidence from Alpha-Particle Scattering

Rutherford's alpha-particle scattering experiment tested the structure of the atom. A narrow beam of fast $\alpha$-particles was directed at very thin gold foil. A detector screen counted where the scattered $\alpha$-particles went.

The observations were:

- Most $\alpha$-particles passed straight through the foil.
- Some $\alpha$-particles were deflected through small angles.
- A very small fraction were deflected through angles greater than $90^\circ$, and a few were back-scattered.

These observations did not fit the old plum pudding model, in which positive charge was spread through the atom with electrons embedded in it.

The conclusions were:

- Most of the atom is empty space, because most $\alpha$-particles pass through with little or no deflection.
- The atom has a small, positively charged nucleus, because positively charged $\alpha$-particles are repelled when they pass close to it.
- Most of the mass of the atom is concentrated in this nucleus, because a few $\alpha$-particles can be scattered through very large angles or backwards.
- The nucleus is tiny compared with the atom, because only a very small fraction of $\alpha$-particles pass close enough to be strongly deflected.

The force involved is electrostatic repulsion between the positive $\alpha$-particle and the positive nucleus. The closer the $\alpha$-particle passes to the nucleus, the larger the repulsive force and the larger the deflection.

The experiment needed very thin foil because the aim was to study scattering by atoms, not absorption by a thick material. It also needed a vacuum because $\alpha$-radiation is absorbed by a few centimetres of air.

## 2. The Nuclear Model of the Atom

The nuclear model of the atom says:

- The atom has a tiny central nucleus.
- The nucleus contains protons and neutrons.
- Protons are positively charged.
- Neutrons have no charge.
- Electrons surround the nucleus.
- Most of the atom is empty space.

Typical scales are very different:

- atomic radius is about $10^{-10}\ \text{m}$
- nuclear radius is about $10^{-15}\ \text{m}$ to $10^{-14}\ \text{m}$

This means the nucleus is about $10^4$ to $10^5$ times smaller in radius than the atom. The volume difference is even more extreme.

The nucleus is held together despite electrostatic repulsion between protons. This requires a short-range attractive interaction between nucleons, called the strong nuclear force. The detailed treatment of nuclear stability belongs later, but the idea helps explain why nuclei can exist at all.

## 3. Protons, Neutrons, Electrons, and Nucleons

Protons and neutrons are collectively called nucleons.

Key particle properties:

| Particle | Relative mass | Charge |
| --- | ---: | ---: |
| proton | about $1$ | $+e$ |
| neutron | about $1$ | $0$ |
| electron | about $\frac{1}{1840}$ | $-e$ |
| $\alpha$-particle | about $4$ | $+2e$ |

The elementary charge is

$$
e = 1.60 \times 10^{-19}\ \text{C}
$$

The nucleon number, $A$, is the total number of protons and neutrons in a nucleus:

$$
A = Z + N
$$

where:

- $Z$ is the proton number
- $N$ is the neutron number

The proton number, $Z$, is the number of protons in the nucleus. It determines the element. For a neutral atom, the number of electrons is also $Z$.

The unified atomic mass unit, $\text{u}$, is used for atomic and nuclear masses. It is defined as one twelfth of the mass of a carbon-12 atom:

$$
1\ \text{u} = \frac{1}{12}\text{ mass of one }{}^{12}_{6}\text{C atom}
$$

Numerically,

$$
1\ \text{u} \approx 1.66 \times 10^{-27}\ \text{kg}
$$

## 4. Nuclide Notation and Isotopes

A nuclide is a particular nucleus with a particular number of protons and neutrons. Nuclides are written using

$$
{}^{A}_{Z}X
$$

where:

- $X$ is the chemical symbol
- $A$ is nucleon number
- $Z$ is proton number

For example,

$$
{}^{238}_{92}\text{U}
$$

has $92$ protons and $238$ nucleons. The number of neutrons is

$$
N = A - Z = 238 - 92 = 146
$$

Isotopes are nuclei of the same element with the same number of protons but different numbers of neutrons.

For example,

$$
{}^{12}_{6}\text{C}
\quad\text{and}\quad
{}^{14}_{6}\text{C}
$$

are isotopes of carbon. They both have $Z = 6$, so they are carbon. They have different nucleon numbers, so they have different numbers of neutrons.

Isotopes of the same element have the same chemical properties in the simple atomic model because they have the same number of electrons when neutral. Their nuclear properties can differ greatly because their nuclei contain different numbers of neutrons.

## 5. Alpha, Beta, and Gamma Radiation

Radioactive substances emit radiation from unstable nuclei. The main types here are $\alpha$, $\beta$, and $\gamma$ radiation.

| Radiation | Nature | Relative mass | Charge |
| --- | --- | ---: | ---: |
| $\alpha$ | helium nucleus, two protons and two neutrons | about $4$ | $+2e$ |
| $\beta^-$ | electron | about $\frac{1}{1840}$ | $-e$ |
| $\beta^+$ | positron | about $\frac{1}{1840}$ | $+e$ |
| $\gamma$ | high-frequency electromagnetic photon | $0$ | $0$ |

Alpha radiation is strongly ionising and weakly penetrating. It is stopped by paper or a few centimetres of air. This is because an $\alpha$-particle is massive and has charge $+2e$, so it interacts strongly with atoms it passes.

Beta radiation is less strongly ionising and more penetrating than alpha radiation. A $\beta$-particle is much lighter and has charge of magnitude $e$.

Gamma radiation is weakly ionising and highly penetrating. A $\gamma$-ray is a photon, so it has no charge and no rest mass. It is electromagnetic radiation emitted by an excited nucleus, often after $\alpha$ or $\beta$ decay.

## 6. Nuclear Decay Equations

In nuclear decay equations, nucleon number and charge are conserved. This is the main bookkeeping rule.

### Alpha Decay

An $\alpha$-particle is a helium nucleus:

$$
{}^{4}_{2}\alpha
\quad\text{or}\quad
{}^{4}_{2}\text{He}
$$

In alpha decay:

$$
{}^{A}_{Z}X
\to
{}^{A-4}_{Z-2}Y
+ {}^{4}_{2}\alpha
$$

The daughter nucleus has nucleon number $A - 4$ and proton number $Z - 2$.

Example:

$$
{}^{238}_{92}\text{U}
\to
{}^{234}_{90}\text{Th}
+ {}^{4}_{2}\alpha
$$

Check:

$$
238 = 234 + 4
$$

and

$$
92 = 90 + 2
$$

### Beta Minus Decay

In $\beta^-$ decay, a neutron in the nucleus changes into a proton. An electron and an electron antineutrino are emitted:

$$
n \to p + \beta^- + \bar{\nu}_e
$$

For the nucleus:

$$
{}^{A}_{Z}X
\to
{}^{A}_{Z+1}Y
+ {}^{0}_{-1}\beta^-
+ \bar{\nu}_e
$$

The nucleon number stays the same. The proton number increases by $1$.

The electron is written with proton number $-1$ in the nuclear equation so that charge is conserved.

### Beta Plus Decay

In $\beta^+$ decay, a proton in the nucleus changes into a neutron. A positron and an electron neutrino are emitted:

$$
p \to n + \beta^+ + \nu_e
$$

For the nucleus:

$$
{}^{A}_{Z}X
\to
{}^{A}_{Z-1}Y
+ {}^{0}_{+1}\beta^+
+ \nu_e
$$

The nucleon number stays the same. The proton number decreases by $1$.

### Gamma Emission

In $\gamma$ emission, the nucleus loses energy but its nucleon number and proton number do not change:

$$
{}^{A}_{Z}X^*
\to
{}^{A}_{Z}X
+ \gamma
$$

The star means the nucleus is in an excited state.

## 7. Antiparticles, Positrons, and Neutrinos

An antiparticle has the same mass as its corresponding particle but opposite charge. The positron is the antiparticle of the electron.

Electron:

$$
e^- \quad \text{charge } -e
$$

Positron:

$$
e^+ \quad \text{charge } +e
$$

When a particle meets its antiparticle, annihilation can occur. For example, an electron and a positron can annihilate to produce gamma photons.

Neutrinos are needed in beta decay. In $\beta^-$ decay, an electron antineutrino is emitted:

$$
\bar{\nu}_e
$$

In $\beta^+$ decay, an electron neutrino is emitted:

$$
\nu_e
$$

Beta particles have a continuous range of energies. This shows that the beta particle does not always take the same amount of energy from the decay. The neutrino or antineutrino carries away some of the energy, so the emitted beta particle can have a range of kinetic energies.

Alpha particles from a particular alpha decay have discrete energies because the decay products are fixed and the energy is shared in a fixed way between the daughter nucleus and the alpha particle.

## 8. Fundamental Particles, Leptons, and Hadrons

A fundamental particle is one that is not known to be made from smaller particles.

In this topic, electrons and neutrinos are leptons. Leptons are fundamental particles and are not affected by the strong nuclear force.

Protons and neutrons are hadrons. Hadrons are affected by the strong nuclear force and are made from quarks. Therefore protons and neutrons are not fundamental particles.

The two hadron groups needed here are:

- baryons: made from three quarks
- mesons: made from one quark and one antiquark

Examples:

$$
\text{proton} = uud
$$

$$
\text{neutron} = udd
$$

The proton and neutron are baryons because each contains three quarks.

## 9. Quarks and Antiquarks

There are six quark flavours:

| Quark flavour | Symbol | Charge |
| --- | --- | ---: |
| up | $u$ | $+\frac{2}{3}e$ |
| down | $d$ | $-\frac{1}{3}e$ |
| strange | $s$ | $-\frac{1}{3}e$ |
| charm | $c$ | $+\frac{2}{3}e$ |
| top | $t$ | $+\frac{2}{3}e$ |
| bottom | $b$ | $-\frac{1}{3}e$ |

Each quark has a corresponding antiquark with the opposite charge.

For example:

$$
\bar{u} \text{ has charge } -\frac{2}{3}e
$$

and

$$
\bar{d} \text{ has charge } +\frac{1}{3}e
$$

Use quark charges to check hadron charge.

For a proton:

$$
uud:
\quad
+\frac{2}{3}e + \frac{2}{3}e - \frac{1}{3}e = +e
$$

For a neutron:

$$
udd:
\quad
+\frac{2}{3}e - \frac{1}{3}e - \frac{1}{3}e = 0
$$

A meson contains a quark and an antiquark. For example, a positive pion can be represented as

$$
\pi^+ = u\bar{d}
$$

Its charge is

$$
+\frac{2}{3}e + \frac{1}{3}e = +e
$$

## 10. Beta Decay at the Quark Level

Beta decay can be described as a change inside a nucleon.

In $\beta^-$ decay, a neutron changes into a proton. At quark level, one down quark changes into an up quark:

$$
d \to u + \beta^- + \bar{\nu}_e
$$

This changes

$$
udd \to uud
$$

so

$$
n \to p + \beta^- + \bar{\nu}_e
$$

In $\beta^+$ decay, a proton changes into a neutron. At quark level, one up quark changes into a down quark:

$$
u \to d + \beta^+ + \nu_e
$$

This changes

$$
uud \to udd
$$

so

$$
p \to n + \beta^+ + \nu_e
$$

This is caused by the weak interaction. The strong nuclear force holds nucleons together and affects hadrons, but beta decay is a weak interaction process.

## 11. Working Routine

Use this routine for particle physics questions:

1. Identify the level: atom, nucleus, nucleon, quark, lepton, or radiation.
2. For nuclide questions, write $A$, $Z$, and $N = A - Z$.
3. For decay equations, conserve nucleon number and charge.
4. Include $\bar{\nu}_e$ in $\beta^-$ decay and $\nu_e$ in $\beta^+$ decay.
5. For particle classification, decide whether the particle is a lepton or hadron.
6. If it is a hadron, decide whether it is a baryon or meson.
7. Use quark charges to check the charge of the hadron.
8. In beta decay, connect the nuclear change to the quark change.

## Common Traps

- Confusing nucleon number $A$ with proton number $Z$.
- Calling isotopes atoms with different numbers of protons. Isotopes have the same number of protons but different numbers of neutrons.
- Forgetting that a neutral atom has the same number of electrons as protons.
- Treating $\gamma$ radiation as a particle with charge. It is a photon with no charge and no rest mass.
- Forgetting the neutrino or antineutrino in beta decay.
- Saying mass alone is conserved in nuclear decay. Mass-energy is conserved.
- Treating protons and neutrons as fundamental particles. They are hadrons made of quarks.
- Giving antiquarks the same charge as quarks. Antiquarks have the opposite charge.

## Quick Self-Check

You should be able to answer these without looking back:

- How did alpha-particle scattering show that atoms have small nuclei?
- What is the difference between nucleon number and proton number?
- How do you find the number of neutrons in ${}^{A}_{Z}X$?
- What changes in alpha decay, beta minus decay, beta plus decay, and gamma emission?
- Which neutrino or antineutrino is emitted in each type of beta decay?
- Why do beta particles have a continuous energy spectrum?
- What is the difference between a lepton and a hadron?
- What quarks make up a proton and a neutron?
- How does quark composition change in beta minus and beta plus decay?

## Connections

- [[10 Physics/01 Topics/22 Quantum Physics/00 Overview|Quantum Physics]] uses photons and particle behaviour at small scales.
- [[10 Physics/01 Topics/23 Nuclear Physics/00 Overview|Nuclear Physics]] develops decay, binding energy, mass defect, and nuclear reactions in more detail.
- [[10 Physics/01 Topics/20 Magnetic Fields/00 Overview|Magnetic Fields]] explains how charged particles are deflected in fields.
