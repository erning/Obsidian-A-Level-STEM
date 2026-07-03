---
title: Further Calculus and Differential Equations 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/13 Further Calculus and Differential Equations/00 Overview|Further Calculus and Differential Equations]]"
status: draft
tags:
  - mathematics/pure
  - lecture-notes
  - zh-CN
---

# Further Calculus and Differential Equations 中文讲义

这一章把微分和积分用到更复杂的函数和变化模型里。进一步微积分关心“怎样选方法”，微分方程关心“一个量的变化率怎样决定它自己的变化”。

学习顺序可以这样看：

- hyperbolic functions 是新的函数族；
- Maclaurin series 用导数做局部展开；
- further integration 训练方法选择；
- differential equations 把变化率写成方程并求解。

## 图示导读

![[assets/generated/mathematics/further-calculus-and-differential-equations.svg]]

这张图用来快速理解“进阶微积分与微分方程”：用斜率场看微分方程的解曲线。

## 学习范围

- 更复杂的求导、积分和函数展开。
- hyperbolic functions、inverse hyperbolic functions 和 Maclaurin series。
- 一阶微分方程：可分离变量和一阶线性方程。
- 常系数线性微分方程：complementary function 和 particular integral。
- 用初值或边界条件确定常数。
- 给定 substitution 后化简微分方程。

## 1. 双曲函数

双曲函数用指数函数定义：

$$
\sinh x=\frac{e^x-e^{-x}}{2},
\qquad
\cosh x=\frac{e^x+e^{-x}}{2}.
$$

并且

$$
\tanh x=\frac{\sinh x}{\cosh x}.
$$

核心恒等式是

$$
\cosh^2x-\sinh^2x=1.
$$

双曲函数和三角函数很像，但符号不同。反双曲函数可以写成对数形式，通常从指数定义推出来。

## 2. Maclaurin series

Maclaurin series 是在 $x=0$ 附近展开函数：

$$
f(x)=f(0)+xf'(0)+\frac{x^2}{2!}f''(0)+\frac{x^3}{3!}f'''(0)+\cdots.
$$

做题步骤很机械：

1. 求 $f(0)$；
2. 连续求导；
3. 把各阶导数在 $x=0$ 的值代入；
4. 写出前几项。

有时会用隐函数求导来得到各阶导数，例如把某个导数先改写成只含 $y$ 的形式。

## 3. 进一步积分的重点

到这一章，积分的关键不是硬算，而是选方法：

- 乘积结构：考虑分部积分；
- 复合函数和内层导数：考虑换元；
- 有理函数：考虑部分分式；
- 二次式根号或分母：考虑配方、三角换元或双曲换元；
- 参数 $n$ 的积分：考虑 reduction formula。

reduction formulae 把含 $n$ 的积分化成含 $n-2$ 或 $n-1$ 的积分。通常由分部积分或某个乘积的导数得到。

## 4. 微分方程是什么

微分方程是含有未知函数及其导数的方程。例如

$$
\frac{dy}{dx}=ky
$$

表示 $y$ 的变化率与 $y$ 本身成正比。

解微分方程，就是找到满足这个关系的函数 $y(x)$。

通解含有任意常数。给了初值以后，可以求出这些常数，得到特解。

## 5. 可分离变量

如果微分方程可以写成

$$
\frac{dy}{dx}=g(x)h(y),
$$

就可以分离变量：

$$
\frac{1}{h(y)}\,dy=g(x)\,dx.
$$

然后两边积分。

例如

$$
\frac{dy}{dx}=xy.
$$

分离得

$$
\frac{1}{y}\,dy=x\,dx.
$$

积分：

$$
\ln|y|=\frac{x^2}{2}+C.
$$

所以

$$
y=Ae^{x^2/2}.
$$

如果分离变量时除以了 $y$，还要想一想是否漏掉 $y=0$ 这样的特殊解。

## 6. 用微分方程建模

