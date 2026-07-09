---
title: "Measurement, Observation and Calculation - Lecture Notes.zh-CN"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701
  - practical-skills
---

# Measurement, Observation and Calculation - Lecture Notes

## 范围

本讲对应 CAIE Chemistry 9701 Syllabus 2025-2027 第 5 节 *Practical assessment*，Paper 3 的三个技能区：*manipulation, measurement and observation*、*presentation of data and observations*，以及 *analysis, conclusions and evaluation* 中与计算有关的部分（syllabus 第 59-62 页）。第 75 页的 mathematical requirements 同样适用。

主线是：按仪器本身的精度记录，清楚呈现，不要凭空制造精度。

## 按仪器精度记录

每件仪器都有精度，读数应反映它；同一组数据里同一类量的所有读数都应记录到同样的精度。

- burette 读到 $0.05\ \mathrm{cm^3}$，所以像 $23.45\ \mathrm{cm^3}$ 或 $23.50\ \mathrm{cm^3}$ 这样的 titre 是正常的，末位是 $0$ 或 $5$。
- 每 $1\ ^\circ\mathrm{C}$ 一格的 thermometer 读到 $0.5\ ^\circ\mathrm{C}$。
- 读数到 $0.01\ \mathrm{g}$ 的天平给出如 $2.46\ \mathrm{g}$ 的质量。
- 每 $1.0\ \mathrm{cm^3}$ 一格的量筒读到 $0.5\ \mathrm{cm^3}$。

如果某一原始质量记为 $0.06\ \mathrm{g}$，那么这一列里所有质量都要写到 $0.01\ \mathrm{g}$。在同一列里混写 $0.06\ \mathrm{g}$ 和 $0.1\ \mathrm{g}$ 会丢分。

## 观察

观察描述你能直接感知到的现象：颜色、沉淀、气体、溶解性、温度变化、气味。观察本身不是结论。

- 先用简单词记颜色：“蓝色”、“黄色”。
- 只有在需要区分时再加细节：“浅蓝”、“深棕”。
- 必要时做比较：“比三分钟时更深棕”。
- 没变化时也要记“no change”或“remains colourless”。阴性观察能排除可能性。

沉淀写作例如“白色 ppt.”。$\Delta H$ 或“ppt.”这类惯用符号无需解释。

## 表格

结果表要在读数前就画好，这样数据只记一次。

- 每列要有表头和单位。可接受的形式有 `volume / cm³`、`volume (cm³)` 或 `volume in cm³`，全表统一一种。
- 原始数据和处理后的数据可以共用一张表，每列标明。
- 同一列里的每个数据精度相同。
- 如果有助于分析，留出计算量的列。

## 图

图能显示规律，并让你读出未知量或斜率。

- 除非计算另有要求，自变量画在 $x$ 轴，因变量画在 $y$ 轴。
- 两轴都标出物理量和单位，写法与表头一致。
- 选好读的标度：每 $20\ \mathrm{mm}$ 方格 $1$、$2$ 或 $5$ 个单位；避免 $3$、$4$、$6$、$7$。
- 数据点在 $x$、$y$ 两个方向上都应占满网格的一半以上。
- 用叉号 $\times$ 或带圈点 $\odot$ 画点。
- 画直线或光滑的最佳拟合曲线，不要把每个点都连起来。理想是点均匀分布在直线两侧。
- 异常点要标出来，不要藏起来。

## 直线图的斜率

在最佳拟合直线上取相距超过线长一半的两点 $(x_1,y_1)$ 和 $(x_2,y_2)$：

$$
m = \frac{y_2 - y_1}{x_2 - x_1}
$$

用大三角形比小三角形更可靠，因为同样的读数不确定度在大差值中占的比例更小。$y$ 轴截距就是 $y = mx + c$ 中的 $c$。

## 计算中的有效数字

计算结果的有效数字应与所用数据中最不精确的那个相同，或多一位。绝不能更多。

若 titre 为 $23.45\ \mathrm{cm^3}$（四位），碱浓度为 $0.100\ \mathrm{mol\ dm^{-3}}$（三位），则算出的酸浓度可写成 $0.131\ \mathrm{mol\ dm^{-3}}$（三位）或 $0.1305\ \mathrm{mol\ dm^{-3}}$（四位）。写成 $0.13048\ \mathrm{mol\ dm^{-3}}$ 是错的。

中间过程多保留几位，只在最后一步四舍五入，避免中间舍入扭曲结果。

## 不确定度与百分比误差

单次读数的最大不确定度取仪器最小分度的一半。每 $1\ ^\circ\mathrm{C}$ 一格的 thermometer，最大不确定度为 $\pm 0.5\ ^\circ\mathrm{C}$。

对于一个变化量，两端的不确定度要相加，所以由两次读数得到的温度变化的不确定度是 $\pm(0.5 + 0.5) = \pm 1.0\ ^\circ\mathrm{C}$。

百分比误差：

$$
\text{percentage error} = \frac{\text{uncertainty}}{\text{measured value}} \times 100
$$

用每 $1\ ^\circ\mathrm{C}$ 一格的 thermometer 测得 $14.0\ ^\circ\mathrm{C}$ 的温度变化：

$$
\text{percentage error} = \frac{2 \times 0.5}{14.0} \times 100 = 7.14\%
$$

乘 $2$ 是因为变化量是两次读数之差。被测变化越大，百分比误差越小，这正是热测量要用足够浓度和体积试剂的原因之一。

## 系统误差与随机误差

- **Systematic error**（系统误差）使每次读数都偏移同样大小，例如天平的零点误差或 thermometer 始终偏高 $1\ ^\circ\mathrm{C}$。用同一件仪器、做校准可减小它；在“变化量”中常会抵消。
- **Random error**（随机误差）逐次不同，例如室温波动。重复实验并取平均可减小它。

“human error”不是可接受的描述。要具体指出仪器、限制，以及是系统还是随机误差。

## 常见错误

- 同一列 titre 里，一个写成 $23.4\ \mathrm{cm^3}$，另一个写成 $23.50\ \mathrm{cm^3}$。
- 把算出的浓度写到六位有效数字。
- 把图上每个点都连起来，而不是画最佳拟合线。
- 求斜率时用了很小的三角形。
- 写“human error”而不是具体指出某个系统或随机误差。
- 忘记温度变化的不确定度来自两次读数。

## 连接

- [Experimental Design and Safety](../Experimental%20Design%20and%20Safety/10%20Lecture%20Notes.md) 提供变量、仪器选择与标准实验操作。
- [Planning, Analysis and Evaluation](../Planning%20Analysis%20and%20Evaluation/10%20Lecture%20Notes.md) 把这些测量用于完整的 Paper 5 分析。
- [Mathematical Tools for Chemistry](../../04%20Reference/Mathematical%20Tools%20for%20Chemistry.md) 给出计算规范。
- [Chemical Formulae and Equations](../../04%20Reference/Chemical%20Formulae%20and%20Equations.md) 支持基于方程式的计算。
