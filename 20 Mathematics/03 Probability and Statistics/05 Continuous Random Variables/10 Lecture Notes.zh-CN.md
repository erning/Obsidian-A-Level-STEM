---
title: Continuous Random Variables 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/05 Continuous Random Variables/00 Overview|Continuous Random Variables]]"
status: draft
tags:
  - mathematics/statistics
  - lecture-notes
  - zh-CN
---

# Continuous Random Variables 中文讲义

这一章的主线是：连续随机变量的概率不是点的高度，而是曲线下面积。概率密度函数可以大于 1，但总面积必须等于 1。

1. 给的是概率密度函数，还是累计分布函数？
2. 函数在定义域外是否为 0？
3. 要求的是区间概率、期望，还是分位点？
4. 积分上下限是否与题目区间一致？

## 图示导读

![[assets/generated/mathematics/continuous-random-variables.svg]]

这张图用来快速理解“连续随机变量”：把概率密度和累积分布作为一对视图理解。

## 学习范围

- 概率密度函数和累计分布函数。
- 区间概率、期望、方差和中位数。
- 分段密度函数和常数确定。
- 连续分布中的单点概率和面积理解。

## 1. 概率密度函数

连续随机变量 $X$ 的概率密度函数记为 $f(x)$。它必须满足

$$
f(x)\ge 0,
$$

并且总面积为 1：

$$
\int_{-\infty}^{\infty} f(x)\,dx=1.
$$

区间概率是面积：

$$
P(a<X<b)=\int_a^b f(x)\,dx.
$$

单点概率为 0：

$$
P(X=a)=0.
$$

## 2. 确定常数

如果密度函数里有未知常数，通常用总面积为 1 求它。

例如

$$
f(x)=kx,\qquad 0\le x\le 2.
$$

因为总面积为 1，

$$
\int_0^2 kx\,dx=1.
$$

所以

$$
2k=1,\qquad k=\frac{1}{2}.
$$

## 3. 累计分布函数

累计分布函数是

$$
F(x)=P(X\le x).
$$

它和密度函数的关系是

$$
F(x)=\int_{-\infty}^{x} f(t)\,dt.
$$

反过来，

$$
f(x)=F'(x).
$$

求区间概率也可以用

$$
P(a<X<b)=F(b)-F(a).
$$

## 4. 期望和方差

连续随机变量的期望是

$$
E(X)=\int_{-\infty}^{\infty} x f(x)\,dx.
$$

方差可以用

$$
Var(X)=E(X^2)-[E(X)]^2,
$$

其中

$$
E(X^2)=\int_{-\infty}^{\infty} x^2 f(x)\,dx.
$$

分段函数要分段积分。

## 5. 中位数和分位点

连续分布的中位数 $m$ 满足

$$
P(X\le m)=\frac{1}{2}.
$$

也就是

$$
F(m)=0.5.
$$

分位点问题本质上也是解 $F(x)=p$。

## 6. 常见错误

- 把密度函数的高度当成概率。
- 忘记密度函数总面积必须等于 1。
- 分段函数积分时漏掉某一段。
- 把 $F(x)$ 和 $f(x)$ 混淆。
- 连续分布里把 $P(X=a)$ 当成非零。

## 快速自查

- 我能不能用总面积为 1 求密度函数里的常数？
- 我能不能从密度函数求累计分布函数？
- 我能不能用积分求期望和方差？
- 我能不能解释为什么连续变量单点概率为 0？
