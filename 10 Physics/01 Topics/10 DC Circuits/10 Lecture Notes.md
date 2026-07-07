---
title: D.C. Circuits Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/10 DC Circuits/00 Overview|D.C. Circuits]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/electricity
  - lecture-notes
---

# D.C. Circuits Lecture Notes

D.C. circuit analysis is conservation of charge and conservation of energy written as circuit equations. Kirchhoff's first law keeps track of charge at junctions. Kirchhoff's second law keeps track of energy around loops. Series and parallel resistor formulae, internal resistance, potential dividers, and potentiometers all come from those two conservation ideas.

The word "circuit" is important. A current needs a complete conducting path. A potential difference is measured between two points. A component is not understood only by its value in ohms, but by where it sits in the circuit and what current and p.d. it has.

## Source Route

- Primary syllabus source: CAIE Physics 9702, Topic 10 D.C. circuits.
- Main subtopics: practical circuits, Kirchhoff's laws, and potential dividers.
- Coursebook route: Kirchhoff's laws, resistor combinations, internal resistance, potential dividers, sensors, and potentiometer circuits.
- Useful earlier knowledge: current, potential difference, e.m.f., resistance, power, $I$-$V$ characteristics, LDRs, and thermistors.

## Visual Guide

![[assets/generated/physics/dc-circuits.svg]]

The visual guide is a reminder to look for structure before calculating: series sections carry the same current, parallel branches share the same p.d., and Kirchhoff's laws are the checks that keep the analysis consistent.

## 1. Practical Circuit Language

A circuit diagram is a model. It replaces physical components with standard symbols so that the electrical structure is clear. The position of each component and connection matters more than the physical shape of the wires drawn on the page.

When reading or drawing a circuit:

- identify the source or sources of e.m.f.
- mark junctions where current can split or combine
- identify complete loops
- decide which components are in series and which are in parallel
- place ammeters in series with the current being measured
- place voltmeters in parallel across the component or section being measured

An ideal ammeter has zero resistance, so it does not change the current it is measuring. A real ammeter has low resistance.

An ideal voltmeter has infinite resistance, so it draws no current. A real voltmeter has high resistance. If a voltmeter has resistance that is not much larger than the component it is measuring, it can change the circuit. This is called loading.

## 2. E.M.F. and Potential Difference

The electromotive force, or e.m.f., of a source is the energy transferred per unit charge in driving charge around a complete circuit.

$$
E = \frac{W}{Q}
$$

The unit is the volt, $\text{V}$, because e.m.f. is also energy per unit charge:

$$
1\ \text{V} = 1\ \text{J C}^{-1}
$$

The name electromotive force is historical. E.m.f. is not a force. It is an energy per unit charge.

Potential difference, or p.d., across a component is the energy transferred per unit charge as charge passes through that component.

The distinction is energy gained versus energy lost:

- In a source of e.m.f., charge gains energy.
- In a component with p.d. across it, charge transfers energy to the component or surroundings.

For example, a $6.0\ \text{V}$ cell gives $6.0\ \text{J}$ of energy to each coulomb of charge that it drives around the circuit. A resistor with a p.d. of $2.0\ \text{V}$ receives $2.0\ \text{J}$ from each coulomb of charge passing through it.

## 3. Kirchhoff's First Law

Kirchhoff's first law states that the sum of the currents entering a junction is equal to the sum of the currents leaving the junction.

$$
\sum I_{\text{in}} = \sum I_{\text{out}}
$$

This is conservation of charge. Charge cannot pile up indefinitely at a junction in a steady D.C. circuit. The rate at which charge enters the junction must equal the rate at which charge leaves it.

For example, if a current of $5.0\ \text{A}$ enters a junction and splits into two branches, one branch carrying $2.0\ \text{A}$ and the other carrying $I$, then

$$
5.0 = 2.0 + I
$$

so

$$
I = 3.0\ \text{A}
$$

If you choose an arrow direction for an unknown current and the answer is negative, the actual current is in the opposite direction. This is not a failure. It is often the cleanest way to handle circuit problems.

