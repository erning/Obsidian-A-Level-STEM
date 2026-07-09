---
title: "21 Organic Synthesis - Lecture Notes.zh-CN"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/as-level
  - chemistry/9701/organic-chemistry
---

# 21 Organic Synthesis - Lecture Notes

## 范围

本讲对应 CAIE Chemistry 9701 AS Level topic 21：**Organic synthesis**。这个主题本身不新增一大批反应，而是要求你把 AS 已学反应用起来：

- 用大纲中的反应识别官能团；
- 预测含多个官能团分子的性质和反应；
- 设计多步合成路线；
- 分析给定路线中的反应类型、试剂条件和可能副产物。

## 合成题的思路

有机合成不是背一条固定路线，而是在官能团之间导航。每一步都问四个问题：

1. 哪个官能团在变化？
2. 什么试剂和条件能完成这个变化？
3. 反应类型是什么？
4. 可能有什么副产物或竞争反应？

完整答案不能只写一串有机物名称。每一步都要写 reagent and condition。

## AS 官能团转化表

| 转化 | 试剂和条件 | 反应类型 |
|---|---|---|
| alkene $\to$ alkane | $\ce{H2(g)}$，Pt/Ni catalyst，heat | electrophilic addition / hydrogenation |
| alkene $\to$ alcohol | steam，$\ce{H2O(g)}$，$\ce{H3PO4}$ catalyst | electrophilic addition |
| alkene $\to$ halogenoalkane | $\ce{HX(g)}$，room temperature | electrophilic addition |
| alkene $\to$ diol | cold dilute acidified $\ce{KMnO4}$ | oxidation |
| halogenoalkane $\to$ alcohol | $\ce{NaOH(aq)}$，heat | nucleophilic substitution |
| halogenoalkane $\to$ nitrile | $\ce{KCN}$ in ethanol，heat | nucleophilic substitution |
| halogenoalkane $\to$ primary amine | $\ce{NH3}$ in ethanol，heat under pressure | nucleophilic substitution |
| halogenoalkane $\to$ alkene | $\ce{NaOH}$ in ethanol，heat | elimination |
| alcohol $\to$ halogenoalkane | $\ce{HX}$、$\ce{PCl5}$、$\ce{PCl3}$ with heat 或 $\ce{SOCl2}$ 等 | substitution |
| alcohol $\to$ alkene | heated $\ce{Al2O3}$ 或 concentrated acid | elimination / dehydration |
| primary alcohol $\to$ aldehyde | acidified $\ce{K2Cr2O7}$ 或 $\ce{KMnO4}$，distillation | oxidation |
| primary alcohol $\to$ carboxylic acid | acidified $\ce{K2Cr2O7}$ 或 $\ce{KMnO4}$，reflux | oxidation |
| secondary alcohol $\to$ ketone | acidified $\ce{K2Cr2O7}$ 或 $\ce{KMnO4}$，distillation | oxidation |
| aldehyde or ketone $\to$ alcohol | $\ce{NaBH4}$ 或 $\ce{LiAlH4}$ | reduction |
| aldehyde or ketone $\to$ hydroxynitrile | $\ce{HCN}$，$\ce{KCN}$ catalyst，heat | nucleophilic addition |
| aldehyde $\to$ carboxylic acid | acidified $\ce{K2Cr2O7}$ 或 $\ce{KMnO4}$，reflux | oxidation |
| carboxylic acid + alcohol $\to$ ester | concentrated $\ce{H2SO4}$ catalyst | condensation / esterification |
| ester $\to$ alcohol + acid or salt | dilute acid，或 dilute alkali and heat | hydrolysis |
| nitrile $\to$ carboxylic acid | dilute acid，或 dilute alkali followed by acidification | hydrolysis |
| carboxylic acid $\to$ primary alcohol | $\ce{LiAlH4}$ | reduction |
| alkene $\to$ addition polymer | 合适聚合条件 | addition polymerisation |

真正做题时不需要把整张表都写出来。你要选一条符合 AS 大纲、步数合理、不会破坏目标官能团的路线。

## 官能团识别

合成和分析经常连在一起。AS 要求用大纲中的反应识别官能团。

| 测试或证据 | 阳性结果 | 提示的官能团 |
|---|---|---|
| aqueous bromine | 褪色 | $\ce{C=C}$ |
| 2,4-DNPH reagent | 橙色沉淀 | carbonyl compound，即 aldehyde 或 ketone |
| Fehling's 或 Tollens' reagent | 橙红色沉淀，或银镜/黑色沉淀 | aldehyde |
| alkaline aqueous iodine | 黄色 tri-iodomethane 沉淀 | aldehyde/ketone 中的 $\ce{CH3CO-}$，或 alcohol 中的 $\ce{CH3CH(OH)-}$ |
| acidified $\ce{KMnO4}$ 紫色变无色 | 物质可被氧化 | 需结合题目判断，例如 alkene、primary alcohol、secondary alcohol、aldehyde 等 |
| carbonate 产生气泡，气体使石灰水变浑浊 | 生成 $\ce{CO2}$ | carboxylic acid |
| aqueous silver nitrate in ethanol 后出现银卤化物沉淀 | 有 halogen | halogenoalkane |

