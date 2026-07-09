---
title: "22 Analytical Techniques - Lecture Notes.zh-CN"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/as-level
  - chemistry/9701/analysis
---

# 22 Analytical Techniques - Lecture Notes

## 范围

本讲对应 CAIE Chemistry 9701 AS Level topic 22：**Analytical techniques**，正式内容包括：

- 22.1 Infrared spectroscopy
- 22.2 Mass spectrometry

本讲也把 AS practical analysis 中的 qualitative analysis 和 organic analysis tests 联系进来。Chromatography 在 CAIE 9701 中的正式学习目标属于 A Level topic 37；这里仅作为题目给出数据时的分析背景，不把它说成 AS topic 22 的正式要求。

## 分析题的核心

分析不是靠猜结构，而是用证据逐步排除。常用证据包括：

- infrared spectroscopy 给出的官能团证据；
- mass spectrometry 给出的 molecular mass、isotopic abundances 和 fragments；
- qualitative observations，例如沉淀、气体、颜色变化；
- organic tests，例如 Fehling's reagent、Tollens' reagent、alkaline aqueous iodine；
- 题目提供的 chromatography separation data。

好的答案要把证据互相核对，而不是只凭一个峰或一个现象下结论。

## Infrared Spectroscopy

红外光谱用吸收频率判断化学键。AS 做题时应使用 syllabus Data section 的数值。

