---
title: Alternating Currents Worked Examples
subject: Physics
syllabus: 9702
parent: "[Alternating Currents](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/electricity
  - worked-examples
---

# Alternating Currents Worked Examples

These examples model the standard CAIE route through sinusoidal a.c.
waveforms, r.m.s. values, mean power in a resistive load, rectification, and
capacitor smoothing.

## Source Route

- Syllabus: CAIE Physics 9702 section 21, Alternating currents.
- Main subtopics: characteristics of alternating currents, rectification, and
  smoothing.
- Coursebook route: sinusoidal current and voltage, oscilloscope traces,
  r.m.s. values, power, half-wave rectification, bridge rectification, and
  smoothing capacitors.

## Example 1: Reading An Oscilloscope Trace

**Prompt.** An oscilloscope trace has peak height $3.2$ divisions from the
centre line. The Y-gain is $2.0\ \mathrm{V\ div^{-1}}$. One complete cycle
takes $4.0$ horizontal divisions and the time-base is
$5.0\ \mathrm{ms\ div^{-1}}$. Find the peak voltage, peak-to-peak voltage,
period, frequency, and angular frequency.

**Solution.**

The peak voltage is

$$
V_0=(3.2)(2.0)=6.4\ \mathrm{V}.
$$

The peak-to-peak voltage is twice the peak value:

$$
V_{\text{p-p}}=2V_0=12.8\ \mathrm{V}.
$$

The period is

$$
T=(4.0)(5.0\ \mathrm{ms})=20\ \mathrm{ms}
=2.0 \times 10^{-2}\ \mathrm{s}.
$$

So

$$
f=\frac{1}{T}
=\frac{1}{2.0 \times 10^{-2}}
=50\ \mathrm{Hz}.
$$

The angular frequency is

$$
\omega=2\pi f=2\pi(50)=3.14 \times 10^2\ \mathrm{rad\ s^{-1}}.
$$

**What this example trains.** Peak, peak-to-peak, period, frequency, and
angular frequency are different readings from the same waveform.

## Example 2: Using A Sinusoidal Equation

**Prompt.** An alternating voltage is represented by

$$
V=9.0\sin(200\pi t),
$$

where $V$ is in volts and $t$ is in seconds. Find the peak voltage, frequency,
period, and voltage at $t=1.25\ \mathrm{ms}$.

**Solution.**

Compare the equation with

$$
V=V_0\sin\omega t.
$$

So

$$
V_0=9.0\ \mathrm{V}
$$

and

$$
\omega=200\pi\ \mathrm{rad\ s^{-1}}.
$$

Using $\omega=2\pi f$,

$$
f=\frac{\omega}{2\pi}
=\frac{200\pi}{2\pi}
=100\ \mathrm{Hz}.
$$

Hence

$$
T=\frac{1}{f}=1.0 \times 10^{-2}\ \mathrm{s}.
$$

At $t=1.25\ \mathrm{ms}=1.25 \times 10^{-3}\ \mathrm{s}$,

$$
V=9.0\sin\left(200\pi \times 1.25 \times 10^{-3}\right)
=9.0\sin\left(\frac{\pi}{4}\right)
=6.36\ \mathrm{V}.
$$

**What this example trains.** The argument of the sine function is an angle in
radians. Convert milliseconds to seconds before substituting.

## Example 3: R.M.S. Values

**Prompt.** A sinusoidal a.c. supply has peak voltage
$24\ \mathrm{V}$. Find its r.m.s. voltage. If it is connected across a
$12\ \Omega$ resistor, find the mean power.

**Solution.**

For a sinusoidal voltage,

$$
V_{\text{r.m.s.}}=\frac{V_0}{\sqrt{2}}.
$$

So

$$
V_{\text{r.m.s.}}
=\frac{24}{\sqrt{2}}
=17.0\ \mathrm{V}.
$$

Mean power in a resistor is calculated using r.m.s. values:

$$
P_{\text{mean}}
=\frac{V_{\text{r.m.s.}}^2}{R}
=\frac{(17.0)^2}{12}
=24\ \mathrm{W}.
$$

**What this example trains.** The r.m.s. value is the steady d.c. value that
would produce the same mean power in the same resistor.

## Example 4: Mean Power From Peak Current

**Prompt.** A sinusoidal current of peak value $2.0\ \mathrm{A}$ passes
through a $12\ \Omega$ resistor. Find the maximum instantaneous power and the
mean power.

