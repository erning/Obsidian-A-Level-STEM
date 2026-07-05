---
title: Measurement and Data Presentation Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/02 Experimental Thinking/Measurement and Data Presentation/00 Overview|Measurement and Data Presentation]]"
status: draft
tags:
  - physics/9702
  - experimental-thinking
  - lecture-notes
---

# Measurement and Data Presentation Lecture Notes

A measurement is not finished when you write down a number. It is finished when the number carries a unit, an uncertainty, and a place in a clear record. "The current is $0.36\ \mathrm{A}$" is an observation; "$I=(0.36\pm0.01)\ \mathrm{A}$, read on a digital ammeter, in series with the resistor" is evidence someone else can check.

This note is about the practical habits that turn observations into evidence: choosing the right instrument, recording data honestly, plotting graphs that expose a relationship, and reading off gradients and intercepts without throwing away precision.

The habit to practise on every measurement is:

1. Name the quantity and its unit.
2. Note the instrument and its resolution.
3. Record the reading with the precision the instrument justifies.
4. Attach an absolute uncertainty.
5. When several readings combine, carry the uncertainty through.

## Visual guide

![[assets/generated/physics/measurement-and-data-presentation.svg]]

This guide highlights the three things a good practical record keeps visible: the uncertainty on each reading, the error bar that uncertainty produces on a graph, and the range of gradients that the error bars still allow.

## Source route

This note covers the practical skills tested in CAIE Physics 9702 Paper 3 (Advanced Practical Skills) and underpins the data handling in Paper 5. The syllabus sections involved are:

- Manipulation, measurement and observation.
- Presentation of data and observations (tables and graphs).
- Analysis, conclusions and evaluation (interpretation of graphs, estimating uncertainties, drawing conclusions).

The coursebook develops these in the Practical Skills P1 and P2 chapters, which run alongside the theory chapters rather than as a separate block.

## 1. Quantities, units and the resolution of an instrument

Every instrument has a resolution: the smallest change it can show reliably.

- A metre rule with a millimetre scale has a resolution of $1\ \mathrm{mm}$.
- A digital voltmeter reading to $0.01\ \mathrm{V}$ has a resolution of $0.01\ \mathrm{V}$.
- A stop-watch reading to $0.01\ \mathrm{s}$ has a resolution of $0.01\ \mathrm{s}$, although human reaction time is the real limit when timing by hand.

Choosing an instrument means matching its range to the largest value you expect, and its resolution to the smallest change you need to detect. A $0$ to $1\ \mathrm{A}$ ammeter is no use if the current is $2\ \mathrm{mA}$; a milliammeter reading to $0.1\ \mathrm{mA}$ is.

The instrument you choose fixes the precision you are allowed to claim. Recording a distance measured on a millimetre rule as $2.0000\ \mathrm{cm}$ adds digits the instrument never gave you.

## 2. Reading analogue and digital instruments

Analogue instruments have a scale and a pointer. You have to judge where the pointer sits between two marks. The usual convention is to read to the nearest half of the smallest division, estimating the last digit by eye. So on a $0$ to $1\ \mathrm{A}$ ammeter with divisions every $0.05\ \mathrm{A}$, a reading might be recorded as $0.37\ \mathrm{A}$, where the $7$ is estimated.

Digital instruments display a number. The resolution is the value of the last digit. A digital meter reading $2.34\ \mathrm{V}$ is resolved to $0.01\ \mathrm{V}$. The uncertainty is usually taken as plus or minus the last digit, or a few counts of the last digit. A digital balance reading $24.6\ \mathrm{g}$ is resolved to $0.1\ \mathrm{g}$.

For either type, write down what you actually read. Do not round further, and do not add zeros.

## 3. Significant figures and consistency

The significant figures in a reading show the precision the measurement supports. In a column of raw data, every entry must be recorded to the same precision, because they all come from the same instrument.

If one length in a column is $2.4\ \mathrm{cm}$, the others cannot appear as $2.43\ \mathrm{cm}$. Either the instrument gave hundredths of a centimetre, in which case the first entry should be $2.40\ \mathrm{cm}$, or it did not, in which case the second entry must lose a digit.

Calculated quantities are different. Their precision is set by the least precise quantity that went into them. As a working rule, if the least precise input has $n$ significant figures, quote the calculated result to $n$ or $n+1$ significant figures, never fewer, never many more.

For example, if resistance is found from

$$
R=\frac{V}{I}
$$

with $V=(2.4\pm0.1)\ \mathrm{V}$ and $I=(0.52\pm0.01)\ \mathrm{A}$, then

$$
R=\frac{2.4}{0.52}=4.6\ \Omega,
$$

quoted to two significant figures, because $V$ has two. Writing $4.615\ \Omega$ would be dishonest.

## 4. Tables of results

A results table is the raw record of the experiment. It should be drawn up before readings are taken, so that values go straight in and are not copied up later.