一句变化率描述可以直接翻译成微分方程。比如“$y$ 的变化率与 $y$ 成正比”就是

$$
\frac{dy}{dt}=ky.
$$

这里 $k$ 是比例常数，需要根据条件求出。

解完以后要解释：

- 量是在增长还是衰减？
- 是否趋向某个极限？
- 常数在模型中表示什么？
- 解的定义域是否符合实际背景？

## 7. 一阶线性方程

一阶线性微分方程常写成

$$
\frac{dy}{dx}+P(x)y=Q(x).
$$

它的核心方法是积分因子。积分因子是

$$
\mu(x)=e^{\int P(x)\,dx}.
$$

两边乘以 $\mu(x)$ 后，左边会变成一个乘积的导数：

$$
\frac{d}{dx}(\mu y)=\mu Q(x).
$$

然后积分即可。

这个方法的关键是先把方程整理成标准形式，让 $\frac{dy}{dx}$ 的系数为 1。

## 8. 常系数线性方程

线性微分方程的通解可以写成

$$
\text{general solution}=\text{complementary function}+\text{particular integral}.
$$

complementary function 解的是对应的齐次方程。particular integral 是非齐次项带来的一个特解。

例如二阶方程含有

$$
\frac{d^2y}{dx^2}.
$$

有些二阶方程可以通过特征方程求解。例如

$$
\frac{d^2y}{dx^2}-3\frac{dy}{dx}+2y=0.
$$

试 $y=e^{\lambda x}$，得到特征方程

$$
\lambda^2-3\lambda+2=0.
$$

解得 $\lambda=1,2$，所以通解是

$$
y=Ae^x+Be^{2x}.
$$

然后用条件求 $A$、$B$。

二阶常系数方程的辅助方程可能有三种情况：

- 两个不同实根；
- 重根；
- 共轭复根。

每种情况对应不同形式的 complementary function。

particular integral 的试探形式要看右边是什么：多项式、$ae^{bx}$、$a\cos px+b\sin px$ 等。把试探形式代回方程，求系数。

## 9. 微分方程中的 substitution

有些微分方程题会给 substitution。比如 $x=e^t$ 可以把某些方程化成常系数形式；$y=ux$ 可以把某些一阶方程化成可分离变量。

步骤是：

1. 小心改写导数；
2. 把 substitution 代入原方程；
3. 解新方程；
4. 换回原变量。

## 10. 用解检查方程

微分方程的答案最好代回去检查。把求出的 $y$ 求导，再放回原方程，看左右是否一致。若有初值，也要检查初值是否满足。

这一步很值得做，因为微分方程中常数、符号和指数特别容易错。

## 做题套路

### 从文字建模

1. 找出变化的量和自变量。
2. 把“变化率”翻译成导数。
3. 需要时引入比例常数。
4. 解微分方程。
5. 用初值或边界条件定常数。
6. 回到原问题解释答案。

### 解微分方程

1. 先分类：可分离、一阶线性、常系数线性，还是需要 substitution。
2. 整理成标准形式。
3. 选对应方法。
4. 写通解和任意常数。
5. 用条件求特解。
6. 代回检查。

## 常见错误

- 分离变量时把含 $x$ 和含 $y$ 的量混在同一边。
- 积分后忘记常数。
- 一阶线性方程没有先整理成标准形式。
- 积分因子算错，后面全错。
- 求出通解后没有代入初值。
- 除以某个表达式时漏掉它等于 0 的特殊解。
- 把 complementary function 和 particular integral 混在一起。
- particular integral 的试探形式和 complementary function 重合时没有调整。
- 解出来以后不解释模型含义。

## 快速自查

- 我能不能判断一个方程是否可分离变量？
- 我能不能写出一阶线性方程的积分因子？
- 我能不能区分通解和特解？
- 我能不能把解代回微分方程检查？
- 我能不能写出 Maclaurin series 的前几项？
- 我能不能识别 complementary function 和 particular integral？
- 我能不能用初值或边界条件确定常数并解释结果？
