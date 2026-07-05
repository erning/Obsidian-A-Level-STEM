---
title: Nuclear Physics Key Practice Solutions
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/23 Nuclear Physics/00 Overview|Nuclear Physics]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/modern-physics
  - solutions
---

# Nuclear Physics Key Practice Solutions

Use these solutions to check conservation, unit conversions, decay reasoning,
and final answers for [[10 Physics/01 Topics/23 Nuclear Physics/30 Key Practice Problems|Key Practice Problems]].

## A. Nuclear Equations and Binding Energy

1. $A$ is the nucleon number, the total number of protons and neutrons. $Z$ is
   the proton number. $A-Z$ is the neutron number.

2. Balance nucleon number:

   $$
   238=A+4,
   $$

   so $A=234$. Balance proton number:

   $$
   92=Z+2,
   $$

   so $Z=90$. The equation is

   $$
   {}^{238}_{92}\mathrm{U}
   \rightarrow
   {}^{234}_{90}\mathrm{Th}
   +
   {}^{4}_{2}\mathrm{He}.
   $$

3. In beta-minus decay, nucleon number is unchanged and proton number
   increases by one:

   $$
   {}^{14}_{6}\mathrm{C}
   \rightarrow
   {}^{14}_{7}\mathrm{N}
   +
   {}^{0}_{-1}e.
   $$

   Check: top numbers $14=14+0$ and bottom numbers $6=7-1$.

4. Use

   $$
   E=\Delta mc^2.
   $$

   Then

   $$
   E=(3.00 \times 10^{-29})(3.00 \times 10^8)^2
   =2.70 \times 10^{-12}\ \mathrm{J}.
   $$

   Convert to MeV:

   $$
   E=\frac{2.70 \times 10^{-12}}{1.60 \times 10^{-13}}
   =16.9\ \mathrm{MeV}.
   $$

5. Binding energy per nucleon is

   $$
   \frac{32.0}{8}=4.00\ \mathrm{MeV\ per\ nucleon}.
   $$

6. The mass of the separated nucleons is

   $$
   2m_p+2m_n
   =
   2(1.673 \times 10^{-27})+2(1.675 \times 10^{-27})
   =6.696 \times 10^{-27}\ \mathrm{kg}.
   $$

   The mass defect is

   $$
   \Delta m
   =6.696 \times 10^{-27}-6.645 \times 10^{-27}
   =5.10 \times 10^{-29}\ \mathrm{kg}.
   $$

7. The binding energy is

   $$
   E_b=\Delta mc^2
   =(5.10 \times 10^{-29})(3.00 \times 10^8)^2
   =4.59 \times 10^{-12}\ \mathrm{J}.
   $$

   In MeV,

   $$
   E_b=\frac{4.59 \times 10^{-12}}{1.60 \times 10^{-13}}
   =28.7\ \mathrm{MeV}.
   $$

   Per nucleon,

   $$
   \frac{28.7}{4}=7.17\ \mathrm{MeV\ per\ nucleon}.
   $$

8. The graph rises steeply for light nuclei, reaches a maximum near iron and
   nickel, and then decreases slowly for very heavy nuclei.

9. Light nuclei can fuse to form products with greater binding energy per
   nucleon. The products are more tightly bound, the total rest mass is lower,
   and the decrease in rest mass appears as released energy.

10. Convert the mass decrease:

    $$
    \Delta m=(0.190)(1.66 \times 10^{-27})
    =3.15 \times 10^{-28}\ \mathrm{kg}.
    $$

    The energy released is

    $$
    E=\Delta mc^2
    =(3.15 \times 10^{-28})(3.00 \times 10^8)^2
    =2.84 \times 10^{-11}\ \mathrm{J}.
    $$

    In MeV,

    $$
    E=\frac{2.84 \times 10^{-11}}{1.60 \times 10^{-13}}
    =177\ \mathrm{MeV}.
    $$

## B. Radioactive Decay

11. Count rate fluctuates because individual nuclei decay unpredictably. The
    fluctuations are evidence that decay is random rather than a sequence of
    equally spaced events.

12. Spontaneous means the decay is not triggered by external conditions such
    as temperature, pressure, or chemical state. Random means it is impossible
    to predict exactly when a particular nucleus will decay.

13. Use

    $$
    A=\lambda N.
    $$

    Then

    $$
    A=(1.5 \times 10^{-5})(4.0 \times 10^{16})
    =6.0 \times 10^{11}\ \mathrm{Bq}.
    $$

14. Use

    $$
    \lambda=\frac{0.693}{t_{1/2}}.
    $$

    With $t_{1/2}=8.0\ \mathrm{days}$,

    $$
    \lambda=\frac{0.693}{8.0}
    =8.66 \times 10^{-2}\ \mathrm{day^{-1}}.
    $$

15. Three half-lives leaves

    $$
    \left(\frac{1}{2}\right)^3=\frac{1}{8}
    $$

    of the original nuclei:

    $$
    N=(1.6 \times 10^{12})\frac{1}{8}
    =2.0 \times 10^{11}.
    $$

16. Use

    $$
    A=A_0e^{-\lambda t}.
    $$

    Then

    $$
    A=500e^{-(0.12)(10)}
    =1.51 \times 10^2\ \mathrm{Bq}.
    $$

17. The half-life is

    $$
    t_{1/2}=\frac{0.693}{0.12}
    =5.8\ \mathrm{min}.
    $$

18. Correct the initial count rate for background:

    $$
    R_0=360-40=320\ \mathrm{counts\ min^{-1}}.
    $$

    After two half-lives,

    $$
    R=320\left(\frac{1}{2}\right)^2
    =80\ \mathrm{counts\ min^{-1}}.
    $$

    Add background back to get the recorded count rate:

    $$
    R_{\text{recorded}}=80+40=120\ \mathrm{counts\ min^{-1}}.
    $$

## C. Decay Graphs and Interpretation

19. Activity decreases exponentially with time. The graph curves downward and
    approaches zero asymptotically in the ideal model.

20. Since

    $$
    A=A_0e^{-\lambda t},
    $$

    taking logarithms gives

    $$
    \ln A=\ln A_0-\lambda t.
    $$

    The gradient is $-\lambda$ and the vertical intercept is $\ln A_0$.

21. The gradient is $-\lambda$, so

    $$
    \lambda=0.025\ \mathrm{s^{-1}}.
    $$

    The half-life is

    $$
    t_{1/2}=\frac{0.693}{0.025}
    =27.7\ \mathrm{s}.
    $$

22. The corrected count rate changes from $640$ to $80$:

    $$
    \frac{80}{640}=\frac{1}{8}=\left(\frac{1}{2}\right)^3.
    $$

    So $45\ \mathrm{min}$ is three half-lives, and

    $$
    t_{1/2}=\frac{45}{3}=15\ \mathrm{min}.
    $$

23. The initial activity doubles because $A=\lambda N$ and $N$ doubles. The
    half-life is unchanged because it is a property of the isotope, not of the
    amount of material.

24. Activity is the rate of decay, measured in becquerels. Number of undecayed
    nuclei is the number of nuclei that have not yet decayed. They are related
    by $A=\lambda N$, but they are not the same quantity.