## 4. Kirchhoff's Second Law

Kirchhoff's second law states that the sum of the e.m.f.s around any closed loop is equal to the sum of the potential differences around that loop.

$$
\sum E = \sum V
$$

This is conservation of energy. If $1\ \text{C}$ of charge goes around a complete loop and returns to the starting point, its energy cannot have changed overall. Energy gained from sources must equal energy transferred to components.

For a simple loop with a cell of e.m.f. $E$ and two resistors $R_1$ and $R_2$ in series, the same current $I$ passes through both resistors. Kirchhoff's second law gives

$$
E = IR_1 + IR_2
$$

When sources oppose each other, their e.m.f.s must be given signs. If you choose a loop direction, a source that drives charge in your chosen direction is positive, while a source that opposes that direction is negative. The same sign care is needed for resistor p.d.s when your chosen loop direction is opposite to the current through a resistor.

A reliable method is:

1. Choose a direction around the loop.
2. Mark current directions.
3. Add e.m.f.s as positive if they raise potential in the chosen direction, negative if they lower it.
4. Add resistor p.d.s according to whether you travel with or against the current.
5. Solve the equations and interpret negative currents as currents opposite to the assumed direction.

## 5. Series Resistors

Resistors are in series when the same current passes through each of them and there is no junction between them where current can split.

For two series resistors $R_1$ and $R_2$, the p.d. across the combination is the sum of the p.d.s across the resistors:

$$
V = V_1 + V_2
$$

Using $V = IR$:

$$
IR = IR_1 + IR_2
$$

Cancelling the common current gives

$$
R = R_1 + R_2
$$

For several resistors in series:

$$
R = R_1 + R_2 + R_3 + \cdots
$$

Series rules:

- The current is the same through every component.
- The total p.d. is shared between the components.
- The combined resistance is larger than any individual resistance.
- Larger resistance gets a larger share of the p.d. in the same series chain.

## 6. Parallel Resistors

Resistors are in parallel when they are connected across the same two points, so each branch has the same p.d.

For two parallel resistors, the current entering the branch point is the sum of the branch currents:

$$
I = I_1 + I_2
$$

The p.d. across each resistor is the same, so

$$
I = \frac{V}{R}, \quad I_1 = \frac{V}{R_1}, \quad I_2 = \frac{V}{R_2}
$$

Substitute into Kirchhoff's first law:

$$
\frac{V}{R} = \frac{V}{R_1} + \frac{V}{R_2}
$$

Cancel the common p.d.:

$$
\frac{1}{R} = \frac{1}{R_1} + \frac{1}{R_2}
$$

For several resistors in parallel:

$$
\frac{1}{R} = \frac{1}{R_1} + \frac{1}{R_2} + \frac{1}{R_3} + \cdots
$$

Parallel rules:

- Each branch has the same p.d.
- The total current is the sum of the branch currents.
- The combined resistance is smaller than the smallest individual branch resistance.
- Adding another parallel branch decreases the total resistance and increases the current drawn from the source, if the source p.d. remains the same.

Never add parallel resistances directly. Add their reciprocals, then invert the result.

## 7. Solving Simple Circuit Problems

Most D.C. circuit questions can be solved by reducing the circuit in stages or by writing Kirchhoff equations.

Use reduction when the circuit is clearly made from series and parallel groups:

1. Identify the smallest series or parallel group.
2. Replace it with an equivalent resistance.
3. Repeat until the total resistance is found.
4. Use the source p.d. or e.m.f. to find total current.
5. Work back through the circuit to find branch currents and p.d.s.

Use Kirchhoff equations when the circuit has several loops, several sources, or no simple reduction route:

1. Label unknown currents with arrows.
2. Apply Kirchhoff's first law at junctions.
3. Choose independent loops.
4. Apply Kirchhoff's second law to each loop.
5. Solve the simultaneous equations.
6. Interpret signs and check with energy and charge conservation.

Good checks:

