---
title: "Equilibria - Lecture Notes.zh-CN"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/as-level
  - chemistry/9701/physical-chemistry
---

# Equilibria - Lecture Notes

## 范围

本笔记对应 CAIE Chemistry 9701 AS Level Physical chemistry Topic 7：Equilibria，包括 7.1 Chemical equilibria: reversible reactions, dynamic equilibrium，以及 7.2 Brønsted-Lowry theory of acids and bases。重点放在 dynamic equilibrium、equilibrium constants 和 Le Chatelier's principle；酸碱部分也纳入，因为它属于 syllabus 中同一 topic。不声称对齐任何 Chemistry coursebook。

## Reversible reactions

Reversible reaction 可以向正反两个方向进行。Forward reaction 把反应物变成产物，reverse reaction 把产物变回反应物。例如：

$$
\ce{N2(g) + 3H2(g) <=> 2NH3(g)}
$$

双向箭头不表示反应停止，而表示两个方向都可能发生。

## Dynamic equilibrium

Dynamic equilibrium 有几个必要条件：

- forward reaction 和 reverse reaction 都在继续；
- forward reaction rate 等于 reverse reaction rate；
- reactants 和 products 的 concentrations 保持 constant；
- 系统必须是 closed system，物质不能随意进入或离开。

“Dynamic” 的意思是微观层面仍在反应。浓度不变，是因为两个方向的速率相等，而不是因为粒子不再反应。

Closed system 很重要。如果气体产物不断逸出，反向反应就不能维持；如果不断加入或移走某个物质，体系也不能建立稳定的 dynamic equilibrium。

## Le Chatelier's principle

Le Chatelier's principle：如果对处于 dynamic equilibrium 的体系作出改变，equilibrium position 会移动，以尽量减小这个改变。

这个原则预测的是移动方向，不是说改变会被完全抵消。体系会作出部分响应，然后达到新的 equilibrium position。

### Concentration

增加某个 reactant 的 concentration，equilibrium 会向消耗该 reactant 的方向移动。增加某个 product 的 concentration，equilibrium 会向消耗该 product 的方向移动。

例如：

$$
\ce{CH3COOH(aq) + C2H5OH(aq) <=> CH3COOC2H5(aq) + H2O(l)}
$$

加入更多 ethanol，equilibrium position 向右移动，生成更多 ester 和 water。

### Pressure

Pressure 变化主要影响含气体的平衡。升高 pressure，equilibrium 向气体分子数较少的一侧移动；降低 pressure，则向气体分子数较多的一侧移动。

对 Haber process：

$$
\ce{N2(g) + 3H2(g) <=> 2NH3(g)}
$$

左边有 4 mol 气体，右边有 2 mol 气体。升高 pressure 会使 equilibrium position 向右移动。

如果两侧气体分子数相同，pressure 对 equilibrium position 没有影响。

### Temperature

Temperature 会影响 equilibrium position，也会改变 equilibrium constant 的数值。

如果 forward reaction 是 exothermic，可以把 heat 看作 product。升高 temperature，体系向吸热方向移动，也就是向左。降低 temperature，则向右。

如果 forward reaction 是 endothermic，可以把 heat 看作 reactant。升高 temperature 会向右，降低 temperature 会向左。

### Catalyst

Catalyst 提供较低 activation energy 的 different pathway，使 forward 和 reverse reactions 都更快。它不改变 equilibrium position，也不改变 equilibrium constant，只是让体系更快达到 equilibrium。

## $K_c$

对于一般平衡：

$$
\ce{aA + bB <=> cC + dD}
$$

$K_c$ 写作：

$$
K_c = \frac{[\ce{C}]^c[\ce{D}]^d}{[\ce{A}]^a[\ce{B}]^b}
$$

系数变成指数。通常不把 pure solids 和 pure liquids 写入表达式，因为它们的 concentration 可视为 constant。

例如：

$$
\ce{H2(g) + I2(g) <=> 2HI(g)}
$$

对应：

$$
K_c = \frac{[\ce{HI}]^2}{[\ce{H2}][\ce{I2}]}
$$

先写表达式，再代入数值，能减少很多错误。

## $K_p$、mole fraction 和 partial pressure

气体平衡常用 partial pressure 写 equilibrium constant。某气体的 partial pressure 是它在混合气体中贡献的压力。

Mole fraction：

$$
\text{mole fraction of A} = \frac{\text{amount of A}}{\text{total amount of gas}}
$$

Partial pressure：

$$
p_A = \text{mole fraction of A} \times \text{total pressure}
$$

例如：

$$
\ce{N2(g) + 3H2(g) <=> 2NH3(g)}
$$

对应：

$$
K_p = \frac{p_{\ce{NH3}}^2}{p_{\ce{N2}}p_{\ce{H2}}^3}
$$

本 syllabus 不要求使用 $K_p$ 和 $K_c$ 之间的关系。

## Equilibrium calculations

做 $K_c$ 计算时，先按 balanced equation 建立 initial amount、change 和 equilibrium amount 的关系，再转换为 concentration。

做 $K_p$ 计算时，先求 equilibrium amounts，再求 total amount、mole fractions 和 partial pressures，最后代入表达式。

AS 题目不会要求解 quadratic equations。若计算看起来变成复杂二次方程，通常是设量或题目条件读错了。

## 哪些因素改变 equilibrium constant

在同一反应中，$K_c$ 或 $K_p$ 的值只随 temperature 改变。

