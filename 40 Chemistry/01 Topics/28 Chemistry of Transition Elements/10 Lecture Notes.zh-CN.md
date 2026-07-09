---
title: "28 Chemistry of Transition Elements - Lecture Notes.zh-CN"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/a-level
  - chemistry/9701/inorganic-chemistry
---

# 28 Chemistry of Transition Elements - Lecture Notes

## 范围

本讲对应 CAIE Chemistry 9701 的 28.1-28.5。已核对本地 2025-2027 syllabus 第 44-46 页。这里不声称与某本 Chemistry coursebook 对齐，因为本地没有经过验证的 Chemistry coursebook。

本节主要看第一行过渡元素，从 $\ce{Ti}$ 到 $\ce{Cu}$。主题包括过渡元素的定义、可变氧化态、催化、配合物、配体交换、颜色、立体异构、氧化还原计算和稳定常数。

## 过渡元素的定义

CAIE 对 transition element 的定义是：

过渡元素是 d 区元素（d-block element），并且能形成一个或多个具有不完整 d 轨道的稳定离子。

重点是稳定离子，而不是原子是不是在 d 区。例如，铜可以形成 $\ce{Cu^{2+}}$，其 d 轨道不完整，所以按这个定义属于过渡元素。锌通常不按这个定义作为过渡元素处理，因为 $\ce{Zn^{2+}}$ 是 $3d^{10}$，d 轨道已满。

形成离子时，过渡金属先失去 $4s$ 电子，再失去 $3d$ 电子。$3d$ 和 $4s$ 亚层能量接近，所以不同数目的电子可以参与失去或成键，这解释了可变氧化态。

## 3d 轨道形状

你需要能画出 $3d_{xy}$ 和 $3d_{z^2}$ 轨道的形状。

- $3d_{xy}$ 轨道有四个叶瓣，位于 $xy$ 平面内，分布在 $x$ 轴和 $y$ 轴之间。
- $3d_{z^2}$ 轨道有沿 $z$ 轴的两个主要叶瓣，中间还有一圈环状电子云。

这些图像的作用是帮助理解：配体从不同方向接近金属中心时，会使 d 轨道能量发生不同变化。

## 过渡元素的典型性质

本 topic 中，过渡元素有四个典型性质：

- 有可变氧化态；
- 能作为催化剂；
- 能形成 complex ions；
- 能形成 coloured compounds。

这些性质都和 $3d$、$4s$ 能级接近，以及可利用的空 d 轨道有关。

## 可变氧化态

过渡元素能形成多个氧化态，是因为 $3d$ 和 $4s$ 亚层能量相近。不同数目的电子可以被移去，且形成的离子仍可能稳定。

常见例子有：

$$
\ce{Fe^{2+}} \text{ 和 } \ce{Fe^{3+}}
$$

$$
\ce{Cu+} \text{ 和 } \ce{Cu^{2+}}
$$

$$
\ce{Mn^{2+}} \text{ 和 } \ce{MnO4-}
$$

可变氧化态让过渡元素在氧化还原反应中很重要，因为它们可以在不同稳定氧化态之间转化。

## 催化作用

过渡元素及其化合物常常是催化剂，原因主要有两个。

第一，它们可以在反应过程中改变氧化态，之后再被再生。这样可以提供较低活化能的反应路径。

第二，它们有能量上可利用的空 d 轨道，可以和配体形成 dative covalent bonds。反应物可以暂时与金属中心结合，从而被定位、活化或使某些键变弱。

写催化解释时，不要只写“过渡金属可以催化”。要说明有多个稳定氧化态，或有可利用空 d 轨道并能形成配位键。

## 配体和配位键

Ligand 是含有孤对电子、并能把这对电子提供给中心金属原子或离子形成 dative covalent bond 的粒子。

配体提供整对电子，金属中心接受这对电子。

CAIE 要求掌握的配体类型包括：

| 类型 | 含义 | 例子 |
|---|---|---|
| Monodentate ligand | 向一个金属中心提供一对孤对电子。 | $\ce{H2O}$、$\ce{NH3}$、$\ce{Cl-}$、$\ce{CN-}$ |
| Bidentate ligand | 向同一个金属中心提供两对孤对电子。 | 1,2-diaminoethane（$\ce{H2NCH2CH2NH2}$，也写作 en）；ethanedioate ion（$\ce{C2O4^2-}$） |
| Polydentate ligand | 向同一个金属中心提供多对孤对电子。 | $\ce{EDTA^4-}$ |

Complex 是一个中心金属原子或离子周围被一个或多个配体包围而形成的分子或离子。

## 配位数、化学式和电荷

Coordination number 是配体和中心金属之间形成的配位键数目。

如果配体是单齿配体（monodentate），配位数通常等于配体个数。如果配体是双齿配体（bidentate），每个配体形成 2 个配位键，所以每个双齿配体（bidentate ligand）对配位数贡献 2。