- At every junction, incoming current equals outgoing current.
- Around every complete loop, energy gained per coulomb equals energy lost per coulomb.
- Parallel branches have the same p.d.
- Series components have the same current.
- The total resistance of a parallel group is less than the smallest branch resistance.

## 8. Internal Resistance and Terminal P.D.

A real source of e.m.f. has internal resistance. A cell can be modelled as an ideal source of e.m.f. $E$ in series with an internal resistance $r$.

When the source supplies a current $I$ to an external resistance $R$, the current passes through both $R$ and $r$. Kirchhoff's second law gives

$$
E = I(R + r)
$$

or

$$
E = IR + Ir
$$

The terminal potential difference, $V$, is the p.d. across the external circuit. For the simple external resistor,

$$
V = IR
$$

Since $Ir$ is the p.d. across the internal resistance, the terminal p.d. is

$$
V = E - Ir
$$

This equation applies to a source delivering current. The larger the current drawn from the source, the larger the lost volts $Ir$ inside the source, and the smaller the terminal p.d.

Physical interpretation:

- $E$ is energy supplied per coulomb by the source.
- $Ir$ is energy per coulomb transferred inside the source, usually as thermal energy.
- $V$ is energy per coulomb available to the external circuit.

If the external resistance is very large compared with $r$, the current is small and $V$ is close to $E$. If the external resistance is small, the current is large and the terminal p.d. can fall noticeably.

To determine $E$ and $r$ experimentally, vary the external resistance and measure terminal p.d. $V$ and current $I$. From

$$
V = E - Ir
$$

a graph of $V$ against $I$ is a straight line with:

- y-intercept $E$
- gradient $-r$

## 9. Potential Dividers

A potential divider uses two or more components in series to produce an output p.d. that is a fraction of the input p.d.

For two resistors $R_1$ and $R_2$ in series across an input p.d. $V_{\text{in}}$, with output taken across $R_2$:

$$
V_{\text{out}} = V_{\text{in}} \frac{R_2}{R_1 + R_2}
$$

This comes from the fact that the same current passes through both resistors:

$$
I = \frac{V_{\text{in}}}{R_1 + R_2}
$$

and the p.d. across $R_2$ is

$$
V_{\text{out}} = IR_2
$$

So the p.d. is shared in proportion to resistance. The larger the resistance across which the output is taken, the larger the output p.d.

If the output is taken across $R_1$ instead, the numerator becomes $R_1$. Always identify which component the output is across.

A variable resistor can act as a potential divider. Moving the slider changes the fraction of the total resistance below or above the slider, so the output p.d. can vary continuously between two limiting values.

The potential divider equation assumes the output device draws negligible current. If a load is connected across the output and has resistance comparable with the output resistor, it changes the effective resistance of that part of the divider. This loading effect changes $V_{\text{out}}$.

## 10. LDR and Thermistor Potential Dividers

LDRs and thermistors turn environmental changes into resistance changes. A potential divider turns resistance changes into voltage changes.

An LDR has resistance that decreases as light intensity increases.

If the output is taken across the LDR:

- bright light makes $R_{\text{LDR}}$ smaller
- the LDR gets a smaller share of the input p.d.
- $V_{\text{out}}$ decreases

If the output is taken across the fixed resistor instead:

- bright light makes $R_{\text{LDR}}$ smaller
- the fixed resistor gets a larger share of the input p.d.
- $V_{\text{out}}$ increases

For an NTC thermistor, resistance decreases as temperature increases.

If the output is taken across the thermistor:

- higher temperature makes $R_{\text{thermistor}}$ smaller
- the thermistor gets a smaller share of the input p.d.
- $V_{\text{out}}$ decreases

If the output is taken across the fixed resistor instead:

- higher temperature makes $R_{\text{thermistor}}$ smaller
- the fixed resistor gets a larger share of the input p.d.
- $V_{\text{out}}$ increases

The same logic works for any sensor divider. First decide which resistance changes, then decide which component the output is measured across.

## 11. Potentiometers and Null Methods