不要机械套用测试。一个现象可能对应多个官能团，要结合题目给出的结构、反应路线和其他证据。

## 多官能团分子

一个分子可能含有多个官能团。做题时要判断条件会优先作用在哪个位置。

例如 $\ce{HOCH2CH2Br}$ 同时有 alcohol group 和 halogenoalkane group：

- $\ce{NaOH(aq)}$ and heat 可把 $\ce{Br}$ 替换成 $\ce{-OH}$，得到二醇；
- ethanolic $\ce{NaOH}$ and heat 可发生 elimination，得到含双键的醇；
- 合适的卤代试剂可把 alcohol group 变成 halogenoalkane。

所以不能只看到第一个官能团就开始写反应，要看整个分子。

## 逆推路线

合成题常用逆推：从目标产物往前想，问“哪一种前体可以一步生成它？”

如果目标是 carboxylic acid：

- 可能来自 primary alcohol 或 aldehyde 的氧化；
- 可能来自 nitrile 的水解；
- 可能来自 ester 的水解再酸化。

如果目标是 alcohol：

- 可能来自 alkene 加 steam；
- 可能来自 halogenoalkane 与 $\ce{NaOH(aq)}$ 取代；
- 可能来自 aldehyde、ketone 或 carboxylic acid 的还原；
- 可能来自 ester 水解。

如果目标比起始卤代烃多 1 个碳，优先考虑 nitrile route。

## 可能副产物和路线分析

大纲要求能分析 possible by-products。AS 中常见点包括：

- alkane 的 free-radical substitution 可能给出多种取代产物；
- 不对称 alkene 与 $\ce{HX}$ 加成可能有不止一种位置产物，主产物可用 carbocation stability 和 Markovnikov addition 解释；
- halogenoalkane 在不同条件下可能发生 substitution 或 elimination；
- esterification 的小分子副产物是 water；
- ester 的碱性水解先给 carboxylate salt，不是游离羧酸；
- incomplete combustion 可产生 carbon monoxide 和 unburnt hydrocarbons。

分析路线时只写相关副产物。不要为了显得完整而写与条件无关的内容。

## 做路线题的步骤

1. 数起始物和目标物的碳数。
2. 找出两者所有官能团。
3. 标出必须改变的键或官能团。
4. 在 AS 反应表中找一一步转化。
5. 如果一步不能完成，插入中间体。
6. 检查试剂条件会不会破坏需要保留的官能团。
7. 写出路线、试剂条件和反应类型。

## 常见错误

- 只写试剂，不写条件。
- 明明有 AS 路线，却使用大纲外反应。
- 忘记 $\ce{KCN}$ 会增加 1 个碳。
- 目标是羧酸时，把伯醇氧化条件写成 distillation。
- 用 $\ce{NaBH4}$ 还原羧酸。
- 忽略 substitution 和 elimination 的竞争。
- 只写测试现象，不说明对应的官能团。

## 快速自测

1. halogenoalkane 分别怎样转化为 alcohol、nitrile、amine 和 alkene？
2. AS 中哪些路线可以制备 carboxylic acid？
3. 哪些 AS 反应会让碳数增加 1？
4. alcohol 氧化时，什么时候写 distillation，什么时候写 reflux？
5. 合成路线的每一步必须包含哪些信息？

## 连接

- [An Introduction to AS Level Organic Chemistry](../13%20An%20Introduction%20to%20AS%20Level%20Organic%20Chemistry/00%20Overview.md)
- [Hydrocarbons](../14%20Hydrocarbons/00%20Overview.md)
- [Halogen Compounds](../15%20Halogen%20Compounds/00%20Overview.md)
- [Hydroxy Compounds](../16%20Hydroxy%20Compounds/00%20Overview.md)
- [Carbonyl Compounds](../17%20Carbonyl%20Compounds/00%20Overview.md)
- [Carboxylic Acids and Derivatives](../18%20Carboxylic%20Acids%20and%20Derivatives/00%20Overview.md)
- [Nitrogen Compounds](../19%20Nitrogen%20Compounds/00%20Overview.md)
- [Polymerisation](../20%20Polymerisation/00%20Overview.md)
- [Analytical Techniques](../22%20Analytical%20Techniques/00%20Overview.md)
