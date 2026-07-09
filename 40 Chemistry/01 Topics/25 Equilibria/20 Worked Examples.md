---
title: 25 Equilibria - Worked Examples
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/a-level
  - chemistry/9701/physical-chemistry
---

# 25 Equilibria - Worked Examples

## Example 1: pH Of Strong Acid And Strong Alkali

Find the pH of $0.0250\ \text{mol dm}^{-3}$ $\ce{HCl(aq)}$.

Hydrochloric acid is a strong monoprotic acid, so:

$$
[\ce{H+}] = 0.0250\ \text{mol dm}^{-3}
$$

$$
\text{pH} = -\log_{10}(0.0250) = 1.60
$$

Find the pH of $0.0150\ \text{mol dm}^{-3}$ $\ce{Ba(OH)2(aq)}$ at $298\ \text{K}$.

$$
\ce{Ba(OH)2(aq) -> Ba^{2+}(aq) + 2OH-(aq)}
$$

$$
[\ce{OH-}] = 2(0.0150) = 0.0300\ \text{mol dm}^{-3}
$$

$$
\text{pOH} = -\log_{10}(0.0300) = 1.52
$$

$$
\text{pH} = 14.00 - 1.52 = 12.48
$$

## Example 2: pH Of A Weak Acid

Calculate the pH of $0.100\ \text{mol dm}^{-3}$ ethanoic acid, $\ce{CH3COOH}$, with $K_a = 1.74 \times 10^{-5}\ \text{mol dm}^{-3}$.

$$
\ce{CH3COOH(aq) <=> H+(aq) + CH3COO-(aq)}
$$

Assuming small dissociation:

$$
K_a \approx \frac{[\ce{H+}]^2}{[\ce{CH3COOH}]}
$$

$$
[\ce{H+}] \approx \sqrt{K_a c}
= \sqrt{(1.74 \times 10^{-5})(0.100)}
= 1.32 \times 10^{-3}\ \text{mol dm}^{-3}
$$

$$
\text{pH} = -\log_{10}(1.32 \times 10^{-3}) = 2.88
$$

Check: $\frac{1.32 \times 10^{-3}}{0.100} \times 100\% = 1.32\%$, so the approximation is acceptable.

## Example 3: Buffer pH

A buffer contains $50.0\ \text{cm}^3$ of $0.200\ \text{mol dm}^{-3}$ $\ce{CH3COOH}$ and $50.0\ \text{cm}^3$ of $0.150\ \text{mol dm}^{-3}$ $\ce{CH3COONa}$. Use $K_a = 1.74 \times 10^{-5}$.

Moles of acid:

$$
n(\ce{CH3COOH}) = 0.200 \times \frac{50.0}{1000} = 0.0100\ \text{mol}
$$

Moles of conjugate base:

$$
n(\ce{CH3COO-}) = 0.150 \times \frac{50.0}{1000} = 0.00750\ \text{mol}
$$

Because both are in the same final volume, use the mole ratio:

$$
\text{pH} = \text{p}K_a + \log_{10}\frac{n(\ce{CH3COO-})}{n(\ce{CH3COOH})}
$$

$$
\text{p}K_a = -\log_{10}(1.74 \times 10^{-5}) = 4.76
$$

$$
\text{pH} = 4.76 + \log_{10}\frac{0.00750}{0.0100}
= 4.64
$$

## Example 4: Buffer After Adding Acid

To the buffer in Example 3, add $1.00 \times 10^{-3}\ \text{mol}$ of $\ce{H+}$. Calculate the new pH.

The conjugate base removes added acid:

$$
\ce{CH3COO-(aq) + H+(aq) -> CH3COOH(aq)}
$$

New moles:

$$
n(\ce{CH3COO-}) = 0.00750 - 0.00100 = 0.00650\ \text{mol}
$$

$$
n(\ce{CH3COOH}) = 0.0100 + 0.00100 = 0.0110\ \text{mol}
$$

$$
\text{pH} = 4.76 + \log_{10}\frac{0.00650}{0.0110}
= 4.53
$$

The pH falls, but only modestly because the buffer consumes most of the added acid.

## Example 5: Solubility Product And Common Ion

For $\ce{AgCl}$, $K_{sp} = 1.8 \times 10^{-10}\ \text{mol}^2\text{ dm}^{-6}$.

In pure water:

$$
\ce{AgCl(s) <=> Ag+(aq) + Cl-(aq)}
$$

If the molar solubility is $s$:

$$
K_{sp} = s^2
$$

$$
s = \sqrt{1.8 \times 10^{-10}} = 1.34 \times 10^{-5}\ \text{mol dm}^{-3}
$$

In $0.100\ \text{mol dm}^{-3}$ $\ce{NaCl(aq)}$, assume $[\ce{Cl-}] \approx 0.100\ \text{mol dm}^{-3}$.

$$
[\ce{Ag+}] = \frac{K_{sp}}{[\ce{Cl-}]}
= \frac{1.8 \times 10^{-10}}{0.100}
= 1.8 \times 10^{-9}\ \text{mol dm}^{-3}
$$

The common ion sharply reduces the solubility.

## Example 6: Solubility Of Magnesium Hydroxide

For:

$$
\ce{Mg(OH)2(s) <=> Mg^{2+}(aq) + 2OH-(aq)}
$$

$K_{sp} = 5.6 \times 10^{-12}$. Find the molar solubility in water.

Let the molar solubility be $s$.

$$
[\ce{Mg^{2+}}] = s,\quad [\ce{OH-}] = 2s
$$

$$
K_{sp} = s(2s)^2 = 4s^3
$$

$$
s = \sqrt[3]{\frac{5.6 \times 10^{-12}}{4}}
= 1.12 \times 10^{-4}\ \text{mol dm}^{-3}
$$

## Example 7: Partition Coefficient

A solute distributes between an organic solvent and water. At equilibrium:

$$
K_{pc} = \frac{[\text{solute in organic solvent}]}{[\text{solute in water}]} = 4.0
$$

$0.100\ \text{mol}$ of solute is shaken with $50.0\ \text{cm}^3$ of organic solvent and $100\ \text{cm}^3$ of water. Find the amount in the organic layer at equilibrium.

Let $x$ be the moles in the organic layer. Then $0.100-x$ is in water.

$$
\frac{x/0.0500}{(0.100-x)/0.100} = 4.0
$$

$$
\frac{20.0x}{1.00 - 10.0x} = 4.0
$$

$$
20.0x = 4.00 - 40.0x
$$

$$
x = 0.0667\ \text{mol}
$$

The organic layer contains more solute because the partition coefficient favours it.
