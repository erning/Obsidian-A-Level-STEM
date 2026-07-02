---
title: 实验设计与数据分析
subject: Physics
syllabus: 9702
status: draft
tags:
  - physics/9702
  - experimental-thinking
---

# 实验设计与数据分析

实验思维的第二层，是从“我想知道什么”出发，设计一个可执行的测量方案，并让数据回答问题。

## 设计实验的基本问题

任何实验都先写清楚：

- 我要研究什么关系？
- independent variable 是什么？
- dependent variable 是什么？
- control variables 是什么？
- 我怎样改变 independent variable？
- 我怎样测量 dependent variable？
- 怎样让数据范围足够大？
- 最大不确定度可能来自哪里？

## 变量控制

控制变量不是列名词，而是说明做法：

- 不要只写“保持温度不变”，要写如何保持，例如使用 water bath 或等待热平衡。
- 不要只写“保持长度不变”，要说明固定方式和测量位置。
- 不要只写“重复实验”，要说明重复哪个量、重复几次、如何取平均。

## 线性化

很多物理关系不是直接直线。学习时要主动寻找能画成直线的方式：

| 原关系 | 可画图像 | 可读信息 |
|---|---|---|
| `y = mx + c` | `y` against `x` | gradient 是 `m`，intercept 是 `c`。 |
| `y = ax^n` | `log y` against `log x` | gradient 是 `n`，intercept 给 `a`。 |
| `y = ae^(kx)` | `ln y` against `x` | gradient 是 `k`，intercept 给 `a`。 |
| capacitor discharge | `ln V` against `t` | gradient 与 `RC` 有关。 |
| radioactive decay | `ln A` against `t` | gradient 与 decay constant 有关。 |

线性化的目的不是凑数学形式，而是让数据更容易检验模型。

## 不确定度

不确定度不是“麻烦的附加项”，而是判断结论可信度的核心：

- absolute uncertainty：直接用单位表达。
- percentage uncertainty：适合比较不同量的相对误差。
- repeated readings：可用半极差估算不确定度。
- derived quantity：乘除关系中常要合并 percentage uncertainties。
- graph gradient：可用 best-fit line 和 worst acceptable line 比较估算不确定度。

## 判断模型是否可信

一个实验结论不要只写“符合”或“不符合”。更好的判断是：

- 数据趋势是否符合模型预测？
- 图像是否接近直线？
- gradient 或 intercept 是否有合理物理意义？
- 异常点是否能解释？
- 差异是否落在不确定度范围内？
- 如果不符合，是模型假设失效，还是实验方法问题？

## 适合自学的小项目

- 用手机视频分析自由落体或抛体运动。
- 用声音软件观察 beat、frequency 和 Doppler effect。
- 用简单电路测量 resistor、filament lamp、diode 的 I-V 图像。
- 用在线天文数据做 redshift 或 Hubble law 图像。
- 用 Python 画 capacitor discharge、radioactive decay 或 SHM 图像。

如果需要用 Python 处理数据或画图，按仓库的 `AGENTS.md` 使用本地 `.venv/`，并设置 Matplotlib backend。

