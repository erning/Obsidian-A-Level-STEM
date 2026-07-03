---
title: Alternating Currents Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/21 Alternating Currents/00 Overview|Alternating Currents]]"
status: draft
tags:
  - physics/9702/topic
  - physics/9702/electricity
  - lecture-notes
---

# Alternating Currents Lecture Notes

Alternating current analysis is about electrical quantities that vary with time. The central model in this topic is a sinusoidal current or voltage. Once you can read the waveform, you can connect it to power in a resistor, compare an a.c. supply with an equivalent d.c. supply, and explain how diode circuits turn a.c. into a more nearly steady d.c. output.

## Source Route

- Primary syllabus source: CAIE Physics 9702.
- 21 Alternating currents
- 21.1 Characteristics of alternating currents
- 21.2 Rectification and smoothing
- Coursebook route: Physics Coursebook Chapter 27: alternating currents, alternating voltages, power, rectification, and smoothing.

## Visual Guide

![[assets/generated/physics/alternating-currents.svg]]

Figure: A sinusoidal waveform is described by its peak value, period, frequency, phase, and r.m.s. value.

## 1. What Alternating Current Means

A direct current keeps the same direction through a circuit. An alternating current changes direction periodically. In this topic the standard waveform is sinusoidal:

$$
I = I_0 \sin \omega t
$$

or, for voltage,

$$
V = V_0 \sin \omega t .
$$

Here $I_0$ and $V_0$ are peak values. They are the maximum magnitudes of the current and voltage, not the values that should usually be substituted into mean power formulae. The period $T$ is the time for one complete cycle, and the frequency $f$ is the number of cycles per second:

$$
f = \frac{1}{T}.
$$

The angular frequency is

$$
\omega = 2 \pi f .
$$

The argument $\omega t$ is an angle in radians. A waveform with a larger frequency completes more cycles each second. A waveform with a larger peak value reaches a larger maximum positive and negative value, but it does not necessarily deliver proportionally larger mean power unless the power relationship is handled correctly.

## 2. Reading an Oscilloscope Trace

An oscilloscope trace is a graph of voltage against time. The vertical scale gives voltage, and the horizontal time-base gives time. A typical calculation has three steps:

1. Count the vertical divisions from the centre line to a peak.
2. Multiply by the Y-gain to find the peak voltage.
3. Count the horizontal divisions for one complete cycle, then multiply by the time-base to find the period.

After that, use $f = 1/T$ for the frequency. If the trace gives a peak-to-peak voltage, halve it to get the peak value:

$$
V_0 = \frac{V_{\text{peak-to-peak}}}{2}.
$$

Do not mix these quantities. A peak voltage, a peak-to-peak voltage, an r.m.s. voltage, and a mean voltage are different descriptions of the same waveform.

## 3. Instantaneous Power In A Resistor

For a resistor, the instantaneous power is

$$
p = VI = I^2 R = \frac{V^2}{R}.
$$

If the current is sinusoidal,

$$
I = I_0 \sin \omega t,
$$

then

$$
p = I_0^2 R \sin^2 \omega t.
$$

The power is never negative because $\sin^2 \omega t$ is never negative. This is physically sensible: a resistor dissipates energy as thermal energy during both half-cycles. When the current reverses direction, the voltage across the resistor reverses too, so the product $VI$ remains positive.

The maximum instantaneous power is

$$
P_{\max} = I_0^2 R = \frac{V_0^2}{R}.
$$

For a sinusoidal alternating current in a resistive load, the mean power is half the maximum power:

$$
P_{\text{mean}} = \frac{1}{2} P_{\max}.
$$

This result comes from the mean value of $\sin^2 \omega t$, which is $1/2$ over a complete cycle.

## 4. R.M.S. Values

The root-mean-square value of an alternating current is the steady direct current that would produce the same mean power in the same resistor. This definition matters because it makes a.c. power formulae look like familiar d.c. formulae.

For a sinusoidal alternating current,

$$
I_{\text{r.m.s.}} = \frac{I_0}{\sqrt{2}}.
$$

For a sinusoidal alternating voltage,

$$
V_{\text{r.m.s.}} = \frac{V_0}{\sqrt{2}}.
$$

Mean power in a resistor is therefore calculated using r.m.s. values:

$$
P_{\text{mean}} = V_{\text{r.m.s.}} I_{\text{r.m.s.}},
$$