| 键 | 含有该键的官能团 | 特征吸收范围 |
|---|---|---|
| $\ce{C-O}$ | hydroxy, ester | $1040-1300\ \mathrm{cm^{-1}}$ |
| $\ce{C=C}$ | aromatic compound, alkene | $1500-1680\ \mathrm{cm^{-1}}$ |
| $\ce{C=O}$ | amide | $1640-1690\ \mathrm{cm^{-1}}$ |
| $\ce{C=O}$ | carbonyl, carboxyl | $1670-1740\ \mathrm{cm^{-1}}$ |
| $\ce{C=O}$ | ester | $1710-1750\ \mathrm{cm^{-1}}$ |
| $\ce{C#N}$ | nitrile | $2200-2250\ \mathrm{cm^{-1}}$ |
| $\ce{C-H}$ | alkane | $2850-2950\ \mathrm{cm^{-1}}$ |
| $\ce{N-H}$ | amine, amide | $3300-3500\ \mathrm{cm^{-1}}$ |
| $\ce{O-H}$ | carboxyl | $2500-3000\ \mathrm{cm^{-1}}$ |
| $\ce{O-H}$ | hydroxy | $3200-3600\ \mathrm{cm^{-1}}$ |

读红外光谱时可以按顺序看：

1. 有没有很宽的 $\ce{O-H}$ 吸收？
2. 有没有 $\ce{C=O}$ 吸收？
3. 有没有 $\ce{C#N}$ 或 $\ce{N-H}$？
4. 这些官能团是否与分子式、化学测试和质谱一致？

例如：

- $2500-3000\ \mathrm{cm^{-1}}$ 的宽 $\ce{O-H}$ 加上 $\ce{C=O}$，强烈支持 carboxylic acid；
- ester 范围的 $\ce{C=O}$ 加 $\ce{C-O}$，支持 ester；
- $2200-2250\ \mathrm{cm^{-1}}$ 的 $\ce{C#N}$，支持 nitrile；
- $3200-3600\ \mathrm{cm^{-1}}$ 的 $\ce{O-H}$ 且没有 $\ce{C=O}$，可支持 alcohol。

## Mass Spectrometry

AS 不要求掌握质谱仪工作原理，重点是读数据。

### Molecular Ion Peak

Molecular ion peak，$M^+$，给出分子的相对分子质量。

如果 $M^+$ 在 $m/e = 60$，则相对分子质量为 60。

### Fragment Ions

Fragment peaks 来自分子碎片。题目可能要求写出简单碎片。

| fragment ion | $m/e$ |
|---|---|
| $\ce{CH3+}$ | 15 |
| $\ce{C2H5+}$ | 29 |
| $\ce{C3H7+}$ | 43 |
| $\ce{CH3CO+}$ | 43 |
| $\ce{C6H5+}$ | 77 |

写 fragment 时要检查它是否可能来自给定结构。

### 同位素丰度和相对原子质量

相对原子质量用加权平均：

$$
A_r = \frac{\sum(\text{isotopic mass} \times \text{relative abundance})}{\sum(\text{relative abundance})}
$$

如果 abundance 用百分数，分母就是 100。

## $[M+1]^+$ 和碳数

$[M+1]^+$ 峰主要来自碳-13。大纲给出的公式是：

$$
n =
\frac{100 \times \text{abundance of } [M+1]^+ \text{ ion}}
{1.1 \times \text{abundance of } M^+ \text{ ion}}
$$

$n$ 是分子中的碳原子数。

例如 $M^+$ 的相对丰度是 100，$[M+1]^+$ 的相对丰度是 4.4：

$$
n = \frac{100 \times 4.4}{1.1 \times 100} = 4
$$

所以分子含有 4 个碳。

## $[M+2]^+$：氯和溴

氯和溴有相差 2 个质量单位的重要同位素，所以会影响 $[M+2]^+$ 峰。

| 元素 | 典型峰型 |
|---|---|
| 1 个 chlorine atom | $M : M+2 \approx 3 : 1$ |
| 1 个 bromine atom | $M : M+2 \approx 1 : 1$ |

这个证据对判断 halogenoalkane 很有用，但仍要和 molecular ion peak、结构式和其他证据一起看。

## Qualitative Analysis

AS practical assessment 强调观察记录。做 qualitative analysis 时要：

- 小心处理未知物；
- 使用适量样品；
- 只加入题目要求的试剂量；
- 记录所有现象，包括 “no change”；
- 若加入 $\ce{NaOH(aq)}$ 或 $\ce{NH3(aq)}$ 产生沉淀，要按要求观察过量试剂中的溶解性；
- 有气泡时要检验气体。

### Organic Analysis Tests

| 测试 | 阳性结果 | 推论 |
|---|---|---|
| Fehling's reagent | 橙红色沉淀 | aldehyde functional group |
| Tollens' reagent | 银镜或黑色沉淀 | aldehyde functional group |
| alkaline aqueous iodine | 黄色沉淀 | $\ce{CH3CO}$ 或 $\ce{CH3CH(OH)}$ group |
| acidified potassium manganate(VII) | 紫色变无色 | compound can be oxidised |

Topic 17 还使用 2,4-DNPH reagent 检测 carbonyl compounds。通常可以先用 2,4-DNPH 判断是否有羰基，再用 Fehling's 或 Tollens' reagent 区分 aldehyde 和 ketone。

### 气体测试

| 气体 | 测试结果 |
|---|---|
| $\ce{NH3}$ | 使湿润红色石蕊试纸变蓝 |
| $\ce{CO2}$ | 使石灰水产生白色沉淀 |
| $\ce{H2}$ | 点燃木条有爆鸣声 |
| $\ce{O2}$ | 使带火星木条复燃 |

例如，未知有机物与碳酸盐产生气泡，气体使石灰水变浑浊，就支持 carboxylic acid。

## Chromatography 作为辅助证据

Chromatography 用于分离混合物。CAIE 9701 中 thin-layer chromatography 和 gas / liquid chromatography 的正式学习目标在 A Level topic 37；但如果 AS 题目直接提供分离数据，可以按题目信息分析。

常用判断：

- 同一条件下，纯物质通常给一个 spot 或一个 peak；
- 混合物给多个 spots 或 peaks；
- 与标准样品在相同条件下位置或 retention time 相同，可以支持身份判断；
- TLC 中：

$$
R_f = \frac{\text{distance moved by spot}}{\text{distance moved by solvent front}}
$$

不要过度下结论。Chromatography 的匹配必须在相同条件下与标准样品比较才有意义。

## 综合推结构

建议顺序：

1. 用 molecular ion peak 找相对分子质量。
2. 如果给出 $[M+1]^+$，估算碳数。
3. 如果给出 $[M+2]^+$，检查 chlorine 或 bromine。
4. 用 infrared data 判断官能团。
5. 用 qualitative tests 确认或排除官能团。
6. 用 fragment peaks 支持碳骨架。
7. 检查提出的结构是否符合所有证据。

如果一个证据不能区分两个结构，先保留两个可能，再找下一条证据。

## 常见错误

- 只凭一个红外吸收峰就确定完整结构。
- 把 molecular ion peak 和 base peak 混淆。
- 忘记很多 $m/e$ 峰来自 fragments，不是完整分子。
- 使用 $[M+1]^+$ 公式时把分子和分母倒置。
- 忽略 chlorine 或 bromine 的 $[M+2]^+$ 峰型。
- 只写结论，不写 qualitative observation。
- 用 chromatography 匹配时忽略实验条件和标准样品。

## 快速自测

1. 哪些红外证据支持 carboxylic acid？
2. 如何从质谱中得到 molecular mass？
3. $M:M+2 \approx 3:1$ 通常提示什么元素？
4. Fehling's reagent 出现橙红色沉淀说明什么？
5. 为什么 qualitative analysis 中 “no change” 也要记录？
6. $R_f$ 比较的是哪两个距离？

## 连接

- [[40 Chemistry/01 Topics/17 Carbonyl Compounds/00 Overview|Carbonyl Compounds]]
- [[40 Chemistry/01 Topics/18 Carboxylic Acids and Derivatives/00 Overview|Carboxylic Acids and Derivatives]]
- [[40 Chemistry/01 Topics/19 Nitrogen Compounds/00 Overview|Nitrogen Compounds]]
- [[40 Chemistry/01 Topics/21 Organic Synthesis/00 Overview|Organic Synthesis]]
- [[40 Chemistry/02 Practical Skills/Qualitative Analysis/00 Overview|Qualitative Analysis]]
- [[40 Chemistry/04 Reference/Data and Periodic Table|Data and Periodic Table]]
