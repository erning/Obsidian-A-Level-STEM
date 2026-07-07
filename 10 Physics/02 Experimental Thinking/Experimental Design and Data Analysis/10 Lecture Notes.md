---
title: Experimental Design and Data Analysis Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/02 Experimental Thinking/Experimental Design and Data Analysis/00 Overview|Experimental Design and Data Analysis]]"
status: active
tags:
  - physics/9702
  - experimental-thinking
  - lecture-notes
---

# Experimental Design and Data Analysis Lecture Notes

An experiment is a question put to the real world. You take a model, turn it into a prediction, vary one thing while holding the rest fixed, and let the data decide whether the prediction survives. A plan that does not make this test sharp is not a plan; it is a hope.

This note covers the higher-order practical skills of CAIE Physics 9702 Paper 5: defining a problem, designing a method, linearising a relationship so a graph can test it, handling error bars and a worst acceptable line, drawing a conclusion with an uncertainty, and evaluating the procedure honestly.

The discipline running through all of it is simple:

1. Say what you will vary, what you will measure, and what you will hold fixed.
2. Choose apparatus that can actually produce the readings.
3. Plot a graph that turns the relationship into a straight line.
4. Read the constants from the gradient and intercept, with their uncertainties.
5. Compare the result with the model, and say where the procedure was weak.

## Visual guide

![[assets/generated/physics/experimental-design-and-data-analysis.svg]]

This guide links the stages of an experiment: the variables you set, the line of best fit with its error bars, the worst acceptable line that the error bars still allow, and the range of gradients that sets the uncertainty in your final constant.

## Source route

This note covers the practical skills tested in CAIE Physics 9702 Paper 5 (Planning, Analysis and Evaluation). The syllabus expectations fall into two blocks:

- Question 1, Planning: defining the problem, methods of data collection, method of analysis, additional detail including safety.
- Question 2, Analysis, conclusions and evaluation: data analysis and linearisation, table of results, graph with error bars, conclusion, treatment of uncertainties.

The coursebook develops these in the Practical Skills P2 chapter, which assumes you have already met the measurement and graphing conventions of Paper 3.

## 1. What an experiment tests

A relationship in physics is a claim. The equation

$$
T=2\pi\sqrt{\frac{l}{g}}
$$

claims that the period of a pendulum depends on the square root of its length and on nothing else (at small angles). An experiment tests that claim by varying $l$, measuring $T$, and checking whether the data follow the predicted shape.

To make the test fair, only one thing may vary at a time. Everything that could also affect $T$ must be held fixed: the mass of the bob, the amplitude (small), the environment. If two things change together, you cannot tell which one caused the effect.

This is the whole reason for naming variables carefully.

## 2. Independent, dependent and control variables

Every experiment has three kinds of variable.

- The **independent variable** is what you choose to change: the length $l$ of the pendulum.
- The **dependent variable** is what you measure as the outcome: the period $T$.
- The **control variables** are everything else that could affect the dependent variable and that you therefore hold constant: the mass of the bob, the amplitude, $g$.

A common fault is to name a control variable without saying how it is kept constant. "Keep the mass the same" is not enough; "use the same bob throughout" is. An examiner wants the method, not the intention.

## 3. Planning a method

A plan has to be workable: if the apparatus were assembled as described, the required readings could actually be taken. The plan should say:

- how the independent variable is set and varied, over the largest range the apparatus allows;
- how the independent and dependent variables are measured, naming the instruments;
- how each control variable is held constant;
- what is plotted on each axis, and how the graph tests the relationship.

A clear, labelled diagram is part of the plan. It should show the apparatus set up, with the instruments in the right place (an ammeter in series, a voltmeter in parallel) and the variables labelled.

The range of the independent variable matters. A small range gives a short line on the graph, and the gradient becomes hard to read. Use the largest range the apparatus allows, and take enough readings (typically six or more) to show up any scatter.

Repeat the dependent variable where you can. Repeating and averaging reduces random error in the measured value, although it does nothing for systematic error.

## 4. Linearisation: turning a relationship into a straight line

A straight line is the easiest relationship to test, because the eye and the ruler can judge it, and the gradient and intercept carry physical meaning. So the first step in analysis is to rewrite the relationship in the form

$$
y=mx+c.
$$

Three forms come up again and again.

**Linear.** If the relationship is already linear, plot $y$ against $x$ directly.

**Power law.** If

$$
y=ax^n,
$$

take logarithms of both sides:

$$
\lg y=n\lg x+\lg a.
$$

A graph of $\lg y$ against $\lg x$ is a straight line with gradient $n$ and intercept $\lg a$.

**Exponential.** If

$$
y=ae^{kx},
$$

take natural logarithms:

$$
\ln y=kx+\ln a.
$$

