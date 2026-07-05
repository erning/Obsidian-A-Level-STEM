---
title: Ideal Gases Key Practice Solutions
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/15 Ideal Gases/00 Overview|Ideal Gases]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/thermal-physics
  - solutions
---

# Ideal Gases Key Practice Solutions

Use these solutions to check units and model assumptions as well as numerical
answers. In gas equations, temperature must be thermodynamic temperature in
kelvin.

## A. Mole, Particles, and Constants

1. Amount of substance is an SI base quantity with base unit mole,
   $\mathrm{mol}$. One mole contains a number of elementary entities equal to
   Avogadro's constant, $N_\mathrm{A}$. Avogadro's constant is the number of
   particles per mole.

2. Number of molecules:

   $$
   N=nN_\mathrm{A}
   =(0.50)(6.02 \times 10^{23})
   =
   3.01 \times 10^{23}.
   $$

   Amount of substance:

   $$
   n=\frac{N}{N_\mathrm{A}}
   =
   \frac{1.20 \times 10^{24}}{6.02 \times 10^{23}}
   =
   1.99\ \mathrm{mol}.
   $$

3. Use $m=nM$:

   $$
   m=(2.00)(32.0)=64.0\ \mathrm{g}.
   $$

   In kilograms,

   $$
   64.0\ \mathrm{g}=0.0640\ \mathrm{kg}.
   $$

4. Use

   $$
   k=\frac{R}{N_\mathrm{A}}.
   $$

   Hence

   $$
   k=
   \frac{8.31}{6.02 \times 10^{23}}
   =
   1.38 \times 10^{-23}\ \mathrm{J\ K^{-1}}.
   $$

## B. Ideal Gas Equation

5. Convert temperature:

   $$
   T=20.0+273.15=293.15\ \mathrm{K}.
   $$

   Use $pV=nRT$:

   $$
   V=\frac{nRT}{p}
   =
   \frac{(1.00)(8.31)(293.15)}
   {1.01 \times 10^5}
   =
   2.41 \times 10^{-2}\ \mathrm{m^3}.
   $$

6. Rearrange $pV=nRT$:

   $$
   n=\frac{pV}{RT}
   =
   \frac{(2.00 \times 10^5)(1.00 \times 10^{-2})}
   {(8.31)(300)}
   =
   0.802\ \mathrm{mol}.
   $$

7. At fixed volume and fixed amount,

   $$
   \frac{p}{T}=\text{constant}.
   $$

   Convert temperatures:

   $$
   T_1=293.15\ \mathrm{K},
   \qquad
   T_2=373.15\ \mathrm{K}.
   $$

   Therefore

   $$
   p_2=p_1\frac{T_2}{T_1}
   =
   (1.00 \times 10^5)
   \frac{373.15}{293.15}
   =
   1.27 \times 10^5\ \mathrm{Pa}.
   $$

8. For a fixed mass of ideal gas,

   $$
   \frac{p_1V_1}{T_1}
   =
   \frac{p_2V_2}{T_2}.
   $$

   Hence

   $$
   p_2=
   \frac{p_1V_1T_2}{T_1V_2}
   =
   \frac{(1.50 \times 10^5)(2.0 \times 10^{-3})(450)}
   {(300)(3.0 \times 10^{-3})}
   =
   1.50 \times 10^5\ \mathrm{Pa}.
   $$

9. Use $pV=NkT$:

   $$
   N=\frac{pV}{kT}
   =
   \frac{(1.2 \times 10^5)(5.0 \times 10^{-3})}
   {(1.38 \times 10^{-23})(280)}
   =
   1.6 \times 10^{23}.
   $$

10. First find the amount of substance:

    $$
    n=\frac{m}{M}
    =
    \frac{0.120}{0.0440}
    =
    2.73\ \mathrm{mol}.
    $$

    Then use $pV=nRT$:

    $$
    p=\frac{nRT}{V}
    =
    \frac{(2.73)(8.31)(300)}
    {6.00 \times 10^{-2}}
    =
    1.13 \times 10^5\ \mathrm{Pa}.
    $$