Each column heading must state the quantity and its unit, following the slash convention. For a current in milliamperes, write the heading as

$$
I/\mathrm{mA}.
$$

The alternatives $I\ \text{in}\ \mathrm{mA}$ or $I\ (\mathrm{mA})$ are tolerated, but $I\ \mathrm{mA}$ or just $\mathrm{mA}$ are not, because they mix quantity and unit or drop the quantity entirely.

Raw data and calculated quantities live in separate columns. If the experiment measures length $l$ and period $T$ and then computes $T^2$, there should be three columns: $l/\mathrm{cm}$, $T/\mathrm{s}$, $T^2/\mathrm{s^2}$. The $T^2$ column is filled in after the raw columns.

Every column of raw data should use the same number of decimal places, matching the instrument. A calculated column may vary down the rows, because the number of significant figures changes with the value.

## 5. Uncertainty of a single reading

Every reading carries an absolute uncertainty. For a single reading, the size of that uncertainty depends on the instrument and on how it was taken.

- Analogue scale: the uncertainty is usually half the smallest division, or a few tenths of it if you estimate well.
- Digital scale: the uncertainty is a few counts of the last digit.
- Stop-watch timed by hand: reaction time dominates, so a realistic uncertainty is about $0.1$ to $0.2\ \mathrm{s}$, not the $0.01\ \mathrm{s}$ the display shows.

The absolute uncertainty and the percentage uncertainty carry the same information in different forms:

$$
\text{percentage uncertainty}
=\frac{\text{absolute uncertainty}}{\text{value}}\times 100\%.
$$

A reading $l=(2.40\pm0.05)\ \mathrm{cm}$ has a percentage uncertainty of

$$
\frac{0.05}{2.40}\times100\%=2.1\%.
$$

Keep both forms in mind. Absolute uncertainties add when quantities add or subtract; percentage uncertainties add when quantities multiply or divide.

## 6. Repeated readings

If a reading is repeated, the spread of the values tells you about the random error. Take several readings and find their mean.

The absolute uncertainty of a repeated measurement is taken as half the range of the readings:

$$
\Delta x=\frac{x_{\max}-x_{\min}}{2}.
$$

For example, if five timings of the same period give $1.83\ \mathrm{s}$, $1.87\ \mathrm{s}$, $1.85\ \mathrm{s}$, $1.84\ \mathrm{s}$, $1.86\ \mathrm{s}$, the mean is $1.85\ \mathrm{s}$ and the range is $0.04\ \mathrm{s}$, so

$$
T=(1.85\pm0.02)\ \mathrm{s}.
$$

Averaging reduces the effect of random error but does nothing for systematic error. If the stop-watch runs slow, every reading is wrong in the same direction, and repeating will not reveal it.

## 7. Propagating uncertainties

When calculated quantities are built from measured ones, the uncertainties propagate. The rules are simple enough to use in every calculation.

For sums and differences, add absolute uncertainties:

$$
\Delta(x+y)=\Delta x+\Delta y.
$$

For products, quotients and powers, add percentage uncertainties:

$$
\frac{\Delta(xy)}{xy}
=\frac{\Delta x}{x}+\frac{\Delta y}{y}.
$$

For a power $x^n$, multiply the percentage uncertainty by $|n|$:

$$
\frac{\Delta(x^n)}{x^n}=|n|\frac{\Delta x}{x}.
$$

These rules are conservative: they assume the worst case, that both errors act in the same direction. They are the rules expected at A Level.

A common application is $T^2$. If $T$ has a $2\%$ uncertainty, then $T^2$ has a $4\%$ uncertainty. This matters when you plot $T^2$ against another variable and have to draw error bars.

## 8. Plotting graphs: axes and scales

A graph is the clearest way to expose a relationship. A well-plotted graph follows conventions that make it easy to read.

- Label both axes with quantity and unit, using the slash convention: $V/\mathrm{V}$ on one axis, $I/\mathrm{mA}$ on the other.
- Choose scales so the data points fill at least half of the grid in both directions. A cluster of points in one corner wastes the graph.
- Use scales that are easy to read: $1$, $2$ or $5$ units per large square. Scales based on $3$ or $7$ make it hard to place and read points.
- A false origin is allowed when the data are far from zero. Label the axis so the break is obvious.
- Number the axes at regular intervals, at least every large square, along the whole length.

## 9. Plotting points and drawing the trend line

Plot each point with a sharp pencil. A fine cross or a small encircled dot is acceptable. Points should be smaller than $1\ \mathrm{mm}$ across, but visible.

Draw the line of best fit with a continuous, thin line. The line should balance the points, with roughly as many above as below, and the scatter should be even along its whole length. Do not join the dots: the trend is what matters, and joining implies the model goes through every point.

If one point clearly sits away from the trend of the others, it may be anomalous. Circle it, label it, and ignore it when drawing the line. Do not silently drop it.

