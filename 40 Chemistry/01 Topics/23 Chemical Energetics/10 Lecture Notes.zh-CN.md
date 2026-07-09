---
title: "23 Chemical Energetics - Lecture Notes.zh-CN"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/a-level
  - chemistry/9701/physical-chemistry
---

# 23 Chemical Energetics - Lecture Notes

## 范围

本笔记对应 CAIE Chemistry 9701 2025-2027 syllabus 的 A Level subject content 23.1-23.4：lattice energy and Born-Haber cycles、enthalpies of solution and hydration、entropy change 和 Gibbs free energy change。不声称对齐任何 Chemistry coursebook。

## 学习主线

这一章把 AS 阶段的焓变和 Hess cycle 推进到离子晶体与热力学可行性。你要能用标准术语定义各类焓变，画 Born-Haber cycle 和溶解能量循环，用离子电荷与半径解释趋势，再用熵变和 Gibbs free energy 判断一个过程在给定条件下是否 thermodynamically feasible。

## 离子焓变术语

**Enthalpy change of atomisation**，$\Delta H^\circ_{\text{at}}$，指由元素的标准状态生成 1 mol 气态原子时的焓变。

例如钠：

$$
\ce{Na(s) -> Na(g)}
$$

氯气生成氯原子时，要注意 1 mol 氯原子来自半个 1 mol 的氯气分子：

$$
\ce{1/2Cl2(g) -> Cl(g)}
$$

syllabus 对 **lattice energy**，$\Delta H^\circ_{\text{latt}}$，采用的定义是：气态离子形成 1 mol 固体离子晶格的焓变。

$$
\ce{Na+(g) + Cl-(g) -> NaCl(s)}
$$

按这个定义，lattice energy 通常为负值，因为形成晶格会放出能量。若题目或数据表使用的是 lattice dissociation enthalpy，符号会相反，所以计算前必须先看清定义。

**First electron affinity**，$\text{EA}_1$，指 1 mol 气态原子各得到 1 个电子，形成 1 mol 气态 1- 离子时的焓变。

$$
\ce{Cl(g) + e- -> Cl-(g)}
$$

第一电子亲和能常为放热，因为进入的电子受到原子核吸引。影响因素包括核电荷、原子半径、屏蔽作用和电子间排斥。Group 17 中，氯的 first electron affinity 比氟更放热，因为氟原子很小，加入电子时电子间排斥更明显；从氯往下，半径和屏蔽增大，第一电子亲和能通常变得不那么放热。Group 16 的 first electron affinity 通常不如对应的 Group 17 元素放热，因为 Group 16 原子还差两个电子才达到满外层。氧的 first electron affinity 不如硫放热，是因为进入的电子位于很紧凑的 2p 轨道，电子间排斥强；从硫往下，半径和屏蔽增大，第一电子亲和能通常也变得不那么放热。Group 16 形成 2- 离子时，第二电子亲和能是吸热的，因为电子要加入已经带负电的离子。

## Born-Haber Cycle

Born-Haber cycle 是离子晶体形成反应的 Hess cycle。它把标准生成焓拆成 atomisation、ionisation energy、electron affinity 和 lattice energy 等步骤。

以 $\ce{NaCl}$ 为例：

$$
\ce{Na(s) + 1/2Cl2(g) -> NaCl(s)}
$$

按本章的 lattice energy 定义：

$$
\Delta H^\circ_{\text{f}} =
\Delta H^\circ_{\text{at}}(\ce{Na})
+ \Delta H^\circ_{\text{at}}(\ce{Cl})
+ \text{IE}_1(\ce{Na})
+ \text{EA}_1(\ce{Cl})
+ \Delta H^\circ_{\text{latt}}(\ce{NaCl})
$$

如果阳离子是 2+，要加入第一、第二电离能；如果阴离子是 2-，要加入第一、第二电子亲和能。syllabus 把 Born-Haber cycle 限定在 +1、+2 阳离子和 -1、-2 阴离子范围内。

lattice energy 的数值大小随离子电荷增大而增大，随离子半径减小而增大。原因是电荷更大、离子距离更近时，静电吸引更强。因此 $\ce{MgO}$ 的 lattice energy 数值大小远大于 $\ce{NaCl}$。

## 溶解与水合能量循环

**Enthalpy change of hydration**，$\Delta H^\circ_{\text{hyd}}$，指 1 mol 气态离子形成 1 mol 水合离子时的焓变。

