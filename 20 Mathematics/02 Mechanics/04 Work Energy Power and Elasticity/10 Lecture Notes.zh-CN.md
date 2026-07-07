---
title: Work, Energy, Power and Elasticity 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/02 Mechanics/04 Work Energy Power and Elasticity/00 Overview|Work, Energy, Power and Elasticity]]"
status: active
tags:
  - mathematics/mechanics
  - lecture-notes
  - zh-CN
---

# Work, Energy, Power and Elasticity 中文讲义

能量方法的好处是不用追踪每一瞬间的加速度。很多题里，路径细节很复杂，但初末位置、速度、高度或弹性伸长量很清楚，这时用能量做“账本”会比直接列 $\sum F=ma$ 简洁得多。

这一章要养成两个习惯：先判断哪些力做功，再判断机械能是否守恒。只要有摩擦、阻力、外部驱动力等非保守做功，就不能直接写机械能守恒。

## 来源范围

- 9709 4.5 Energy, work and power
- 9231 3.4 Hooke's law
- 课本路线：9709 Mechanics 的 energy、work 和 power 章节；9231 Further Mechanics 的 Hooke's law 和 elastic energy 内容。

## 图示导读

![[assets/generated/mathematics/work-energy-power-and-elasticity.svg]]

这张图用功来表示能量转移，用弹性伸长来表示能量储存。做题时可以把每一项都看成账本里的收入或支出。

## 1. 功

恒力做功是

$$
W=Fs\cos\theta,
$$

其中 $\theta$ 是力和位移之间的夹角。

如果力帮助运动，功为正；如果力阻碍运动，功为负；如果力与位移垂直，功为 0。支持力经常不做功，就是因为它和运动方向垂直。

变力做功等于力-位移图像下的面积：

$$
W=\int F\,dx.
$$

## 2. 动能和势能

动能是

$$
KE=\frac{1}{2}mv^2.
$$

重力势能变化常写成

$$
\Delta GPE=mg\Delta h,
$$

其中 $\Delta h$ 是高度变化。零势能面可以自己选，因为真正影响运动的是势能变化。

功能关系可以写成

$$
\text{work done by resultant force}=\Delta KE.
$$

也可以从能量储存的角度看：

$$
\Delta KE+\Delta GPE=\text{work done by external non-conservative forces}.
$$

如果没有摩擦、阻力、外力驱动等非保守做功，机械能守恒：

$$
KE+GPE=\text{constant}.
$$

有摩擦时，机械能通常减少，减少的部分转化为热、声或内能。

## 3. 功率

功率是做功的快慢：

$$
P=\frac{dW}{dt}.
$$

当力和速度同方向时，

$$
P=Fv.
$$

这个公式默认力和速度方向相同。如果力和速度不在同一方向，要取力在速度方向上的分量。

## 4. 胡克定律

弹性绳或弹簧在模型允许范围内满足胡克定律。CAIE 常用写法是

$$
T=\frac{\lambda x}{l},
$$

其中 $l$ 是自然长度，$x$ 是伸长量或压缩量，$\lambda$ 是弹性模量。如果令 $k=\lambda/l$，就得到熟悉的 $T=kx$。

弹性势能是

$$
E=\frac{\lambda x^2}{2l}.
$$

它也可以理解为拉力-伸长图像下的面积。

弹性题一定要分清“长度”和“伸长量”。若自然长度是 $l$，当前长度是 $L$，伸长量是

$$
x=L-l.
$$

## 5. 能量方法怎么选

如果题目只关心初末速度、高度或伸长量，中间细节不重要，能量方法通常更好。

如果题目问加速度、张力、支持力或某一瞬间的合力，通常需要 $\sum F=ma$。

很多题需要两者结合：先用能量求速度，再用牛顿第二定律求某一点的加速度或张力。

## 做题顺序

1. 选系统，确定初态和末态。
2. 写出能量储存：$KE$、$GPE$，必要时还有弹性势能。
3. 写出外力做功，特别是摩擦、阻力和驱动力。
4. 先列能量方程，再代数字。
5. 弹性题先算伸长量 $x$，不要把当前长度直接代入。
6. 检查每一项单位都是 J，损失项符号是否合理。

## 常见错误

- 把位移方向和力方向夹角弄错。
- 有摩擦时还直接用机械能守恒。
- 把功率 $P=Fv$ 用在力和速度不同方向的情况。
- 弹性题把总长度当伸长量。
- 忘记弹性势能是 $\dfrac{\lambda x^2}{2l}$，不是 $\dfrac{\lambda x}{l}$。

## 快速自查

- 我能不能判断一个力是否做功？
- 我能不能区分动能、重力势能和弹性势能？
- 我能不能说明什么时候机械能守恒？
- 我能不能从力-位移图像读出做功？
- 我能不能在弹性题里正确找出伸长量？

## 关联内容

- [[20 Mathematics/02 Mechanics/02 Kinematics and Newtonian Motion/00 Overview|Kinematics and Newtonian Motion]]
- [[20 Mathematics/02 Mechanics/05 Projectiles and Circular Motion/00 Overview|Projectiles and Circular Motion]]
- [[20 Mathematics/02 Mechanics/06 Rigid Bodies and Variable Forces/00 Overview|Rigid Bodies and Variable Forces]]
- [[10 Physics/01 Topics/05 Work Energy and Power/00 Overview|Physics Work, Energy and Power]]
- [[10 Physics/01 Topics/06 Deformation of Solids/00 Overview|Physics Deformation of Solids]]

## 学习顺序

1. 从恒力做功和功的正负号开始。
2. 练习 $KE$、$GPE$ 和机械能守恒。
3. 加入摩擦和其他外力做功。
4. 把功率看成能量转移率。
5. 学习胡克定律和弹性势能。
6. 当题目要求某一瞬间的力时，把能量和牛顿第二定律结合起来。
