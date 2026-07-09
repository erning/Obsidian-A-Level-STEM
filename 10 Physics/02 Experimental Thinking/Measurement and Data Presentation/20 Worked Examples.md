---
title: Measurement and Data Presentation Worked Examples
subject: Physics
syllabus: 9702
parent: "[Measurement and Data Presentation](00%20Overview.md)"
status: active
tags:
  - physics/9702
  - experimental-thinking
  - worked-examples
---

# Measurement and Data Presentation Worked Examples

These examples model the practical skills route through instrument choice,
tables, significant figures, uncertainties, graph gradients, error bars, and
linearisation.

## Source Route

- Syllabus: CAIE Physics 9702 practical skills for Paper 3 and Paper 5.
- Main subtopics: manipulation, measurement and observation; presentation of
  data and observations; analysis, conclusions and evaluation.
- Coursebook route: precision, accuracy, errors, uncertainties, tables,
  graphing, gradients, intercepts, error bars, and linearised graphs.

## Example 1: Choosing and Recording an Instrument Reading

**Prompt.** A wire diameter is about $0.40\ \mathrm{mm}$. Choose a suitable
instrument and state a sensible reading with uncertainty.

**Solution.**

A metre rule is unsuitable because its millimetre scale cannot resolve a
diameter of about $0.40\ \mathrm{mm}$ well. A micrometer screw gauge is more
suitable because it can read small diameters, often to
$0.01\ \mathrm{mm}$.

A sensible record might be

$$
d=(0.42\pm0.01)\ \mathrm{mm}.
$$

The uncertainty is not written as zero just because the scale gives a neat
reading. The last digit is limited by the instrument resolution.

**What this example trains.** Instrument choice is about range and resolution,
not just whether the instrument can physically touch the object.

## Example 2: A Results Table With Raw and Calculated Columns

**Prompt.** A student measures potential difference $V$ and current $I$ for a
resistor. The current is measured in milliamperes. Write a suitable table
layout and calculate $R$ for $V=2.40\ \mathrm{V}$ and
$I=520\ \mathrm{mA}$.

**Solution.**

A suitable table layout is:

| $V/\mathrm{V}$ | $I/\mathrm{mA}$ | $R/\Omega$ |
|---:|---:|---:|
| $2.40$ | $520$ | $4.62$ |

The calculated resistance is

$$
R=\frac{V}{I}.
$$

Convert the current:

$$
520\ \mathrm{mA}=0.520\ \mathrm{A}.
$$

So

$$
R=\frac{2.40}{0.520}
=4.62\ \Omega.
$$

The headings include both quantity and unit. Raw measured columns and the
calculated column are kept separate.

**What this example trains.** A table heading such as $I/\mathrm{mA}$ is clear
and conventional; a heading such as just $\mathrm{mA}$ is incomplete.

## Example 3: Repeated Readings and Half-Range Uncertainty

**Prompt.** Five readings of the same period are
$1.83\ \mathrm{s}$, $1.87\ \mathrm{s}$, $1.85\ \mathrm{s}$,
$1.84\ \mathrm{s}$, and $1.86\ \mathrm{s}$. Find the mean period and its
absolute uncertainty.

**Solution.**

The mean is

$$
\bar{T}=\frac{1.83+1.87+1.85+1.84+1.86}{5}
=1.85\ \mathrm{s}.
$$

The range is

$$
1.87-1.83=0.04\ \mathrm{s}.
$$

For repeated readings, a suitable absolute uncertainty is half the range:

$$
\Delta T=\frac{0.04}{2}=0.02\ \mathrm{s}.
$$

So

$$
T=(1.85\pm0.02)\ \mathrm{s}.
$$

**What this example trains.** Repeated readings estimate random scatter; they
do not remove systematic error.

## Example 4: Propagating Uncertainty in a Quotient

**Prompt.** A resistor has $V=(2.40\pm0.05)\ \mathrm{V}$ and
$I=(0.520\pm0.005)\ \mathrm{A}$. Find $R=V/I$ with an uncertainty estimate.

**Solution.**

The resistance is

