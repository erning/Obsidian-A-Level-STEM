---
title: 24 Electrochemistry - Worked Examples
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/a-level
  - chemistry/9701/physical-chemistry
---

# 24 Electrochemistry - Worked Examples

## Example 1: Predicting Electrolysis Products

Predict the products for molten $\ce{PbBr2}$ using inert electrodes.

Molten $\ce{PbBr2}$ contains $\ce{Pb^{2+}}$ and $\ce{Br-}$ ions only.

Cathode reduction:

$$
\ce{Pb^{2+} + 2e- -> Pb}
$$

Anode oxidation:

$$
\ce{2Br- -> Br2 + 2e-}
$$

Products: lead at the cathode and bromine at the anode.

For aqueous sodium chloride, water is also present. Concentrated $\ce{NaCl(aq)}$ usually gives $\ce{H2}$ at the cathode and $\ce{Cl2}$ at the anode. Dilute $\ce{NaCl(aq)}$ may give $\ce{O2}$ at the anode instead.

## Example 2: Mass Deposited During Electrolysis

A current of $2.00\ \text{A}$ passes through aqueous copper(II) sulfate for $30.0\ \text{min}$. Calculate the mass of copper deposited. Use $F = 96500\ \text{C mol}^{-1}$ and $A_r(\ce{Cu}) = 63.5$.

Cathode reaction:

$$
\ce{Cu^{2+} + 2e- -> Cu}
$$

Charge passed:

$$
Q = It = 2.00 \times (30.0 \times 60) = 3600\ \text{C}
$$

Moles of electrons:

$$
n(e^-) = \frac{3600}{96500} = 0.0373\ \text{mol}
$$

Moles of copper:

$$
n(\ce{Cu}) = \frac{0.0373}{2} = 0.0187\ \text{mol}
$$

Mass:

$$
m = 0.0187 \times 63.5 = 1.19\ \text{g}
$$

## Example 3: Determining The Avogadro Constant

In an electrolysis experiment, a current of $0.250\ \text{A}$ passes for $1930\ \text{s}$ and deposits $0.540\ \text{g}$ of silver. Use $A_r(\ce{Ag}) = 107.9$ and $e = 1.60 \times 10^{-19}\ \text{C}$ to estimate the Avogadro constant.

Half-equation:

$$
\ce{Ag+ + e- -> Ag}
$$

Charge:

$$
Q = 0.250 \times 1930 = 482.5\ \text{C}
$$

Moles of silver:

$$
n(\ce{Ag}) = \frac{0.540}{107.9} = 5.00 \times 10^{-3}\ \text{mol}
$$

The half-equation shows $n(e^-) = n(\ce{Ag})$, so:

$$
F = \frac{Q}{n(e^-)}
= \frac{482.5}{5.00 \times 10^{-3}}
= 9.65 \times 10^4\ \text{C mol}^{-1}
$$

$$
L = \frac{F}{e}
= \frac{9.65 \times 10^4}{1.60 \times 10^{-19}}
= 6.03 \times 10^{23}\ \text{mol}^{-1}
$$

## Example 4: Cell Potential And Electron Flow

Use the standard electrode potentials:

$$
\ce{Cu^{2+}(aq) + 2e- <=> Cu(s)} \quad E^\circ = +0.34\ \text{V}
$$

$$
\ce{Zn^{2+}(aq) + 2e- <=> Zn(s)} \quad E^\circ = -0.76\ \text{V}
$$

The more positive reduction potential is copper, so copper(II) ions are reduced at the cathode. Zinc is oxidised at the anode.

$$
E^\circ_{\text{cell}} = +0.34 - (-0.76) = +1.10\ \text{V}
$$

Overall reaction:

$$
\ce{Zn(s) + Cu^{2+}(aq) -> Zn^{2+}(aq) + Cu(s)}
$$

Electrons flow through the external circuit from zinc to copper.

## Example 5: Predicting Redox Feasibility

Decide whether $\ce{Fe^{3+}(aq)}$ can oxidise $\ce{I-(aq)}$ under standard conditions.

Data:

$$
\ce{Fe^{3+}(aq) + e- <=> Fe^{2+}(aq)} \quad E^\circ = +0.77\ \text{V}
$$

$$
\ce{I2(aq) + 2e- <=> 2I-(aq)} \quad E^\circ = +0.54\ \text{V}
$$

If $\ce{Fe^{3+}}$ oxidises $\ce{I-}$, then $\ce{Fe^{3+}}$ is reduced and iodide is oxidised.

$$
E^\circ_{\text{cell}} = +0.77 - (+0.54) = +0.23\ \text{V}
$$

The reaction is feasible under standard conditions.

$$
\ce{2Fe^{3+}(aq) + 2I-(aq) -> 2Fe^{2+}(aq) + I2(aq)}
$$

## Example 6: Nernst Equation For An Ion Pair

For:

$$
\ce{Fe^{3+}(aq) + e- <=> Fe^{2+}(aq)}
$$

$E^\circ = +0.77\ \text{V}$, $[\ce{Fe^{3+}}] = 0.010\ \text{mol dm}^{-3}$, and $[\ce{Fe^{2+}}] = 1.00\ \text{mol dm}^{-3}$.

$$
E = E^\circ + 0.059\log\frac{[\ce{Fe^{3+}}]}{[\ce{Fe^{2+}}]}
$$

$$
E = 0.77 + 0.059\log(0.010)
$$

$$
E = 0.77 + 0.059(-2.00) = 0.652\ \text{V}
$$

Lowering the concentration of the oxidised species lowers the electrode potential.

## Example 7: Gibbs Free Energy From Cell Potential

A cell reaction transfers 2 mol of electrons and has $E^\circ_{\text{cell}} = +1.10\ \text{V}$. Calculate $\Delta G^\circ$.

$$
\Delta G^\circ = -nE^\circ_{\text{cell}}F
$$

$$
\Delta G^\circ = -2 \times 1.10 \times 96500
= -212000\ \text{J mol}^{-1}
$$

$$
\Delta G^\circ = -212\ \text{kJ mol}^{-1}
$$

The negative value matches the positive cell potential.
