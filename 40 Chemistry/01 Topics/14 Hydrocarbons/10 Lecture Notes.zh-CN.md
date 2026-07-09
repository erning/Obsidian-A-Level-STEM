---
title: "14 Hydrocarbons - Lecture Notes.zh-CN"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/as-level
  - chemistry/9701/organic-chemistry
---

# 14 Hydrocarbons - Lecture Notes

## 范围

本笔记对应 CAIE Chemistry 9701 AS Level Topic 14：14.1 alkanes 和 14.2 alkenes。不声称与任何 Chemistry coursebook 对齐。

## AS 中的 Hydrocarbons

Hydrocarbon 只含碳和氢。AS 重点比较两类：

- **Alkanes** 是 saturated hydrocarbons。直链 alkane 的通式为 $\ce{C_nH_{2n+2}}$，只含碳碳单键。
- **Alkenes** 是 unsaturated hydrocarbons。含一个双键、非环状的 alkene 通式为 $\ce{C_nH_{2n}}$，官能团是 $\ce{C=C}$。

这个对比很重要。Alkanes 中的 $\ce{C-H}$ 和 $\ce{C-C}$ 键强、极性小，所以通常不容易被极性试剂进攻。Alkenes 的 $\ce{C=C}$ 含有电子丰富的 $\pi$ 键，更容易和 electrophiles 发生反应。

## Alkanes 的制备

Alkenes 加氢可以制备 alkanes：

$$
\ce{CH2=CH2 + H2 -> CH3CH3}
$$

试剂和条件：$\ce{H2(g)}$，Pt 或 Ni catalyst，heat。

Cracking 也能从长链 alkane 得到较短链 alkanes 和 alkenes。条件是 heat with $\ce{Al2O3}$。Cracking 很有用，因为它把较重的 crude oil fractions 转化为更有用、较低 $M_r$ 的燃料和化工原料。

例如：

$$
\ce{C10H22 -> C6H14 + C4H8}
$$

## Alkanes 的反应

### Combustion

完全燃烧生成二氧化碳和水：

$$
\ce{CH4 + 2O2 -> CO2 + 2H2O}
$$

氧气不足时发生不完全燃烧，可能生成一氧化碳、碳和水：

$$
\ce{2CH4 + 3O2 -> 2CO + 4H2O}
$$

内燃机中燃烧 alkanes 会带来环境问题。一氧化碳有毒；高温下空气中的氮和氧可形成 oxides of nitrogen；未燃烧 hydrocarbons 也会造成污染。Catalytic converters 可氧化一氧化碳和 hydrocarbons，并还原 oxides of nitrogen。

### Free-Radical Substitution

Alkanes 和 $\ce{Cl2}$ 或 $\ce{Br2}$ 在 ultraviolet light 下发生 substitution。一个氢原子被卤素原子替代。以 ethane 为例：

$$
\ce{CH3CH3 + Cl2 -> CH3CH2Cl + HCl}
$$

机制分为三步。

Initiation 通过 homolytic fission 生成 radicals：

$$
\ce{Cl2 ->[uv] 2Cl^.}
$$

Propagation 消耗一个 radical，同时再生成一个 radical：

$$
\ce{Cl^. + CH3CH3 -> HCl + CH3CH2^.}
$$

$$
\ce{CH3CH2^. + Cl2 -> CH3CH2Cl + Cl^.}
$$

Termination 使 radicals 结合并消失：

$$
\ce{Cl^. + Cl^. -> Cl2}
$$

$$
\ce{CH3CH2^. + Cl^. -> CH3CH2Cl}
$$

$$
\ce{CH3CH2^. + CH3CH2^. -> CH3CH2CH2CH3}
$$

Free-radical substitution 可以继续发生，因此产物常是混合物。

## Alkenes 的制备

AS 中常见三条路线：

1. Halogenoalkane 和 ethanolic $\ce{NaOH}$ 加热，发生 elimination：

$$
\ce{CH3CH2Br + NaOH -> CH2=CH2 + NaBr + H2O}
$$

2. Alcohol 脱水，用 heated $\ce{Al2O3}$ 或 concentrated $\ce{H2SO4}$：

$$
\ce{CH3CH2OH -> CH2=CH2 + H2O}
$$

3. 长链 alkane 的 cracking。

## Alkenes 的反应

### Electrophilic Addition

Alkene 的 $\pi$ 键电子密度高，能进攻 electrophile，所以典型反应是 electrophilic addition。

Hydrogenation：

$$
\ce{CH2=CH2 + H2 -> CH3CH3}
$$

条件：$\ce{H2(g)}$，Pt 或 Ni catalyst，heat。

与 steam 加成：

$$
\ce{CH2=CH2 + H2O -> CH3CH2OH}
$$

条件：$\ce{H2O(g)}$ 和 $\ce{H3PO4}$ catalyst。

与 hydrogen halide 在室温下加成：

$$
\ce{CH3CH=CH2 + HBr -> CH3CHBrCH3}
$$

与 halogen 加成：

$$
\ce{CH2=CH2 + Br2 -> CH2BrCH2Br}
$$

Aqueous bromine 可检验 $\ce{C=C}$：橙棕色溴水褪色，因为 $\ce{Br2}$ 加到双键两端。

### Electrophilic Addition 机制

Ethene 和 bromine 反应时，电子丰富的 $\ce{C=C}$ 使 $\ce{Br2}$ 极化。Curly arrow 从双键指向较近的溴原子，另一个 curly arrow 从 $\ce{Br-Br}$ 键指向较远的溴原子，生成 $\ce{Br-}$。随后 $\ce{Br-}$ 进攻 carbocation，生成 $\ce{CH2BrCH2Br}$。

Propene 和 hydrogen bromide 反应时，第一步可能形成两种 carbocations。主要路线形成更稳定的 secondary carbocation：

$$
\ce{CH3CH=CH2 + H+ -> CH3CH+CH3}
$$

然后 bromide 进攻：

$$
\ce{CH3CH+CH3 + Br- -> CH3CHBrCH3}
$$

Alkyl groups 有正 inductive effect，能把电子密度推向 carbocation，使其更稳定。稳定性通常为 tertiary > secondary > primary。这解释了 AS 层面的 Markovnikov addition：主要产物来自更稳定的 carbocation intermediate。

### Alkenes 的氧化

Cold dilute acidified $\ce{KMnO4}$ 把 alkene 氧化成 diol：

$$
\ce{CH2=CH2 + [O] + H2O -> HOCH2CH2OH}
$$

Hot concentrated acidified $\ce{KMnO4}$ 会断裂碳碳双键。产物能帮助判断原来双键的位置。

- 双键碳上有氢时，通常被氧化为 carboxylic acid。
- 末端 $\ce{=CH2}$ 碳会进一步氧化为 $\ce{CO2}$。
- 双键碳上没有氢时，形成 ketone。

### Addition Polymerisation

Alkenes 能发生 addition polymerisation。双键打开，monomers 相连，不脱去小分子：

$$
\ce{n CH2=CH2 -> [-CH2-CH2-]_{n}}
$$

Propene 形成 poly(propene)：

$$
\ce{n CH2=CHCH3 -> [-CH2-CH(CH3)-]_{n}}
$$

## 学习方法

学 alkanes 时抓住“强、低极性的单键”，再联系 combustion、cracking 和 free-radical substitution。学 alkenes 时抓住“电子丰富的双键”，再联系 electrophilic addition、oxidation 和 polymerisation。
