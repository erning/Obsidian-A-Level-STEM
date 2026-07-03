---
title: Electricity Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/09 Electricity/00 Overview|Electricity]]"
status: draft
tags:
  - physics/9702/topic
  - physics/9702/electricity
  - lecture-notes
---

# Electricity Lecture Notes

Electricity is best learned as two linked stories: charge flow and energy transfer. Current tells you how quickly charge passes a point. Potential difference tells you how much energy is transferred per unit charge. Resistance tells you how strongly a component opposes current for a given potential difference.

Every formula in this topic is attached to one of those ideas. If you keep charge, energy, and resistance separate in your head, the algebra becomes much less mysterious.

## Source Route

- Primary syllabus source: CAIE Physics 9702, Topic 9 Electricity.
- Main subtopics: electric current, potential difference and power, resistance and resistivity.
- Coursebook route: electric current, potential difference, resistance, $I$-$V$ characteristics, temperature effects, LDRs, thermistors, and resistivity.
- Useful earlier knowledge: SI units, rate, energy transfer, power, graph gradients, and proportionality.

## Visual Guide

![[assets/generated/physics/electricity.svg]]

The visual guide shows the basic circuit language: charge flows around a complete circuit, potential difference is measured across a component, and resistance controls the size of the current.

## 1. Electric Current as Flow of Charge

An electric current is a flow of charge carriers. Charge carriers are particles that carry electric charge and can move through a material or through a beam.

In a metal, the charge carriers are free electrons. The metal ions are fixed in position in the lattice, while the electrons are mobile. In an electrolyte, both positive and negative ions can move. In a particle beam, the charge carriers might be protons or electrons.

Current is defined as the rate of flow of charge:

$$
I = \frac{Q}{t}
$$

or

$$
Q = It
$$

where:

- $I$ is current in amperes, $\text{A}$
- $Q$ is charge in coulombs, $\text{C}$
- $t$ is time in seconds, $\text{s}$

One ampere means one coulomb of charge passes a point each second:

$$
1\ \text{A} = 1\ \text{C s}^{-1}
$$

When the current varies, the more precise idea is that current is the rate of flow of charge at that instant. In this topic most calculations use steady current, so $Q = It$ is enough.

## 2. Conventional Current and Electron Flow

The direction of conventional current is defined as the direction in which positive charge would flow. In a simple circuit with a cell, conventional current goes from the positive terminal of the cell around the external circuit to the negative terminal.

In a metal wire, the actual mobile charge carriers are electrons. Electrons have negative charge, so their drift is opposite to the direction of conventional current.

This does not mean the circuit waits for one electron to travel all the way around. Free electrons are already present throughout the metal. When the circuit is completed, an electric field is established in the wire and electrons throughout the circuit begin to drift almost immediately.

Keep these directions distinct:

- conventional current in a metal: from positive terminal to negative terminal through the external circuit
- electron drift in a metal: from negative terminal to positive terminal through the external circuit
- current due to positive charge carriers: same direction as carrier motion
- current due to negative charge carriers: opposite direction to carrier motion

## 3. Quantisation of Charge

Electric charge is quantised. This means charge occurs in fixed-sized packets, not as any arbitrary amount.

The elementary charge has magnitude

$$
e = 1.60 \times 10^{-19}\ \text{C}
$$

An electron has charge $-e$. A proton has charge $+e$. Ions usually carry charges such as $+e$, $-e$, $+2e$, or $-2e$.

For an isolated object or ion, the total charge is an integer multiple of $e$:

$$
Q = Ne
$$

where $N$ is an integer, with sign included if needed.

For example, $3.20 \times 10^{-19}\ \text{C}$ is possible because it is $2e$. A charge such as $2.50 \times 10^{-19}\ \text{C}$ is not a possible net charge for an ordinary isolated object because it is not an integer multiple of $e$.

## 4. Current in a Conductor: Drift Velocity

The equation for current in a current-carrying conductor is

$$
I = Anvq
$$

where:

- $A$ is the cross-sectional area of the conductor, in $\text{m}^2$
- $n$ is the number density of charge carriers, in $\text{m}^{-3}$
- $v$ is the mean drift velocity of the charge carriers, in $\text{m s}^{-1}$
- $q$ is the charge on each charge carrier, in $\text{C}$

This equation comes from counting how much charge passes through a cross-section each second. In one second, carriers with drift velocity $v$ move a distance $v$. The volume of conductor that passes the cross-section is $Av$. The number of carriers in that volume is $Anv$. The charge carried through is therefore $Anvq$.

For electrons in a metal, $q$ is negative if sign is being tracked. In most magnitude calculations, use $q = e$ and take $I$ and $v$ as positive magnitudes in their chosen directions.

The mean drift velocity in a metal is usually very small, often a fraction of a millimetre per second. This surprises many learners because a lamp lights almost immediately. The reason is that current begins throughout the circuit when the electric field is established, while individual electrons drift slowly.