$$
R=\frac{2.40}{0.520}=4.62\ \Omega.
$$

For a quotient, add percentage uncertainties:

$$
\frac{\Delta R}{R}
=
\frac{\Delta V}{V}
+
\frac{\Delta I}{I}.
$$

For the voltage,

$$
\frac{0.05}{2.40}\times 100\%=2.08\%.
$$

For the current,

$$
\frac{0.005}{0.520}\times 100\%=0.96\%.
$$

So

$$
\frac{\Delta R}{R}=3.04\%.
$$

The absolute uncertainty is

$$
\Delta R=0.0304(4.62)=0.14\ \Omega.
$$

Quote the result as

$$
R=(4.6\pm0.1)\ \Omega.
$$

**What this example trains.** Products and quotients use percentage
uncertainties, not absolute uncertainties.

## Example 5: Linearising a Spring Oscillation Graph

**Prompt.** For a mass-spring oscillator,

$$
T=2\pi\sqrt{\frac{m}{k}}.
$$

Show what graph should be plotted to find $k$, and find $k$ if the gradient is
$1.60\ \mathrm{s^2\ kg^{-1}}$.

**Solution.**

Square the equation:

$$
T^2=\frac{4\pi^2}{k}m.
$$

This has the straight-line form

$$
y=mx+c
$$

if $T^2$ is plotted on the vertical axis and $m$ on the horizontal axis. The
gradient is

$$
\text{gradient}=\frac{4\pi^2}{k}.
$$

Therefore

$$
k=\frac{4\pi^2}{\text{gradient}}
=\frac{4\pi^2}{1.60}
=24.7\ \mathrm{N\ m^{-1}}.
$$

**What this example trains.** A graph choice is justified by rearranging the
physics equation into straight-line form.

## Example 6: Intercept With a False Origin

**Prompt.** A line of best fit has gradient
$2.50\ \mathrm{V\ A^{-1}}$ and passes through the point
$(0.30\ \mathrm{A},1.10\ \mathrm{V})$. The graph has a false origin, so the
intercept cannot be read directly. Find the $V$-axis intercept.

**Solution.**

Use the straight-line equation

$$
y=mx+c.
$$

Here $y=V$, $x=I$, and $m=2.50\ \mathrm{V\ A^{-1}}$. Substitute the point:

$$
1.10=(2.50)(0.30)+c.
$$

So

$$
c=1.10-0.75=0.35\ \mathrm{V}.
$$

**What this example trains.** With a false origin, use a point on the line and
the gradient to find the intercept.

## Example 7: Gradient Uncertainty From a Worst Acceptable Line

**Prompt.** A best-fit line has gradient $2.40\ \mathrm{N\ m^{-1}}$. The
steepest or shallowest worst acceptable line has gradient
$2.15\ \mathrm{N\ m^{-1}}$. Estimate the absolute uncertainty in the gradient.

**Solution.**

For Paper 5-style graph uncertainty,

$$
\Delta(\text{gradient})
=
|\text{best-fit gradient}-\text{worst acceptable gradient}|.
$$

So

$$
\Delta(\text{gradient})=|2.40-2.15|
=0.25\ \mathrm{N\ m^{-1}}.
$$

A sensible quoted result is

$$
\text{gradient}=(2.4\pm0.3)\ \mathrm{N\ m^{-1}}.
$$

**What this example trains.** Error bars are used to judge the range of
straight lines still supported by the data.

## Example 8: Logarithmic Linearisation

**Prompt.** A relationship has the form

$$
y=ax^n.
$$

State what graph should be plotted to find $n$ and $a$.

**Solution.**

Take logarithms:

$$
\lg y=\lg a+n\lg x.
$$

This has the form $y=mx+c$ if $\lg y$ is plotted against $\lg x$. The gradient
is

$$
n,
$$

and the intercept is

$$
\lg a.
$$

Therefore

$$
a=10^{\text{intercept}}.
$$

When using real data, show the units inside the logarithm, such as
$\lg(L/\mathrm{cm})$. The logarithm itself has no unit.

**What this example trains.** Linearisation tells you which derived quantities
to calculate before plotting.
