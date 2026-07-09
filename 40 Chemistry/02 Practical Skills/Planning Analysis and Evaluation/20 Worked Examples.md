---
title: "Planning, Analysis and Evaluation - Worked Examples"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701
  - practical-skills
---

# Planning, Analysis and Evaluation - Worked Examples

These examples model the four Paper 5 skills: planning, analysis, conclusion and evaluation. They follow [the lecture notes](10%20Lecture%20Notes.md).

## Example 1: Full plan: temperature and rate

**Question (planning).** It is suggested that the rate of the reaction between hydrochloric acid and sodium thiosulfate increases with temperature. Plan an experiment to test this.

**Prediction.** As temperature rises, the time for the cross to disappear decreases; the rate, taken as $1/t$, increases. The expected graph of $1/t$ against temperature is a rising curve.

**Variables.**

- Independent: temperature of the reaction mixture, set at $25$, $35$, $45$, $55$ and $65\ ^\circ\mathrm{C}$ using a water-bath.
- Dependent: time $t$ for the cross to disappear.
- Controlled: concentrations and volumes of $\ce{HCl}$ and $\ce{Na2S2O3}$, total volume, the flask and the printed cross.

**Method.**

1. Place equal volumes of the thiosulfate solution and the acid in separate tubes in the water-bath until each reaches the set temperature (checked with a thermometer).
2. Mix them in a flask over the cross, start the clock, swirl once, and stop when the cross just disappears.
3. Record $t$; repeat at each temperature and average concordant times.
4. Plot $1/t$ against temperature.

**Safety.** Sulfur dioxide is an irritant; use a fume hood or good ventilation and small volumes. Hot water burns; use a test-tube holder and handle hot glass with care. Wear eye protection.

**Reliability and validity.** Pre-heating both solutions to the set temperature controls the actual reaction temperature. A control is not needed to prove causation here, but repeating each temperature checks random error.

## Example 2: Analysis: linearising data with $y = mx + c$

**Question (analysis).** The reaction $\ce{A -> products}$ is suspected to be first order. Concentration of $\ce{A}$ was measured against time:

| $t$ / s | $0$ | $20$ | $40$ | $60$ | $80$ | $100$ |
| ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| $[\ce{A}]$ / mol dm⁻³ | $0.500$ | $0.397$ | $0.315$ | $0.250$ | $0.198$ | $0.158$ |

**Processing.** For a first-order reaction, $\ln[\ce{A}]$ falls linearly with time. Calculate $\ln[\ce{A}]$:

| $t$ / s | $0$ | $20$ | $40$ | $60$ | $80$ | $100$ |
| ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| $\ln[\ce{A}]$ | $-0.693$ | $-0.924$ | $-1.155$ | $-1.386$ | $-1.619$ | $-1.845$ |

The $\ln[\ce{A}]$ values fall by almost exactly $0.231$ every $20\ \mathrm{s}$, so a plot of $\ln[\ce{A}]$ against $t$ is a straight line.

**Using $y = mx + c$.** With $y = \ln[\ce{A}]$ and $x = t$:

$$
\ln[\ce{A}] = -kt + \ln[\ce{A}]_0
$$

The gradient is $-k$. Using two well-separated points:

$$
m = \frac{-1.845 - (-0.693)}{100 - 0} = \frac{-1.152}{100} = -0.01152\ \mathrm{s^{-1}}
$$

So $k = 0.0115\ \mathrm{s^{-1}}$ (to three significant figures). The intercept is $\ln[\ce{A}]_0 = -0.693$, giving $[\ce{A}]_0 = 0.500\ \mathrm{mol\ dm^{-3}}$, which matches the data and confirms consistency.

**Conclusion.** The straight-line $\ln[\ce{A}]$ against $t$ plot supports the hypothesis that the reaction is first order.

## Example 3: Evaluation: a calorimetry weakness

**Question (evaluation).** An experiment to find the enthalpy change of reaction in a plastic cup gave $\Delta T = 8.0\ ^\circ\mathrm{C}$, but the literature value implied $\Delta T$ should have been about $10.0\ ^\circ\mathrm{C}$.

**Identify the largest error.** The measured temperature change is too small. The dominant cause is heat loss to the surroundings and to the cup during the reaction, which is a systematic error making $\Delta T$ low.

**Effect on the result.** Since $\Delta H = -mc\Delta T/n$, an underestimated $\Delta T$ gives an enthalpy change that is too small in magnitude (less exothermic than the true value).

**Realistic improvement.** Add a lid to the cup and use more concentrated reagents to give a larger, faster temperature change, so that the same heat loss is a smaller fraction of the total. Extrapolating the cooling curve back to the mixing time also corrects for heat lost during the reaction.

**Judgement of validity.** The data are reliable in the sense that repeats would agree closely (random error is small), but the result is not accurate because of the systematic heat loss. So the method is reliable but biased low.

## Example 4: Dealing with anomalous data

**Situation.** Five repeats of a titre give $23.40$, $23.45$, $23.50$, $24.80$ and $23.45\ \mathrm{cm^3}$.

**Handling.** The value $24.80\ \mathrm{cm^3}$ is far from the others and is anomalous. The concordant titres ($23.40$, $23.45$, $23.50$, $23.45$) all lie within $0.10\ \mathrm{cm^3}$ of each other. The mean should be taken from the concordant values only:

$$
\text{mean} = \frac{23.40 + 23.45 + 23.50 + 23.45}{4} = 23.45\ \mathrm{cm^3}
$$

**Explanation and improvement.** The anomaly could come from an end-point overshot once, or from using the wrong solution. The improvement is to repeat until two further titres agree within $0.10\ \mathrm{cm^3}$, and to read the burette at eye level to avoid parallax.

## Quick Checks for a Paper 5 Answer

- Does the plan state the independent variable's range and the dependent variable's measurement?
- Does it give a control variable with a method to keep it constant?
- Does the analysis plot quantities that produce a straight line from the suspected relationship?
- Does the conclusion link the data pattern to chemistry, not just to numbers?
- Does the evaluation name the single largest error and a realistic improvement that targets it?
