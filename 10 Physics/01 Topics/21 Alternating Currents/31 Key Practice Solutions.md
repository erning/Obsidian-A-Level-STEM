---
title: Alternating Currents Key Practice Solutions
subject: Physics
syllabus: 9702
parent: "[Alternating Currents](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/electricity
  - solutions
---

# Alternating Currents Key Practice Solutions

Use these solutions to check the setup, waveform reading, units, and final
answers for [Key Practice Problems](30%20Key%20Practice%20Problems.md).

## A. Sinusoidal Waveforms

1. An alternating current changes direction periodically. In this topic the
   standard model is a sinusoidal current or voltage.

2. The peak value is the maximum magnitude of the voltage. The period $T$ is
   the time for one complete cycle. The frequency $f$ is the number of cycles
   per second, so $f=1/T$.

3. Compare

   $$
   V=9.0\sin(200\pi t)
   $$

   with

   $$
   V=V_0\sin\omega t.
   $$

   Therefore

   $$
   V_0=9.0\ \mathrm{V}
   $$

   and

   $$
   \omega=200\pi\ \mathrm{rad\ s^{-1}}.
   $$

   Since $\omega=2\pi f$,

   $$
   f=\frac{200\pi}{2\pi}=100\ \mathrm{Hz}.
   $$

   Hence

   $$
   T=\frac{1}{f}=1.0 \times 10^{-2}\ \mathrm{s}.
   $$

4. Convert the time:

   $$
   1.25\ \mathrm{ms}=1.25 \times 10^{-3}\ \mathrm{s}.
   $$

   Then

   $$
   V=9.0\sin(200\pi \times 1.25 \times 10^{-3})
   =9.0\sin\left(\frac{\pi}{4}\right)
   =6.36\ \mathrm{V}.
   $$

5. The peak voltage is

   $$
   V_0=(2.5)(4.0)=10\ \mathrm{V}.
   $$

   The peak-to-peak voltage is

   $$
   V_{\text{p-p}}=2V_0=20\ \mathrm{V}.
   $$

   The period is

   $$
   T=(5.0)(2.0\ \mathrm{ms})=10\ \mathrm{ms}
   =1.0 \times 10^{-2}\ \mathrm{s}.
   $$

   Thus

   $$
   f=\frac{1}{T}=100\ \mathrm{Hz}.
   $$

6. The angular frequency is

   $$
   \omega=2\pi f=2\pi(50)=100\pi\ \mathrm{rad\ s^{-1}}.
   $$

   The current starts at zero and initially increases, so

   $$
   I=0.60\sin(100\pi t).
   $$

## B. R.M.S. Values and Power

7. The r.m.s. value of an alternating current is the steady direct current
   that would produce the same mean power in the same resistor.

8. For a sinusoidal current,

   $$
   I_{\text{r.m.s.}}=\frac{I_0}{\sqrt{2}}
   =\frac{3.0}{\sqrt{2}}
   =2.1\ \mathrm{A}.
   $$

9. For a sinusoidal voltage,

   $$
   V_{\text{r.m.s.}}=\frac{V_0}{\sqrt{2}}
   =\frac{24}{\sqrt{2}}
   =17\ \mathrm{V}.
   $$

10. The maximum instantaneous power is

    $$
    P_{\max}=I_0^2R=(2.0)^2(12)=48\ \mathrm{W}.
    $$

    For a sinusoidal current in a resistive load,

    $$
    P_{\text{mean}}=\frac{1}{2}P_{\max}=24\ \mathrm{W}.
    $$

11. The r.m.s. current is

    $$
    I_{\text{r.m.s.}}=\frac{V_{\text{r.m.s.}}}{R}
    =\frac{12}{6.0}
    =2.0\ \mathrm{A}.
    $$

    The mean power is

    $$
    P_{\text{mean}}=V_{\text{r.m.s.}}I_{\text{r.m.s.}}
    =(12)(2.0)=24\ \mathrm{W}.
    $$

12. The labelled mains value is r.m.s. For a sinusoidal voltage,

    $$
    V_0=V_{\text{r.m.s.}}\sqrt{2}
    =(230)\sqrt{2}
    =3.25 \times 10^2\ \mathrm{V}.
    $$

    So the peak voltage is about $325\ \mathrm{V}$ and the peak-to-peak
    voltage is about $650\ \mathrm{V}$.

13. The formula $P=V^2/R$ gives mean power only if $V$ is the r.m.s. voltage.
    The correct r.m.s. value is

    $$
    V_{\text{r.m.s.}}=\frac{20}{\sqrt{2}}=14.1\ \mathrm{V}.
    $$

    Thus

    $$
    P_{\text{mean}}=\frac{(14.1)^2}{10}=20\ \mathrm{W}.
    $$

    The student's $40\ \mathrm{W}$ is the maximum instantaneous power.

14. In a resistor, voltage and current reverse direction together. The product
    $VI$ is therefore positive during both half-cycles, so energy is dissipated
    as thermal energy throughout the cycle.

## C. Rectification and Smoothing

15. Rectification is the process of making current through a load pass in one
    direction only.

16. A single diode conducts during one half-cycle and blocks during the other.
    The output is a series of pulses of one polarity separated by intervals of
    zero output.

17. In a bridge rectifier, one pair of diodes conducts during one half-cycle
    and the other pair conducts during the next half-cycle. The input polarity
    reverses, but the current through the load keeps the same direction.

18. A half-wave rectifier gives one output pulse per input cycle, so the pulse
    frequency is $50\ \mathrm{Hz}$. A full-wave rectifier gives two output
    pulses per input cycle, so the pulse frequency is $100\ \mathrm{Hz}$.

19. Full-wave rectification is easier to smooth because the pulses are closer
    together. The smoothing capacitor has less time to discharge between
    peaks, so the ripple is smaller.

20. The capacitor is connected in parallel with the load. It charges quickly
    near the peaks of the rectified waveform and discharges through the load
    between peaks. This keeps the load voltage from falling immediately to
    zero.

21. Increasing the smoothing capacitance reduces ripple because the capacitor
    stores more charge for a given voltage and discharges more slowly between
    peaks.

22. Increasing the load resistance reduces ripple because the discharge
    current is smaller. The time constant $RC$ is larger, so the capacitor
    voltage falls more slowly.

23. The output is not perfectly steady because the capacitor still discharges
    through the load between charging peaks. The voltage therefore falls a
    little before the next recharge.

24. A full-wave rectified output has pulses of the same polarity in both
    half-cycles. The negative half-cycles of the input should be flipped above
    the zero line, not left below it.