A graph of $\ln y$ against $x$ is a straight line with gradient $k$ and intercept $\ln a$.

Choosing the right linearisation is the analytical heart of a Paper 5 Question 2. The raw data may not look linear at all, but the right logarithmic plot will straighten them.

## 5. Logarithms and table conventions

When the analysis needs logarithms, the table gains extra columns. The argument of a logarithm must carry its unit, because the logarithm is taken of a quantity with a unit, and the logarithm itself has none. The heading is written as, for example,

$$
\lg(d/\mathrm{cm}).
$$

The number of decimal places in a logarithmic column follows the number of significant figures in the original value. If $d=76.5\ \mathrm{cm}$ (3 sig fig), then $\lg(d/\mathrm{cm})$ should be given to 3 or 4 decimal places:

$$
\lg(76.5)=1.884.
$$

Giving only 1.88 loses information that the original measurement contained; giving 1.88371 invents information it did not.

## 6. Error bars

Every data point on a Paper 5 graph carries an error bar. The error bar shows the absolute uncertainty in that point, drawn as a line through the point, in the $y$ direction (and in the $x$ direction too, if the uncertainty in $x$ is significant).

The length of the bar comes from the uncertainty propagation rules. If the plotted quantity is $T^2$ and $T$ has a $3\%$ uncertainty, then $T^2$ has a $6\%$ uncertainty, and the bar extends that far above and below the point.

Error bars turn a single line into a family of acceptable lines. Any straight line that passes through every error bar is consistent with the data.

## 7. The worst acceptable line

Draw the line of best fit first, balancing the points. Then draw the worst acceptable straight line: the steepest or shallowest line that still passes through every error bar.

The worst acceptable line should be distinguished from the best fit, either drawn as a broken line or clearly labelled. It represents the most the data will allow the gradient to move.

The uncertainty in the gradient is then

$$
\Delta m=|m_{\text{best}}-m_{\text{worst}}|.
$$

The same idea gives the uncertainty in the intercept:

$$
\Delta c=|c_{\text{best}}-c_{\text{worst}}|.
$$

This is the standard method for estimating uncertainty in a gradient at A Level.

## 8. Finding a constant and its uncertainty

Once the gradient and intercept are read, they are matched to the linearised equation to find the physical constant.

For example, suppose the relationship under test is

$$
T=2\pi\sqrt{\frac{l}{g}},
$$

and a graph of $T^2$ against $l$ is plotted. Squaring gives

$$
T^2=\frac{4\pi^2}{g}l.
$$

So the gradient of the $T^2$ against $l$ graph is $4\pi^2/g$, and

$$
g=\frac{4\pi^2}{\text{gradient}}.
$$

If the best-fit gradient is $4.02\ \mathrm{s^2\ m^{-1}}$ and the worst acceptable gradient is $4.11\ \mathrm{s^2\ m^{-1}}$, then

$$
g_{\text{best}}=\frac{4\pi^2}{4.02}=9.80\ \mathrm{m\ s^{-2}},
$$

and

$$
g_{\text{worst}}=\frac{4\pi^2}{4.11}=9.59\ \mathrm{m\ s^{-2}}.
$$

The absolute uncertainty is

$$
\Delta g=|9.80-9.59|=0.21\ \mathrm{m\ s^{-2}},
$$

so quote

$$
g=(9.8\pm0.2)\ \mathrm{m\ s^{-2}}.
$$

The final value carries a unit and an uncertainty. Both are required.

## 9. Drawing conclusions

A conclusion compares the result with what the model predicts, and it does so using uncertainty, not wishful thinking.

If a known value exists (such as $g=9.81\ \mathrm{m\ s^{-2}}$), compare it with the experimental value using percentage difference:

$$
\text{percentage difference}
=\frac{|g_{\text{exp}}-g_{\text{known}}|}{g_{\text{known}}}\times 100\%.
$$

Then compare this percentage difference with the experimental percentage uncertainty. If the percentage difference is smaller than the uncertainty, the data are consistent with the accepted value. If it is larger, either the model is wrong or there is a systematic error.

The same logic applies to testing whether two separately found values of a constant agree. Compute the percentage difference between them and compare with the sum of their percentage uncertainties.

Never claim the data "prove" the relationship. The data are consistent with it, within uncertainty, or they are not.

## 10. Identifying limitations

An evaluation names the real weaknesses of the procedure, not generic ones. For each limitation, state the quantity being measured and why it is uncertain.

Good limitations are specific to the experiment:

- "The temperature of the wire was not monitored, so its resistance may have changed as current heated it."
- "The stopwatch was started and stopped by hand, so reaction time limits the timing of short intervals."
- "The measurement of the spring's extension used a metre rule, so the uncertainty in each reading is about $1\ \mathrm{mm}$."

