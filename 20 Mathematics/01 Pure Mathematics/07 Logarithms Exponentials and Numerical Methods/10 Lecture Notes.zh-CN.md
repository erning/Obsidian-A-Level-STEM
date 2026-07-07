---
title: Logarithms, Exponentials and Numerical Methods 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/07 Logarithms Exponentials and Numerical Methods/00 Overview|Logarithms, Exponentials and Numerical Methods]]"
status: active
tags:
  - mathematics/pure
  - lecture-notes
  - zh-CN
---

# Logarithms, Exponentials and Numerical Methods 中文讲义

这一章有两条主线。指数和对数处理增长、衰减、反函数和变形；数值方法处理“代数上不好解，但可以逐步逼近”的方程。

记住两个提醒：

- 对数先守定义域，真数必须大于 0；
- 迭代先守精度，中间步骤不要过早四舍五入。

## 图示导读

![[assets/generated/mathematics/logarithms-exponentials-and-numerical-methods.svg]]

这张图用来快速理解“对数、指数函数与数值方法”：把指数、对数互为反函数和牛顿迭代放在一起看。

## 来源范围

- 9709 2.2 Logarithmic and exponential functions。
- 9709 3.2 Logarithmic and exponential functions。
- 9709 2.6 Numerical solution of equations。
- 9709 3.6 Numerical solution of equations。
- Coursebook route：9709 Pure Mathematics 2 and 3 Chapters 2 and 6。

## 学习范围

- 指数函数、对数函数和反函数关系。
- 对数运算法则、指数方程和对数方程。
- 指数增长、指数衰减和半衰期。
- 用对数把关系式化成直线形式。
- 用变号、图像和不动点迭代（fixed-point iteration）近似求根。
- 牛顿迭代（Newton iteration）作为切线法的补充理解。

## 1. 指数和对数互为反函数

如果

$$
y=a^x,\qquad a>0,\ a\ne 1,
$$

那么它的反函数是

$$
x=\log_a y.
$$

对数回答的问题是：“底数 $a$ 要乘自己多少次，才能得到这个数？”

最常用的自然对数是 $\ln x$，底数是 $e$。它和 $e^x$ 互为反函数：

$$
\ln(e^x)=x,\qquad e^{\ln x}=x.
$$

第二个式子要求 $x>0$。

图像上，$y=e^{kx}$ 的形状由 $k$ 的符号控制。$k>0$ 时增长，$k<0$ 时衰减。$y=\ln x$ 的定义域是 $x>0$，并且在 $x=0$ 有竖直渐近线。

## 2. 对数法则

常用法则是

$$
\log_a xy=\log_a x+\log_a y,
$$

$$
\log_a\frac{x}{y}=\log_a x-\log_a y,
$$

$$
\log_a x^n=n\log_a x.
$$

这些法则都要求相关真数为正。比如 $\ln(x-2)$ 只有在

$$
x>2
$$

时才有定义。

对数法则不能拆加法：

$$
\ln(x+y)\ne \ln x+\ln y.
$$

解对数方程时，第一步先写定义域。最后得到的解还要代回去检查。

## 3. 指数和对数方程

未知数在指数上时，通常要取对数。例如

$$
3e^{2x}=15.
$$

先除以 3：

$$
e^{2x}=5.
$$

再取自然对数：

$$
2x=\ln5,
$$

所以

$$
x=\frac{1}{2}\ln5.
$$

对数不等式也要注意单调性。$\ln x$ 在 $x>0$ 上递增，所以取 $\ln$ 不会改变不等号方向。底数大于 1 的指数函数递增；底数在 0 和 1 之间的指数函数递减。

## 4. 指数模型

指数增长和衰减常写成

$$
N=N_0e^{kt}.
$$

如果 $k>0$，是增长；如果 $k<0$，是衰减。

半衰期问题中，如果每隔 $T$ 时间剩下一半，那么

$$
\frac{1}{2}=e^{kT}.
$$

所以

$$
k=\frac{\ln(1/2)}{T}.
$$

指数模型里最常见的错误是符号。衰减的 $k$ 应该是负数。

## 5. 化成直线形式

对数可以把一些非线性关系化成直线。这样可以从图像的斜率和截距读出常数。

如果

$$
y=kx^n,
$$

两边取对数：

$$
\ln y=\ln k+n\ln x.
$$

这说明画 $\ln y$ 对 $\ln x$ 的图像，会得到直线。斜率是 $n$，截距是 $\ln k$。

