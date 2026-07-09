---
title: "Electrochemistry - Lecture Notes.zh-CN"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/as-level
  - chemistry/9701/physical-chemistry
---

# Electrochemistry - Lecture Notes.zh-CN

## 范围

本笔记对应 CAIE Chemistry 9701 AS Level Physical chemistry Topic 6：Electrochemistry，具体是 6.1 Redox processes: electron transfer and changes in oxidation number (oxidation state)。经 syllabus 核对，electrolysis 和 standard electrode potentials 属于后面的 A Level Topic 24，所以这里只把它们作为后续应用提到，不作为 AS Topic 6 的主体内容。不声称对齐任何 Chemistry coursebook。

## 从电子转移理解 redox

Redox reaction 的本质是电子转移。Oxidation 是失去电子，reduction 是得到电子。

例如：

$$
\ce{Mg -> Mg^{2+} + 2e-}
$$

镁失去电子，所以这是 oxidation。

$$
\ce{Cu^{2+} + 2e- -> Cu}
$$

铜离子得到电子，所以这是 reduction。

把两个 half-equations 合并，可以得到：

$$
\ce{Mg + Cu^{2+} -> Mg^{2+} + Cu}
$$

一个物种失去的电子，被另一个物种得到。Oxidation 和 reduction 总是同时发生。

## Oxidation number 的规则

Oxidation number 是给原子分配的形式电荷，用来追踪电子变化。它不一定等于真实电荷，但很适合判断 redox。

常用规则如下：

| 规则 | 例子 |
|---|---|
| 单质中元素 oxidation number 为 0 | $\ce{Mg}$、$\ce{O2}$、$\ce{Cl2}$ |
| 单原子离子的 oxidation number 等于离子电荷 | $\ce{Na+}$ 为 +1，$\ce{S^{2-}}$ 为 -2 |
| 中性化合物中所有 oxidation numbers 总和为 0 | $\ce{H2O}$ 总和为 0 |
| 多原子离子中所有 oxidation numbers 总和等于离子电荷 | $\ce{SO4^{2-}}$ 总和为 -2 |
| Group 1 金属通常为 +1 | $\ce{NaCl}$ 中 $\ce{Na}$ 为 +1 |
| Group 2 金属通常为 +2 | $\ce{MgO}$ 中 $\ce{Mg}$ 为 +2 |
| 氟在化合物中为 -1 | $\ce{NaF}$ 中 $\ce{F}$ 为 -1 |
| 氢与非金属结合时通常为 +1 | $\ce{HCl}$ 中 $\ce{H}$ 为 +1 |
| 氧通常为 -2 | $\ce{CO2}$ 中 $\ce{O}$ 为 -2 |

例如，在 $\ce{SO4^{2-}}$ 中，氧通常为 -2，四个氧共 $-8$。整个离子电荷是 -2，所以硫为 +6：

$$
x + 4(-2) = -2
$$

$$
x = +6
$$

## 用 oxidation number 判断氧化还原

Oxidation number 增加，就是 oxidation；oxidation number 降低，就是 reduction。

看反应：

$$
\ce{Zn + Cu^{2+} -> Zn^{2+} + Cu}
$$

锌从 0 变为 +2，oxidation number 增加，所以锌被 oxidised。铜从 +2 变为 0，oxidation number 降低，所以铜被 reduced。因为两者同时发生，这是 redox reaction。

不是所有反应都是 redox。例如：

$$
\ce{H+(aq) + OH-(aq) -> H2O(l)}
$$

氢仍是 +1，氧仍是 -2，没有 oxidation number 改变，所以这个离子方程式不是 redox。

## Oxidising agent 与 reducing agent

Oxidising agent 使别的物种被氧化；它自己得到电子，被 reduced。Reducing agent 使别的物种被还原；它自己失去电子，被 oxidised。

在反应：

$$
\ce{Zn + Cu^{2+} -> Zn^{2+} + Cu}
$$