The equation also gives useful physical predictions:

- For a fixed wire and material, larger current means larger drift velocity.
- For a fixed current, a smaller cross-sectional area means larger drift velocity.
- For a fixed current and area, a smaller number density means larger drift velocity.

Check units:

$$
\text{m}^2 \times \text{m}^{-3} \times \text{m s}^{-1} \times \text{C}
= \text{C s}^{-1}
= \text{A}
$$

## 5. Potential Difference

Potential difference is about energy transfer. The potential difference across a component is defined as the energy transferred per unit charge as charge passes through the component.

$$
V = \frac{W}{Q}
$$

where:

- $V$ is potential difference in volts, $\text{V}$
- $W$ is energy transferred, or work done, in joules, $\text{J}$
- $Q$ is charge in coulombs, $\text{C}$

One volt means one joule per coulomb:

$$
1\ \text{V} = 1\ \text{J C}^{-1}
$$

Rearranging gives

$$
W = VQ
$$

This is often the most useful interpretation: if each coulomb transfers $V$ joules of energy, then $Q$ coulombs transfer $VQ$ joules.

A voltmeter is connected in parallel with a component because potential difference is measured between the two ends of that component.

Be precise with language. Current is not used up in a component. Energy is transferred in a component. The same charge can pass through several components in a series circuit, losing energy in each one.

## 6. Electrical Power

Power is the rate of energy transfer:

$$
P = \frac{W}{t}
$$

Combining $V = \frac{W}{Q}$ with $I = \frac{Q}{t}$ gives

$$
P = VI
$$

where $P$ is in watts, $\text{W}$.

For a resistor or component where resistance is being used in the calculation, combine $P = VI$ with $V = IR$:

$$
P = I^2R
$$

and

$$
P = \frac{V^2}{R}
$$

Choose the form that matches the known quantities:

- Use $P = VI$ when $V$ and $I$ are known.
- Use $P = I^2R$ when current and resistance are known.
- Use $P = \frac{V^2}{R}$ when potential difference and resistance are known.

These equations describe the rate at which electrical energy is transferred to other forms, often thermal energy, light, sound, or kinetic energy.

If time is involved, use

$$
W = Pt
$$

and combine it with the electrical equations when needed:

$$
W = VIt
$$

## 7. Resistance

Resistance is defined as the ratio of potential difference across a component to the current through it:

$$
R = \frac{V}{I}
$$

The unit of resistance is the ohm, $\Omega$:

$$
1\ \Omega = 1\ \text{V A}^{-1}
$$

Rearranging the definition gives

$$
V = IR
$$

This equation is always a way to calculate the resistance at a particular operating point, provided $V$ is the p.d. across the component and $I$ is the current through it.

Do not confuse $V = IR$ with Ohm's law. Ohm's law is a statement about proportionality and constant resistance under constant physical conditions. The equation $R = \frac{V}{I}$ defines resistance even for non-ohmic components, where $R$ changes with $V$, $I$, temperature, or light intensity.

An ammeter is connected in series because it measures the current through a component. A voltmeter is connected in parallel because it measures the p.d. across a component.

## 8. Ohm's Law and $I$-$V$ Characteristics

A conductor obeys Ohm's law if the current in it is directly proportional to the potential difference across its ends, provided physical conditions such as temperature remain constant.

For an ohmic conductor at constant temperature:

$$
I \propto V
$$

and the $I$-$V$ characteristic is a straight line through the origin.

Be careful about graph axes. For a graph of $I$ against $V$, the gradient is

$$
\frac{I}{V} = \frac{1}{R}
$$

For a graph of $V$ against $I$, the gradient is

$$
\frac{V}{I} = R
$$

A metallic conductor at constant temperature has a straight-line $I$-$V$ characteristic through the origin. If the p.d. is reversed, the current reverses, and the graph is symmetrical through the origin.

## 9. Filament Lamps

A filament lamp is non-ohmic. Its $I$-$V$ characteristic passes through the origin but curves as the current increases.

At small currents, the filament is relatively cool and its resistance is lower. As current increases, the filament gets hotter. The metal ions in the filament vibrate more strongly, so conduction electrons collide with them more often. The mean drift velocity for a given electric field is reduced, so the resistance increases.

For an $I$ against $V$ graph, this means the graph becomes less steep as $|V|$ increases. A larger p.d. still gives a larger current, but not in direct proportion.

The important explanation is:

1. Increasing current heats the filament.
2. Higher temperature makes metal ions vibrate more.
3. Electrons collide more frequently with the ions.
4. Resistance increases.

## 10. Semiconductor Diodes

A semiconductor diode allows current much more easily in one direction than the other.

In forward bias, the diode is connected so that it can conduct. For a silicon diode, the current remains very small until the p.d. reaches about $0.6\ \text{V}$. Above this threshold voltage, the current increases rapidly and the diode has a much lower resistance.

