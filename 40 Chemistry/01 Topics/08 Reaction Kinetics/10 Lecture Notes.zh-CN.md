---
title: "Reaction Kinetics - Lecture Notes.zh-CN"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/as-level
  - chemistry/9701/physical-chemistry
---

# Reaction Kinetics - Lecture Notes

## 范围

本笔记对应 CAIE Chemistry 9701 AS Level Physical chemistry Topic 8：Reaction kinetics，包括 8.1 Rate of reaction、8.2 Effect of temperature on reaction rates and the concept of activation energy，以及 8.3 Homogeneous and heterogeneous catalysts。不声称对齐任何 Chemistry coursebook。

## Rate of reaction

Rate of reaction 描述反应进行得多快，本质上是单位时间内某个量的变化：

$$
\text{rate} = \frac{\text{change in amount, concentration, mass or volume}}{\text{time taken}}
$$

单位取决于测量的量。若测 concentration，单位可为 $\mathrm{mol\,dm^{-3}\,s^{-1}}$；若测 gas volume，单位可为 $\mathrm{cm^3\,s^{-1}}$；若测 mass loss，单位可为 $\mathrm{g\,s^{-1}}$。

例如：

$$
\ce{CaCO3(s) + 2HCl(aq) -> CaCl2(aq) + CO2(g) + H2O(l)}
$$

这个反应可以通过测 $\ce{CO2}$ 体积随时间增加，或测体系质量随 $\ce{CO2}$ 逸出而减少，来研究 rate。

## Collision theory

粒子必须 collision 才可能反应，但不是所有 collision 都能生成产物。

Frequency of collisions 指单位时间内碰撞发生的频率。Effective collision 是能导致反应的碰撞；non-effective collision 是没有导致反应的碰撞。

要成为 effective collision，粒子需要足够能量，并且取向合适。AS 重点关注能量条件：粒子能量至少要达到 activation energy, $E_A$。

## Concentration 和 pressure 对 rate 的影响

提高 solution 中 reactant 的 concentration，通常会提高 reaction rate。因为单位体积内 reacting particles 更多，碰撞更频繁，effective collisions 的频率也增加。

对 gases，提高 pressure 的效果类似。气体粒子被压到更小体积内，粒子间距离更小，碰撞更频繁，因此 effective collisions 更频繁，rate 增大。

完整解释应包括：

- particles per unit volume 增加；
- collisions 更频繁；
- effective collisions 更频繁；
- reaction rate 增大。

不要只写“more collisions”。真正直接导致 rate 增大的，是 effective collisions 频率增大。

## 从数据计算 rate

平均速率：

$$
\text{average rate} = \frac{\Delta y}{\Delta t}
$$

$y$ 可以是 concentration、gas volume、mass 或其他实验读数。

如果图像是 product volume against time，斜率为正；如果是 reactant concentration against time，斜率为负。通常报告 rate 时取正值，也就是斜率的大小。

某一时刻的 instantaneous rate 用该点切线的 gradient 求。Initial rate 是反应刚开始时的 rate，通常用 $t = 0$ 处切线的 gradient。

有些实验测的是达到某个固定现象所需时间，例如沉淀遮住十字。时间越短，反应越快，常用相对速率：

$$
\text{relative rate} = \frac{1}{t}
$$

## Activation energy

Activation energy, $E_A$，是 collision 要成为 effective collision 所需的 minimum energy。

Reaction pathway diagram 中，$E_A$ 是从 reactants 到能量峰顶的竖直差值；$\Delta H$ 是 products 与 reactants 之间的竖直差值。两者不是同一个量。

例如：

$$
\ce{H2(g) + I2(g) -> 2HI(g)}
$$

反应粒子需要足够能量来削弱旧键并开始形成新键。路径图峰顶代表高能的 transition state。

## Boltzmann distribution

Boltzmann distribution 表示一定 temperature 下粒子能量的分布。

重要特征：

