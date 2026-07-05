---
title: D.C. Circuits Worked Examples
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/10 DC Circuits/00 Overview|D.C. Circuits]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/electricity
  - worked-examples
---

# D.C. Circuits Worked Examples

These examples model the standard CAIE route through practical circuits,
Kirchhoff's laws, resistor networks, internal resistance, potential dividers,
and potentiometer circuits.

## Source Route

- Syllabus: CAIE Physics 9702 section 10, D.C. circuits.
- Coursebook route: Chapters 9 and 11, especially Kirchhoff's laws, series and
  parallel resistors, meters, internal resistance, potential dividers, and
  potentiometers.

## Example 1: Meter Connections and Loading

**Prompt.** A $10\ \mathrm{V}$ supply is connected to a
$100\ \Omega$ resistor. Find the current with an ideal ammeter. Then find the
ammeter reading if the ammeter has resistance $5.0\ \Omega$ and is connected
in series.

**Solution.**

An ammeter is connected in series so that the current to be measured passes
through it.

With an ideal ammeter, the resistance is zero, so

$$
I=\frac{V}{R}
=\frac{10}{100}
=0.100\ \mathrm{A}.
$$

With a $5.0\ \Omega$ ammeter in series, the total resistance is

$$
100+5.0=105\ \Omega.
$$

The current is

$$
I=\frac{10}{105}
=0.0952\ \mathrm{A}.
$$

The reading is smaller because the real ammeter has added resistance to the
circuit. This is why an ammeter should have very low resistance.

**What this example trains.** A measuring instrument is part of the circuit
unless it can be treated as ideal.

## Example 2: Kirchhoff's First Law at a Junction

**Prompt.** A current of $4.8\ \mathrm{A}$ enters a junction. Three currents
leave: $1.2\ \mathrm{A}$, $0.9\ \mathrm{A}$, and $I$. Find $I$.

**Solution.**

Kirchhoff's first law is conservation of charge:

$$
\sum I_{\text{in}}=\sum I_{\text{out}}.
$$

So

$$
4.8=1.2+0.9+I.
$$

Therefore

$$
I=4.8-2.1
=2.7\ \mathrm{A}.
$$

**What this example trains.** Current does not disappear at a junction.

## Example 3: Mixed Series and Parallel Network

**Prompt.** A $6.0\ \Omega$ resistor and a $3.0\ \Omega$ resistor are in
parallel. This parallel group is in series with a $4.0\ \Omega$ resistor and a
$12\ \mathrm{V}$ supply of negligible internal resistance. Find the total
current and the current in each parallel branch.

**Solution.**

First find the parallel group:

$$
\frac{1}{R_p}=\frac{1}{6.0}+\frac{1}{3.0}
=\frac{1}{2.0}.
$$

So

$$
R_p=2.0\ \Omega.
$$

The total resistance is

$$
R_{\text{total}}=4.0+2.0=6.0\ \Omega.
$$

Total current:

$$
I=\frac{12}{6.0}
=2.0\ \mathrm{A}.
$$

The p.d. across the $4.0\ \Omega$ resistor is

$$
V=(2.0)(4.0)=8.0\ \mathrm{V}.
$$

So the p.d. across the parallel group is

$$
12-8.0=4.0\ \mathrm{V}.
$$

Branch currents:

$$
I_{6\Omega}=\frac{4.0}{6.0}=0.667\ \mathrm{A},
$$

$$
I_{3\Omega}=\frac{4.0}{3.0}=1.33\ \mathrm{A}.
$$

They add to $2.0\ \mathrm{A}$, as required by Kirchhoff's first law.

**What this example trains.** Reduce the network, then work back through p.d.s
and branch currents.

## Example 4: Kirchhoff's Second Law with Opposing Sources

**Prompt.** A loop contains a $12\ \mathrm{V}$ cell, a $3.0\ \mathrm{V}$ cell
opposing it, and two series resistors of $6.0\ \Omega$ and $3.0\ \Omega$.
Find the current, assuming negligible internal resistance.

**Solution.**

The net e.m.f. around the loop is

$$
12-3.0=9.0\ \mathrm{V}.
$$

The total resistance is

$$
6.0+3.0=9.0\ \Omega.
$$

Kirchhoff's second law gives

$$
\sum E=\sum IR.
$$

So

$$
9.0=I(9.0),
$$

and

$$
I=1.0\ \mathrm{A}.
$$

The current is in the direction driven by the $12\ \mathrm{V}$ cell.

**What this example trains.** Sources can add or oppose depending on loop
direction.

## Example 5: Internal Resistance and Terminal P.D.

**Prompt.** A cell has e.m.f. $5.0\ \mathrm{V}$ and internal resistance
$2.0\ \Omega$. It is connected to an external resistor of $8.0\ \Omega$. Find
the current, the lost volts inside the cell, and the terminal p.d.

**Solution.**

The total resistance is

$$
R+r=8.0+2.0=10.0\ \Omega.
$$

Current:

$$
I=\frac{E}{R+r}
=\frac{5.0}{10.0}
=0.50\ \mathrm{A}.
$$

Lost volts across the internal resistance:

