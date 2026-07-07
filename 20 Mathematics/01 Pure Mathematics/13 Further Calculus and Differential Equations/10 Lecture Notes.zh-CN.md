---
title: Further Calculus and Differential Equations 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/13 Further Calculus and Differential Equations/00 Overview|Further Calculus and Differential Equations]]"
status: active
tags:
  - mathematics/pure
  - lecture-notes
  - zh-CN
---

# Further Calculus and Differential Equations 中文讲义

这一章把微分和积分用到更复杂的函数和变化模型里。进一步微积分关心“怎样选方法”，微分方程关心“一个量的变化率怎样决定它自己的变化”。

学习顺序可以这样看：

- 双曲函数（hyperbolic functions）是新的函数族；
- Maclaurin 级数（Maclaurin series）用导数做局部展开；
- 进一步积分训练方法选择；
- 微分方程把变化率写成方程并求解。

## 图示导读

![[assets/generated/mathematics/further-calculus-and-differential-equations.svg]]

这张图用来快速理解“进阶微积分与微分方程”：用斜率场看微分方程的解曲线。

## 来源范围

- 9709 3.8 Differential equations。
- 9231 2.1 Hyperbolic functions。
- 9231 2.3 Differentiation。
- 9231 2.4 Integration。
- 9231 2.6 Differential equations。
- Coursebook route：9709 Pure Mathematics 2 and 3 Chapter 10；9231 Further Mathematics Coursebook chapters on hyperbolic functions, further calculus, and differential equations。

## 学习范围

- 更复杂的求导、积分和函数展开。
- 双曲函数（hyperbolic functions）、反双曲函数（inverse hyperbolic functions）和 Maclaurin 级数（Maclaurin series）。
- 一阶微分方程：可分离变量和一阶线性方程。
- 常系数线性微分方程：互补函数（complementary function）和特解（particular integral）。
- 用初值或边界条件确定常数。
- 给定换元（substitution）后化简微分方程。

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

双曲函数和三角函数很像，但符号不同。这个符号差异来自指数定义，不要把三角恒等式机械照搬。还要记住：$\sinh x$ 是奇函数，$\cosh x$ 是偶函数，并且 $\cosh x\ge1$。

常用反双曲函数的对数形式是：

$$
\sinh^{-1}x=\ln\left(x+\sqrt{x^2+1}\right),
$$

$$
\cosh^{-1}x=\ln\left(x+\sqrt{x^2-1}\right),\qquad x\ge1,
$$

以及

$$
\tanh^{-1}x=\frac12\ln\left(\frac{1+x}{1-x}\right),\qquad |x|<1.
$$

这里的 $-1$ 表示反函数，不是倒数。倒数函数要写作 $\operatorname{cosech}x$、$\operatorname{sech}x$ 和 $\coth x$。

推导时通常设 $y=\sinh^{-1}x$，于是 $x=\sinh y$。再令 $u=e^y>0$，解关于 $u$ 的二次方程。最后必须选正根，因为 $e^y$ 永远为正。

对应的反函数导数是：

$$
\frac{d}{dx}\sinh^{-1}x=\frac1{\sqrt{x^2+1}},
\qquad
\frac{d}{dx}\cosh^{-1}x=\frac1{\sqrt{x^2-1}},
\qquad
\frac{d}{dx}\tanh^{-1}x=\frac1{1-x^2}.
$$

## 2. Maclaurin 级数

Maclaurin 级数（Maclaurin series）是在 $x=0$ 附近展开函数：

$$
f(x)=f(0)+xf'(0)+\frac{x^2}{2!}f''(0)+\frac{x^3}{3!}f'''(0)+\cdots.
$$

做题步骤很机械：

1. 求 $f(0)$；
2. 连续求导；
3. 把各阶导数在 $x=0$ 的值代入；
4. 写出前几项。

有时会用隐函数求导来得到各阶导数，例如把某个导数先改写成只含 $y$ 的形式。

很多展开也可以由已知级数快速得到。例如由指数定义可得：

$$
\sinh x=x+\frac{x^3}{3!}+\frac{x^5}{5!}+\cdots,
\qquad
\cosh x=1+\frac{x^2}{2!}+\frac{x^4}{4!}+\cdots.
$$

乘积展开时，只保留会影响目标阶数的项。比如到 $x^3$ 为止：

$$
e^x\cos x
=\left(1+x+\frac{x^2}{2}+\frac{x^3}{6}+\cdots\right)
\left(1-\frac{x^2}{2}+\cdots\right)
=1+x-\frac{x^3}{3}+\cdots.
$$

这里没有 $x^2$ 项，因为 $\frac{x^2}{2}$ 和 $-\frac{x^2}{2}$ 抵消了。写答案时要清楚说明保留到哪一阶，不要写出会受省略项影响的“假精确”项。

## 3. 进一步积分的重点

到这一章，积分的关键不是硬算，而是选方法：

- 乘积结构：考虑分部积分；
- 复合函数和内层导数：考虑换元；
- 有理函数：考虑部分分式；
- 二次式根号或分母：考虑配方、三角换元或双曲换元；
- 参数 $n$ 的积分：考虑递推公式。

常见结构可以这样快速识别：

| 结构 | 常见处理 |
| --- | --- |
| $\sqrt{a^2-x^2}$ | 令 $x=a\sin\theta$，或直接识别反正弦形式 |
| $\sqrt{x^2+a^2}$ | 令 $x=a\sinh u$，或识别反双曲正弦形式 |
| $\sqrt{x^2-a^2}$ | 在 $x\ge a$ 时可令 $x=a\cosh u$ |
| 已配方的二次式 | 先平移变量，再套标准形式 |

