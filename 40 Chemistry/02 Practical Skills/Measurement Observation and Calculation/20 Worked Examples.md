---
title: "Measurement, Observation and Calculation - Worked Examples"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701
  - practical-skills
---

# Measurement, Observation and Calculation - Worked Examples

These examples show precision, significant figures, percentage error and graph handling in action. They follow [the lecture notes](10%20Lecture%20Notes.md).

## Example 1: Significant figures in a titration calculation

**Data.** $25.0\ \mathrm{cm^3}$ of an acid $\ce{HCl}$ is titrated against $0.100\ \mathrm{mol\ dm^{-3}}$ sodium hydroxide. Concordant titres average $23.45\ \mathrm{cm^3}$.

**Step 1: moles of alkali.**

$$
n(\ce{NaOH}) = \frac{0.100\ \mathrm{mol\ dm^{-3}} \times 23.45\ \mathrm{cm^3}}{1000\ \mathrm{cm^3\ dm^{-3}}} = 2.345 \times 10^{-3}\ \mathrm{mol}
$$

**Step 2: moles of acid.** The reaction is $1:1$:

$$
\ce{HCl + NaOH -> NaCl + H2O}
$$

so $n(\ce{HCl}) = 2.345 \times 10^{-3}\ \mathrm{mol}$.

**Step 3: concentration of acid.**

$$
[\ce{HCl}] = \frac{2.345 \times 10^{-3}\ \mathrm{mol}}{25.0 \times 10^{-3}\ \mathrm{dm^3}} = 0.0938\ \mathrm{mol\ dm^{-3}}
$$

**Significant-figure check.** The titre is four significant figures; the alkali concentration and the acid volume are three. The answer is therefore given to three (or four) significant figures: $0.0938\ \mathrm{mol\ dm^{-3}}$ (three) or $0.09380\ \mathrm{mol\ dm^{-3}}$ (four). Writing $0.0937999\ \mathrm{mol\ dm^{-3}}$ would be wrong.

## Example 2: Percentage error in a temperature change

**Data.** A neutralisation raised the temperature from $21.5\ ^\circ\mathrm{C}$ to $35.5\ ^\circ\mathrm{C}$, using a thermometer calibrated every $1\ ^\circ\mathrm{C}$.

**Temperature change.**

$$
\Delta T = 35.5 - 21.5 = 14.0\ ^\circ\mathrm{C}
$$

**Uncertainty.** Each reading has a maximum uncertainty of $\pm 0.5\ ^\circ\mathrm{C}$, so the change, being the difference of two readings, has uncertainty $\pm(0.5 + 0.5) = \pm 1.0\ ^\circ\mathrm{C}$.

**Percentage error.**

$$
\frac{1.0}{14.0} \times 100 = 7.14\%
$$

**Interpretation.** A $7\%$ error is large. Using a larger quantity of reagent to give a bigger temperature change would reduce this percentage error, which is why thermometric work uses solutions of sufficient concentration and volume.

## Example 3: Designing a results table

**Task.** Record a rates experiment in which $5\ \mathrm{cm^3}$ of acid is added to $25\ \mathrm{cm^3}$ of thiosulfate of five different concentrations, and the time for a cross to disappear is measured twice at each concentration.

A correct table:

| $[\ce{Na2S2O3}]$ / mol dm⁻³ | $t$ run 1 / s | $t$ run 2 / s | mean $t$ / s | $1/t$ / $10^{-2}$ s⁻¹ |
| ---: | ---: | ---: | ---: | ---: |
| $0.40$ | $24$ | $25$ | $24.5$ | $4.08$ |
| $0.32$ | $31$ | $30$ | $30.5$ | $3.28$ |

**Checks.** Every time entry has the same precision (nearest $1\ \mathrm{s}$). Each column has a heading with units. The concentration column keeps the same number of decimal places. The mean is taken only from concordant runs.

## Example 4: Gradient of a rate graph

**Task.** A graph of rate ($y$, in $\mathrm{mol\ dm^{-3}\ s^{-1}}$) against concentration ($x$, in $\mathrm{mol\ dm^{-3}}$) is a straight line through the origin. Two points on the line of best fit are $(0.10, 0.0048)$ and $(0.50, 0.0240)$.

**Gradient.** Use two points more than half the line length apart:

$$
m = \frac{0.0240 - 0.0048}{0.50 - 0.10} = \frac{0.0192}{0.40} = 0.0480\ \mathrm{s^{-1}}
$$

**Interpretation.** For $\text{rate} = k[\text{reactant}]$, the gradient is the rate constant $k$. So $k = 0.0480\ \mathrm{s^{-1}}$, and the units $\mathrm{s^{-1}}$ indicate a first-order reaction.

**Why a large triangle.** Reading uncertainty in each coordinate is a fixed amount. Spread over a $0.40\ \mathrm{mol\ dm^{-3}}$ interval, it is a small percentage; crammed into a $0.05\ \mathrm{mol\ dm^{-3}}$ interval, it would dominate the gradient.

## Example 5: Distinguishing systematic from random error

**Situation.** In an enthalpy experiment, a candidate's thermometer consistently reads $1\ ^\circ\mathrm{C}$ above the true value; room temperature also drifts during the experiment.

- The $1\ ^\circ\mathrm{C}$ offset is a **systematic error**: every reading is shifted the same way. It is reduced by calibration and by using the same thermometer throughout, and it largely cancels in a temperature *change*.
- The room-temperature drift is a **random error**: it varies from run to run. It is reduced by insulation, by working quickly, and by repeating and averaging.

"Human error" is not an acceptable label for either. Name the instrument and the limitation.

## Quick Checks for Any Calculation

- Are all readings of one quantity given to the same precision?
- Does the final answer match the least precise input in significant figures?
- Is the percentage error worked out from the correct uncertainty?
- For a change of a quantity, is the uncertainty doubled?
- Does the gradient use two well-separated points on the line of best fit?
