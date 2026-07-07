---
title: Discrete Random Variables 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/03 Discrete Random Variables/00 Overview|Discrete Random Variables]]"
status: active
tags:
  - mathematics/statistics
  - lecture-notes
  - zh-CN
---

# Discrete Random Variables 中文讲义

随机变量是把随机试验结果变成数字的规则。离散随机变量只取一个个分开的值，所以它的分布可以用表格列出来：每个可能值对应一个概率。

学这章时先养成一个习惯：不要一上来写公式，先用一句话说明 $X$ 表示什么，再列出 $X$ 能取哪些值。

## 来源范围

- 9709 5.4 Discrete random variables。
- 9709 6.2 Linear combinations of random variables。
- 教材路线：9709 Probability and Statistics 1 中 discrete random variables and common discrete distributions 相关章节。

## 关联内容

- [[20 Mathematics/03 Probability and Statistics/02 Counting and Probability/00 Overview|Counting and Probability]]
- [[20 Mathematics/03 Probability and Statistics/04 Normal and Poisson Distributions/00 Overview|Normal and Poisson Distributions]]
- [[20 Mathematics/03 Probability and Statistics/07 Chi Squared Nonparametric and PGF/00 Overview|Chi-Squared, Non-Parametric Tests and PGF]]

## 学习顺序

1. 从简单实验建立概率分布表。
2. 练习期望和方差计算。
3. 学习线性变换和独立随机变量之和。
4. 学习二项分布建模条件。
5. 学习几何分布建模条件。
6. 最后处理累计概率和端点检查。

## 图示导读

![[assets/generated/mathematics/discrete-random-variables.svg]]

这张图把单点概率和累计概率放在一起看。离散变量里，端点是否包含非常重要。

## 1. 随机变量

随机变量是把随机结果转成数字的规则。例如投两枚硬币，令 $X$ 表示正面个数，则

$$
X=0,1,2.
$$

离散随机变量只取分开的值。它的概率分布要满足两件事：

$$
0\le P(X=x)\le 1,
$$

$$
\sum P(X=x)=1.
$$

例如投两枚公平硬币，令 $X$ 表示正面个数，则分布表为

| $x$ | $0$ | $1$ | $2$ |
|---|---:|---:|---:|
| $P(X=x)$ | $\frac14$ | $\frac12$ | $\frac14$ |

概率和为 1。由表也可以直接看累计概率，例如

$$
P(X\le 1)=\frac14+\frac12=\frac34.
$$

## 2. 期望

期望是长期平均值：

$$
E(X)=\sum xP(X=x).
$$

它不一定是随机变量实际能取到的值。例如掷骰子的期望是 3.5，但骰子不会掷出 3.5。

## 3. 方差

方差衡量随机变量围绕期望的分散程度：

$$
\operatorname{Var}(X)=E\left((X-\mu)^2\right),
$$

其中 $\mu=E(X)$。

计算时常用

$$
\operatorname{Var}(X)=E(X^2)-[E(X)]^2.
$$

标准差是

$$
\sqrt{\operatorname{Var}(X)}.
$$

以上面的两枚硬币为例，

$$
E(X)=0\cdot\frac14+1\cdot\frac12+2\cdot\frac14=1,
$$

并且

$$
E(X^2)=0^2\cdot\frac14+1^2\cdot\frac12+2^2\cdot\frac14=\frac32.
$$

所以

$$
\operatorname{Var}(X)=\frac32-1^2=\frac12.
$$

## 4. 线性变换

如果

$$
Y=aX+b,
$$

那么

$$
E(Y)=aE(X)+b,
$$

$$
\operatorname{Var}(Y)=a^2\operatorname{Var}(X).
$$

注意加上常数 $b$ 会改变中心位置，但不会改变分散程度。

如果 $X,Y$ 独立，那么

$$
\operatorname{Var}(aX+bY)=a^2\operatorname{Var}(X)+b^2\operatorname{Var}(Y).
$$

这里“独立”很关键。没有独立性，方差不能这样直接相加。

## 5. 二项分布

若满足以下条件：

- 固定试验次数 $n$；
- 每次只有成功和失败；
- 每次成功概率相同，为 $p$；
- 各次试验独立；

则成功次数

$$
X\sim B(n,p).
$$

概率是

$$
P(X=r)=\binom{n}{r}p^r(1-p)^{n-r}.
$$

期望和方差是

$$
E(X)=np,\qquad \operatorname{Var}(X)=np(1-p).
$$

累积二项概率通常要把几个单点概率相加。例如若 $X\sim B(8,0.3)$，则

$$
P(X\le 2)=P(X=0)+P(X=1)+P(X=2),
$$

也就是

$$
P(X\le 2)=0.7^8+8(0.3)(0.7)^7+\binom82(0.3)^2(0.7)^6.
$$

## 6. 几何分布

CAIE 的几何分布 $\operatorname{Geo}(p)$ 表示“第一次成功出现在第几次试验”。如果 $X\sim\operatorname{Geo}(p)$，则

$$
P(X=r)=p(1-p)^{r-1},\qquad r=1,2,3,\ldots
$$

期望是

$$
E(X)=\frac1p.
$$

它适合“独立重复试验，直到第一次成功”的场景。注意 $X$ 从 1 开始，不是从 0 开始。

在这个约定下，

$$
P(X\le r)=1-(1-p)^r,
$$

因为 $X\le r$ 表示前 $r$ 次中至少成功一次；而

$$
P(X>r)=(1-p)^r,
$$

表示前 $r$ 次全失败。

## 7. 累积分布

累积概率

$$
P(X\le r)
$$

是把 $r$ 及以下的概率都加起来。计算 $P(X<r)$、$P(X\ge r)$ 时，要注意离散变量端点是否包含。

例如

$$
P(X\ge 3)=1-P(X\le 2).
$$

若 $X\sim\operatorname{Geo}(0.2)$，则

$$
P(X\le 4)=1-0.8^4=0.5904.
$$

但

$$
P(X<4)=P(X\le 3)=1-0.8^3=0.488.
$$

端点是否包含会改变答案。

## 做题顺序

1. 用一句话定义随机变量。
2. 列出可能取值。
3. 写出概率分布表或识别标准分布。
4. 检查概率和是否为 1。
5. 需要时计算 $E(X)$、$E(X^2)$ 和 $\operatorname{Var}(X)$。
6. 使用二项或几何分布前，先检查模型条件。
7. 把期望、方差和概率放回题目语境解释。

## 常见错误

- 概率分布表里概率和不等于 1。
- 把期望当成一定能取到的值。
- 方差线性变换时写成 $a\operatorname{Var}(X)+b$，漏掉正确的 $a^2\operatorname{Var}(X)$。
- 二项分布题没有检查独立和固定成功概率。
- 几何分布中忘记 $r$ 从 1 开始。
- 离散概率中把 $<$ 和 $\le$ 混淆。

## 快速自查

- 我能不能先写清楚随机变量表示什么？
- 我能不能检查概率分布是否合法？
- 我能不能计算 $E(X)$ 和 $\operatorname{Var}(X)$？
- 我能不能判断一个问题是否适合二项分布？
- 我能不能判断一个问题是否适合几何分布？