A bad limitation is one that could be pasted into any report: "human error", "the apparatus was not precise enough", "there may have been parallax error". These say nothing unless tied to a specific reading and a specific instrument.

Sort limitations into two kinds. Some threaten **reliability** (the scatter of the data, the size of the random error). Others threaten **validity** (whether the measurement tests what it claims to test, which is usually a control variable that slipped).

## 11. Suggesting improvements

An improvement should address a specific limitation you just named, and it should be realistic in a school laboratory.

- If reaction time limits the timing of an oscillation, use a stopwatch with a larger number of oscillations timed together, or use light gates connected to a data logger.
- If a metre rule limits the precision of a small extension, use a set-square and a travelling microscope, or measure a larger extension by using a longer wire.
- If heat loss limits a thermal experiment, use a lagged container and a lid.

An improvement that could have been made with the apparatus already provided, while following the question's instructions, will not gain credit. The improvement has to go beyond what was already available.

## 12. Safety

A plan should include a brief assessment of risk and a precaution. The precaution should match the risk.

- A load falling from a height: use a sand tray or box below the mass, and keep feet clear.
- A hot liquid or heating element: use a heatproof mat, and handle the beaker with tongs or gloves.
- A stretched wire under tension: wear safety spectacles, and keep faces away from the line of the wire.
- A laser or bright light: do not look directly into the beam; warn others.

A generic "be careful" is not a safety precaution. Name the hazard, then name the action.

## 13. Sensors and data loggers

The syllabus expects you to be able to describe the use of a few instruments that extend what a manual experiment can do.

- An **oscilloscope** (or storage oscilloscope) measures voltage, current (via a known resistor), time intervals and frequency. The timebase sets the horizontal scale; the $Y$-gain sets the vertical scale.
- **Light gates** connected to a data logger can measure the time an object takes to pass through, and hence velocity and acceleration, free of hand-timing error.
- A **motion sensor** with a data logger records position against time and can derive velocity and acceleration curves.

These instruments reduce random error (by removing human reaction time) and can reveal effects too fast or too small for manual reading.

## Worked-thinking pattern

1. Read the question and identify the relationship being tested.
2. Name the independent, dependent and control variables, saying how each control is held constant.
3. Describe the apparatus and method, with a diagram, over the largest range possible.
4. Rewrite the relationship as $y=mx+c$, deciding what to plot on each axis.
5. Complete the table, including any logarithmic columns, with correct headings and significant figures.
6. Plot the graph with error bars, and draw the best fit and worst acceptable lines.
7. Read the gradient and intercept, and use them to find the constant with its uncertainty.
8. State the conclusion by comparing percentage difference with percentage uncertainty.
9. Name specific limitations and pair each with a realistic improvement.

## Common traps

- Naming a control variable without saying how it is held constant.
- Using a small range of the independent variable, so the gradient is hard to read.
- Linearising wrongly, so the gradient does not correspond to the expected constant.
- Forgetting the unit inside a logarithm, writing $\lg d$ instead of $\lg(d/\mathrm{cm})$.
- Giving too few decimal places in a logarithmic column.
- Drawing a worst acceptable line that does not pass through every error bar.
- Reading the gradient from two points that are close together.
- Quoting a final value without a unit or without an uncertainty.
- Claiming the data "prove" the relationship, rather than being consistent with it.
- Listing generic limitations ("human error") not tied to a specific reading.
- Suggesting an improvement that was already possible with the apparatus provided.
- Writing "be careful" instead of naming a hazard and a matching precaution.

## Quick self-check

After working through this note, you should be able to:

- Identify the independent, dependent and control variables in an experiment, and state how each control is held constant.
- Describe a workable method with a clear diagram and a sensible range.
- Linearise $y=ax^n$ and $y=ae^{kx}$ into straight-line forms.
- Set up a table with logarithmic columns using the correct heading conventions.
- Draw a graph with error bars and both a best-fit and a worst acceptable line.
- Estimate the uncertainty in the gradient and intercept from the two lines.
- Find a physical constant from the gradient, with its unit and uncertainty.
- Decide whether data support a relationship by comparing percentage difference with percentage uncertainty.
- Name specific limitations and pair each with a realistic improvement.
- State a relevant hazard and a matching safety precaution.

## Connections

- [[10 Physics/02 Experimental Thinking/Measurement and Data Presentation/00 Overview|Measurement and Data Presentation]]
- [[10 Physics/01 Topics/17 Oscillations/00 Overview|Oscillations]]
- [[10 Physics/01 Topics/19 Capacitance/00 Overview|Capacitance]]
- [[10 Physics/01 Topics/23 Nuclear Physics/00 Overview|Nuclear Physics]]
- [[10 Physics/04 Reference/Math Tools and Formulae|Math Tools and Formulae]]
