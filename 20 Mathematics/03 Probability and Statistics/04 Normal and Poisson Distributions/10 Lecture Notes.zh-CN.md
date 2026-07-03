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

正态分布处理围绕中心上下波动的连续测量值，泊松分布处理固定区间内随机事件发生的次数。一个看曲线下面积，一个算离散计数概率；二者又会通过近似和随机变量线性组合联系起来。

这章最重要的习惯是先看模型：变量是连续测量，还是计数？参数有没有和单位区间匹配？如果用正态近似离散分布，有没有做连续性修正？

## 图示导读

![[assets/generated/mathematics/normal-and-poisson-distributions.svg]]

这张图比较连续正态面积和离散泊松计数。正态图像下的面积是概率；泊松分布的每个整数点都有一个概率。

## 1. 正态分布

若

$$
X\sim N(\mu,\sigma^2),
$$

表示 $X$ 服从均值为 $\mu$、方差为 $\sigma^2$ 的正态分布。

注意第二个参数是方差 $\sigma^2$，标准差是 $\sigma$。正态分布曲线关于 $\mu$ 对称，概率对应曲线下面积。

正态分布是连续分布，所以

$$
P(X=a)=0.
$$

因此 $<$ 和 $\le$ 在正态概率里没有区别。

## 2. 标准化

标准化公式是

$$
Z=\frac{X-\mu}{\sigma}.
$$

于是

$$
Z\sim N(0,1).
$$

查表或用计算器时，通常先把 $X$ 转成 $Z$。

例如求

$$
P(a<X<b),
$$

可以标准化成

$$
P\left(\frac{a-\mu}{\sigma}<Z<\frac{b-\mu}{\sigma}\right).
$$

反求临界值时，先由概率找到对应的 $z$ 值，再用

$$
z=\frac{x-\mu}{\sigma}
$$

解出 $x$、$\mu$ 或 $\sigma$。

## 3. 泊松分布

泊松分布用于固定区间内的随机计数。这里的区间可以是时间、长度、面积或体积。它适合事件大致独立、平均发生率比较稳定的情况。

如果单位区间内平均发生次数为 $\lambda$，则

$$
X\sim \operatorname{Po}(\lambda).
$$

概率公式是

$$
P(X=r)=\frac{e^{-\lambda}\lambda^r}{r!}.
$$

泊松分布的均值和方差都是

$$
E(X)=\operatorname{Var}(X)=\lambda.
$$

如果时间区间变为原来的 $k$ 倍，平均次数也变为 $k\lambda$。

## 4. 线性组合

线性变换满足

$$
E(aX+b)=aE(X)+b,\qquad \operatorname{Var}(aX+b)=a^2\operatorname{Var}(X).
$$

如果 $X,Y$ 独立，则

$$
\operatorname{Var}(aX+bY)=a^2\operatorname{Var}(X)+b^2\operatorname{Var}(Y).
$$

分布类型也有稳定性：

- 正态变量做线性变换仍是正态；
- 独立正态变量的线性组合仍是正态；
- 独立泊松变量相加仍是泊松，参数相加。

## 5. 近似

当 $n$ 大、$p$ 小，且 $np$ 适中时，

$$
B(n,p)\approx \operatorname{Po}(np).
$$

CAIE 给的经验条件是 $n>50$ 且 $np<5$。

当 $n$ 较大时，二项分布也可用正态近似：

$$
B(n,p)\approx N(np,np(1-p)).
$$

常用条件是 $np>5$ 且 $n(1-p)>5$。

当 $\lambda$ 较大时，泊松分布可用正态近似：

$$
\operatorname{Po}(\lambda)\approx N(\lambda,\lambda),
$$

通常要求 $\lambda>15$ 左右。

用正态近似离散分布时，需要连续性修正。例如

$$
P(X\le 10)
$$

近似为

$$
P(Y<10.5).
$$

又如

$$
P(4\le X\le 10)
$$

近似为

$$
P(3.5<Y<10.5).
$$

## 常见错误

- 把正态分布的第二个参数 $\sigma^2$ 当成标准差。
- 标准化时忘记除以 $\sigma$。
- 泊松分布中区间长度变了但 $\lambda$ 没变。
- 用正态近似离散分布时忘记连续性修正。
- 把连续分布的单点概率当成非零。
- 随机变量不独立时还直接相加方差。

## 快速自查

- 我能不能把 $X$ 标准化成 $Z$？
- 我能不能从图像面积理解正态概率？
- 我能不能判断什么时候适合泊松分布？
- 我能不能按区间长度调整 $\lambda$？
- 我能不能正确使用连续性修正？
