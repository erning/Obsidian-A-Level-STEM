---
title: 24 Electrochemistry - Lecture Notes.zh-CN
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/a-level
  - chemistry/9701/physical-chemistry
---

# 24 Electrochemistry - Lecture Notes.zh-CN

## 来源范围

本笔记对应 CAIE Chemistry 9701 2025-2027 syllabus 的 A Level subject content 24.1-24.2：electrolysis、standard electrode potentials、standard cell potentials、Nernst equation，以及 cell potential 与 Gibbs free energy 的联系。不声称对齐任何 Chemistry coursebook。

## 学习主线

本章把 redox 反应变成可计算、可预测的体系。你要能预测电解产物，用电荷计算生成物的物质的量，描述 standard electrode potential 的测量方法，组合 electrode potentials 预测电池方向，并在需要时用 Nernst equation 处理浓度变化。

## Electrolysis

Electrolysis 用外接电源推动本来自发性不足的 redox 反应。cathode 发生 reduction，anode 发生 oxidation。

熔融电解质中，参与反应的离子来自化合物本身。例如熔融 $\ce{NaCl}$：

Cathode：

$$
\ce{Na+ + e- -> Na}
$$

Anode：

$$
\ce{2Cl- -> Cl2 + 2e-}
$$

水溶液电解更复杂，因为水也可能参与反应。产物取决于电解质状态、相关物种在 redox series 或 electrode-potential series 中的位置，以及浓度。例如水溶液 $\ce{NaCl}$ 中，浓溶液在阳极更可能生成 $\ce{Cl2}$，稀溶液则可能由水或 $\ce{OH-}$ 生成 $\ce{O2}$。

电解计算从电荷开始：

$$
Q = It
$$

$Q$ 为电荷，单位 coulomb；$I$ 为电流，单位 ampere；$t$ 为时间，单位 second。

Faraday constant 表示 1 mol 电子所带的电荷：

$$
F = Le
$$

其中 $L$ 是 Avogadro constant，$e$ 是单个电子的电荷。常用关系为：

$$
n(\text{electrons}) = \frac{Q}{F}
$$

再用 half-equation 把电子的物质的量换成产物的物质的量。例如：

$$
\ce{Cu^{2+} + 2e- -> Cu}
$$

表示生成 1 mol 铜需要 2 mol 电子。

通过电解法也可以测定 Avogadro constant。实验测出电流、时间和沉积或放出的物质量，先由 $Q=It$ 得到电荷，再求出 $F$，最后用 $L=F/e$。

## Standard Electrode Potentials

**Standard electrode potential**，$E^\circ$，是相对于 standard hydrogen electrode 测得的标准还原电势。常用标准条件包括 $298\ \text{K}$、水溶液中离子浓度 $1\ \text{mol dm}^{-3}$、气体压强 $100\ \text{kPa}$。

standard hydrogen electrode 的半反应为：

$$
\ce{2H+(aq) + 2e- <=> H2(g)}
$$

其 $E^\circ = 0.00\ \text{V}$。实验中用铂电极提供导电表面，氢气在标准压强下通入，溶液中 $\ce{H+}$ 为标准浓度。

金属与其离子的半电池可写成：

$$
\ce{Cu^{2+}(aq) + 2e- <=> Cu(s)}
$$

非金属半电池通常需要惰性铂电极，例如：

$$
\ce{Cl2(g) + 2e- <=> 2Cl-(aq)}
$$

同一元素不同氧化态的离子也需要惰性电极，例如：

$$
\ce{Fe^{3+}(aq) + e- <=> Fe^{2+}(aq)}
$$

测量时把待测半电池与 standard hydrogen electrode 通过 salt bridge 和高电阻电压表连接。

## Standard Cell Potentials

**Standard cell potential**，$E^\circ_{\text{cell}}$，由两个 standard electrode potentials 组合得到。

使用标准还原电势时：

$$
E^\circ_{\text{cell}} = E^\circ_{\text{cathode}} - E^\circ_{\text{anode}}
$$

还原电势更正的半电池更容易发生 reduction，是可行简单电池中的 cathode。还原电势较低的半电池发生 oxidation，是 anode。

例如锌铜电池：

$$
\ce{Cu^{2+}(aq) + 2e- <=> Cu(s)} \quad E^\circ = +0.34\ \text{V}
$$

$$
\ce{Zn^{2+}(aq) + 2e- <=> Zn(s)} \quad E^\circ = -0.76\ \text{V}
$$

铜离子被还原，锌被氧化：

$$
\ce{Zn(s) + Cu^{2+}(aq) -> Zn^{2+}(aq) + Cu(s)}
$$

$$
E^\circ_{\text{cell}} = +0.34 - (-0.76) = +1.10\ \text{V}
$$

$E^\circ_{\text{cell}}$ 为正表示该反应在标准条件下 thermodynamically feasible。外电路电子从 anode 流向 cathode。

平衡电子数时不要把 electrode potential 乘以系数。$E^\circ$ 是 intensive quantity，不随反应倍数改变。

## 氧化剂与还原剂

$E^\circ$ 越正，物种越倾向于被还原，因此还原半反应左侧的 oxidised species 是更强的 oxidising agent。$E^\circ$ 越不正或越负，右侧的 reduced species 越容易被氧化，是更强的 reducing agent。

构造 redox equation 时，先选出相关 half-equations，把发生 oxidation 的半反应反向，配平电子，再相加并约去电子。

## 浓度影响与 Nernst Equation

浓度改变会改变 electrode potential。对写成下列形式的还原半反应：

$$
\ce{Ox + z e- <=> Red}
$$

syllabus 给出的 $298\ \text{K}$ 形式为：

$$
E = E^\circ + \frac{0.059}{z}\log\frac{[\text{oxidised species}]}{[\text{reduced species}]}
$$

例如：

$$
\ce{Fe^{3+}(aq) + e- <=> Fe^{2+}(aq)}
$$

$$
E = E^\circ + 0.059\log\frac{[\ce{Fe^{3+}}]}{[\ce{Fe^{2+}}]}
$$

oxidised species 浓度升高，$E$ 增大；reduced species 浓度升高，$E$ 减小。对 $\ce{Cu^{2+}/Cu}$ 这样的金属/离子半电池，固体金属不写入浓度比。

## Gibbs Free Energy

标准条件下：

$$
\Delta G^\circ = -nE^\circ_{\text{cell}}F
$$

$n$ 是配平方程中转移电子的物质的量，$F$ 是 Faraday constant。若 $E^\circ_{\text{cell}}$ 为正，则 $\Delta G^\circ$ 为负，反应在标准条件下 thermodynamically feasible。

## 做题流程

1. 先写 half-equations。
2. 用电子得失判断 oxidation 和 reduction。
3. 电解计算先用 $Q=It$，再换算成电子的物质的量。
4. 简单电池中，还原电势更正的一端通常是 cathode。
5. 计算 $E^\circ_{\text{cell}}$ 时不要把 $E^\circ$ 乘以系数。
6. 题目给出非标准浓度时，再考虑 Nernst equation。
7. 需要判断热力学可行性时，用 $\Delta G^\circ = -nE^\circ_{\text{cell}}F$ 连接。

## 常见错误

- 只背 anode 和 cathode 的电荷，而忘记 anode 是 oxidation、cathode 是 reduction。
- 忘记水溶液电解时水也可能放电。
- 在 $Q=It$ 中把分钟直接当秒使用。
- 反转 half-equation 后，cell potential 的方向处理错误。
- 把 $E^\circ$ 按化学计量数倍乘。
- 不说明浓度条件，就把 standard electrode potentials 用到非标准体系。
