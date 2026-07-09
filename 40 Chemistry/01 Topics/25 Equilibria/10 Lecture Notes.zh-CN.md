---
title: "25 Equilibria - Lecture Notes.zh-CN"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/a-level
  - chemistry/9701/physical-chemistry
---

# 25 Equilibria - Lecture Notes

## 范围

本笔记对应 CAIE Chemistry 9701 2025-2027 syllabus 的 A Level subject content 25.1-25.2：acids and bases、buffer solutions、solubility product、common ion effect 和 partition coefficients。不声称对齐任何 Chemistry coursebook。

## 学习主线

本章的关键不是套公式，而是先判断体系类型：strong acid、strong alkali、weak acid、buffer、sparingly soluble salt，还是两个溶剂之间的 partition。类型判断正确后，再写平衡表达式并代入数据。

## Conjugate Acid-Base Pairs

酸给出质子，碱接受质子。酸失去质子后形成 conjugate base；碱得到质子后形成 conjugate acid。

例如：

$$
\ce{CH3COOH(aq) + H2O(l) <=> CH3COO-(aq) + H3O+(aq)}
$$

其中 conjugate acid-base pairs 是 $\ce{CH3COOH/CH3COO-}$ 和 $\ce{H3O+/H2O}$。

氨在水中：

$$
\ce{NH3(aq) + H2O(l) <=> NH4+(aq) + OH-(aq)}
$$

conjugate acid-base pairs 是 $\ce{NH4+/NH3}$ 和 $\ce{H2O/OH-}$。

## pH、Ka、pKa 和 Kw

pH 定义为：

$$
\text{pH} = -\log_{10}[\ce{H+}]
$$

因此：

$$
[\ce{H+}] = 10^{-\text{pH}}
$$

弱酸：

$$
\ce{HA(aq) <=> H+(aq) + A-(aq)}
$$

其 acid dissociation constant 为：

$$
K_a = \frac{[\ce{H+}][\ce{A-}]}{[\ce{HA}]}
$$

并且：

$$
\text{p}K_a = -\log_{10}K_a
$$

水的离子积：

$$
K_w = [\ce{H+}][\ce{OH-}]
$$

若题目没有另给数据，$298\ \text{K}$ 时常用 $K_w = 1.00 \times 10^{-14}\ \text{mol}^2\text{ dm}^{-6}$。syllabus 说明 $K_b$ 和 $K_w = K_a \times K_b$ 不会考查。

强酸和强碱通常视作完全电离。单元强酸浓度为 $c$ 时，$[\ce{H+}]=c$。$\ce{NaOH}$ 中 $[\ce{OH-}]=c$，而 $\ce{Ba(OH)2}$ 中 $[\ce{OH-}]=2c$。

弱酸浓度为 $c$ 且电离程度很小时：

$$
[\ce{H+}] \approx \sqrt{K_a c}
$$

若算出的 $[\ce{H+}]$ 相对于原弱酸浓度很小，这个近似通常合理。

## Buffer Solutions

Buffer solution 能在加入少量酸或碱时抵抗 pH 变化。酸性 buffer 含有弱酸和它的 conjugate base，常由弱酸和该酸的盐混合制得，也可由弱酸部分中和制得。

对 $\ce{HA/A-}$ 缓冲对：

加入的酸由 conjugate base 消耗：

$$
\ce{A-(aq) + H+(aq) -> HA(aq)}
$$

加入的碱由弱酸消耗：

$$
\ce{HA(aq) + OH-(aq) -> A-(aq) + H2O(l)}
$$

由：

$$
K_a = \frac{[\ce{H+}][\ce{A-}]}{[\ce{HA}]}
$$

可得：

$$
[\ce{H+}] = K_a\frac{[\ce{HA}]}{[\ce{A-}]}
$$

也可写成：

$$
\text{pH} = \text{p}K_a + \log_{10}\frac{[\ce{A-}]}{[\ce{HA}]}
$$

若 $\ce{HA}$ 和 $\ce{A-}$ 在同一个最终体积中，浓度比可以直接用物质的量之比代替。

血液中的 $\ce{HCO3-}$ 通过含二氧化碳的平衡体系帮助控制 pH：

$$
\ce{CO2(aq) + H2O(l) <=> H2CO3(aq) <=> H+(aq) + HCO3-(aq)}
$$

加入酸时，$\ce{HCO3-}$ 主要消耗 $\ce{H+}$；加入碱时，碳酸提供酸性组分来消耗 $\ce{OH-}$。

## Solubility Product 与 Common Ion Effect

**Solubility product**，$K_{sp}$，是微溶离子化合物溶解平衡的 equilibrium constant。

氯化银：

$$
\ce{AgCl(s) <=> Ag+(aq) + Cl-(aq)}
$$

$$
K_{sp} = [\ce{Ag+}][\ce{Cl-}]
$$

氢氧化镁：

$$
\ce{Mg(OH)2(s) <=> Mg^{2+}(aq) + 2OH-(aq)}
$$

$$
K_{sp} = [\ce{Mg^{2+}}][\ce{OH-}]^2
$$

固体不写入表达式。指数来自配平方程。如果 $\ce{Mg(OH)2}$ 的 molar solubility 为 $s$，则 $[\ce{Mg^{2+}}]=s$，$[\ce{OH-}]=2s$，所以 $K_{sp}=4s^3$。

common ion effect 指溶液中已有某个共同离子时，微溶盐的溶解度降低。例如 $\ce{AgCl}$ 在 $\ce{NaCl}$ 溶液中：

$$
\ce{AgCl(s) <=> Ag+(aq) + Cl-(aq)}
$$

额外的 $\ce{Cl-}$ 使平衡向左移动，因此 $\ce{AgCl}$ 溶解得更少。

## Partition Coefficients

**Partition coefficient**，$K_{pc}$，描述溶质在两个互不相溶溶剂之间达到平衡时的浓度比。syllabus 限定溶质在两个溶剂中处于同一 physical state。

常见定义：

$$
K_{pc} = \frac{\text{concentration of solute in solvent 1}}{\text{concentration of solute in solvent 2}}
$$

题目可以把两个溶剂顺序反过来，所以一定要按题目定义。

$K_{pc}$ 的数值与溶质和溶剂的极性有关。极性溶质更倾向于极性溶剂；非极性溶质更倾向于非极性溶剂。若溶质在某个溶剂中反应、电离或改变物理状态，简单 partition 模型就不再适用。

## 做题流程

1. 先判断体系：strong、weak、buffer、$K_{sp}$、common ion 或 partition。
2. 写出平衡方程和平衡表达式。
3. 区分初始浓度、变化量和平衡浓度。
4. 只有在化学上合理时才使用近似。
5. 对数定义要清楚：pH 对应 $[\ce{H+}]$，p$K_a$ 对应 $K_a$。
6. 解释 buffer 和 common ion effect 时，要配合化学方程式。

## 常见错误

- 把 strong acid 和 concentrated acid 混为一谈。
- 对强酸硬套 $K_a$ 表达式。
- 忘记 $\ce{Ba(OH)2}$ 每个 formula unit 产生 2 个 $\ce{OH-}$。
- 写 $K_{sp}$ 时漏掉指数。
- buffer 题中先发生中和却直接用初始浓度。
- 没看清 $K_{pc}$ 的分子和分母是哪一个溶剂。
