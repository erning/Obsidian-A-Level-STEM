---
title: "37 Analytical Techniques - Lecture Notes.zh-CN"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/a-level
  - chemistry/9701/analysis
---

# 37 Analytical Techniques - Lecture Notes

## 范围

本讲义依据 CAIE Chemistry 9701 A Level Topic 37：thin-layer chromatography、gas / liquid chromatography、carbon-13 NMR spectroscopy 和 proton NMR spectroscopy。这里不声称对齐任何教材。

## 与 AS 的连接

AS 的 analytical techniques 包括 mass spectrometry 和 infrared spectroscopy。A Level 加入分离技术和 NMR。分析结构时仍然不能只靠一个证据下结论，要把 formula、functional groups、purity、carbon environments、proton environments、integration、splitting 和 exchange behaviour 合在一起判断。

## Thin-layer chromatography

Thin-layer chromatography，TLC，用薄层板分离物质。

- Stationary phase 是固体，例如在固体载体上的 aluminium oxide。
- Mobile phase 是 polar 或 non-polar solvent。
- Baseline 是样品起点线。
- Solvent front 是溶剂到达的最远位置。
- $R_f$ value 的定义是：

$$
R_f=\frac{\text{distance moved by spot}}{\text{distance moved by solvent front}}
$$

$R_f$ 只能在相同条件下比较。物质与 stationary phase 作用越强，移动越慢，$R_f$ 越小；相对更易溶于 mobile phase，则移动更远，$R_f$ 越大。

TLC 可用于判断纯度：在某一 solvent system 中，纯物质通常只有一个 spot，混合物会有多个 spot。与 known standard 比较 $R_f$ 可辅助鉴定。

## Gas / liquid chromatography

Gas / liquid chromatography 中，stationary phase 是高沸点 non-polar liquid，附着在固体载体上；mobile phase 是 unreactive gas。

不同组分离开柱子的时间不同，这叫 retention time。与 stationary phase 作用越强，停留越久，retention time 越大。

混合物百分组成可由峰面积估算：

$$
\text{percentage of component}=\frac{\text{area of its peak}}{\text{total peak area}}\times 100
$$

Retention time 可与标准样比较用于鉴定；peak area 用于组成比例。

## Carbon-13 NMR

Carbon-13 NMR 显示不同 carbon environments。简单分子中，每一组化学等价的碳通常给一个 peak。

数峰前先看对称性。例如 ethane 只有一个 carbon environment，因为两个碳等价。Propanone，$\ce{CH3COCH3}$，有两个 carbon environments：两个甲基碳等价，carbonyl carbon 不同。

在本课程层次，不用 carbon-13 NMR 的峰高来判断碳原子数比例。主要看峰数和大致 chemical shift。

## Proton NMR

Proton NMR 提供几类证据。

Chemical shift 说明质子所处环境。靠近电负性原子或不饱和结构的质子通常出现在更 downfield 的位置。

Relative peak area，也叫 integration，给出不同质子环境中质子的相对数量。

Splitting pattern 说明相邻碳上等价质子的数量。简单情况用 $n+1$ rule：

- 0 个相邻等价质子：singlet。
- 1 个：doublet。
- 2 个：triplet。
- 3 个：quartet。
- 更复杂情况可能是 multiplet。

例如 ethyl group，$\ce{-CH2CH3}$，常见 $\ce{-CH3}$ 为 triplet，$\ce{-CH2}$ 为 quartet，积分比 3:2。

## TMS、deuterated solvents 和 D2O exchange

Tetramethylsilane，TMS，用作 chemical shift 的标准，信号在 $\delta=0$，且通常不与样品反应。

Deuterated solvents，例如 $\ce{CDCl3}$，用于 proton NMR，因为普通含氢溶剂会产生很强的质子信号，干扰样品。

连在氧或氮上的质子可通过 $\ce{D2O}$ exchange 鉴定。加入 $\ce{D2O}$ 后，$\ce{O-H}$ 和 $\ce{N-H}$ 的信号会消失或明显减弱，因为这些质子与 deuterium 交换。

## 组合证据

推断结构时可按以下顺序：

1. 用 chromatography 判断纯度或混合物组成。
2. 用 carbon-13 NMR 数 carbon environments 和对称性。
3. 用 proton NMR chemical shifts 判断质子环境。
4. 用 integration 得到质子比例。
5. 用 splitting 判断相邻质子。
6. 用 $\ce{D2O}$ exchange 判断 $\ce{O-H}$ 或 $\ce{N-H}$。

如果两种结构都符合某一条证据，不要急着排除，要等其他证据区分。

## 常见错误

- 混淆 $R_f$ value 和 retention time。
- 把不同 solvent system 下的 $R_f$ 当成通用常数。
- 用 carbon-13 NMR 的峰高判断碳比例。
- 使用 $n+1$ rule 前不检查相邻等价质子。
- 忘记 $\ce{O-H}$ 和 $\ce{N-H}$ 可与 $\ce{D2O}$ 交换。