$$
P_{\text{mean}} = I_{\text{r.m.s.}}^2 R,
$$

$$
P_{\text{mean}} = \frac{V_{\text{r.m.s.}}^2}{R}.
$$

The common mistake is to put the peak values directly into these formulae. For a sinusoidal waveform, that gives a power value twice as large as the mean power. Use peak values when the question asks for a maximum instantaneous value. Use r.m.s. values when the question asks for mean power or the labelled value of a mains supply.

## 5. Half-Wave Rectification

Rectification means using diodes to make current through a load pass in one direction only. A single diode in series with a load resistor gives half-wave rectification.

During one half-cycle, the diode is forward-biased and current flows through the load. During the opposite half-cycle, the diode is reverse-biased and the current is nearly zero. The output across the load is therefore a series of pulses separated by intervals of zero output.

Graphically, half-wave rectification keeps one half of the sinusoidal waveform and removes the other half. It is simple, but it wastes half of the input cycle and produces a very uneven output.

## 6. Full-Wave Rectification

Full-wave rectification uses four diodes arranged as a bridge rectifier. The direction of current through the load is the same during both halves of the input cycle.

In one half-cycle, one pair of diodes conducts. In the next half-cycle, the other pair conducts. The input terminals have reversed polarity, but the load current still has the same direction. Graphically, both halves of the sine wave are turned into pulses of the same polarity.

Full-wave rectification gives a higher average output than half-wave rectification and the pulses are closer together. That makes the output easier to smooth.

## 7. Smoothing With A Capacitor

A smoothing capacitor is connected in parallel with the load resistor. Its job is not to create a perfectly constant voltage. Its job is to reduce the variation in the rectified output.

When the rectified voltage rises, the capacitor charges quickly. When the rectified voltage falls, the capacitor discharges through the load resistor. This discharge keeps the output voltage from falling immediately to zero, so the output becomes a d.c. voltage with a smaller ripple.

The size of the ripple depends on the time constant of the load circuit:

$$
\tau = RC.
$$

A larger capacitance stores more charge for a given voltage. A larger load resistance reduces the discharge current. Both increase the time constant and reduce the ripple. However, the output is still not perfectly steady unless further regulation is used.

Full-wave rectification is easier to smooth than half-wave rectification because the capacitor is recharged more often. The time between peaks is shorter, so the capacitor has less time to discharge between peaks.

## 8. Problem Routines

For waveform problems:

1. Identify whether the value is peak, peak-to-peak, r.m.s., or mean.
2. Use $T = 1/f$ and $\omega = 2 \pi f$ to connect time and angle.
3. Substitute into the sinusoidal equation only after the units and angle measure are clear.

For power problems:

1. Decide whether the question asks for instantaneous, maximum, or mean power.
2. Use peak values for maximum instantaneous power.
3. Use r.m.s. values for mean power in a resistor.

For rectification and smoothing problems:

1. Sketch the input waveform.
2. Sketch the output after the diode arrangement.
3. Add the capacitor effect: rapid charging near peaks and slower discharging through the load.
4. State how changing $C$ or $R$ changes the ripple.

## 9. Common Traps

- Using peak voltage in a mean power formula.
- Treating $V_0$ and $V_{\text{r.m.s.}}$ as the same quantity.
- Confusing frequency $f$ with angular frequency $\omega$.
- Forgetting that r.m.s. formulae in this topic assume a sinusoidal waveform.
- Saying that a smoothing capacitor removes ripple completely.
- Drawing a full-wave rectified output with alternating positive and negative pulses.

## 10. Quick Self-Check

You have the topic if you can do these without notes:

- Explain why a resistor dissipates power during both halves of an a.c. cycle.
- Convert between peak and r.m.s. values for a sinusoidal waveform.
- Explain why mean power is half the maximum power for a sinusoidal current in a resistor.
- Sketch half-wave and full-wave rectified outputs from the same sinusoidal input.
- Explain how increasing capacitance or load resistance affects ripple.

## Connections

- [[10 Physics/01 Topics/09 Electricity/00 Overview|Electricity]]
- [[10 Physics/01 Topics/10 DC Circuits/00 Overview|DC Circuits]]
- [[10 Physics/01 Topics/19 Capacitance/00 Overview|Capacitance]]
- [[10 Physics/01 Topics/20 Magnetic Fields/00 Overview|Magnetic Fields]]