A potentiometer is used to compare potential differences. It is a special kind of potential divider, usually made from a uniform resistance wire with a driver cell connected across it.

If the wire is uniform, the p.d. along the wire is proportional to length. This means a length $l$ of wire corresponds to a definite fraction of the p.d. across the whole wire.

In a potentiometer comparison, a test cell or p.d. is connected through a galvanometer and a movable contact called a jockey. The jockey is moved until the galvanometer shows zero deflection. This is the balance point.

At balance:

- the galvanometer current is zero
- no current is drawn from the cell or p.d. being compared
- the p.d. along the selected length of potentiometer wire equals the p.d. being measured

This is a null method. A null method looks for zero current rather than using a meter reading that draws current from the circuit being measured. That is why a potentiometer can compare e.m.f.s accurately.

If two p.d.s give balance lengths $l_1$ and $l_2$ on the same potentiometer wire with the same driver circuit, then

$$
\frac{V_1}{V_2} = \frac{l_1}{l_2}
$$

For two cells whose e.m.f.s are being compared:

$$
\frac{E_1}{E_2} = \frac{l_1}{l_2}
$$

The driver cell must provide a p.d. along the potentiometer wire large enough to balance the unknown p.d. If the unknown p.d. is larger than the p.d. available along the wire, no balance point is found.

Do not slide the jockey along the wire while pressing hard. That can damage the wire and make its resistance non-uniform.

## 12. Working Routine

Use this routine for D.C. circuit questions:

1. Redraw the circuit if the layout is visually confusing.
2. Mark junctions, branches, and loops.
3. Label currents with assumed directions.
4. Decide whether series and parallel reduction is enough.
5. If not, write Kirchhoff's first law at junctions and second law around independent loops.
6. Keep signs consistent for e.m.f.s and resistor p.d.s.
7. For internal resistance, separate $E$, $Ir$, and terminal p.d. $V$.
8. For potential dividers, identify exactly where $V_{\text{out}}$ is measured.
9. Check with limiting cases, such as very large resistance, very small resistance, or zero current.

## Common Traps

- Treating every drawn row of components as a series path. Series means same current, not just side by side on the page.
- Treating every pair of nearby components as parallel. Parallel means connected across the same two points.
- Forgetting that a parallel group has lower resistance than any individual branch.
- Adding p.d.s around a loop without considering the direction of each source.
- Treating e.m.f. and terminal p.d. as always equal. They differ when internal resistance has a non-negligible p.d. across it.
- Using $V_{\text{out}} = V_{\text{in}}\frac{R_2}{R_1 + R_2}$ without checking which resistor the output is across.
- Ignoring loading when the output device has resistance comparable with the divider resistance.
- Forgetting that a null galvanometer reading means zero current through the galvanometer, not zero p.d. everywhere.

## Quick Self-Check

You should be able to answer these without looking back:

- Why is Kirchhoff's first law a statement of conservation of charge?
- Why is Kirchhoff's second law a statement of conservation of energy?
- How do you derive the formula for resistors in series using Kirchhoff's laws?
- How do you derive the formula for resistors in parallel using Kirchhoff's laws?
- Why is terminal p.d. less than e.m.f. for a source delivering current?
- What do the intercept and gradient of a $V$ against $I$ graph give for a source with internal resistance?
- In a potential divider, how does changing the lower resistor change $V_{\text{out}}$?
- How can an LDR or thermistor be used to make a sensor voltage?
- Why is a potentiometer balance method accurate for comparing e.m.f.s?

## Connections

- [[10 Physics/01 Topics/09 Electricity/00 Overview|Electricity]] provides current, p.d., resistance, power, LDR, and thermistor definitions.
- [[10 Physics/01 Topics/19 Capacitance/00 Overview|Capacitance]] uses potential difference, charge, and circuits with time-dependent behaviour.
- [[10 Physics/01 Topics/21 Alternating Currents/00 Overview|Alternating Currents]] extends circuit ideas to time-varying current and voltage.