例如：

$$
\int\frac{dx}{\sqrt{x^2+a^2}}
=\sinh^{-1}\left(\frac{x}{a}\right)+C
=\ln\left|x+\sqrt{x^2+a^2}\right|+C'.
$$

换元的边界很重要：它应该消掉根号、露出标准导数，或把重复结构变简单。若换元后式子更乱，通常说明方法选错了。

递推公式（reduction formulae）把含 $n$ 的积分化成含 $n-2$ 或 $n-1$ 的积分。通常由分部积分或某个乘积的导数得到。

例如

$$
I_n=\int_0^{\pi/2}\sin^n x\,dx
$$

可以由分部积分得到

$$
I_n=\frac{n-1}{n}I_{n-2}.
$$

使用递推公式时，还要知道起始值，例如 $I_0$ 或 $I_1$。只有递推关系本身还不能算出具体数值。

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

例如

$$
\frac{dy}{dx}+2y=e^{-x}
$$

的积分因子是 $\mu=e^{2x}$，所以

$$
\frac{d}{dx}(e^{2x}y)=e^x.
$$

积分后

$$
e^{2x}y=e^x+C,
$$

因此

$$
y=e^{-x}+Ce^{-2x}.
$$

这个方法的关键是先把方程整理成标准形式，让 $\frac{dy}{dx}$ 的系数为 1。$\int P(x)\,dx$ 里的常数通常不写，因为它只会让积分因子多乘一个非零常数，不影响最后结果。

## 8. 常系数线性方程

线性微分方程的通解可以写成

$$
\text{通解}=\text{互补函数}+\text{特解}.
$$

互补函数（complementary function）解的是对应的齐次方程。特解（particular integral）是非齐次项带来的一个特解。

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

- 两个不同实根 $\alpha,\beta$：$Ae^{\alpha x}+Be^{\beta x}$；
- 重根 $\alpha$：$(A+Bx)e^{\alpha x}$；
- 共轭复根 $\alpha\pm i\beta$：$e^{\alpha x}(A\cos\beta x+B\sin\beta x)$。

每种情况对应不同形式的互补函数。

特解的试探形式要看右边是什么：多项式、$ae^{bx}$、$a\cos px+b\sin px$ 等。把试探形式代回方程，求系数。

一个重要边界：如果试探形式已经出现在互补函数里，要乘以 $x$，直到它和互补函数独立。例如右边是 $e^x$，而互补函数里已经有 $e^x$，就不能试 $Ae^x$，应先试 $Axe^x$。这就是特解（particular integral）中常见的重复根或重合情况。

## 9. 微分方程中的换元

有些微分方程题会给换元（substitution）。比如 $x=e^t$ 可以把某些方程化成常系数形式；$y=ux$ 可以把某些一阶方程化成可分离变量。

步骤是：

1. 小心改写导数；
2. 把换元代入原方程；
3. 解新方程；
4. 换回原变量。

两个常用导数改写要熟：

若 $x=e^t$，则

$$
\frac{dy}{dx}=\frac1x\frac{dy}{dt},
\qquad
\frac{d^2y}{dx^2}=\frac1{x^2}\left(\frac{d^2y}{dt^2}-\frac{dy}{dt}\right).
$$

若 $y=ux$，其中 $u$ 是 $x$ 的函数，则

$$
\frac{dy}{dx}=u+x\frac{du}{dx}.
$$

换元只是中间步骤，除非题目特别说明，最终答案要换回原来的变量。

## 10. 用解检查方程

微分方程的答案最好代回去检查。把求出的 $y$ 求导，再放回原方程，看左右是否一致。若有初值，也要检查初值是否满足。

这一步很值得做，因为微分方程中常数、符号和指数特别容易错。

## 做题顺序

### 从文字建模

1. 找出变化的量和自变量。
2. 把“变化率”翻译成导数。
3. 需要时引入比例常数。
4. 解微分方程。
5. 用初值或边界条件定常数。
6. 回到原问题解释答案。

### 解微分方程

1. 先分类：可分离、一阶线性、常系数线性，还是需要换元。
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
- 把互补函数和特解混在一起。
- 特解的试探形式和互补函数重合时没有调整。
- 换元后没有把所有导数改写完整，或最后没有换回原变量。
- 解出来以后不解释模型含义。

## 快速自查

- 我能不能判断一个方程是否可分离变量？
- 我能不能写出一阶线性方程的积分因子？
- 我能不能写出常用反双曲函数的对数形式和定义域？
- 我能不能根据积分结构选择三角换元、双曲换元或递推公式？
- 我能不能区分通解和特解？
- 我能不能把解代回微分方程检查？
- 我能不能写出 Maclaurin 级数的前几项？
- 我能不能识别互补函数、特解，以及试探形式重合时的调整？
- 我能不能用初值或边界条件确定常数并解释结果？

## 关联内容

- [[20 Mathematics/01 Pure Mathematics/05 Differentiation/00 Overview|Differentiation]]：进一步求导、Maclaurin 级数和微分方程都依赖导数语言。
- [[20 Mathematics/01 Pure Mathematics/06 Integration/00 Overview|Integration]]：分离变量、一阶线性方程和递推公式都需要积分方法。
- [[10 Physics/01 Topics/17 Oscillations/00 Overview|Physics Oscillations]]：常系数线性微分方程会在振动模型中再次出现。
