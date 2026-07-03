---
title: Capacitance Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/19 Capacitance/00 Overview|Capacitance]]"
status: draft
tags:
  - physics/9702/topic
  - physics/9702/electricity
  - lecture-notes
---

# Capacitance Lecture Notes

A capacitor stores separated charge and electric potential energy. A capacitor-resistor circuit then turns that stored charge into a time process: charge, potential difference, and current all change exponentially during discharge.

The topic has two habits that prevent most mistakes. First, remember that the "charge stored" on a capacitor means the magnitude of charge on either plate, even though the total charge of the two-plate capacitor is zero. Second, remember that capacitor combination rules are not the same as resistor rules.

## Source Route

- Primary syllabus source: CAIE Physics 9702.
- 19 Capacitance
- 19.1 Capacitors and capacitance
- 19.2 Energy stored in a capacitor
- 19.3 Discharging a capacitor
- Coursebook route: Physics Coursebook Chapter 23, Capacitance.

## Visual Guide

![[assets/generated/physics/capacitance.svg]]

Figure: Capacitors store charge and energy; discharge through a resistor follows exponential decay.

## 1. What a Capacitor Stores

A capacitor consists of two conductors separated by an insulator called a dielectric. In a simple parallel-plate capacitor, a supply moves electrons from one plate to the other. One plate becomes negatively charged and the other becomes positively charged.

If the plates carry charges $+Q$ and $-Q$, the net charge of the whole capacitor is zero. However, the charge stored by the capacitor is defined as the magnitude $Q$ on either plate.

As charge is separated, the potential difference across the capacitor increases. Work must be done to move more charge because the existing charge on the plates resists further separation. That work becomes electric potential energy stored in the capacitor.

## 2. Capacitance

Capacitance is the charge stored per unit potential difference:

$$
C = \frac{Q}{V}.
$$

Equivalently,

$$
Q = CV.
$$

Here:

- $C$ is capacitance;
- $Q$ is the magnitude of charge stored on either plate;
- $V$ is the potential difference across the capacitor.

The unit of capacitance is the farad:

$$
1\ \mathrm{F} = 1\ \mathrm{C\ V^{-1}}.
$$

One farad is a large capacitance in ordinary circuits, so practical capacitors are often measured in $\mu\mathrm{F}$, $\mathrm{nF}$, or $\mathrm{pF}$.

The same definition applies to an isolated spherical conductor. Its capacitance is the ratio of charge on the conductor to its potential relative to infinity. Using the point-charge potential outside a charged sphere,

$$
V = \frac{Q}{4\pi\varepsilon_0r},
$$

so an isolated conducting sphere of radius $r$ has capacitance

$$
C = 4\pi\varepsilon_0r.
$$

The important idea is still the same: capacitance tells you how much charge is stored for each volt of potential.

## 3. Capacitors in Parallel

Capacitors in parallel have the same potential difference across each capacitor:

$$
V_1 = V_2 = V_3 = \cdots = V.
$$

The total charge stored is the sum of the charges:

$$
Q_\text{total} = Q_1 + Q_2 + Q_3 + \cdots.
$$

Using $Q = CV$,

$$
C_\text{total}V = C_1V + C_2V + C_3V + \cdots.
$$

So

$$
C_\text{total} = C_1 + C_2 + C_3 + \cdots.
$$

Parallel capacitors act like a larger effective plate area. The total capacitance is greater than any individual capacitance.

## 4. Capacitors in Series

Capacitors in series store the same magnitude of charge:

$$
Q_1 = Q_2 = Q_3 = \cdots = Q.
$$

The total potential difference is the sum of the potential differences:

$$
V_\text{total} = V_1 + V_2 + V_3 + \cdots.
$$

Using $V = \frac{Q}{C}$,

$$
\frac{Q}{C_\text{total}} = \frac{Q}{C_1} + \frac{Q}{C_2} + \frac{Q}{C_3} + \cdots.
$$

So

$$
\frac{1}{C_\text{total}} = \frac{1}{C_1} + \frac{1}{C_2} + \frac{1}{C_3} + \cdots.
$$

For two capacitors in series,

$$
C_\text{total} = \frac{C_1C_2}{C_1 + C_2}.
$$

The total capacitance of capacitors in series is less than the smallest individual capacitance. This is the opposite of what happens for resistors in series.

## 5. Networks and Charge Sharing

For mixed capacitor networks, simplify one part at a time:

1. Identify any pure parallel groups and replace them with their combined capacitance.
2. Identify any pure series groups and replace them with their combined capacitance.
3. Repeat until the network becomes a single equivalent capacitance.
4. Work backwards if you need individual charges or voltages.

When a charged capacitor is connected to another capacitor, total charge is conserved, but stored energy may decrease. The lost energy is transferred to the connecting wires and circuit as thermal energy and electromagnetic radiation during charge redistribution.

This is not a contradiction. Charge is conserved. Energy is conserved too, but not all of the initial energy remains stored in the capacitors.

## 6. Energy Stored in a Capacitor

The energy stored in a capacitor is the work done in charging it. On a graph of potential difference $V$ against charge $Q$, the energy stored is the area under the graph:

$$
W = \int V\,dQ.
$$

