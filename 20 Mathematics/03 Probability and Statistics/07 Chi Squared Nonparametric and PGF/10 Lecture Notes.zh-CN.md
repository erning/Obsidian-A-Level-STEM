---
title: Chi-Squared, Non-Parametric Tests and PGF 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/07 Chi Squared Nonparametric and PGF/00 Overview|Chi-Squared, Non-Parametric Tests and PGF]]"
status: draft
tags:
  - mathematics/statistics
  - lecture-notes
  - zh-CN
---

# Chi-Squared, Non-Parametric Tests and PGF 中文讲义

这一章的主线是：有些问题不能只靠均值和方差。卡方检验比较观察频数和期望频数，非参数检验减少对总体分布的依赖，概率生成函数则用一个函数打包离散分布的信息。

1. 数据是频数表、配对符号，还是离散随机变量分布？
2. 卡方检验是拟合优度，还是独立性检验？
3. 期望频数是否足够大，类别是否需要合并？
4. PGF 是用来求分布、期望，还是多个独立变量之和？

## 图示导读

![[assets/generated/mathematics/chi-squared-non-parametric-tests-and-pgf.svg]]

这张图用来快速理解“卡方检验、非参数检验与概率生成函数”：用观察值与期望值的差异理解卡方尾部面积。

## 学习范围

- 卡方拟合优度检验和独立性检验。
- 非参数检验的思想，如符号检验和秩检验。
- 概率生成函数的定义、期望和方差提取。
- 独立随机变量和的 PGF。

## 1. 卡方检验在比较什么

卡方检验比较观察频数 $O$ 和期望频数 $E$。检验统计量是

$$
\chi^2=\sum \frac{(O-E)^2}{E}.
$$

如果观察频数和期望频数很接近，$\chi^2$ 会比较小；差得越多，$\chi^2$ 越大。

卡方检验通常是右尾检验，因为差异太大才会让我们怀疑零假设。

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

## 4. 非参数检验

非参数检验不强依赖总体服从正态分布这类假设。它常用符号、秩或顺序信息。

符号检验只看差值是正还是负，不看差多少。它适合配对数据，比如同一批人使用某方法前后的变化方向。

非参数检验的优点是条件较弱，缺点是丢掉了一部分数值信息。

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

## 6. 用 PGF 求期望和方差

PGF 的一阶导数可以给出期望：

$$
E(X)=G_X'(1).
$$

还可以用

$$
E(X(X-1))=G_X''(1).
$$

再由

$$
Var(X)=E(X^2)-[E(X)]^2
$$

求方差，其中

$$
E(X^2)=E(X(X-1))+E(X).
$$

如果 $X$ 和 $Y$ 独立，那么

$$
G_{X+Y}(t)=G_X(t)G_Y(t).
$$

这是 PGF 很好用的地方。

## 7. 常见错误

- 卡方检验中把观察频数和期望频数的位置弄混。
- 期望频数太小却不合并类别。
- 自由度没有扣掉估计参数。
- 独立性检验中期望频数公式写错。
- PGF 求方差时把 $G''(1)$ 直接当成 $E(X^2)$。

## 快速自查

- 我能不能区分拟合优度检验和独立性检验？
- 我能不能正确计算期望频数和自由度？
- 我能不能解释非参数检验为什么少依赖分布假设？
- 我能不能从 PGF 读出概率、期望和方差？