| 配离子 | 金属氧化态 | 配体 | 配位数 |
|---|---:|---|---:|
| $\ce{[Cu(H2O)6]^2+}$ | +2 | 6 个 $\ce{H2O}$ | 6 |
| $\ce{[Cu(NH3)4(H2O)2]^2+}$ | +2 | 4 个 $\ce{NH3}$ 和 2 个 $\ce{H2O}$ | 6 |
| $\ce{[CoCl4]^2-}$ | +2 | 4 个 $\ce{Cl-}$ | 4 |
| $\ce{[Fe(CN)6]^3-}$ | +3 | 6 个 $\ce{CN-}$ | 6 |
| $\ce{[Ni(en)3]^2+}$ | +2 | 3 个 bidentate en | 6 |

计算配离子电荷时，把金属离子电荷和所有配体电荷相加。$\ce{H2O}$ 和 $\ce{NH3}$ 是中性配体；$\ce{Cl-}$、$\ce{CN-}$、$\ce{C2O4^2-}$ 和 $\ce{EDTA^4-}$ 带负电。

## 配合物形状

需要掌握 linear、square planar、tetrahedral 和 octahedral。

| 配位数 | 常见形状 | 典型键角 |
|---:|---|---:|
| 2 | linear | $180^\circ$ |
| 4 | tetrahedral | 约 $109.5^\circ$ |
| 4 | square planar | $90^\circ$ |
| 6 | octahedral | $90^\circ$ |

配位数 4 不一定唯一决定形状，可能是四面体（tetrahedral），也可能是平面正方形（square planar）。

## 配体交换

Ligand exchange 是指配合物中的某些配体被另一种配体取代。金属中心仍在，但周围配体环境改变。

铜(II) 水溶液中常写作：

$$
\ce{[Cu(H2O)6]^2+}
$$

它呈浅蓝色。加入过量氨水时，形成深蓝色配合物：

$$
\ce{[Cu(H2O)6]^2+(aq) + 4NH3(aq) <=> [Cu(NH3)4(H2O)2]^2+(aq) + 4H2O(l)}
$$

加入浓氯离子时，可以形成氯配合物：

$$
\ce{[Cu(H2O)6]^2+(aq) + 4Cl-(aq) <=> [CuCl4]^2-(aq) + 6H2O(l)}
$$

颜色由蓝色变为绿色或黄绿色，因为配体和几何结构改变了。

钴(II) 水溶液中常写作：

$$
\ce{[Co(H2O)6]^2+}
$$

它呈粉红色。加入浓氯离子时：

$$
\ce{[Co(H2O)6]^2+(aq) + 4Cl-(aq) <=> [CoCl4]^2-(aq) + 6H2O(l)}
$$

颜色由粉红色变为蓝色。加水会让平衡向水合配离子方向移动，因为水作为配体大量存在。

钴(II) 与过量氨水也会发生配体交换。粉红色的 $\ce{[Co(H2O)6]^2+}$ 形成土黄色的 $\ce{[Co(NH3)6]^2+}$：

$$
\ce{[Co(H2O)6]^2+(aq) + 6NH3(aq) <=> [Co(NH3)6]^2+(aq) + 6H2O(l)}
$$

$\ce{[Co(NH3)6]^2+}$ 在空气中很容易被氧化成棕色的 $\ce{[Co(NH3)6]^3+}$，因此实际观察到的颜色常变为棕色。

氢氧根离子常与铜(II) 或钴(II) 形成沉淀：

$$
\ce{[M(H2O)6]^2+(aq) + 2OH-(aq) -> [M(H2O)4(OH)2](s) + 2H2O(l)}
$$

这里的 $\ce{M}$ 可以代表本语境中的 $\ce{Cu}$ 或 $\ce{Co}$。答题时最好同时写现象和形成的配合物或沉淀。

## 氧化还原和标准电极电势

过渡元素有可变氧化态，所以经常出现在氧化还原体系中。用 standard electrode potentials 判断可行性时，把发生还原的半电池和发生氧化的半电池组合起来。

标准条件下，如果：

$$
E^\circ_\mathrm{cell} > 0
$$

反应在热力学上可行。

syllabus 明确提到的体系包括酸性溶液中的：

$$
\ce{MnO4- / C2O4^2-}
$$

$$
\ce{MnO4- / Fe^{2+}}
$$

以及：

$$
\ce{Cu^{2+} / I-}
$$

常用方程包括：

$$
\ce{MnO4- + 8H+ + 5e- -> Mn^{2+} + 4H2O}
$$

$$
\ce{C2O4^2- -> 2CO2 + 2e-}
$$

$$
\ce{MnO4- + 8H+ + 5Fe^{2+} -> Mn^{2+} + 4H2O + 5Fe^{3+}}
$$

$$
\ce{2MnO4- + 16H+ + 5C2O4^2- -> 2Mn^{2+} + 8H2O + 10CO2}
$$