$$
\ce{Na+(g) -> Na+(aq)}
$$

**Enthalpy change of solution**，$\Delta H^\circ_{\text{sol}}$，指 1 mol 物质溶于足量溶剂形成无限稀释溶液时的焓变。

$$
\ce{NaCl(s) -> Na+(aq) + Cl-(aq)}
$$

若 lattice energy 定义为气态离子形成固体晶格：

$$
\Delta H^\circ_{\text{sol}}
= -\Delta H^\circ_{\text{latt}}
+ \sum \Delta H^\circ_{\text{hyd}}(\text{ions})
$$

$-\Delta H^\circ_{\text{latt}}$ 表示把晶格拆成气态离子所需的能量。hydration enthalpy 通常为负，因为离子与水分子形成 ion-dipole attraction。离子电荷越高、半径越小，电荷密度越大，水合焓数值大小通常越大。

溶解焓为正并不自动表示不溶，因为溶解过程还可能得到熵的推动。

## 熵变

Entropy，$S$，表示一个体系中粒子及其能量可能排列方式的数目。粒子和能量分布方式越多，熵通常越大。

常见判断：

| 变化 | $\Delta S$ 通常符号 | 原因 |
|---|---:|---|
| 固体熔化或液体沸腾 | 正 | 粒子排列方式增多 |
| 气体凝结或液体凝固 | 负 | 粒子更有序 |
| 温度升高 | 正 | 能量分配方式增多 |
| 反应生成更多气体分子 | 正 | 气体粒子的空间排列方式增多 |
| 反应中气体分子数减少 | 负 | 气体粒子数减少 |

反应的标准熵变：

$$
\Delta S^\circ = \sum S^\circ(\text{products}) - \sum S^\circ(\text{reactants})
$$

计算时要乘上化学方程式中的系数。标准熵的单位通常是 $\text{J mol}^{-1}\text{ K}^{-1}$。

## Gibbs Free Energy 与可行性

Gibbs equation：

$$
\Delta G^\circ = \Delta H^\circ - T\Delta S^\circ
$$

在标准条件下，若 $\Delta G^\circ < 0$，反应或过程 thermodynamically feasible；若 $\Delta G^\circ > 0$，在这些条件下不可行；若 $\Delta G^\circ = 0$，体系处于平衡。

代入前先统一单位。如果 $\Delta H^\circ$ 用 $\text{kJ mol}^{-1}$，就要把 $\Delta S^\circ$ 从 $\text{J mol}^{-1}\text{ K}^{-1}$ 转成 $\text{kJ mol}^{-1}\text{ K}^{-1}$。

温度的影响来自 $-T\Delta S^\circ$：

| $\Delta H^\circ$ | $\Delta S^\circ$ | 温度影响 |
|---:|---:|---|
| 负 | 正 | 简化模型下所有温度都可行 |
| 负 | 负 | 低温更可行 |
| 正 | 正 | 高温更可行 |
| 正 | 负 | 简化模型下所有温度都不可行 |

注意，feasible 是热力学判断，不等于反应速率快。$\Delta G^\circ$ 为负的反应仍可能因为活化能高而非常慢。

## 做题流程

1. 先写带 state symbols 的配平方程。
2. 判断题目属于 Born-Haber、溶解循环、熵变还是 Gibbs free energy。
3. 计算前先画循环或在心里走一遍路径。
4. 每个符号都回到定义，尤其是 lattice energy。
5. 用 Gibbs equation 前统一能量和熵的单位。
6. 最后给出化学解释：电荷密度、无序程度、温度影响或可行性。

## 常见错误

- 把 lattice energy 和 lattice dissociation enthalpy 的符号混用。
- 2+ 或 2- 离子的循环中漏掉第二电离能或第二电子亲和能。
- 把 hydration enthalpy 写成正值。
- 在 Gibbs equation 中混用 $\text{J mol}^{-1}\text{ K}^{-1}$ 和 $\text{kJ mol}^{-1}$。
- 把 thermodynamically feasible 误解为反应一定很快。

## 连接

本章直接连接 [Electrochemistry](../24%20Electrochemistry/00%20Overview.md)，其中 $\Delta G^\circ$ 会与 standard cell potential 联系起来。它也支持 [Group 2](../27%20Group%202/00%20Overview.md) 中关于溶解性和热稳定性的趋势解释。