For a capacitor with constant capacitance,

$$
V = \frac{Q}{C}.
$$

The graph of $V$ against $Q$ is a straight line through the origin, so the area under the graph is a triangle:

$$
W = \frac{1}{2}QV.
$$

Using $Q = CV$, equivalent forms are

$$
W = \frac{1}{2}CV^2
$$

and

$$
W = \frac{Q^2}{2C}.
$$

The syllabus formulae to keep fluent are

$$
W = \frac{1}{2}QV = \frac{1}{2}CV^2.
$$

The square in $W = \frac{1}{2}CV^2$ matters. Doubling the charging voltage stores four times as much energy, if $C$ is unchanged.

## 7. Capacitor Discharge Through a Resistor

When a charged capacitor is connected across a resistor, it discharges. At first, the potential difference across the capacitor is large, so the current is large. As charge leaves the plates, the potential difference falls. The current therefore falls too.

For discharge through a resistor:

$$
Q = Q_0e^{-t/RC},
$$

$$
V = V_0e^{-t/RC},
$$

and

$$
I = I_0e^{-t/RC}.
$$

The current direction during discharge is opposite to the charging direction. If a sign convention is used, the discharge current may be written with a negative sign. In many graph questions, only the magnitude of current is plotted, so the curve is shown as a positive exponential decay.

The general form is

$$
x = x_0e^{-t/RC},
$$

where $x$ may represent charge, potential difference, or current magnitude.

## 8. Time Constant

The time constant of a capacitor-resistor discharge circuit is

$$
\tau = RC.
$$

Its unit is seconds:

$$
\Omega\ \mathrm{F} = \mathrm{s}.
$$

After one time constant,

$$
x = x_0e^{-1} \approx 0.37x_0.
$$

So one time constant does not mean the capacitor is fully discharged. Exponential decay approaches zero gradually. In practice, after about five time constants, the remaining value is small enough that the capacitor is often treated as almost discharged.

Increasing $R$ makes charge leave more slowly. Increasing $C$ means more charge is stored for the same initial potential difference, so discharge also takes longer. Both effects increase $RC$.

## 9. Reading Discharge Graphs

For a discharging capacitor:

- $Q$ against $t$ is an exponential decay;
- $V$ against $t$ is an exponential decay with the same time constant;
- current magnitude $I$ against $t$ is an exponential decay with the same time constant.

Useful graph facts:

- The initial current magnitude is $I_0 = \frac{V_0}{R}$.
- The area under an $I$-$t$ graph gives charge transferred.
- A graph of $\ln V$ against $t$ is a straight line with gradient $-\frac{1}{RC}$.
- The same linearisation works for $\ln Q$ or $\ln I$, if the data are discharge data.

When analysing experimental data, do not expect a measured curve to reach exactly zero. Look for the exponential pattern and the time constant.

## 10. Problem-Solving Routine

For capacitance and networks:

1. Identify whether each group is series or parallel.
2. Use parallel rules when voltages are the same.
3. Use series rules when charges are the same.
4. Find $C_\text{total}$ before using $Q = CV$.
5. Work backwards through the network to find individual charges or voltages.

For energy:

1. Decide whether the graph is $V$ against $Q$.
2. Use area under the graph for stored energy.
3. Choose $W = \frac{1}{2}QV$, $W = \frac{1}{2}CV^2$, or $W = \frac{Q^2}{2C}$ based on known quantities.
4. Check that changing voltage has a square effect on stored energy.

For discharge:

1. Identify $R$, $C$, and the initial value $x_0$.
2. Calculate $\tau = RC$.
3. Use $x = x_0e^{-t/RC}$.
4. Keep track of whether current sign or current magnitude is being used.
5. Use logarithms if solving for time.

## 11. Common Traps

- Treating the total charge of a two-plate capacitor as $+Q$ instead of zero.
- Forgetting that "charge stored" means the magnitude on either plate.
- Using resistor combination rules for capacitors.
- Assuming series capacitors have the same voltage rather than the same charge.
- Assuming parallel capacitors have the same charge rather than the same voltage.
- Forgetting the factor $\frac{1}{2}$ in stored energy.
- Thinking a capacitor reaches exactly zero charge after one time constant.
- Ignoring current direction when comparing charging and discharging.

## 12. Quick Self-Check

You are ready to move on when you can:

- define capacitance using $C = \frac{Q}{V}$;
- apply the definition to both two-plate capacitors and isolated conductors;
- derive and use capacitor series and parallel rules;
- find stored energy from a $V$-$Q$ graph;
- use $W = \frac{1}{2}QV = \frac{1}{2}CV^2$;
- analyse discharge graphs for $Q$, $V$, and $I$;
- use $\tau = RC$ and $x = x_0e^{-t/RC}$;
- explain physically why discharge current decreases with time.

## Connections

- [[10 Physics/01 Topics/10 DC Circuits/00 Overview|D.C. Circuits]]
- [[10 Physics/01 Topics/21 Alternating Currents/00 Overview|Alternating Currents]]
- [[20 Mathematics/01 Pure Mathematics/07 Logarithms Exponentials and Numerical Methods/00 Overview|Logarithms, Exponentials and Numerical Methods]]
