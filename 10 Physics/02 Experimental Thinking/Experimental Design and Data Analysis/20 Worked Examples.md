---
title: Experimental Design and Data Analysis Worked Examples
subject: Physics
syllabus: 9702
parent: "[Experimental Design and Data Analysis](00%20Overview.md)"
status: active
tags:
  - physics/9702
  - experimental-thinking
  - worked-examples
---

# Experimental Design and Data Analysis Worked Examples

These examples model the Paper 5 route through planning, variables, workable
methods, linearisation, uncertainty in graph constants, conclusions, evaluation,
and safety.

## Source Route

- Syllabus: CAIE Physics 9702 Paper 5 practical skills.
- Main subtopics: planning; data analysis; tables; graphs; conclusions;
  treatment of uncertainties; evaluation.
- Coursebook route: designing investigations, controlling variables,
  linearising relationships, error bars, worst acceptable lines, uncertainty
  in constants, limitations, improvements, and safety.

## Example 1: Variables in a Pendulum Experiment

**Prompt.** An experiment tests how the period $T$ of a simple pendulum
depends on its length $l$. Identify the independent, dependent, and control
variables, and say how each control is kept constant.

**Solution.**

The independent variable is the length $l$ of the pendulum, because this is
the quantity deliberately changed.

The dependent variable is the period $T$, because this is the measured outcome.

Control variables include:

- the mass of the bob, kept constant by using the same bob throughout;
- the amplitude, kept small and released from the same marked angle each time;
- the support and string, kept constant by using the same clamp, string, and
  pivot arrangement;
- the timing method, kept constant by timing the same number of oscillations
  each time.

**What this example trains.** A control variable is not fully stated unless the
method says how it is kept constant.

## Example 2: A Workable Plan

**Prompt.** Plan how to test

$$
T=2\pi\sqrt{\frac{l}{g}}
$$

for a simple pendulum in a school laboratory.

**Solution.**

Set up a pendulum using a bob on a string clamped to a stand. Measure the
length $l$ from the pivot to the centre of the bob using a metre rule.

Vary $l$ over the largest sensible range allowed by the stand, for example
$0.20\ \mathrm{m}$ to $1.00\ \mathrm{m}$, using at least six values.

For each $l$, displace the bob by a small angle and release it without pushing.
Time $10$ complete oscillations with a stop-watch, then divide by $10$ to find
$T$. Repeat the timing and take a mean.

Keep the same bob, small amplitude, pivot, string, and timing method
throughout.

For the analysis, square the model:

$$
T^2=\frac{4\pi^2}{g}l.
$$

Plot $T^2$ against $l$. The gradient is

$$
\frac{4\pi^2}{g},
$$

so

$$
g=\frac{4\pi^2}{\text{gradient}}.
$$

Safety: clamp the stand securely and keep the swinging bob away from the edge
of the bench.

**What this example trains.** A plan needs variables, apparatus, method, range,
repeats, analysis, and safety.

## Example 3: Linearising Common Relationships

**Prompt.** State the graph needed to test each relationship and identify the
gradient.

$$
y=ax^n
$$

and

$$
y=ae^{kx}.
$$

**Solution.**

For the power law,

$$
y=ax^n,
$$

take logarithms:

$$
\lg y=\lg a+n\lg x.
$$

Plot $\lg y$ against $\lg x$. The gradient is $n$ and the intercept is
$\lg a$.

For the exponential relationship,

$$
y=ae^{kx},
$$

take natural logarithms:

$$
\ln y=\ln a+kx.
$$

Plot $\ln y$ against $x$. The gradient is $k$ and the intercept is $\ln a$.

In table headings, show the unit inside the logarithm, for example
$\ln(V/\mathrm{V})$.

**What this example trains.** The graph axes come from the algebra, not from
guessing which curve looks straight.

## Example 4: Finding a Constant From a Gradient

**Prompt.** A graph of $T^2$ against $l$ for a pendulum has best-fit gradient
$4.02\ \mathrm{s^2\ m^{-1}}$. Find $g$.

**Solution.**

The linearised equation is

$$
T^2=\frac{4\pi^2}{g}l.
$$

So

$$
\text{gradient}=\frac{4\pi^2}{g}.
$$

Therefore

$$
g=\frac{4\pi^2}{\text{gradient}}
=\frac{4\pi^2}{4.02}
=9.82\ \mathrm{m\ s^{-2}}.
$$

**What this example trains.** The physical constant is often not the gradient
itself; it is found by matching the gradient to the linearised equation.

## Example 5: Uncertainty From a Worst Acceptable Line

**Prompt.** In the pendulum graph from Example 4, the worst acceptable line has
gradient $4.11\ \mathrm{s^2\ m^{-1}}$. Estimate the uncertainty in $g$.

**Solution.**

Use the worst acceptable gradient in the same expression:

$$
g_{\text{worst}}=\frac{4\pi^2}{4.11}
=9.60\ \mathrm{m\ s^{-2}}.
$$

The absolute uncertainty is

$$
\Delta g=|g_{\text{best}}-g_{\text{worst}}|
=|9.82-9.60|
=0.22\ \mathrm{m\ s^{-2}}.
$$

Quote

$$
g=(9.8\pm0.2)\ \mathrm{m\ s^{-2}}.
$$

**What this example trains.** A worst acceptable line gives uncertainty in the
final constant, not only uncertainty in the gradient.

## Example 6: Drawing a Conclusion With Uncertainty

**Prompt.** The experiment gives

$$
g=(9.8\pm0.2)\ \mathrm{m\ s^{-2}}.
$$

The accepted value is $9.81\ \mathrm{m\ s^{-2}}$. State a conclusion.

**Solution.**

The accepted value lies inside the range

$$
9.6\ \mathrm{m\ s^{-2}}\ \text{to}\ 10.0\ \mathrm{m\ s^{-2}}.
$$

So the result is consistent with the accepted value within experimental
uncertainty.

Do not say the experiment proves the model. A better conclusion is:

The data are consistent with

$$
T=2\pi\sqrt{\frac{l}{g}}
$$

within the uncertainty of the gradient method.

**What this example trains.** Conclusions compare data with a model using
uncertainty.

## Example 7: Limitation and Improvement

**Prompt.** A student writes, "Human error affected the timing. Use better
apparatus." Rewrite this as a useful evaluation point for the pendulum
experiment.

**Solution.**

Useful limitation:

The stop-watch was started and stopped by hand, so reaction time gives a large
uncertainty in the time for a single oscillation.

Matching improvement:

Time $20$ oscillations and divide by $20$, or use a light gate connected to a
data logger to measure the period automatically.

This improvement addresses the named limitation directly.

**What this example trains.** Evaluation marks come from specific
limitation-improvement pairs, not generic phrases.

## Example 8: Safety and Sensors

**Prompt.** An experiment uses a trolley rolling down a ramp to investigate
acceleration. Give a suitable sensor method and one safety precaution.

**Solution.**

Use two light gates connected to a data logger. Attach a card of known length
to the trolley. Each light gate measures the time for the card to pass through,
so the speed at each gate can be calculated. The time between gates is measured
by the data logger, allowing acceleration to be found.

Safety precaution:

Place a box or cushion at the bottom of the ramp to stop the trolley, and keep
feet clear of the ramp.

**What this example trains.** A safety point must name both the hazard and the
precaution, and sensors must be described in terms of what they measure.