In reverse bias, the diode allows only a tiny current, so its resistance is very large.

The diode $I$-$V$ characteristic is not a straight line and is not symmetrical about the origin. A diode is therefore non-ohmic.

For this course, remember the shape:

- almost no current for reverse bias
- almost no current for small forward p.d.
- rapid rise in current after about $0.6\ \text{V}$ for a silicon diode

## 11. Thermistors and LDRs

A thermistor is a component whose resistance changes strongly with temperature. In this course, assume a thermistor has a negative temperature coefficient unless told otherwise. That means its resistance decreases as temperature increases.

For an NTC thermistor:

- higher temperature gives lower resistance
- lower temperature gives higher resistance

The microscopic reason is different from a metal. In a semiconductor thermistor, increasing temperature releases many more charge carriers. This increase in charge carrier number is more important than the increase in collisions, so the resistance falls.

A light-dependent resistor, or LDR, is a semiconductor component whose resistance decreases as light intensity increases. Light releases additional charge carriers in the semiconductor, so the material conducts more easily.

For an LDR:

- brighter light gives lower resistance
- darker conditions give higher resistance

These components are useful in sensing circuits because their resistance changes when the environment changes.

## 12. Resistivity

Resistance depends on the dimensions of a conductor and on the material. For a wire at constant temperature:

- a longer wire has greater resistance
- a wire with larger cross-sectional area has lower resistance
- different materials have different resistances even with the same length and area

The material property that describes this is resistivity, $\rho$.

For a uniform conductor:

$$
R = \frac{\rho L}{A}
$$

where:

- $R$ is resistance in $\Omega$
- $\rho$ is resistivity in $\Omega\ \text{m}$
- $L$ is length in $\text{m}$
- $A$ is cross-sectional area in $\text{m}^2$

Rearranging gives

$$
\rho = \frac{RA}{L}
$$

The unit is ohm metre, $\Omega\ \text{m}$, not ohm per metre.

If a wire has diameter $d$, its cross-sectional area is

$$
A = \frac{\pi d^2}{4}
$$

Make sure the diameter is in metres before calculating area.

Resistivity is a property of the material at a stated temperature. Changing the length or area of a sample changes its resistance, but it does not change the material's resistivity. Changing temperature can change resistivity.

For metals, resistivity generally increases as temperature increases because lattice ions vibrate more and conduction electrons collide more often.

## 13. Working Routine

Use this routine for electricity questions:

1. Decide whether the question is about charge flow, energy per charge, power, resistance, an $I$-$V$ graph, or resistivity.
2. Write the definition before the formula when the concept is new.
3. Convert units early: minutes to seconds, millimetres to metres, $\text{mm}^2$ to $\text{m}^2$, and kilowatts to watts.
4. Check whether current is conventional current, electron flow, or just a magnitude.
5. For $I$-$V$ graphs, check which quantity is on each axis before using a gradient.
6. For resistivity, calculate cross-sectional area carefully.
7. For component behaviour, explain the physical change, not only the graph shape.

## Common Traps

- Saying current is used up. Charge flows around the circuit; energy is transferred in components.
- Treating potential difference as the same thing as current.
- Forgetting that electron flow in a metal is opposite to conventional current.
- Using $Q = It$ with time left in minutes or hours.
- Treating $V = IR$ as Ohm's law. Ohm's law is the proportionality condition at constant physical conditions.
- Reading resistance from the gradient of an $I$ against $V$ graph. The gradient is $\frac{1}{R}$ for that axis choice.
- Forgetting that a filament lamp's resistance increases as it heats.
- Using diameter instead of cross-sectional area in $R = \frac{\rho L}{A}$.
- Writing the unit of resistivity as $\Omega\ \text{m}^{-1}$. It is $\Omega\ \text{m}$.

## Quick Self-Check

You should be able to answer these without looking back:

- What is the difference between conventional current and electron flow in a metal?
- What does it mean to say charge is quantised?
- What does each symbol in $I = Anvq$ mean?
- Why can electron drift be slow even though a lamp lights almost immediately?
- What is potential difference in terms of energy and charge?
- Which power equation should you use if you know $I$ and $R$?
- What is the difference between $V = IR$ and Ohm's law?
- How do the $I$-$V$ characteristics of a metal conductor, filament lamp, and diode differ?
- What happens to the resistance of an LDR when light intensity increases?
- Why is the unit of resistivity $\Omega\ \text{m}$?

## Connections

- [[10 Physics/01 Topics/10 DC Circuits/00 Overview|D.C. Circuits]] uses these definitions to analyse complete circuits.
- [[10 Physics/01 Topics/18 Electric Fields/00 Overview|Electric Fields]] gives a deeper model of force and energy per unit charge.
- [[10 Physics/01 Topics/20 Magnetic Fields/00 Overview|Magnetic Fields]] uses current as moving charge that produces magnetic effects.