For a curved trend, draw a smooth curve through the points. If the question asks for the gradient at a point, draw a tangent to the curve at that point and find the gradient of the tangent.

## 10. Reading gradients and intercepts

The gradient of a straight-line graph comes from two points on the line, not from data points. Choose two points as far apart as possible, more than half the length of the line apart, and read their coordinates carefully.

$$
m=\frac{\Delta y}{\Delta x}.
$$

Read the coordinates to the nearest half of the smallest grid square. Use a large triangle when you show your working; a small triangle magnifies reading errors.

The $y$-intercept is the value of $y$ where the line crosses the $y$-axis. If the graph has a false origin, the intercept is not where the drawn line meets the drawn axis. Instead, read the coordinates of a point on the line and substitute into

$$
y=mx+c
$$

to find $c$.

The link back to physics is the equation of a straight line. If you can write the physical relationship as

$$
y=mx+c,
$$

then the gradient $m$ and intercept $c$ carry physical meaning. For example, for the oscillating spring

$$
T=2\pi\sqrt{\frac{m}{k}},
$$

squaring both sides gives

$$
T^2=\frac{4\pi^2}{k}m.
$$

A graph of $T^2$ against $m$ is a straight line through the origin with gradient $4\pi^2/k$, so the spring constant can be found from the gradient.

## 11. A complete worked example

A student measures the extension $x$ of a spring for different loads $F$, and uses the graph to find the spring constant $k$. The data are:

| $F/\mathrm{N}$ | $x/\mathrm{cm}$ |
|---:|---:|
| $1.0$ | $2.3$ |
| $2.0$ | $4.6$ |
| $3.0$ | $7.1$ |
| $4.0$ | $9.2$ |
| $5.0$ | $11.6$ |

Hooke's law gives $F=kx$, so a graph of $F$ against $x$ is a straight line through the origin with gradient $k$. The units must match: $x$ is in centimetres, so the gradient from the graph has units $\mathrm{N\ cm^{-1}}$, and a conversion to $\mathrm{N\ m^{-1}}$ is needed at the end.

Taking two well-separated points on the line of best fit, say $(0,0)$ and $(11.6\ \mathrm{cm},5.0\ \mathrm{N})$,

$$
k=\frac{5.0}{11.6\times10^{-2}}=43\ \mathrm{N\ m^{-1}}.
$$

The uncertainty in $x$ is about $0.2\ \mathrm{cm}$ (half the smallest division, estimated). Over a $12\ \mathrm{cm}$ range that is roughly $2\%$, so the percentage uncertainty in $k$ is also about $2\%$, giving

$$
k=(43\pm1)\ \mathrm{N\ m^{-1}}.
$$

## Worked-thinking pattern

1. Read the question and identify the quantity being measured or found.
2. Note the instrument, its resolution, and the precision you are allowed to claim.
3. Record every reading with unit and uncertainty, in a table whose headings use the slash convention.
4. Decide what graph to plot, and rewrite the relationship as $y=mx+c$ if possible.
5. Plot carefully, draw a line of best fit, and read the gradient from two well-separated points.
6. Carry the uncertainty through the calculation and quote the final value with unit and uncertainty.

## Common traps

- Quoting a calculated value to more significant figures than the measurements support.
- Recording raw readings in a column to different precisions.
- Writing column headings as $I\ \mathrm{mA}$ or just $\mathrm{mA}$, instead of $I/\mathrm{mA}$.
- Joining the dots instead of drawing a line of best fit.
- Reading the gradient from two points that are close together.
- Forgetting to convert units when the graph axes use centimetres or milliamperes.
- Treating a digital display's last digit as more reliable than it is, especially on a stop-watch timed by hand.
- Assuming repeated readings remove systematic error.
- Reading the $y$-intercept directly from the axis when a false origin has been used.

## Quick self-check

After working through this note, you should be able to:

- Choose an instrument whose range and resolution match the measurement.
- Read analogue and digital instruments to their justified precision.
- Keep raw data in a column at a consistent precision, with correct headings.
- Quote calculated values to the right number of significant figures.
- Convert between absolute and percentage uncertainty.
- Propagate uncertainty through sums, differences, products, quotients and powers.
- Plot a graph that fills the grid, with labelled axes and a sensible scale.
- Draw a line of best fit and read a gradient from two well-separated points.
- Use a false origin correctly when finding the intercept.
- Rewrite a physical relationship as $y=mx+c$ and interpret the gradient.

## Connections

- [[10 Physics/01 Topics/01 Physical Quantities and Units/00 Overview|Physical Quantities and Units]]
- [[10 Physics/02 Experimental Thinking/Experimental Design and Data Analysis/00 Overview|Experimental Design and Data Analysis]]
- [[10 Physics/04 Reference/Math Tools and Formulae|Math Tools and Formulae]]