改变 concentration 或 pressure 会改变 equilibrium position，但在同一 temperature 下，新平衡仍会满足同一个 $K$ 值。Catalyst 不改变 $K$，只改变达到平衡的速度。

如果 forward reaction 是 exothermic，升高 temperature 会使 equilibrium 向 reactants 一侧移动，$K$ 变小。如果 forward reaction 是 endothermic，升高 temperature 会使 equilibrium 向 products 一侧移动，$K$ 变大。

## 工业平衡例子

Haber process：

$$
\ce{N2(g) + 3H2(g) <=> 2NH3(g)}
$$

正反应放热，且气体分子数从 4 mol 变为 2 mol。低 temperature 和高 pressure 有利于 ammonia yield。但工业上需要 compromise：temperature 不能太低，否则 rate 太慢；pressure 高有利于 yield，但设备成本和安全要求增加；iron catalyst 提高速率，但不改变 equilibrium position。

常见条件约为 $450\ ^\circ\mathrm{C}$、约 $200\ \mathrm{atm}$ 的高压，以及 iron catalyst。这些是 compromise conditions：更低 temperature 有利于 equilibrium yield，但 rate 太慢；更高 pressure 有利于 yield，但成本和安全压力更大。

Contact process 中的重要平衡是：

$$
\ce{2SO2(g) + O2(g) <=> 2SO3(g)}
$$

正反应也是放热，且气体分子数减少。较低 temperature 和较高 pressure 有利于 $\ce{SO3}$，但实际条件同样要平衡 yield、rate 和 cost。$\ce{V2O5}$ catalyst 用来提高达到 equilibrium 的速率。

常见条件约为 $450\ ^\circ\mathrm{C}$、接近 atmospheric pressure，以及 $\ce{V2O5}$ catalyst。由于这些条件下 $\ce{SO3}$ 的 equilibrium yield 已经很高，大幅升高 pressure 带来的收益不大，反而增加成本。

## Brønsted-Lowry acids and bases

Brønsted-Lowry acid 是 proton donor，Brønsted-Lowry base 是 proton acceptor。

例如：

$$
\ce{HCl(aq) + H2O(l) -> H3O+(aq) + Cl-(aq)}
$$

$\ce{HCl}$ 给出 proton，是 acid；water 接受 proton，是 base。

Syllabus 中常见 acids 包括 hydrochloric acid $\ce{HCl}$、sulfuric acid $\ce{H2SO4}$、nitric acid $\ce{HNO3}$、ethanoic acid $\ce{CH3COOH}$。常见 alkalis 包括 sodium hydroxide $\ce{NaOH}$、potassium hydroxide $\ce{KOH}$ 和 ammonia $\ce{NH3}$。

## Strong、weak 与 concentration

Strong acids 和 strong bases 在 aqueous solution 中 fully dissociated。Weak acids 和 weak bases 只 partially dissociated。

Strong/weak 说的是 dissociation extent，不是 concentration。Dilute strong acid 仍然 fully dissociated；concentrated weak acid 仍然只 partially dissociated。

Water 的 pH 为 7，acid solutions 的 pH 低于 7，alkaline solutions 的 pH 高于 7。

同浓度下，strong acid 通常 pH 更低，与 reactive metal 反应更快，conductivity 更高，因为溶液中 ions 尤其是 $\ce{H+}$ 的浓度更高。

## Neutralisation、salts 和 titration curves

Neutralisation 是 $\ce{H+(aq)}$ 与 $\ce{OH-(aq)}$ 生成水：

$$
\ce{H+(aq) + OH-(aq) -> H2O(l)}
$$

中和反应还会生成 salts。例如：

$$
\ce{HCl(aq) + NaOH(aq) -> NaCl(aq) + H2O(l)}
$$

AS 需要能 sketch 强酸、弱酸与强碱、弱碱组合的 pH titration curves。Indicator 的 transition range 应落在 end point 附近陡直变化的区域内。题目会给 suitable data，不要求使用 $pK_a$。

常见趋势：

- strong acid + strong alkali：equivalence point 接近 pH 7，竖直段明显；
- strong acid + weak alkali：equivalence point 低于 pH 7；
- weak acid + strong alkali：equivalence point 高于 pH 7；
- weak acid + weak alkali：pH 突变较小，indicator 选择更困难。

## 解题顺序

Le Chatelier 题：先说改变了什么，再说体系怎样 minimises this change，最后写 equilibrium position 向哪边移动。

$K_c$ 或 $K_p$ 题：先从 balanced equation 写表达式，再处理 concentration 或 partial pressure。

酸碱题：先判断题目问的是 proton transfer、dissociation extent、pH trend、neutralisation，还是 indicator choice。不要把 strong 和 concentrated 混用。

## 快速自测

- 为什么 dynamic equilibrium 不等于反应停止？
- 为什么升高 pressure 有利于 Haber process 生成 ammonia？
- $K_c$ 和 $K_p$ 表达式中的指数从哪里来？
- 哪些改变会影响 equilibrium position？哪些会改变 $K$？
- Strong acid 和 concentrated acid 的区别是什么？

## 连接

- [Chemical Energetics](../05%20Chemical%20Energetics/10%20Lecture%20Notes.md)
- [Reaction Kinetics](../08%20Reaction%20Kinetics/10%20Lecture%20Notes.md)
- [A Level Equilibria](../25%20Equilibria/00%20Overview.md)