$$
Ir=(0.50)(2.0)=1.0\ \mathrm{V}.
$$

Terminal p.d.:

$$
V=E-Ir
=5.0-1.0
=4.0\ \mathrm{V}.
$$

This is also $IR=(0.50)(8.0)=4.0\ \mathrm{V}$.

**What this example trains.** Terminal p.d. is less than e.m.f. when a source
delivers current through internal resistance.

## Example 6: E.M.F. and Internal Resistance from a Graph

**Prompt.** A graph of terminal p.d. $V$ against current $I$ for a power supply
is a straight line with intercept $1.50\ \mathrm{V}$ and gradient
$-0.40\ \mathrm{V\ A^{-1}}$. Find the e.m.f. and internal resistance. Then
find $V$ when $I=2.0\ \mathrm{A}$.

**Solution.**

For a source delivering current,

$$
V=E-Ir.
$$

On a $V$ against $I$ graph:

- intercept is $E$
- gradient is $-r$

Thus

$$
E=1.50\ \mathrm{V},
\qquad
r=0.40\ \Omega.
$$

At $I=2.0\ \mathrm{A}$,

$$
V=1.50-(2.0)(0.40)
=0.70\ \mathrm{V}.
$$

**What this example trains.** The gradient is negative because terminal p.d.
falls as current increases.

## Example 7: Potential Divider with Loading

**Prompt.** A $12\ \mathrm{V}$ supply is connected across two series resistors,
$R_1=2.0\ \mathrm{k\Omega}$ and $R_2=4.0\ \mathrm{k\Omega}$. The output is
taken across $R_2$. Find the unloaded output p.d. Then a
$4.0\ \mathrm{k\Omega}$ load is connected across $R_2$. Find the new output
p.d.

**Solution.**

Unloaded:

$$
V_{\text{out}}=V_{\text{in}}\frac{R_2}{R_1+R_2}
=12\frac{4.0}{2.0+4.0}
=8.0\ \mathrm{V}.
$$

With the load connected across $R_2$, the lower part of the divider is
$4.0\ \mathrm{k\Omega}$ in parallel with $4.0\ \mathrm{k\Omega}$:

$$
R_{\text{lower}}=2.0\ \mathrm{k\Omega}.
$$

Now

$$
V_{\text{out}}=12\frac{2.0}{2.0+2.0}
=6.0\ \mathrm{V}.
$$

The load reduces the effective output resistance and changes the output p.d.

**What this example trains.** The simple potential divider formula assumes the
output draws negligible current.

## Example 8: LDR Potential Divider

**Prompt.** A $6.0\ \mathrm{V}$ supply is connected across an LDR in series
with a fixed $10\ \mathrm{k\Omega}$ resistor. The output is taken across the
fixed resistor. The LDR resistance is $50\ \mathrm{k\Omega}$ in the dark and
$5.0\ \mathrm{k\Omega}$ in bright light. Find the output p.d. in both cases.

**Solution.**

Dark:

$$
V_{\text{out}}
=6.0\frac{10}{50+10}
=1.0\ \mathrm{V}.
$$

Bright light:

$$
V_{\text{out}}
=6.0\frac{10}{5.0+10}
=4.0\ \mathrm{V}.
$$

The output across the fixed resistor increases in bright light because the LDR
resistance decreases, leaving a larger share of the input p.d. across the fixed
resistor.

**What this example trains.** First identify which component the output is
across.

## Example 9: Potentiometer Comparison

**Prompt.** A standard cell of e.m.f. $1.50\ \mathrm{V}$ balances at
$60.0\ \mathrm{cm}$ on a potentiometer wire. An unknown cell balances at
$72.0\ \mathrm{cm}$ using the same driver circuit. Find the unknown e.m.f.

**Solution.**

For the same potentiometer wire and driver circuit,

$$
\frac{E_x}{E_s}=\frac{l_x}{l_s}.
$$

Thus

$$
E_x=E_s\frac{l_x}{l_s}
=1.50\frac{72.0}{60.0}
=1.80\ \mathrm{V}.
$$

At balance, the galvanometer current is zero, so no current is drawn from the
cell being measured.

**What this example trains.** A potentiometer is a null method for comparing
potential differences.

## Example 10: Designing a Divider Output

**Prompt.** A $12\ \mathrm{V}$ supply feeds two series resistors. The output is
taken across the lower resistor $R_2$. If $R_1=3.0\ \mathrm{k\Omega}$, choose
$R_2$ to give $V_{\text{out}}=3.0\ \mathrm{V}$ with no load connected.

**Solution.**

Use

$$
V_{\text{out}}=V_{\text{in}}\frac{R_2}{R_1+R_2}.
$$

Substitute:

$$
3.0=12\frac{R_2}{3.0+R_2}.
$$

So

$$
\frac{R_2}{3.0+R_2}=0.25.
$$

Therefore

$$
R_2=0.25(3.0+R_2).
$$

Thus

$$
0.75R_2=0.75,
$$

so

$$
R_2=1.0\ \mathrm{k\Omega}.
$$

**What this example trains.** Design problems use the same divider equation,
but require algebra before substitution is finished.
