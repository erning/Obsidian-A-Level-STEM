---
title: Experimental Design and Data Analysis Key Practice Solutions
subject: Physics
syllabus: 9702
parent: "[[10 Physics/02 Experimental Thinking/Experimental Design and Data Analysis/00 Overview|Experimental Design and Data Analysis]]"
status: active
tags:
  - physics/9702
  - experimental-thinking
  - solutions
---

# Experimental Design and Data Analysis Key Practice Solutions

Use these solutions to check planning logic, graph choice, uncertainty
reasoning, and evaluation quality for [[10 Physics/02 Experimental Thinking/Experimental Design and Data Analysis/30 Key Practice Problems|Key Practice Problems]].

## A. Planning and Variables

1. The independent variable is the pendulum length $l$. The dependent variable
   is the period $T$. Control variables include the mass of the bob, the
   release amplitude, the pivot/string arrangement, and the number of
   oscillations timed.

2. Use the same bob throughout to keep mass constant. Release from the same
   small marked angle each time to keep amplitude constant. Use the same pivot
   and string arrangement throughout. Time the same number of oscillations for
   each length.

3. Clamp a pendulum to a stand and measure $l$ from pivot to the centre of the
   bob with a metre rule. Vary $l$ over a large range, such as
   $0.20\ \mathrm{m}$ to $1.00\ \mathrm{m}$, using at least six values. For
   each value, displace the bob by a small angle, release without pushing, time
   $10$ or $20$ oscillations, and divide by the number of oscillations to find
   $T$. Repeat and average. Plot $T^2$ against $l$. Since

   $$
   T^2=\frac{4\pi^2}{g}l,
   $$

   the gradient is $4\pi^2/g$, so

   $$
   g=\frac{4\pi^2}{\text{gradient}}.
   $$

4. The independent variable can be current $I$, varied using a variable
   resistor or supply. The dependent variable is p.d. $V$ across the fixed
   resistor. Control variables include the same resistor and constant
   temperature, controlled by keeping current low and switching off between
   readings. Plot $V$ against $I$; the gradient is $R$.

5. Hazard: the load or spring could snap or fall. Precaution: wear eye
   protection, keep faces away from the line of the wire or spring, and place a
   tray or box below the load.

6. A wide range gives a longer graph line, reducing percentage uncertainty in
   the gradient. At least six readings show scatter and make anomalies easier
   to identify.

## B. Linearisation and Data Analysis

7. Take logarithms:

   $$
   \lg y=\lg a+n\lg x.
   $$

   Plot $\lg y$ against $\lg x$. The gradient is $n$ and the intercept is
   $\lg a$, so $a=10^{\text{intercept}}$.

8. Take natural logarithms:

   $$
   \ln y=\ln a+kx.
   $$

   Plot $\ln y$ against $x$. The gradient is $k$ and the intercept is $\ln a$,
   so $a=e^{\text{intercept}}$.

9. For a pendulum,

   $$
   T^2=\frac{4\pi^2}{g}l.
   $$

   Hence

   $$
   g=\frac{4\pi^2}{4.05}
   =9.75\ \mathrm{m\ s^{-2}}.
   $$

10. Using the worst acceptable gradient,

    $$
    g_{\text{worst}}=\frac{4\pi^2}{4.20}
    =9.40\ \mathrm{m\ s^{-2}}.
    $$

    The uncertainty is

    $$
    \Delta g=|9.75-9.40|
    =0.35\ \mathrm{m\ s^{-2}}.
    $$

    Quote

    $$
    g=(9.8\pm0.4)\ \mathrm{m\ s^{-2}}.
    $$

11. The absolute uncertainty is

    $$
    |3.60-3.25|=0.35
    $$

    in the gradient units.

12. Use $y=mx+c$:

    $$
    5.1=(1.80)(2.0)+c.
    $$

    Therefore

    $$
    c=1.5.
    $$

13. Since $L=76.5\ \mathrm{cm}$ has $3$ significant figures,
    $\lg(L/\mathrm{cm})$ should be given to about $3$ or $4$ decimal places:

    $$
    \lg(76.5)=1.884.
    $$

14. Taking natural logarithms gives

    $$
    \ln V=\ln V_0-\frac{t}{RC}.
    $$

    Plot $\ln(V/\mathrm{V})$ against $t$. The gradient is

    $$
    -\frac{1}{RC},
    $$

    so

    $$
    RC=-\frac{1}{\text{gradient}}.
    $$

## C. Conclusions, Evaluation, and Instruments

15. The experimental range is

    $$
    9.4\ \mathrm{m\ s^{-2}}\ \text{to}\ 10.0\ \mathrm{m\ s^{-2}}.
    $$

    The accepted value $9.81\ \mathrm{m\ s^{-2}}$ lies within this range, so
    the result is consistent with the accepted value.

16. Experimental data have uncertainty and only test the model under the
    conditions used. They can support or be consistent with a model; they do
    not prove it for all conditions.

17. Specific limitation: the stop-watch was started and stopped by hand, so
    reaction time gives significant uncertainty in the timing. Matching
    improvement: time more oscillations and divide by the number timed, or use
    a light gate/data logger to measure the period automatically.

18. It is weak because it does not address the main limitation. If the scatter
    comes from hand timing, improving the ruler will not significantly reduce
    the uncertainty in the dependent variable.

19. A systematic curve suggests the relationship is not linear in the plotted
    variables, the wrong linearisation has been used, or a control variable is
    changing.

20. Hazard: hot liquid can burn skin. Precaution: use a heatproof mat and
    handle the container with tongs or thermal gloves.

21. Background count rate should be measured and subtracted. The source-detector
    distance and detector geometry should be kept constant. Counting intervals
    should be kept the same or corrected for.

22. On an oscilloscope, the time-base gives the time per division. Measure the
    horizontal separation between features, multiply by the time-base, and use
    $f=1/T$ if one full period is measured.

23. Attach a card of known length to the moving object. A light gate measures
    the time for the card to block the beam. Speed is

    $$
    v=\frac{\text{card length}}{\text{blocking time}}.
    $$

24. Paper 5 improvements should go beyond the method already available. If the
    candidate could already have done the improvement using the provided
    apparatus and instructions, it is not a new improvement to the procedure.
