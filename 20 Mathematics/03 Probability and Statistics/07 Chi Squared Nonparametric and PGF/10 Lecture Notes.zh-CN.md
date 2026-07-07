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

这一章有三类工具。卡方检验比较频数表中的观察频数和期望频数；非参数检验在正态模型不合适时，把原始数据换成符号或秩；概率母函数（probability generating function, PGF，也称概率生成函数）把非负整数离散分布写成一个函数，方便读概率、求矩和处理独立随机变量之和。

它们看起来跨度很大，但共同点是都在选择合适的表示：频数表、符号/秩，或者 PGF。

## 来源范围

- 9231 4.3 Chi-squared tests。
- 9231 4.4 Non-parametric tests。
- 9231 4.5 Probability generating functions。
- 教材路线：9231 Further Probability and Statistics 中 chi-squared tests, non-parametric tests, and probability generating functions 相关内容。

## 关联内容

- [[20 Mathematics/03 Probability and Statistics/03 Discrete Random Variables/00 Overview|Discrete Random Variables]]
- [[20 Mathematics/03 Probability and Statistics/06 Sampling Estimation and Hypothesis Tests/00 Overview|Sampling, Estimation and Hypothesis Tests]]
- [[20 Mathematics/01 Pure Mathematics/04 Sequences Series and Binomial Expansions/00 Overview|Sequences, Series and Binomial Expansions]]

## 学习顺序

1. 先练习卡方拟合优度检验，包括估计参数和合并类别。
2. 练习列联表中的卡方独立性检验。
3. 学习非参数检验适用的情况。
4. 比较 sign test、Wilcoxon signed-rank test、matched-pairs signed-rank test 和 rank-sum test。
5. 为常见离散分布建立 PGF。
6. 用 PGF 求期望、方差和独立随机变量之和。

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

CAIE 要求参与计算的每个期望频数至少为 $5$。若某些类别期望频数太小，需要合并类别、行或列。

基本流程是：

1. 用文字写清 $H_0$ 和 $H_1$。
2. 在 $H_0$ 下计算期望频数。
3. 若需要，先合并类别、行或列，再确定最终的期望频数和自由度。
4. 计算 $\chi^2=\sum (O-E)^2/E$。
5. 与右尾临界值比较，或使用右尾 $p$ 值。
6. 用题目语境写结论。

因为每一项都被平方，卡方统计量本身不直接给方向。若要解释证据来自哪里，应回到表格中看哪些单元的 $(O-E)^2/E$ 贡献最大，以及这些单元中 $O$ 是高于还是低于 $E$。

## 2. 拟合优度检验（Goodness-of-Fit）

拟合优度检验问的是：数据是否符合某个给定分布？

原假设通常写成

$$
H_0:\text{the data follow the stated distribution}.
$$

如果分布完全给定，期望频数由

$$
E_i=Np_i
$$

计算，其中 $N$ 是总观察频数，$p_i$ 是 $H_0$ 下第 $i$ 类的概率。

如果某个参数没有给出，而是由同一组数据估计出来，就要在自由度中扣掉这个参数。若合并后共有 $k$ 类，并且从数据估计了 $q$ 个参数，则

$$
\nu=k-1-q.
$$

例如用样本均值估计泊松分布的 $\lambda$，就是 $q=1$。如果假设中已经完全给出分布和参数，则 $q=0$。

合并类别应在最终计算统计量和自由度之前完成。通常合并相邻或自然相关的类别，不要看完结果后随意挑选“方便”的格子合并。合并后，观察频数和期望频数都要按同样方式相加。

## 3. 列联表中的独立性检验

独立性检验用于列联表，问两个分类变量是否独立。

在独立假设下，每个单元的期望频数为

$$
E=\frac{\text{row total}\times \text{column total}}{\text{grand total}}.
$$

若表格为 $r$ 行 $c$ 列，自由度为

$$
\nu=(r-1)(c-1).
$$

如果为了让每个期望频数至少为 $5$ 而合并了行或列，自由度要用合并后的行数和列数重新计算。本 syllabus 不要求 Yates correction。

典型假设是

$$
H_0:\text{the two categorical variables are independent},
$$

$$
H_1:\text{the two categorical variables are not independent}.
$$

独立性检验使用频数，不使用百分比来计算统计量。百分比可以用于事后解释，但不能替代观察频数和期望频数。

## 4. 非参数检验

非参数检验不强依赖总体服从正态分布这类假设。它常用符号、秩或顺序信息。

它不是“完全没有假设”。符号检验用到的结构很少；Wilcoxon 检验使用秩信息，并且在本 syllabus 中要注意对称性条件。题目不会涉及 tied ranks、等于被检验中位数的观察值或零差值配对。

### Sign Test

符号检验只看观察值在假设中位数之上还是之下，或配对差值是正还是负，不看差多少。它简单稳健，但会丢掉大小信息。

对单样本中位数检验，设要检验的中位数为 $m_0$。数出高于 $m_0$ 和低于 $m_0$ 的观察值个数。在 $H_0$ 下，每个非相等观察值高于或低于 $m_0$ 的概率相同，所以正号个数服从

$$
B(n,0.5).
$$

对配对数据，先取差值，再数正差值和负差值。单尾备择决定使用二项分布哪一侧尾部；若做精确的双尾检验，通常把较小一侧尾概率乘以 $2$。

### Wilcoxon Signed-Rank 和 Matched-Pairs 检验