$$
\ce{2Cu^{2+} + 4I- -> 2CuI(s) + I2}
$$

计算题按配平方程的物质的量比做；可行性题使用题目给出的 $E^\circ$ 数据。

## 配合物颜色

自由的气态过渡金属离子中，d 轨道通常是简并的（degenerate），即能量相同。形成配合物后，配体从特定方向接近金属离子，对不同 d 轨道的影响不同，原本等能的 d 轨道分裂成两组非简并 d 轨道（non-degenerate d orbitals）。

在 octahedral complex 中：

- 2 个 d 轨道能量较高；
- 3 个 d 轨道能量较低。

在 tetrahedral complex 中：

- 3 个 d 轨道能量较高；
- 2 个 d 轨道能量较低。

两组能级之间的能量差是 $\Delta E$。如果电子吸收合适频率的光，就可以从较低能级跃迁到较高能级：

$$
\Delta E = h\nu
$$

吸收光的频率由 $\Delta E$ 决定。我们看到的颜色是被吸收颜色的 complementary colour。

不同配体会改变 $\Delta E$，因此改变被吸收光的频率，也改变观察到的颜色。这就是配体交换会导致颜色变化的原因。

## 立体异构

Stereoisomers 有相同化学式和相同连接关系，但空间排布不同。

### 几何异构

Geometrical isomerism 出现在配体可以以不同空间位置排列，而且不能通过自由旋转互相转化的配合物中。

Square planar 配合物可以有 cis/trans 异构，例如：

$$
\ce{[Pt(NH3)2Cl2]}
$$

cis 异构体中两个 $\ce{Cl-}$ 相邻，trans 异构体中两个 $\ce{Cl-}$ 相对。

Octahedral 配合物也可以有 cis/trans 异构，例如：

$$
\ce{[Co(NH3)4(H2O)2]^2+}
$$

以及含 bidentate ligand 的：

$$
\ce{[Ni(en)2(H2O)2]^2+}
$$

### 光学异构

Optical isomers 是不能重合的镜像异构体。含 bidentate ligand 的 octahedral complex 很容易出现这种异构，因为螯合环可以形成左右手性排布。

例子包括：

$$
\ce{[Ni(en)3]^2+}
$$

和：

$$
\ce{[Ni(en)2(H2O)2]^2+}
$$

其中 en 是 1,2-diaminoethane（$\ce{H2NCH2CH2NH2}$）。

### 整体极性

判断配合物整体极性时，看形状和键偶极是否抵消。对称的 trans square planar 或 trans octahedral 配合物中，相同键偶极可能相互抵消，因此可能不显极性。cis 结构通常不够对称，偶极不完全抵消，因此常有极性。

## 稳定常数

稳定常数（stability constant），$K_\mathrm{stab}$，是溶剂中配离子由其组成离子或分子形成时的平衡常数。

对一般配合物：

$$
\ce{M^{n+}(aq) + xL(aq) <=> [ML_x]^{n+}(aq)}
$$

如果 $\ce{L}$ 是中性配体：

$$
K_\mathrm{stab} =
\frac{[\ce{[ML_x]^{n+}}]}{[\ce{M^{n+}}][\ce{L}]^x}
$$

如果配体带电，也要把相应配体浓度写进表达式，并带上正确指数。水不写进 $K_\mathrm{stab}$ 表达式。

例如：

$$
\ce{M^{2+}(aq) + EDTA^4-(aq) <=> [M(EDTA)]^2-(aq)}
$$

$$
K_\mathrm{stab} =
\frac{[\ce{[M(EDTA)]^2-}]}{[\ce{M^{2+}}][\ce{EDTA^4-}]}
$$

$K_\mathrm{stab}$ 很大，说明平衡强烈偏向生成配离子，配合物更稳定。配体交换也可以用稳定常数比较：更稳定的配合物在平衡中更占优势。

## 常见错误

- 把 transition element 定义成“所有 d-block element”，漏掉 stable ions with incomplete d orbitals。
- 忘记 ligand 是提供孤对电子形成 dative covalent bond。
- 写配离子时丢失电荷。
- 把 coordination number 当作配体个数，而不是配位键数。
- 把“吸收的颜色”和“观察到的颜色”混为一谈。
- 在 $K_\mathrm{stab}$ 表达式中把水写进去。
- 写 $\ce{MnO4-}$ 氧化还原方程时漏掉酸性条件中的 $\ce{H+}$。

## 连接

- [The Periodic Table: Chemical Periodicity](../09%20The%20Periodic%20Table%20Chemical%20Periodicity/00%20Overview.md)
- [Electrochemistry](../24%20Electrochemistry/00%20Overview.md)
- [Equilibria](../25%20Equilibria/00%20Overview.md)
- [Reaction Kinetics](../26%20Reaction%20Kinetics/00%20Overview.md)
