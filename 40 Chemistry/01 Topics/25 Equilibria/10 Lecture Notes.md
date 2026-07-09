---
title: 25 Equilibria - Lecture Notes
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/a-level
  - chemistry/9701/physical-chemistry
---

# 25 Equilibria - Lecture Notes

## Source Route

These notes follow the CAIE Chemistry 9701 syllabus for 2025-2027, A Level subject content, sections 25.1-25.2: acids and bases, buffer solutions, solubility product and common ion effect, and partition coefficients. No Chemistry coursebook alignment is claimed.

## Learning Scope

This topic is about using equilibrium constants to explain and calculate chemical behaviour. The key decision is to identify the system first: strong acid, strong alkali, weak acid, buffer, sparingly soluble salt, or partition between two solvents. Once the system is identified, write the correct expression before using numbers.

## Conjugate Acid-Base Pairs

An acid donates a proton and a base accepts a proton. When an acid loses a proton, it forms its conjugate base. When a base gains a proton, it forms its conjugate acid.

For example:

$$
\ce{CH3COOH(aq) + H2O(l) <=> CH3COO-(aq) + H3O+(aq)}
$$

The conjugate acid-base pairs are $\ce{CH3COOH/CH3COO-}$ and $\ce{H3O+/H2O}$.

For ammonia in water:

$$
\ce{NH3(aq) + H2O(l) <=> NH4+(aq) + OH-(aq)}
$$

The conjugate acid-base pairs are $\ce{NH4+/NH3}$ and $\ce{H2O/OH-}$.

## pH, Ka, pKa And Kw

pH is defined by:

$$
\text{pH} = -\log_{10}[\ce{H+}]
$$

so:

$$
[\ce{H+}] = 10^{-\text{pH}}
$$

For a weak acid:

$$
\ce{HA(aq) <=> H+(aq) + A-(aq)}
$$

the acid dissociation constant is:

$$
K_a = \frac{[\ce{H+}][\ce{A-}]}{[\ce{HA}]}
$$

and:

$$
\text{p}K_a = -\log_{10}K_a
$$

For water:

$$
K_w = [\ce{H+}][\ce{OH-}]
$$

At $298\ \text{K}$, $K_w$ is commonly taken as $1.00 \times 10^{-14}\ \text{mol}^2\text{ dm}^{-6}$ when data are not otherwise given. The syllabus states that $K_b$ and the equation $K_w = K_a \times K_b$ will not be tested.

Strong acids and strong alkalis are treated as fully dissociated. A monoprotic strong acid with concentration $c$ has $[\ce{H+}] = c$. A strong alkali such as $\ce{NaOH}$ has $[\ce{OH-}] = c$, while $\ce{Ba(OH)2}$ gives $[\ce{OH-}] = 2c$.

For a weak acid of concentration $c$, if the degree of dissociation is small:

$$
[\ce{H+}] \approx \sqrt{K_a c}
$$

This approximation works when the calculated $[\ce{H+}]$ is small compared with the original acid concentration.

## Buffer Solutions

A buffer solution resists changes in pH when small amounts of acid or alkali are added. An acidic buffer contains a weak acid and its conjugate base, often made by mixing a weak acid with a salt of that acid or by partial neutralisation of the weak acid.

For the buffer pair $\ce{HA/A-}$:

Added acid is removed by the conjugate base:

$$
\ce{A-(aq) + H+(aq) -> HA(aq)}
$$

Added alkali is removed by the weak acid:

$$
\ce{HA(aq) + OH-(aq) -> A-(aq) + H2O(l)}
$$

From:

$$
K_a = \frac{[\ce{H+}][\ce{A-}]}{[\ce{HA}]}
$$

you can rearrange:

$$
[\ce{H+}] = K_a\frac{[\ce{HA}]}{[\ce{A-}]}
$$

or use:

$$
\text{pH} = \text{p}K_a + \log_{10}\frac{[\ce{A-}]}{[\ce{HA}]}
$$

In buffer calculations, the ratio of concentrations may be replaced by the ratio of moles if both species are in the same final solution volume.

Hydrogencarbonate ions help control pH in blood through equilibria involving dissolved carbon dioxide:

$$
\ce{CO2(aq) + H2O(l) <=> H2CO3(aq) <=> H+(aq) + HCO3-(aq)}
$$

Added acid is removed mainly by $\ce{HCO3-}$, and added alkali is removed by carbonic acid.

## Solubility Product And Common Ion Effect

The **solubility product**, $K_{sp}$, is the equilibrium constant for a sparingly soluble ionic compound dissolving in water.

For silver chloride:

$$
\ce{AgCl(s) <=> Ag+(aq) + Cl-(aq)}
$$

$$
K_{sp} = [\ce{Ag+}][\ce{Cl-}]
$$

For magnesium hydroxide:

$$
\ce{Mg(OH)2(s) <=> Mg^{2+}(aq) + 2OH-(aq)}
$$

$$
K_{sp} = [\ce{Mg^{2+}}][\ce{OH-}]^2
$$

The solid does not appear in the expression. Powers come from the balanced equation. If the molar solubility of $\ce{Mg(OH)2}$ is $s$, then $[\ce{Mg^{2+}}]=s$ and $[\ce{OH-}]=2s$, so $K_{sp}=4s^3$.

The common ion effect reduces solubility when the solution already contains one of the ions from the sparingly soluble salt. For $\ce{AgCl}$ in sodium chloride solution, added $\ce{Cl-}$ shifts:

$$
\ce{AgCl(s) <=> Ag+(aq) + Cl-(aq)}
$$

to the left, so less $\ce{AgCl}$ dissolves.

## Partition Coefficients

A **partition coefficient**, $K_{pc}$, compares the equilibrium concentrations of a solute distributed between two immiscible solvents. The solute must be in the same physical state in both solvents.

A common form is:

$$
K_{pc} = \frac{\text{concentration of solute in solvent 1}}{\text{concentration of solute in solvent 2}}
$$

Always follow the definition given in the question because the order of the two solvents can be reversed.

The numerical value depends on the polarities of the solute and solvents. A polar solute is more likely to dissolve in a polar solvent. A non-polar solute is more likely to dissolve in a non-polar solvent. If the solute reacts, ionises, or changes physical state in one solvent, the simple partition model no longer applies.

## Working Routine

1. Identify the system: strong, weak, buffer, $K_{sp}$, common ion, or partition.
2. Write the equilibrium equation and expression.
3. Decide which concentrations are initial, change, and equilibrium values.
4. Use approximations only when they are chemically reasonable.
5. Keep logarithms tied to their definitions: pH for $[\ce{H+}]$ and p$K_a$ for $K_a$.
6. For buffers and common ions, explain the shift using an equation, not only words.

## Common Mistakes

- Confusing strong acid with concentrated acid.
- Using $K_a$ expressions for strong acids.
- Forgetting that $\ce{Ba(OH)2}$ produces two hydroxide ions per formula unit.
- Omitting powers in $K_{sp}$ expressions.
- Using concentrations in a buffer ratio when moles after reaction are required first.
- Reversing the definition of $K_{pc}$ without noticing.

## Connections

- [AS Equilibria](../07%20Equilibria/00%20Overview.md)
- [A Level Chemical Energetics](../23%20Chemical%20Energetics/00%20Overview.md)
- [A Level Reaction Kinetics](../26%20Reaction%20Kinetics/00%20Overview.md)
- [A Level Electrochemistry](../24%20Electrochemistry/00%20Overview.md)