**Solution.**

The maximum instantaneous power occurs when the current has its peak value:

$$
P_{\max}=I_0^2R=(2.0)^2(12)=48\ \mathrm{W}.
$$

For a sinusoidal alternating current in a resistive load,

$$
P_{\text{mean}}=\frac{1}{2}P_{\max}.
$$

Therefore

$$
P_{\text{mean}}=24\ \mathrm{W}.
$$

The same result comes from

$$
I_{\text{r.m.s.}}=\frac{2.0}{\sqrt{2}}=1.41\ \mathrm{A},
$$

so

$$
P_{\text{mean}}=I_{\text{r.m.s.}}^2R=(1.41)^2(12)=24\ \mathrm{W}.
$$

**What this example trains.** Peak values are for maximum instantaneous power;
r.m.s. values are for mean power.

## Example 5: Mains R.M.S. and Peak Values

**Prompt.** A mains supply is labelled $230\ \mathrm{V}$ r.m.s. Find the peak
voltage and peak-to-peak voltage, assuming the waveform is sinusoidal.

**Solution.**

For a sinusoidal voltage,

$$
V_{\text{r.m.s.}}=\frac{V_0}{\sqrt{2}}.
$$

Therefore

$$
V_0=V_{\text{r.m.s.}}\sqrt{2}
=(230)\sqrt{2}
=325\ \mathrm{V}.
$$

The peak-to-peak voltage is

$$
V_{\text{p-p}}=2V_0=650\ \mathrm{V}.
$$

**What this example trains.** A labelled a.c. supply value is normally an
r.m.s. value, not the peak of the sine wave.

## Example 6: Half-Wave and Full-Wave Rectification

**Prompt.** Describe the output across a load resistor for a sinusoidal input
after half-wave rectification and after full-wave rectification.

**Solution.**

In half-wave rectification, a single diode conducts during one half-cycle and
blocks during the other half-cycle. The load receives pulses of one polarity
separated by intervals of zero output.

In full-wave rectification, a bridge rectifier uses four diodes so that the
load current has the same direction during both halves of the input cycle. The
negative half-cycles are turned into pulses of the same polarity as the
positive half-cycles.

For the same input frequency, the full-wave output has pulses twice as often
as the half-wave output. It is therefore easier to smooth.

**What this example trains.** Rectification changes the sign pattern of the
output; it does not by itself make the output perfectly steady.

## Example 7: Capacitor Smoothing

**Prompt.** Explain how a capacitor smooths the output of a full-wave rectifier
and how changing capacitance or load resistance affects the ripple.

**Solution.**

The smoothing capacitor is connected in parallel with the load. Near each peak
of the rectified waveform, the diode circuit charges the capacitor quickly.
Between peaks, the rectified input voltage falls, so the capacitor discharges
through the load resistor.

The load voltage does not fall immediately to zero because the capacitor
supplies charge while it discharges. The output is therefore a d.c. voltage
with ripple, not a perfectly constant d.c. voltage.

The discharge time constant is

$$
\tau=RC.
$$

A larger capacitance stores more charge for the same voltage. A larger load
resistance gives a smaller discharge current. Both increase $\tau$, so the
capacitor discharges less between peaks and the ripple is reduced.

**What this example trains.** Smoothing is capacitor charge and discharge
applied to a rectified waveform.

## Example 8: Repairing A Peak-Value Power Error

**Prompt.** A student says that a sinusoidal voltage with peak value
$20\ \mathrm{V}$ across a $10\ \Omega$ resistor has mean power
$P=V^2/R=40\ \mathrm{W}$. Correct the calculation.

**Solution.**

The formula

$$
P_{\text{mean}}=\frac{V_{\text{r.m.s.}}^2}{R}
$$

uses r.m.s. voltage, not peak voltage.

First find

$$
V_{\text{r.m.s.}}=\frac{20}{\sqrt{2}}=14.1\ \mathrm{V}.
$$

Then

$$
P_{\text{mean}}
=\frac{(14.1)^2}{10}
=20\ \mathrm{W}.
$$

The student's value $40\ \mathrm{W}$ is the maximum instantaneous power, not
the mean power.

**What this example trains.** If peak voltage is put directly into
$P=V^2/R$, the answer is twice the mean power for a sinusoidal waveform.
