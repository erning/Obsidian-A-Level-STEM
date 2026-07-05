---
title: Capacitance Worked Examples
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/19 Capacitance/00 Overview|Capacitance]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/electricity
  - worked-examples
---

# Capacitance Worked Examples

These examples model the standard CAIE route through $C=Q/V$, capacitor
networks, stored energy, $V$-$Q$ graph area, discharge time constant, and
exponential decay.

## Source Route

- Syllabus: CAIE Physics 9702 section 19, Capacitance.
- Main subtopics: capacitors and capacitance, energy stored in a capacitor,
  and capacitor discharge through a resistor.
- Coursebook route: charge storage, series and parallel combinations, stored
  energy, discharge graphs, time constant, and logarithmic analysis.

## Example 1: Charge Stored

**Prompt.** A $220\ \mu\mathrm{F}$ capacitor is connected across a
$9.0\ \mathrm{V}$ supply. Find the charge stored.

**Solution.**

Capacitance is

$$
C=\frac{Q}{V}.
$$

So

$$
Q=CV.
$$

Convert capacitance:

$$
220\ \mu\mathrm{F}=220 \times 10^{-6}\ \mathrm{F}.
$$

Therefore

$$
Q=(220 \times 10^{-6})(9.0)
=1.98 \times 10^{-3}\ \mathrm{C}.
$$

The charge stored means the magnitude of charge on either plate.

**What this example trains.** A capacitor with plates $+Q$ and $-Q$ has zero
net charge, but stored charge is the magnitude $Q$ on either plate.

## Example 2: Series and Parallel Combination

**Prompt.** A $4.0\ \mu\mathrm{F}$ capacitor and a $6.0\ \mu\mathrm{F}$
capacitor are connected in parallel. This parallel group is then connected in
series with a $5.0\ \mu\mathrm{F}$ capacitor. Find the equivalent capacitance.

**Solution.**

For the parallel group,

$$
C_p=4.0+6.0=10.0\ \mu\mathrm{F}.
$$

This is in series with $5.0\ \mu\mathrm{F}$, so

$$
\frac{1}{C_{\text{total}}}
=
\frac{1}{10.0}
+
\frac{1}{5.0}.
$$

Thus

$$
\frac{1}{C_{\text{total}}}=0.300\ \mu\mathrm{F}^{-1},
$$

and

$$
C_{\text{total}}=3.33\ \mu\mathrm{F}.
$$

**What this example trains.** Capacitor combination rules are opposite in
pattern to resistor rules.

## Example 3: Series Capacitor Voltages

**Prompt.** Capacitors $3.0\ \mu\mathrm{F}$ and $6.0\ \mu\mathrm{F}$ are in
series across $12\ \mathrm{V}$. Find the charge on each capacitor and the
potential difference across each.

**Solution.**

For series capacitors,

$$
\frac{1}{C_{\text{total}}}
=
\frac{1}{3.0}
+
\frac{1}{6.0}
=0.500\ \mu\mathrm{F}^{-1}.
$$

So

$$
C_{\text{total}}=2.0\ \mu\mathrm{F}.
$$

The same charge is stored on each series capacitor:

$$
Q=C_{\text{total}}V
=(2.0 \times 10^{-6})(12)
=2.4 \times 10^{-5}\ \mathrm{C}.
$$

Voltages:

$$
V_1=\frac{Q}{C_1}
=\frac{2.4 \times 10^{-5}}{3.0 \times 10^{-6}}
=8.0\ \mathrm{V},
$$

$$
V_2=\frac{Q}{C_2}
=\frac{2.4 \times 10^{-5}}{6.0 \times 10^{-6}}
=4.0\ \mathrm{V}.
$$

The voltages add to $12\ \mathrm{V}$.

**What this example trains.** Series capacitors have the same charge, not the
same voltage.

## Example 4: Energy Stored in a Capacitor

**Prompt.** A $470\ \mu\mathrm{F}$ capacitor is charged to $12\ \mathrm{V}$.
Find the stored energy.

**Solution.**

Use

$$
W=\frac{1}{2}CV^2.
$$

So

$$
W=
\frac{1}{2}(470 \times 10^{-6})(12)^2
=3.38 \times 10^{-2}\ \mathrm{J}.
$$

Doubling the voltage would quadruple the stored energy, because energy depends
on $V^2$.

**What this example trains.** The factor $\frac{1}{2}$ and the square on $V$
are both essential.

## Example 5: Energy from a $V$-$Q$ Graph

**Prompt.** During charging, a capacitor reaches charge
$4.0 \times 10^{-3}\ \mathrm{C}$ at potential difference $200\ \mathrm{V}$.
Find the energy stored using the area under a $V$ against $Q$ graph.

**Solution.**

For a capacitor, the $V$-$Q$ graph is a straight line through the origin. The
area under the graph is a triangle:

$$
W=\frac{1}{2}QV.
$$

Therefore

$$
W=
\frac{1}{2}(4.0 \times 10^{-3})(200)
=0.40\ \mathrm{J}.
$$

**What this example trains.** Stored energy is not simply $QV$ because the
voltage rises from zero during charging.

## Example 6: One Time Constant

**Prompt.** A $47\ \mu\mathrm{F}$ capacitor discharges through a
$100\ \mathrm{k\Omega}$ resistor from initial p.d. $12\ \mathrm{V}$. Find the
time constant and the p.d. after one time constant.

**Solution.**

The time constant is

$$
\tau=RC.
$$

Convert units:

$$
R=100 \times 10^3\ \Omega,
\qquad
C=47 \times 10^{-6}\ \mathrm{F}.
$$

So

$$
\tau=(100 \times 10^3)(47 \times 10^{-6})
=4.7\ \mathrm{s}.
$$

After one time constant,

$$
V=V_0e^{-1}=0.37V_0.
$$

Thus

$$
V=0.37(12)=4.4\ \mathrm{V}.
$$

**What this example trains.** One time constant is not full discharge.

## Example 7: Exponential Discharge

**Prompt.** For the circuit in Example 6, find the p.d. after
$9.4\ \mathrm{s}$.

**Solution.**

Use

$$
V=V_0e^{-t/RC}.
$$

Here

$$
RC=4.7\ \mathrm{s},
\qquad
t=9.4\ \mathrm{s}=2RC.
$$

Therefore

$$
V=12e^{-2}=1.62\ \mathrm{V}.
$$

**What this example trains.** Charge, current magnitude, and p.d. share the
same exponential factor during discharge.

## Example 8: Finding $RC$ from a Log Graph

**Prompt.** A graph of $\ln V$ against time for a discharging capacitor has
gradient $-0.20\ \mathrm{s^{-1}}$. Find the time constant. If
$C=1000\ \mu\mathrm{F}$, find $R$.

**Solution.**

For discharge,

$$
V=V_0e^{-t/RC}.
$$

Taking logarithms gives

$$
\ln V=\ln V_0-\frac{t}{RC}.
$$

So the gradient is

$$
-\frac{1}{RC}.
$$

Thus

$$
\frac{1}{RC}=0.20,
\qquad
RC=5.0\ \mathrm{s}.
$$

With $C=1000\ \mu\mathrm{F}=1.00 \times 10^{-3}\ \mathrm{F}$,

$$
R=\frac{RC}{C}
=\frac{5.0}{1.00 \times 10^{-3}}
=5.0 \times 10^3\ \Omega.
$$

**What this example trains.** A logarithmic graph turns exponential discharge
into a straight line.
