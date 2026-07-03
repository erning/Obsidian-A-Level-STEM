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

连续随机变量的概率不是某一点的高度，而是曲线下面积。概率密度函数可以大于 1，这并不矛盾；只要总面积等于 1，它就是合法的密度函数。

这章做题时一定要先写定义域，也就是密度函数在哪些地方不为 0。很多错误都来自忘记定义域，或者积分上下限跨出了定义域。

## 图示导读

![[assets/generated/mathematics/continuous-random-variables.svg]]

这张图把概率密度和累计分布作为一对视图。密度看局部形状，累计分布看从左到右累积了多少面积。

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

所以连续变量里，$P(a<X<b)$、$P(a\le X<b)$ 和 $P(a\le X\le b)$ 的概率相同。

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

分段密度函数要分段积分。不要把某一段漏掉，也不要在定义域外继续积分。

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

CDF 要从 0 开始，最后趋近于 1；如果你求出的函数不满足这一点，通常说明分段或常数出了问题。

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

更一般地，如果要求 $g(X)$ 的期望，

$$
E(g(X))=\int_{-\infty}^{\infty}g(x)f(x)\,dx.
$$

例如 $E(X^2)$ 就是把 $g(x)$ 取成 $x^2$。

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

## 6. 相关变量

如果 $Y=g(X)$，常用 CDF 方法：

$$
F_Y(y)=P(Y\le y).
$$

把关于 $Y$ 的事件改写成关于 $X$ 的事件，再使用 $X$ 的 CDF。如果还要 $Y$ 的 PDF，就对 $F_Y(y)$ 求导。

例如 $Y=X^3$，且在定义域上单调递增，则

$$
F_Y(y)=P(X^3\le y)=P(X\le \sqrt[3]{y})=F_X(\sqrt[3]{y}).
$$

这类题最要小心的是 $Y$ 的取值范围，以及变换在定义域上是否一一对应。

## 常见错误

- 把密度函数的高度当成概率。
- 忘记密度函数总面积必须等于 1。
- 分段函数积分时漏掉某一段。
- 把 $F(x)$ 和 $f(x)$ 混淆。
- 连续分布里把 $P(X=a)$ 当成非零。
- 做相关变量时忘记检查新变量的取值范围。

## 快速自查

- 我能不能用总面积为 1 求密度函数里的常数？
- 我能不能从密度函数求累计分布函数？
- 我能不能用积分求期望和方差？
- 我能不能解释为什么连续变量单点概率为 0？
- 我能不能用 CDF 方法处理简单变量变换？
