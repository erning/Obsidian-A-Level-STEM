---
title: Capacitance Key Practice Solutions
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/19 Capacitance/00 Overview|Capacitance]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/electricity
  - solutions
---

# Capacitance Key Practice Solutions

Use these solutions to check combination rules and unit conversions. In series,
capacitors have the same charge; in parallel, they have the same p.d.

## A. Capacitance and Networks

1. Capacitance is charge stored per unit potential difference:

   $$
   C=\frac{Q}{V}.
   $$

   One farad is

   $$
   1\ \mathrm{F}=1\ \mathrm{C\ V^{-1}}.
   $$

2. Use $Q=CV$:

   $$
   Q=(100 \times 10^{-6})(6.0)
   =
   6.0 \times 10^{-4}\ \mathrm{C}.
   $$

3. Use

   $$
   C=\frac{Q}{V}
   =
   \frac{3.6 \times 10^{-3}}{12}
   =
   3.0 \times 10^{-4}\ \mathrm{F}.
   $$

   In microfarads,

   $$
   C=300\ \mu\mathrm{F}.
   $$

4. For parallel capacitors,

   $$
   C_{\text{total}}=2.0+3.0+5.0=10.0\ \mu\mathrm{F}.
   $$

5. For series capacitors,

   $$
   \frac{1}{C_{\text{total}}}
   =
   \frac{1}{2.0}+\frac{1}{3.0}
   =
   0.833\ \mu\mathrm{F}^{-1}.
   $$

   Hence

   $$
   C_{\text{total}}=1.2\ \mu\mathrm{F}.
   $$

6. Parallel group:

   $$
   C_p=6.0+3.0=9.0\ \mu\mathrm{F}.
   $$

   Then series with $2.0\ \mu\mathrm{F}$:

   $$
   \frac{1}{C_{\text{total}}}
   =
   \frac{1}{9.0}+\frac{1}{2.0}
   =
   0.611\ \mu\mathrm{F}^{-1}.
   $$

   So

   $$
   C_{\text{total}}=1.64\ \mu\mathrm{F}.
   $$

7. Series equivalent capacitance:

   $$
   C_{\text{total}}
   =
   \frac{(4.0)(8.0)}{4.0+8.0}
   =
   2.67\ \mu\mathrm{F}.
   $$

   Charge on each capacitor:

   $$
   Q=C_{\text{total}}V
   =
   (2.67 \times 10^{-6})(12)
   =
   3.2 \times 10^{-5}\ \mathrm{C}.
   $$

   Voltages:

   $$
   V_{4\mu\mathrm{F}}
   =
   \frac{3.2 \times 10^{-5}}{4.0 \times 10^{-6}}
   =
   8.0\ \mathrm{V},
   $$

   $$
   V_{8\mu\mathrm{F}}
   =
   \frac{3.2 \times 10^{-5}}{8.0 \times 10^{-6}}
   =
   4.0\ \mathrm{V}.
   $$

## B. Energy Stored

8. Use

   $$
   W=\frac{1}{2}CV^2.
   $$

   Hence

   $$
   W=
   \frac{1}{2}(220 \times 10^{-6})(15)^2
   =
   2.48 \times 10^{-2}\ \mathrm{J}.
   $$

9. Use

   $$
   W=\frac{1}{2}QV
   =
   \frac{1}{2}(2.0 \times 10^{-3})(50)
   =
   5.0 \times 10^{-2}\ \mathrm{J}.
   $$

10. The area under the straight-line $V$-$Q$ graph is triangular:

    $$
    W=\frac{1}{2}QV
    =
    \frac{1}{2}(5.0 \times 10^{-3})(80)
    =
    0.20\ \mathrm{J}.
    $$

    This is the energy stored in the capacitor.

11. Stored energy is

    $$
    W=\frac{1}{2}CV^2.
    $$

    If $V$ doubles and $C$ stays constant, $W$ increases by a factor of
    $2^2=4$.

12. Initial stored energy:

    $$
    W=\frac{1}{2}CV^2
    =
    \frac{1}{2}(10 \times 10^{-6})(20)^2
    =
    2.0 \times 10^{-3}\ \mathrm{J}.
    $$

    This energy is transferred out of the capacitor during complete discharge.

## C. Discharge Through a Resistor

13. Time constant:

    $$
    \tau=RC
    =
    (2.0 \times 10^3)(470 \times 10^{-6})
    =
    0.94\ \mathrm{s}.
    $$

14. Use

    $$
    V=V_0e^{-t/RC}.
    $$

    Here $t/RC=6.0/3.0=2.0$, so

    $$
    V=9.0e^{-2}=1.22\ \mathrm{V}.
    $$

15. After one time constant,

    $$
    Q=Q_0e^{-1}=0.37Q_0
    =
    7.4 \times 10^{-4}\ \mathrm{C}.
    $$

    After $8.0\ \mathrm{s}$, $t/RC=8.0/4.0=2.0$, so

    $$
    Q=(2.0 \times 10^{-3})e^{-2}
    =
    2.7 \times 10^{-4}\ \mathrm{C}.
    $$

16. Initial current magnitude:

    $$
    I_0=\frac{V_0}{R}
    =
    \frac{12}{4.0 \times 10^3}
    =
    3.0 \times 10^{-3}\ \mathrm{A}.
    $$

17. For a graph of $\ln V$ against $t$, gradient is $-\frac{1}{RC}$. Hence

    $$
    RC=\frac{1}{0.50}=2.0\ \mathrm{s}.
    $$

## D. Graphs and Interpretation

18. During discharge, $Q$ against $t$, $V$ against $t$, and current magnitude
    against $t$ are all exponential decays with the same time constant. They
    approach zero gradually rather than reaching zero suddenly.

19. As the capacitor discharges, the charge on the plates decreases, so the
    p.d. across the capacitor decreases. The current through the resistor is
    linked to this p.d. by $I=V/R$, so the current decreases with time.

20. After one time constant,

    $$
    x=x_0e^{-1}\approx 0.37x_0.
    $$

    The capacitor still has about $37\%$ of its initial charge and p.d.; it is
    not fully discharged.