Wilcoxon signed-rank test 不只看正负，还给偏差绝对值排序，再带着原来的符号比较。它比符号检验保留更多信息，但有效性依赖对称性。

单样本中位数检验中，先计算

$$
d_i=x_i-m_0.
$$

把 $|d_i|$ 排秩，再把原来的正负号带回去。公式表常用 $P$ 表示正差值对应秩的和。在 $H_0$ 下，正秩和负秩应大致平衡。配对样本 matched-pairs signed-rank test 完全类似，只是 $d_i$ 来自每一对观测的差值。

大样本时可使用正态近似。若 $P$ 是样本容量为 $n$ 时正秩之和，则在 $H_0$ 下

$$
E(P)=\frac{n(n+1)}{4},\qquad
\operatorname{Var}(P)=\frac{n(n+1)(2n+1)}{24}.
$$

对秩和统计量使用正态近似时，要考虑连续性修正。

### Wilcoxon Rank-Sum Test

Wilcoxon rank-sum test 用合并后的秩比较两个独立样本，适合在不直接使用双样本正态模型时检验两个总体是否可以看作相同。

把两个样本合并后一起排秩，再取较小样本的秩和。若样本量为 $m$ 和 $n$，且 $m\le n$，较小样本的秩和为 $R_m$，则在 $H_0$ 下

$$
E(R_m)=\frac{m(m+n+1)}{2},\qquad
\operatorname{Var}(R_m)=\frac{mn(m+n+1)}{12}.
$$

若备择假设说第一个总体倾向于取较大值，那么第一个样本的秩和应偏大；若说它倾向于取较小值，秩和应偏小。判断尾部方向时，一定要看你正在使用的是哪个样本的秩和。

## 5. 概率母函数（PGF）

对非负整数取值的离散随机变量 $X$，概率母函数是

$$
G_X(t)=E(t^X)=\sum_{x=0}^{\infty}P(X=x)t^x.
$$

它把整个分布装进一个函数里。$t^x$ 的系数就是 $P(X=x)$。此外，

$$
G_X(1)=1,
$$

因为所有概率相加为 $1$。

常见例子：

- 若 $X$ 在 $1,2,\ldots,n$ 上离散均匀分布，则

$$
G_X(t)=\frac{t+t^2+\cdots+t^n}{n}
=\frac{t(1-t^n)}{n(1-t)}.
$$

- 若 $X\sim B(n,p)$，则 $G_X(t)=(1-p+pt)^n$。

- 若 $X\sim \operatorname{Geo}(p)$，且第一次成功出现在第 $1,2,\ldots$ 次，则

$$
G_X(t)=\frac{pt}{1-(1-p)t}.
$$

- 若 $X\sim \operatorname{Po}(\lambda)$，则

$$
G_X(t)=e^{\lambda(t-1)}.
$$

若随机变量从 $0$ 开始取值，常数项就是 $P(X=0)$。若从 $1$ 开始取值，常数项为 $0$。这常用来分辨几何分布是从 $0$ 计数还是从 $1$ 计数。

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

因为

$$
X^2=X(X-1)+X,
$$

所以

$$
E(X^2)=G_X''(1)+G_X'(1).
$$

如果 $X$ 和 $Y$ 独立，那么

$$
G_{X+Y}(t)=G_X(t)G_Y(t).
$$

这是 PGF 很好用的地方。

两个常见结论：

- 成功概率相同的独立二项变量相加时，试验次数相加。
- 独立泊松变量相加时，均值参数相加。

例如，若 $X\sim \operatorname{Po}(\lambda)$、$Y\sim \operatorname{Po}(\mu)$ 且相互独立，则

$$
G_{X+Y}(t)=e^{\lambda(t-1)}e^{\mu(t-1)}
=e^{(\lambda+\mu)(t-1)}.
$$

所以

$$
X+Y\sim \operatorname{Po}(\lambda+\mu).
$$

## 做题顺序

1. 先判断数据类型：频数、符号、秩，还是离散分布。
2. 卡方检验先算期望频数，并检查是否都至少为 $5$。
3. 自由度要考虑合并后的类别、行列数，以及是否估计了参数。
4. 非参数检验先判断是单样本、配对样本，还是两个独立样本。
5. Wilcoxon 检验要排对正确的量，并把秩和与尾部方向对应起来。
6. PGF 题先把分布写成 $t$ 的幂级数。
7. 求均值和方差时在 $t=1$ 处代入导数。
8. 做随机变量和的 PGF 前，先确认独立。

## 常见错误

- 卡方检验中把观察频数和期望频数的位置弄混。
- 期望频数太小却不合并类别。
- 自由度没有扣掉估计参数。
- 合并类别时先看结果再挑对自己有利的合并方式。
- 独立性检验中期望频数公式写错。
- 把 paired signed-rank 数据和 independent rank-sum 数据混在一起。
- PGF 求方差时把 $G''(1)$ 直接当成 $E(X^2)$。
- 没有独立性时还把 PGF 直接相乘。
- 把非参数检验理解成完全没有假设。

## 快速自查

- 我能不能区分拟合优度检验和独立性检验？
- 我能不能正确计算期望频数、合并类别并选择自由度？
- 我能不能解释符号检验、signed-rank test 和 rank-sum test 分别适合什么数据？
- 我能不能不混淆 signed-rank 和 rank-sum 的排秩对象？
- 我能不能从 PGF 读出概率、期望和方差？
- 我能不能用 PGF 处理独立随机变量之和？
