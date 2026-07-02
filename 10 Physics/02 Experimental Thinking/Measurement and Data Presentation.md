---
title: 实验操作与数据表达
subject: Physics
syllabus: 9702
status: draft
tags:
  - physics/9702
  - experimental-thinking
---

# 实验操作与数据表达

实验思维的第一层，是把一个现象变成可信的数据。即使暂时没有实验室，也要知道一个量怎样被测出来，以及数据为什么值得相信。

## 测量前先问

- 我要测的物理量是什么？
- 它能不能直接测？如果不能，需要先测哪些量？
- 仪器的量程是否足够？
- 仪器的分辨率是否足够？
- 哪些变量会偷偷影响结果？

## 常见测量工具

| 工具 | 适合测什么 | 注意点 |
|---|---|---|
| metre rule | 长度、位移、伸长量 | 视差、零点、读数精度。 |
| vernier / digital calipers | 直径、厚度、小长度 | 多点测量并取平均。 |
| micrometer | 细线直径、小厚度 | 注意零误差。 |
| stop-watch | 时间间隔、周期 | 人反应时间大，周期测量应测多次振动。 |
| balance | 质量 | 读数精度和校零。 |
| newton meter | 力 | 注意量程和弹簧零点。 |
| ammeter / voltmeter | 电流、电压 | 连接方式、内阻影响和量程。 |
| oscilloscope | 电压随时间变化 | time-base、y-gain、触发稳定性。 |
| light gate / data logger | 时间、速度、加速度 | 遮光片长度和采样设置。 |

## 表格怎么写

一张好表格应该让别人不看正文也能理解数据：

- 原始数据和计算量放在同一张表里。
- 表头写成 $\text{quantity}/\text{unit}$，例如 $I/\mathrm{mA}$。
- 同一列原始读数保持相同精度。
- 计算量使用合理有效数字。
- 如果计算步骤关键，要在表格下方写一个 sample calculation。

## 图像怎么画

图像不是装饰，是实验中的推理工具：

- 坐标轴写清物理量和单位。
- 数据点尽量占满图纸的有效范围。
- 选择容易读数的比例，例如 1、2、5 的倍数。
- best-fit line 要反映整体趋势，而不是机械连点。
- 曲线需要时画 tangent，用 tangent 求局部 gradient。
- 如果有异常点，标出并说明为什么可能异常。

## 结果怎么表达

一个物理测量结果至少要包括：

- 数值。
- 单位。
- 合理有效数字。
- 不确定度或误差来源。
- 简短判断：结果是否支持原模型。

例如不要只写“弹簧常量是 24.8”。更完整的表达是：

> The spring constant is approximately $25\,\mathrm{N\,m^{-1}}$; the main uncertainty comes from measuring small extensions with a ruler.

## 日常练习

每学一个主题，补一个“怎么测”问题：

- 学 speed：怎样测一个小车的瞬时速度？
- 学 Young modulus：怎样测细金属丝的直径和伸长量？
- 学 resistivity：怎样测导线的电阻率？
- 学 capacitor discharge：怎样从电压随时间变化求 time constant？
- 学 astronomy：怎样从图像数据估算恒星温度或距离？
