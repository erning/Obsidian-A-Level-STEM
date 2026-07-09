---
title: "26 Reaction Kinetics - Lecture Notes.zh-CN"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/a-level
  - chemistry/9701/physical-chemistry
---

# 26 Reaction Kinetics - Lecture Notes

## 范围

本笔记对应 CAIE Chemistry 9701 2025-2027 syllabus 的 A Level subject content 26.1-26.2：simple rate equations、orders of reaction、rate constants、half-life、mechanisms、rate-determining step、intermediates、temperature effects，以及 homogeneous and heterogeneous catalysts。不声称对齐任何 Chemistry coursebook。

## 学习主线

A Level kinetics 的核心是用实验数据写 rate equation，再用 rate equation 检查反应机理。你需要能从 initial rates、graphs 和 half-life 数据判断反应级数，计算 rate constant 及其单位，把 rate equation 与 rate-determining step 联系起来，并解释 homogeneous 与 heterogeneous catalysis。

## Rate Equations And Orders

Rate equation 表示速率如何随反应物浓度变化。对两个反应物：

$$
\text{rate} = k[\ce{A}]^m[\ce{B}]^n
$$

$k$ 是 rate constant，$m$ 是关于 $\ce{A}$ 的 order，$n$ 是关于 $\ce{B}$ 的 order。syllabus 中 $m$ 和 $n$ 可为 0、1 或 2。overall order 是 $m+n$。

反应级数来自实验数据，不是直接从总方程的化学计量数抄来。

常见级数含义：

| Order | 浓度加倍时的影响 | rate 对 concentration 图像 |
|---:|---|---|
| 0 | rate 不变 | 水平线 |
| 1 | rate 加倍 | 过原点直线 |
| 2 | rate 变为 4 倍 | 向上弯曲的曲线 |

rate constant 与温度有关。它的单位取决于 overall order，因为 rate 通常使用 $\text{mol dm}^{-3}\text{ s}^{-1}$。

例子：

| Overall order | Rate equation | $k$ 的单位 |
|---:|---|---|
| 0 | $\text{rate}=k$ | $\text{mol dm}^{-3}\text{ s}^{-1}$ |
| 1 | $\text{rate}=k[\ce{A}]$ | $\text{s}^{-1}$ |
| 2 | $\text{rate}=k[\ce{A}][\ce{B}]$ | $\text{dm}^3\text{ mol}^{-1}\text{ s}^{-1}$ |
| 3 | $\text{rate}=k[\ce{A}]^2[\ce{B}]$ | $\text{dm}^6\text{ mol}^{-2}\text{ s}^{-1}$ |

## 从 Initial Rates 判断级数

Initial rates method 比较多组实验：只改变一个反应物浓度，其他浓度保持不变。如果 $[\ce{A}]$ 变为 2 倍，rate 变为 4 倍，则关于 $\ce{A}$ 是 second order，因为 $2^2=4$。

当其他浓度不变时：

$$
\frac{\text{rate}_2}{\text{rate}_1}
= \left(\frac{[\ce{A}]_2}{[\ce{A}]_1}\right)^m
$$

## Graphs And Initial Rates

从 concentration-time 数据求某一时刻的 rate，要取该点切线的斜率。反应物浓度随时间下降，斜率为负，但 rate 报告为正值：

$$
\text{rate} = -\frac{\Delta[\text{reactant}]}{\Delta t}
$$

rate-concentration 图像中：

- zero order 是水平线
- first order 是过原点直线
- second order 是随浓度升高变陡的曲线

## Half-Life

Half-life，$t_{1/2}$，是反应物浓度降到原来一半所需的时间。

first-order reaction 的 half-life 与浓度无关。这是判断 first order 的重要特征。如果 concentration-time 表中每次浓度减半所需时间相同，就说明该反应对这个反应物是一阶。

first-order reaction：

$$
k = \frac{0.693}{t_{1/2}}
$$

若 $t_{1/2}$ 用 second，$k$ 的单位就是 $\text{s}^{-1}$。

## Mechanisms And Rate-Determining Step

Reaction mechanism 是一系列 elementary steps，相加后得到 overall reaction。**Rate-determining step** 是最慢的一步。**Intermediate** 在某一步生成、后面又被消耗，不出现在总方程中。**Catalyst** 在某一步被消耗，后面又被再生。

检查机理时看四点：

1. 所有步骤相加是否得到 overall reaction。
2. slow step 是否与 rate equation 一致。
3. intermediates 是否在总方程中约去。
4. catalysts 是否最终再生。

如果 slow step 是：

$$
\ce{A + B -> P}
$$

则该 elementary slow step 对应的 rate equation 通常为：

$$
\text{rate} = k[\ce{A}][\ce{B}]
$$

若实验 rate equation 与总方程的系数不一致，说明总反应通常不是一步完成。

## 温度与 Rate Constant

升高温度会增大 rate constant，因此在浓度不变时反应速率增大。原因是有更多粒子能量达到或超过 activation energy，successful collisions 增多。温度改变 $k$，不改变 reaction order。

## Catalysts

Catalyst 通过提供较低 activation energy 的 alternative route 来提高反应速率。催化剂会再生，总体上不被消耗。

**Heterogeneous catalyst** 与反应物处于不同相。其作用方式包括反应物吸附到表面、键被削弱、表面反应发生、产物脱附。

例子：

- Haber process 中的铁：

$$
\ce{N2(g) + 3H2(g) <=> 2NH3(g)}
$$

- catalytic converter 中的 palladium、platinum 和 rhodium，例如：

$$
\ce{2NO(g) + 2CO(g) -> N2(g) + 2CO2(g)}
$$

**Homogeneous catalyst** 与反应物处于同一相。它在某一步被使用，之后又被再生。

大气中的 nitrogen oxides 可催化 sulfur dioxide 的氧化。简化循环为：

$$
\ce{SO2(g) + NO2(g) -> SO3(g) + NO(g)}
$$

$$
\ce{2NO(g) + O2(g) -> 2NO2(g)}
$$

$\ce{Fe^{2+}}$ 和 $\ce{Fe^{3+}}$ 也可催化 iodide ions 与 peroxodisulfate ions 的反应：

$$
\ce{S2O8^{2-}(aq) + 2I-(aq) -> 2SO4^{2-}(aq) + I2(aq)}
$$

催化过程中 $\ce{Fe^{2+}}$ 和 $\ce{Fe^{3+}}$ 相互转化，最终再生。

## 做题流程

1. 让实验数据决定 rate equation。
2. 比较 initial rates 时，一次只看一个浓度变化。
3. 级数确定后再用 rate equation 求 $k$。
4. 通过重排 rate equation 得到 $k$ 的单位。
5. 用等 half-life 判断 first-order behaviour。
6. 对 mechanism，要把步骤相加，并检查 slow step 是否匹配 rate equation。
7. 区分 thermodynamic feasibility 和 kinetic speed。

## 常见错误

- 没有实验依据就把总方程系数写进 rate equation。
- 比较 initial-rate 数据时同时改变了多个浓度。
- 没有先求 overall order 就写 $k$ 的单位。
- 以为所有反应的 half-life 都与浓度无关。
- 把 intermediate 误认为 catalyst。
- 说 catalyst 改变 equilibrium yield；催化剂改变速率，不改变平衡位置。
