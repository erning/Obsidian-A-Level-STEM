---
title: 07 Chi-Squared, Non-Parametric Tests and PGF
subject: Mathematics
syllabus:
  - 9231
status: draft
tags:
  - mathematics/statistics
---

# 07 Chi-Squared, Non-Parametric Tests and PGF

## 教材对应

- 9231：Chi-squared tests，non-parametric tests，probability generating functions

## 需要掌握

- 使用 chi-squared goodness of fit test 和 independence test。
- 理解 observed frequency、expected frequency、degrees of freedom 和 test statistic。
- 知道什么时候需要合并类别。
- 理解 non-parametric tests 的意义：不依赖强正态假设。
- 使用 sign test、Wilcoxon signed-rank test、Wilcoxon rank-sum test。
- 理解 probability generating function（PGF），并用它求 mean、variance 和 sum of independent random variables。

## 练习方向

- Chi-squared 题先写类别、hypotheses 和 expected frequencies。
- 检查 expected frequency 是否足够大。
- Non-parametric test 先判断数据类型和配对关系。
- PGF 题先从 distribution 写出 generating function，再做代数操作。

## 连接

- Chi-squared 和 non-parametric tests 扩展了 [[20 Mathematics/03 Probability and Statistics/06 Sampling Estimation and Hypothesis Tests|Hypothesis Tests]]。
- PGF 是 [[20 Mathematics/03 Probability and Statistics/03 Discrete Random Variables|Discrete Random Variables]] 的高阶工具。

## 易错点

- Degrees of freedom 算错。
- Goodness of fit 和 independence test 混用。
- Wilcoxon tests 没检查配对关系或对称性条件。
- PGF 求导后忘记在 $t = 1$ 处代入。