$\ce{Cu^{2+}}$ 被还原，所以它是 oxidising agent。$\ce{Zn}$ 被氧化，所以它是 reducing agent。

记忆时不要只看名称。最可靠的判断是：

- oxidising agent 自己被 reduced；
- reducing agent 自己被 oxidised。

## Disproportionation

Disproportionation 是同一种元素在同一个反应中既被氧化又被还原。

例如：

$$
\ce{Cl2 + 2OH- -> Cl- + ClO- + H2O}
$$

$\ce{Cl2}$ 中氯为 0。$\ce{Cl-}$ 中氯为 -1，被还原；$\ce{ClO-}$ 中氧为 -2，整个离子为 -1，所以氯为 +1，被氧化。同一个元素同时降低和升高 oxidation number，因此这是 disproportionation。

## 用 oxidation number 辅助配平

配平 redox 方程式时，总的 oxidation number 增加量必须等于总的降低量。

例如，酸性条件下 $\ce{Fe^{2+}}$ 被 $\ce{MnO4-}$ 氧化：

$$
\ce{Fe^{2+} -> Fe^{3+} + e-}
$$

铁从 +2 到 +3，每个铁失去 1 个电子。$\ce{MnO4-}$ 中锰为 +7，变为 $\ce{Mn^{2+}}$ 时得到 5 个电子：

$$
\ce{MnO4- + 8H+ + 5e- -> Mn^{2+} + 4H2O}
$$

因此需要 5 个 $\ce{Fe^{2+}}$：

$$
\ce{5Fe^{2+} + MnO4- + 8H+ -> 5Fe^{3+} + Mn^{2+} + 4H2O}
$$

最后检查原子数和总电荷。左边总电荷为 $5(+2)-1+8(+1)=+17$，右边为 $5(+3)+2=+17$。

## Roman numerals

当一个元素有多个常见 oxidation states 时，可以用 Roman numeral 表示其 oxidation number 的大小。它写在元素名称后面的括号里。

例如：

- iron(II) 表示 $\ce{Fe^{2+}}$；
- iron(III) 表示 $\ce{Fe^{3+}}$；
- copper(I) oxide 是 $\ce{Cu2O}$；
- copper(II) oxide 是 $\ce{CuO}$；
- manganate(VII) 中锰为 +7，例如 $\ce{MnO4-}$。

Roman numeral 表示 oxidation number，不表示原子个数。

## 与后续 electrochemistry 的关系

AS Topic 6 的 redox 是后续 electrolysis、electrode processes 和 electrode potentials 的基础。Electrolysis 中，一个电极发生 oxidation，另一个电极发生 reduction；标准电极电势比较的是 half-equation 作为 reduction 发生的趋势。但这些细节属于 [[40 Chemistry/01 Topics/24 Electrochemistry/00 Overview|A Level Electrochemistry]]。

## 解题顺序

1. 先给可能变化的元素分配 oxidation numbers。
2. 找出哪些元素数值升高，哪些降低。
3. 判断谁被 oxidised，谁被 reduced。
4. 判断 oxidising agent 和 reducing agent。
5. 配平时让总升高量等于总降低量。
6. 最后检查原子数和总电荷。

## 常见错误

- 把多原子离子的总电荷当成每个原子的 oxidation number。
- 说 oxidising agent 被氧化。实际上 oxidising agent 自己被 reduced。
- 只用“得氧”“失氢”判断，而没有给出 electron transfer 或 oxidation number 证据。
- 忽略 disproportionation，因为同一种元素出现在两个不同产物中。

## 快速自测

- $\ce{SO3}$ 和 $\ce{SO4^{2-}}$ 中硫的 oxidation numbers 分别是多少？
- 为什么 $\ce{Fe^{2+} -> Fe^{3+} + e-}$ 是 oxidation？
- 怎样判断一个物种是 oxidising agent 还是 reducing agent？
- 怎样从 oxidation number 判断 disproportionation？