## C. Kinetic Theory

11. The model assumes many molecules moving randomly; elastic collisions with
    each other and with the walls; negligible molecular volume compared with
    the container volume; negligible intermolecular forces except during
    collisions; and collision duration negligible compared with time between
    collisions.

12. A molecule colliding with a wall changes momentum. The wall exerts a force
    on the molecule, so by Newton's third law the molecule exerts a force on
    the wall. Many collisions per second produce a total force. Pressure is
    this force per unit area.

13. For one molecule in a cube, the impulse delivered to a wall in one elastic
    collision is proportional to $2mc_x$, and the time between collisions with
    that wall is proportional to $2l/c_x$. This gives an average force
    proportional to $mc_x^2/l$. Dividing by wall area and summing over all
    molecules gives a pressure involving $\sum c_x^2$. Random three-dimensional
    motion gives

    $$
    \langle c_x^2\rangle=\frac{1}{3}\langle c^2\rangle,
    $$

    so

    $$
    pV=\frac{1}{3}Nm\langle c^2\rangle.
    $$

14. Since $c_{\mathrm{r.m.s.}}=\sqrt{\langle c^2\rangle}$,

    $$
    \langle c^2\rangle=(500)^2=2.50 \times 10^5\ \mathrm{m^2\ s^{-2}}.
    $$

    Use

    $$
    p=\frac{1}{3}\frac{Nm\langle c^2\rangle}{V}.
    $$

    Therefore

    $$
    p=
    \frac{1}{3}
    \frac{(2.5 \times 10^{22})(4.65 \times 10^{-26})(2.50 \times 10^5)}
    {1.0 \times 10^{-3}}
    =
    9.7 \times 10^4\ \mathrm{Pa}.
    $$

15. Use

    $$
    pV=\frac{1}{3}Nm c_{\mathrm{r.m.s.}}^2.
    $$

    Hence

    $$
    c_{\mathrm{r.m.s.}}
    =
    \sqrt{\frac{3pV}{Nm}}.
    $$

    Substitute:

    $$
    c_{\mathrm{r.m.s.}}
    =
    \sqrt{
    \frac{3(1.0 \times 10^5)(2.0 \times 10^{-2})}
    {(5.0 \times 10^{23})(6.64 \times 10^{-27})}
    }
    =
    1.3 \times 10^3\ \mathrm{m\ s^{-1}}.
    $$

16. Convert temperature:

    $$
    T=27.0+273.15=300.15\ \mathrm{K}.
    $$

    Mean translational kinetic energy:

    $$
    \langle E_k\rangle
    =
    \frac{3}{2}kT
    =
    \frac{3}{2}
    (1.38 \times 10^{-23})(300.15)
    =
    6.21 \times 10^{-21}\ \mathrm{J}.
    $$

17. Mean translational kinetic energy is proportional to thermodynamic
    temperature, so it doubles. Since kinetic energy is proportional to
    $c_{\mathrm{r.m.s.}}^2$, the r.m.s. speed increases by a factor
    $\sqrt{2}$.

## D. Interpretation and Limits

18. The ideal gas equation requires thermodynamic temperature in kelvin.
    $20\ ^\circ\mathrm{C}$ is $293\ \mathrm{K}$, not $20\ \mathrm{K}$. Since
    $n=\frac{pV}{RT}$, using $20$ instead of $293$ makes the calculated $n$
    too large by a factor of about

    $$
    \frac{293}{20}=14.7.
    $$

19. At high pressure, molecules are closer together, so their own volume is no
    longer negligible compared with the container volume. At low temperature,
    molecules move more slowly and intermolecular attractions become more
    significant. The gas may then deviate from ideal behaviour or approach
    condensation.

20. Mean speed is the average of the molecular speeds, $\langle c\rangle$.
    Mean-square speed is the average of the squared speeds,
    $\langle c^2\rangle$. Root-mean-square speed is

    $$
    c_{\mathrm{r.m.s.}}=\sqrt{\langle c^2\rangle}.
    $$

    It is not generally equal to the mean speed.
