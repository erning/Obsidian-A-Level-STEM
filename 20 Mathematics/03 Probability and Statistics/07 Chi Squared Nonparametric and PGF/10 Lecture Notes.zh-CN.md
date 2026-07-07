---
title: Chi-Squared, Non-Parametric Tests and PGF 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/07 Chi Squared Nonparametric and PGF/00 Overview|Chi-Squared, Non-Parametric Tests and PGF]]"
status: active
tags:
  - mathematics/statistics
  - lecture-notes
  - zh-CN
---

# Chi-Squared, Non-Parametric Tests and PGF 中文讲义

这一章有三类工具。卡方检验比较观察频数和期望频数；非参数检验用符号或秩来减少对总体分布的要求；概率生成函数用一个函数打包离散分布的信息。

它们看起来跨度很大，但共同点是都在选择合适的表示：频数表、符号/秩，或者生成函数。

## 图示导读

![[assets/generated/mathematics/chi-squared-non-parametric-tests-and-pgf.svg]]

这张图用观察频数和期望频数的差异理解卡方统计量。差异越大，统计量越大，越容易落入右尾拒绝域。

## 1. 卡方检验在比较什么

卡方检验比较观察频数 $O$ 和期望频数 $E$。检验统计量是

$$
\chi^2=\sum \frac{(O-E)^2}{E}.
$$

如果观察频数和期望频数很接近，$\chi^2$ 会比较小；差得越多，$\chi^2$ 越大。

卡方检验通常是右尾检验，因为差异太大才会让我们怀疑原假设。

CAIE 要求期望频数至少为 5。若某些类别期望频数太小，需要合并类别、行或列。

## 2. 拟合优度检验

拟合优度检验问的是：数据是否符合某个给定分布？

例如掷骰子 120 次，理论上每个点数期望出现 20 次。把观察次数和 20 比较，就可以检验骰子是否看起来公平。

自由度通常是

$$
\text{number of categories}-1-\text{number of estimated parameters}.
$$

如果某些期望频数太小，需要合并类别。

## 3. 独立性检验

独立性检验用于列联表，问两个分类变量是否独立。

期望频数用

$$
E=\frac{\text{row total}\times \text{column total}}{\text{grand total}}.
$$

自由度是

$$
(r-1)(c-1),
$$

其中 $r$ 是行数，$c$ 是列数。

若检验统计量落入拒绝域，说明数据提供了反对“独立”的证据。

这个 syllabus 不要求 Yates correction。

## 4. 非参数检验

非参数检验不强依赖总体服从正态分布这类假设。它常用符号、秩或顺序信息。

符号检验只看差值是正还是负，不看差多少。它适合配对数据，比如同一批人使用某方法前后的变化方向。

Wilcoxon signed-rank test 不只看正负，还给差值的绝对大小排序，再带着符号比较。它比符号检验保留更多信息，但要求分布具有对称性。

Wilcoxon rank-sum test 用合并后的秩比较两个独立样本，适合检验两个总体是否可以看作相同，而不想直接假定正态模型。

非参数检验的优点是条件较弱，缺点是会丢掉一部分数值信息。它不是完全没有假设，而是假设少一些。

## 5. 概率生成函数

对非负整数取值的离散随机变量 $X$，概率生成函数是

$$
G_X(t)=E(t^X)=\sum_{x=0}^{\infty}P(X=x)t^x.
$$

它把整个分布装进一个函数里。$t^x$ 的系数就是 $P(X=x)$。

例如若 $X\sim B(n,p)$，则

$$
G_X(t)=(1-p+pt)^n.
$$

若 $X\sim \operatorname{Geo}(p)$，且第一次成功出现在第 $1,2,\ldots$ 次，则

$$
G_X(t)=\frac{pt}{1-(1-p)t}.
$$

若 $X\sim \operatorname{Po}(\lambda)$，则

$$
G_X(t)=e^{\lambda(t-1)}.
$$

## 6. 用 PGF 求期望和方差

PGF 的一阶导数可以给出期望：

$$
E(X)=G_X'(1).
$$

还可以用

$$
E(X(X-1))=G_X''(1).
$$

所以方差可以直接写成

$$
\operatorname{Var}(X)=G_X''(1)+G_X'(1)-[G_X'(1)]^2.
$$

注意 $G_X''(1)$ 是 $E[X(X-1)]$，不是 $E(X^2)$。

如果 $X$ 和 $Y$ 独立，那么

$$
G_{X+Y}(t)=G_X(t)G_Y(t).
$$

这是 PGF 很好用的地方。

## 做题顺序

1. 先判断数据类型：频数、符号、秩，还是离散分布。
2. 卡方检验先算期望频数，并检查是否都至少为 5。
3. 根据拟合优度或独立性选择自由度公式。
4. 非参数检验先判断是单样本、配对样本，还是两个独立样本。
5. PGF 题先把分布写成 $t$ 的幂级数。
6. 求均值和方差时在 $t=1$ 处代入导数。
7. 做随机变量和的 PGF 前，先确认独立。

## 常见错误

- 卡方检验中把观察频数和期望频数的位置弄混。
- 期望频数太小却不合并类别。
- 自由度没有扣掉估计参数。
- 独立性检验中期望频数公式写错。
- PGF 求方差时把 $G''(1)$ 直接当成 $E(X^2)$。
- 没有独立性时还把 PGF 直接相乘。
- 把非参数检验理解成完全没有假设。

## 快速自查

- 我能不能区分拟合优度检验和独立性检验？
- 我能不能正确计算期望频数和自由度？
- 我能不能解释符号检验、signed-rank test 和 rank-sum test 分别适合什么数据？
- 我能不能从 PGF 读出概率、期望和方差？
- 我能不能用 PGF 处理独立随机变量之和？
