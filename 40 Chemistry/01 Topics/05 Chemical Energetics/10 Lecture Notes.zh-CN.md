---
title: "Chemical Energetics - Lecture Notes.zh-CN"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/as-level
  - chemistry/9701/physical-chemistry
---

# Chemical Energetics - Lecture Notes

## 范围

本笔记对应 CAIE Chemistry 9701 AS Level Physical chemistry Topic 5：Chemical energetics，包括 5.1 Enthalpy change, $\Delta H$，以及 5.2 Hess's law。不声称对齐任何 Chemistry coursebook。

## 焓变的核心意义

化学反应常伴随能量转移。在恒压条件下，反应的热效应用焓变 $\Delta H$ 表示，常用单位是 $\mathrm{kJ\,mol^{-1}}$。这里的“每摩尔”要按化学方程式来理解：方程式写成几摩尔物质反应，$\Delta H$ 就对应那一个“反应量”。

判断符号时要站在 reacting chemicals 的角度：

| 反应类型 | 能量变化 | 产物相对焓 | $\Delta H$ 符号 |
|---|---|---|---|
| Exothermic | 向 surroundings 放出能量 | 低于反应物 | 负 |
| Endothermic | 从 surroundings 吸收能量 | 高于反应物 | 正 |

如果溶液温度升高，说明 surroundings 得到能量，反应本身通常是 exothermic，因此 $\Delta H < 0$。如果温度降低，说明反应从 surroundings 吸热，通常是 endothermic，因此 $\Delta H > 0$。

## 反应路径图

Reaction pathway diagram 的纵轴是 enthalpy，横轴是 progress of reaction。反应物与产物的竖直差值是 $\Delta H$，从反应物到曲线最高点的竖直差值是 activation energy, $E_A$。

$E_A$ 和 $\Delta H$ 不能混在一起。$E_A$ 是粒子发生有效反应前必须跨过的能量障碍；$\Delta H$ 是反应物和产物之间的焓差。

Exothermic reaction 的产物在反应物下方，$\Delta H$ 为负。Endothermic reaction 的产物在反应物上方，$\Delta H$ 为正。无论哪一种反应，$E_A$ 都是正的，因为反应都要经过较高能量的过渡状态。

催化剂会提供 different mechanism，使 activation energy 降低；但反应物和产物没有变，所以 $\Delta H$ 不变。

## 标准条件与常见焓变

本 syllabus 采用的 standard conditions 是 298 K 和 101 kPa，用 $^\ominus$ 表示。标准焓变要求所有物质处于这些条件下的 standard states。

常见术语要按定义识别：

- $\Delta H_r^\ominus$：standard enthalpy change of reaction，按方程式所示物质的量发生反应时的焓变。
- $\Delta H_f^\ominus$：standard enthalpy change of formation，由元素在 standard states 下生成 1 mol 化合物时的焓变。
- $\Delta H_c^\ominus$：standard enthalpy change of combustion，1 mol 物质在氧气中完全燃烧时的焓变。
- $\Delta H_{neut}^\ominus$：standard enthalpy change of neutralisation，酸和碱反应生成 1 mol 水时的焓变。

例如，$\ce{CO2(g)}$ 的 formation equation 是：

$$
\ce{C(s, graphite) + O2(g) -> CO2(g)}
$$

因为生成的是 1 mol $\ce{CO2(g)}$，所以它符合 formation enthalpy 的定义。元素在 standard state 下的 $\Delta H_f^\ominus$ 定义为 0。

强酸和强碱中和的核心离子方程式是：

$$
\ce{H+(aq) + OH-(aq) -> H2O(l)}
$$

所以这类中和反应的焓变数值通常很接近。

## 断键、成键与 bond energy

反应有能量变化，是因为旧键断裂、新键形成。

断键需要吸收能量，因此 bond breaking 是 endothermic，键能按断键方向取正值。成键会释放能量，因此 bond making 是 exothermic。

