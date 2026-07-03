---
title: Normal and Poisson Distributions 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/04 Normal and Poisson Distributions/00 Overview|Normal and Poisson Distributions]]"
status: draft
tags:
  - mathematics/statistics
  - lecture-notes
  - zh-CN
---

# Normal and Poisson Distributions 中文讲义

这一章的主线是：正态分布处理连续测量值的波动，泊松分布处理单位时间或单位区域内的稀有计数。一个是连续曲线下面积，一个是离散计数概率。

1. 随机变量是连续测量值，还是计数？
2. 正态分布是否需要标准化？
3. 泊松分布的平均发生率 $\lambda$ 是否与区间长度匹配？
4. 近似时是否需要连续性修正？

## 图示导读

![[assets/generated/mathematics/normal-and-poisson-distributions.svg]]

这张图用来快速理解“正态分布与泊松分布”：比较连续正态面积和离散泊松计数。

## 学习范围

- 正态分布、标准化和正态表。
- 正态分布中的区间概率和反求临界值。
- 泊松分布、均值和方差。
- 二项、泊松、正态之间的近似关系。

## 1. 正态分布

若

$$
X\sim N(\mu,\sigma^2),
$$

表示 $X$ 服从均值为 $\mu$、方差为 $\sigma^2$ 的正态分布。

正态分布曲线关于 $\mu$ 对称。概率对应曲线下面积。

标准化公式是

$$
Z=\frac{X-\mu}{\sigma}.
$$

于是

$$
Z\sim N(0,1).
$$

查表或用计算器时，通常先把 $X$ 转成 $Z$。

## 2. 区间概率

例如求

$$
P(a<X<b),
$$

可以标准化成

$$
P\left(\frac{a-\mu}{\sigma}<Z<\frac{b-\mu}{\sigma}\right).
$$

正态分布是连续的，所以

$$
P(X=a)=0.
$$

因此 $<$ 和 $\le$ 在连续分布里没有区别。

## 3. 泊松分布

泊松分布用于计数。如果单位区间内平均发生次数为 $\lambda$，则

$$
X\sim Po(\lambda).
$$

概率公式是

$$
P(X=r)=\frac{e^{-\lambda}\lambda^r}{r!}.
$$

泊松分布的均值和方差都是

$$
E(X)=Var(X)=\lambda.
$$

如果时间区间变为原来的 $k$ 倍，平均次数也变为 $k\lambda$。

## 4. 近似

当 $n$ 大、$p$ 小，且 $np$ 适中时，

$$
B(n,p)\approx Po(np).
$$

当 $n$ 较大时，二项分布也可用正态近似：

$$
B(n,p)\approx N(np,np(1-p)).
$$

用正态近似离散分布时，需要连续性修正。例如

$$
P(X\le 10)
$$

近似为

$$
P(Y<10.5).
$$

## 5. 常见错误

- 把正态分布的第二个参数 $\sigma^2$ 当成标准差。
- 标准化时忘记除以 $\sigma$。
- 泊松分布中区间长度变了但 $\lambda$ 没变。
- 用正态近似离散分布时忘记连续性修正。
- 把连续分布的单点概率当成非零。

## 快速自查

- 我能不能把 $X$ 标准化成 $Z$？
- 我能不能从图像面积理解正态概率？
- 我能不能判断什么时候适合泊松分布？
- 我能不能正确使用连续性修正？