如果

$$
y=ka^x,
$$

两边取对数：

$$
\ln y=\ln k+x\ln a.
$$

这说明画 $\ln y$ 对 $x$ 的图像，会得到直线。斜率是 $\ln a$，截距是 $\ln k$。

如果

$$
y=ke^{bx},
$$

则

$$
\ln y=\ln k+bx.
$$

斜率就是 $b$。

做这种题时，先判断应该画 $\ln y$ 对 $x$，还是 $\ln y$ 对 $\ln x$。轴选错了，斜率意义就错了。

## 6. 方程求根的数值思想

很多方程不能漂亮地因式分解，比如

$$
x^3-x-1=0.
$$

这时可以用数值方法找近似根。最基本的检查是变号：如果 $f(a)$ 和 $f(b)$ 异号，并且函数在区间内连续，那么 $[a,b]$ 内至少有一个根。

这个方法能定位根所在的区间，但不直接给精确值。

也可以把方程理解成两条图像的交点。例如 $f(x)=0$ 可以改写成 $g(x)=h(x)$。图像先告诉你根大概在哪里，迭代再负责把数值逼近。

## 7. 不动点迭代

如果方程能改写成

$$
x=F(x),
$$

可以用

$$
x_{n+1}=F(x_n)
$$

反复迭代。

从一个初值 $x_0$ 出发，依次算 $x_1,x_2,x_3,\ldots$。如果这些数逐渐靠近某个 $\alpha$，那么 $\alpha$ 就是一个不动点（fixed point），也对应原方程的根。

但不是所有改写都稳定。同一个方程，不同的 rearrangement 可能一个收敛、一个发散，也可能收敛到不同的根。做题时要观察连续几步是否靠近同一个数，并按题目要求给出小数位数。

中间迭代要保留足够精度，最后再按要求四舍五入。

## 8. 牛顿迭代

牛顿迭代（Newton iteration）用切线逼近根：

$$
x_{n+1}=x_n-\frac{f(x_n)}{f'(x_n)}.
$$

它通常收敛很快，但依赖初始值。如果起点选得不好，可能跑到别的根附近，甚至不收敛。若 $f'(x_n)$ 接近 0，也会出问题。

在这套笔记里，不动点迭代是 9709 的核心要求；牛顿迭代作为图像和切线思想的延伸来理解。

## 做题顺序

### 指数或对数方程

1. 先写真数大于 0 的定义域条件。
2. 能简化先简化，再取对数。
3. 对数法则只用于乘法、除法和幂。
4. 解出候选值。
5. 代回原方程检查。

### 化成直线形式

1. 先识别模型：$y=kx^n$、$y=ka^x$ 还是 $y=ke^{bx}$。
2. 两边取 $\ln$。
3. 整理成 $Y=mX+c$。
4. 判断横轴和纵轴应该是什么。
5. 从斜率和截距还原参数。

### 数值求根

1. 先用图像或变号定位根。
2. 使用给定或合适的 rearrangement，写成 $x=F(x)$。
3. 选靠近根的初值。
4. 保留足够精度迭代。
5. 把结果代回原方程，并说明精度。

## 常见错误

- 对数方程没有先写真数大于 0 的条件。
- 把 $\ln(x+y)$ 拆成 $\ln x+\ln y$。这是错的。
- 指数衰减模型里把 $k$ 写成正数。
- 数值方法中太早四舍五入，导致后面误差变大。
- 迭代结果看起来稳定，但没有按要求说明精度。
- 化直线时把 $\ln y$ 对 $x$ 和 $\ln y$ 对 $\ln x$ 混淆。
- 以为任何 rearrangement 都会收敛。
- 找到近似根后没有代回原方程检查。

## 快速自查

- 我能不能说明指数和对数为什么互为反函数？
- 我能不能熟练使用对数法则，并检查定义域？
- 我能不能从半衰期求出指数模型中的常数？
- 我能不能把 $y=kx^n$ 和 $y=ka^x$ 化成直线形式？
- 我能不能用变号定位根？
- 我能不能用不动点迭代写出清楚的迭代表？
- 我能不能解释牛顿迭代的切线意义？

## 关联内容

- [[10 Physics/01 Topics/19 Capacitance/00 Overview|Physics Capacitance]]：指数衰减模型会用于电容放电。
- [[10 Physics/01 Topics/23 Nuclear Physics/00 Overview|Physics Nuclear Physics]]：半衰期和指数衰减会用于放射性衰变模型。