用 bond energy 估算反应焓变时：

$$
\Delta H_r = \sum \text{bond energies of bonds broken} - \sum \text{bond energies of bonds made}
$$

如果成键释放的能量大于断键吸收的能量，$\Delta H_r$ 为负；如果断键吸收的能量更大，$\Delta H_r$ 为正。

注意 average bond energy 的限制。很多数据表给出的键能是多个化合物中的平均值，所以计算结果常是估算值，不一定等于实验测量值。

## Calorimetry 计算

简单量热实验用温度变化来估算热量：

$$
q = mc\Delta T
$$

其中 $m$ 通常是被加热或冷却的 solution 的质量，$c$ 常取 $4.18\ \mathrm{J\,g^{-1}\,K^{-1}}$，$\Delta T$ 是温度变化。

反应焓变常用：

$$
\Delta H = -\frac{mc\Delta T}{n}
$$

负号表示视角转换：$mc\Delta T$ 描述 solution 得到或失去的热量，而 $\Delta H$ 描述 reacting chemicals 的焓变。若溶液升温，$mc\Delta T$ 为正，反应放热，$\Delta H$ 应为负。

做题时要先判断 $n$ 是什么。燃烧题通常用燃料的物质的量；中和题通常用生成水的物质的量；混合反应要看 limiting reactant。

简单量热实验常低估放热反应的 $|\Delta H|$，因为热量会散失到空气和仪器中，温度变化比真实值小。

## Hess's Law

Hess's law 的意思是：只要初态和终态相同，反应的 enthalpy change 与路径无关。焓是 state function。

使用 Hess's law 时，关键规则很少：

- 方程式反向，$\Delta H$ 变号。
- 方程式乘以某个倍数，$\Delta H$ 也乘以同一倍数。
- 把方程式相加，消去中间物质。
- 把对应的焓变相加。

用 formation enthalpy 时，常用关系是：

$$
\Delta H_r^\ominus = \sum \Delta H_f^\ominus(\text{products}) - \sum \Delta H_f^\ominus(\text{reactants})
$$

用 combustion enthalpy 时，常见关系是：

$$
\Delta H_r^\ominus = \sum \Delta H_c^\ominus(\text{reactants}) - \sum \Delta H_c^\ominus(\text{products})
$$

这两个式子的顺序不同，原因在于能量循环中箭头方向不同。最稳妥的方法是画 cycle，沿箭头走；逆着箭头走时变号。

## 解题顺序

1. 先写平衡方程式。
2. 判断 $\Delta H$ 对应的“每摩尔”是什么。
3. 看数据类型：calorimetry、bond energy、formation enthalpy 还是 combustion enthalpy。
4. 方程式反向或倍乘时同步处理 $\Delta H$。
5. 最后写符号和单位。
6. 用题意检查符号是否合理。

## 常见错误

- 把 solution 的质量误写成固体反应物的质量。
- 方程式反向后忘记让 $\Delta H$ 变号。
- 把 activation energy 当成 enthalpy change。
- 使用 average bond energies 后还把结果当作精确实验值。
- 只写数字不写正负号。

## 快速自测

- 溶液升温时，为什么反应的 $\Delta H$ 通常是负值？
- Exothermic pathway diagram 上，$E_A$ 和 $\Delta H$ 分别是哪两段竖直距离？
- $\Delta H = -mc\Delta T/n$ 中的 $n$ 在燃烧题、中和题中分别通常代表什么？
- 用 Hess cycle 时，逆着箭头走为什么要变号？

## 连接

- [[40 Chemistry/01 Topics/08 Reaction Kinetics/10 Lecture Notes|Reaction Kinetics]]
- [[40 Chemistry/01 Topics/23 Chemical Energetics/00 Overview|A Level Chemical Energetics]]
- [[40 Chemistry/02 Practical Skills/00 Overview|Practical Skills]]