- 曲线从原点开始，因为没有粒子能量为负，也几乎没有粒子能量恰好为零；
- 曲线下面积代表 particles 总数；
- 曲线有峰值，说明许多粒子有中等能量；
- 只有能量大于或等于 $E_A$ 的粒子，才可能发生 effective collisions。

图上把 $E_A$ 画成一条竖线，竖线右侧的面积代表有足够能量反应的粒子。

## Temperature 对 rate 的影响

提高 temperature 会提高 reaction rate，有两个原因。

第一，粒子运动更快，collision frequency 增大。

第二，也是更重要的一点，Boltzmann distribution 改变，使能量大于或等于 $E_A$ 的粒子比例显著增加。因此 effective collisions 的频率明显增加。

升温后，Boltzmann curve 会变得更低、更宽，峰值向较高能量移动。如果粒子总数不变，曲线下面积不变，但 $E_A$ 右侧面积变大。

一个完整的 AS 解释要同时提到 Boltzmann distribution 和 effective collisions。

## Catalysts and catalysis

Catalyst 能提高 reaction rate，并且在反应结束时 chemically unchanged。Catalysis 是 catalyst 导致的速率增加。

有 catalyst 时，反应走 different mechanism，并且这个 mechanism 有较低的 activation energy。用 Boltzmann distribution 看，就是 $E_A$ 竖线向左移动；在同一 temperature 下，更多粒子能量超过 $E_A$，所以 effective collisions 更多。

Catalyst 不改变 $\Delta H$，因为 reactants 和 products 没变。它也不改变 equilibrium constant 或 final equilibrium position，只是让体系更快达到 equilibrium。

## Homogeneous 和 heterogeneous catalysts

Homogeneous catalyst 与 reactants 处于同一 physical state。例如，aqueous reaction mixture 中的 aqueous catalyst 是 homogeneous。

Heterogeneous catalyst 与 reactants 处于不同 physical state。例如，气体反应物通过 solid catalyst 表面反应，就是 heterogeneous catalysis。

AS 层面需要会使用 homogeneous 和 heterogeneous 这两个术语，不要求展开复杂的 surface mechanism。

## Catalysed pathway diagram

有 catalyst 的 reaction pathway diagram 峰值更低，表示 activation energy 更低。Reactants 和 products 的能量位置不变，因此 $\Delta H$ 不变。

对 exothermic reaction，products 低于 reactants；有无 catalyst 的路径峰值不同，但起点和终点相同。对 endothermic reaction，products 高于 reactants；catalyst 仍然只降低峰值，不改变 $\Delta H$ 的正负。

## Practical rate evidence

常见 rate 实验包括：

- 用 gas syringe 测 gas volume 随 time 增加；
- 测气体逸出导致的 mass loss；
- 测颜色深浅或 absorbance 随 time 改变；
- 测沉淀遮住标记所需时间；
- 定时取样并 titration。

实验设计要一次只改变一个变量。例如研究 concentration 时，应尽量保持 temperature、total volume、particle size 和 catalyst amount 不变。

Rate 常随时间降低，因为 reactants 被消耗，concentration 降低，单位时间内 effective collisions 变少。

## 解题顺序

解释 rate 变化时，先问：collision frequency 是否改变？超过 $E_A$ 的粒子比例是否改变？reaction mechanism 是否改变？

数据题中，先确定测量量，再用 change divided by time，最后写单位。

Catalyst 题中，要写出 different mechanism with lower activation energy，并联系 Boltzmann distribution 或 reaction pathway diagram。

## 快速自测

- 为什么多数反应的 rate 会随时间降低？
- 怎样从 gas volume-time 数据求平均速率？
- 为什么升温的主要影响不是简单的“碰撞更多”？
- Catalyst 为什么改变 $E_A$ 但不改变 $\Delta H$？
- Homogeneous catalyst 和 heterogeneous catalyst 的区别是什么？

## 连接

- [Chemical Energetics](../05%20Chemical%20Energetics/10%20Lecture%20Notes.md)
- [Equilibria](../07%20Equilibria/10%20Lecture%20Notes.md)
- [A Level Reaction Kinetics](../26%20Reaction%20Kinetics/00%20Overview.md)
