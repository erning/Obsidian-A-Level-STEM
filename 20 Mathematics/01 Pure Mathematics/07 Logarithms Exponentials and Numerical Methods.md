---
title: 07 Logarithms Exponentials and Numerical Methods
subject: Mathematics
syllabus:
  - 9709
  - 9231
status: draft
tags:
  - mathematics/pure
---

# 07 Logarithms Exponentials and Numerical Methods

## 教材对应

- 9709：Pure Mathematics 2 and 3 Chapters 2, 6
- 9231：Hyperbolic functions、differential equations 和 series 中继续使用 exponential/logarithmic structure

## 需要掌握

- 理解 logarithms 和 exponentials 是 inverse functions。
- 使用 laws of logarithms，解 logarithmic/exponential equations。
- 理解 `e^x` 和 `ln x` 的图像、导数和积分。
- 用 exponential functions 建模 growth、decay、compound change 和 linearisation。
- 用 sign change、graphical methods 和 fixed-point iteration 求近似根。
- 能判断 iteration 是否在数值上合理，即使不做严格收敛证明。

## 练习方向

- 解 log 方程前先写 domain。
- 对指数模型写出初始值、rate 和长期行为。
- 用 `ln y` against `x` 或 `log y` against `log x` 理解线性化。
- 对 numerical root，先找 bracket，再迭代。

## 连接

- Exponentials 是 [[10 Physics/01 Topics/19 Capacitance|Capacitance]]、[[10 Physics/01 Topics/23 Nuclear Physics|Nuclear Physics]] 和 differential equations 的共同语言。
- Numerical methods 是把 exact mathematics 和计算现实连接起来的桥。

## 易错点

- 忘记 logarithm 的输入必须为正。
- 把 `e^(a+b)` 错写成 `e^a + e^b`。
- 固定点迭代中不检查结果是否接近原方程的根。
- 过早四舍五入导致数值误差累积。
