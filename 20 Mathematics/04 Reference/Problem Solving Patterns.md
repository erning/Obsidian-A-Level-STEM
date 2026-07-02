---
title: 解题模式
subject: Mathematics
syllabus:
  - 9709
  - 9231
status: draft
tags:
  - mathematics/reference
---

# 解题模式

这份笔记收集可以反复迁移的解题模式。它不是题型清单，而是“看到什么信号，就想到什么结构”的索引。

## 通用流程

1. 写出对象：函数、方程、向量、矩阵、随机变量还是力学系统。
2. 写出已知和目标。
3. 画图或结构图。
4. 选择方法，并说明条件。
5. 执行计算。
6. 用图像、定义域、单位、概率范围或极端情况检查。

## 常见信号

| 信号 | 常见方法 | 检查 |
|---|---|---|
| quadratic vertex | completing the square | 顶点和对称轴是否正确 |
| repeated root / tangent | discriminant 或联立方程 | 图像是否相切 |
| product to integrate | integration by parts | 反求导检查 |
| composite expression | chain rule 或 substitution | 内函数是否完整出现 |
| rational function | partial fractions 或 asymptotes | 分母零点和长期行为 |
| maximum/minimum | derivative = 0，加二阶或符号检查 | 图像形状是否符合 |
| distance/angle in space | dot product、cross product、projection | 长度非负，角度范围合理 |
| transformation | matrix representation | determinant 和图像方向 |
| independent repeated trials | binomial/geometric model | 参数和事件定义 |
| rare counts in interval | Poisson model | 单位时间/空间的 rate |
| sample inference | confidence interval 或 hypothesis test | 假设、样本和条件 |
| force problem | free-body diagram | 合力方向和单位 |
| energy problem | conservation / work-energy | 初末状态是否清楚 |

## 错题归档

每道错题不要只写正确答案。至少标一个错误类型：

- `concept`：定义或对象错。
- `representation`：代数、图像、语言之间转换错。
- `condition`：方法适用条件错。
- `algebra`：符号、展开、整理错。
- `model`：情境翻译错。
- `check`：没有发现明显不合理。
