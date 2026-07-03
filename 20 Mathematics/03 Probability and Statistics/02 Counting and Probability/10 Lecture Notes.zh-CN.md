---
title: Counting and Probability 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/02 Counting and Probability/00 Overview|Counting and Probability]]"
status: draft
tags:
  - mathematics/statistics
  - lecture-notes
  - zh-CN
---

# Counting and Probability 中文讲义

这一章的主线是：先数清楚样本空间，再谈概率。概率题最怕凭感觉。你要先明确事件是什么、总情况有多少、满足条件的情况有多少，以及事件之间是否独立或互斥。

1. 这是排列问题、组合问题，还是概率规则问题？
2. 顺序是否重要？是否允许重复？
3. 两个事件是互斥、独立，还是条件概率关系？
4. 用树状图、表格、Venn 图，还是公式最清楚？

## 图示导读

![[assets/generated/mathematics/counting-and-probability.svg]]

这张图用来快速理解“计数与概率”：用概率树看样本空间怎样展开。

## 学习范围

- 乘法原理、排列、组合和二项式系数。
- 概率基本规则、互斥事件和补事件。
- 条件概率、独立事件和树状图。
- Venn 图、样本空间表格和计数概率。

## 1. 计数先问顺序

如果顺序重要，用排列。若从 $n$ 个不同对象中选 $r$ 个并排列，

$$
{}^nP_r=\frac{n!}{(n-r)!}.
$$

如果顺序不重要，用组合：

$$
{}^nC_r=\binom{n}{r}=\frac{n!}{r!(n-r)!}.
$$

例如从 10 人中选 3 人组成小组，顺序不重要，用组合。若选出队长、副队长、记录员，角色不同，顺序重要，用排列。

## 2. 乘法原理

如果一个过程分几步完成，每一步的选择数相乘，就是总选择数。

例如一个密码由 2 个字母和 3 个数字组成，若允许重复，则总数是

$$
26^2\cdot 10^3.
$$

若不允许重复，就要改成

$$
26\cdot 25\cdot 10\cdot 9\cdot 8.
$$

所以“是否允许重复”必须先读清楚。

## 3. 概率基本规则

概率定义为

$$
P(A)=\frac{\text{number of favourable outcomes}}{\text{number of possible outcomes}}
$$

前提是所有基本结果等可能。

补事件：

$$
P(A')=1-P(A).
$$

加法公式：

$$
P(A\cup B)=P(A)+P(B)-P(A\cap B).
$$

若 $A$ 和 $B$ 互斥，则

$$
P(A\cap B)=0.
$$

## 4. 条件概率和独立

条件概率是

$$
P(A\mid B)=\frac{P(A\cap B)}{P(B)}.
$$

它表示“已知 $B$ 发生的条件下，$A$ 发生的概率”。

如果 $A$ 和 $B$ 独立，则

$$
P(A\cap B)=P(A)P(B).
$$

等价地，

$$
P(A\mid B)=P(A).
$$

独立和互斥不是一回事。两个非空互斥事件不能独立，因为一个发生会让另一个不可能发生。

## 5. 树状图

连续试验、抽取不放回、条件变化时，树状图很有用。沿一条路径相乘，不同路径相加。

如果是不放回抽取，第二次概率会改变；如果是放回抽取，概率通常保持不变。

## 6. 常见错误

- 排列和组合混用。
- 忘记“不放回”会改变后续概率。
- 把互斥当独立。
- 加概率时重复计算交集。
- 样本空间没有列全就开始算概率。

## 快速自查

- 我能不能判断顺序是否重要？
- 我能不能解释互斥和独立的区别？
- 我能不能正确使用条件概率公式？
- 我能不能用树状图把多步概率列清楚？
