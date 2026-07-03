---
title: Work, Energy, Power and Elasticity 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/02 Mechanics/04 Work Energy Power and Elasticity/00 Overview|Work, Energy, Power and Elasticity]]"
status: draft
tags:
  - mathematics/mechanics
  - lecture-notes
  - zh-CN
---

# Work, Energy, Power and Elasticity 中文讲义

这一章的主线是：用能量看运动。力学题不一定都要从 $F=ma$ 开始。有些题里，初末状态比过程更重要，这时能量方法会更短。

1. 题目更适合用力和加速度，还是用能量守恒？
2. 哪些力做功，哪些力不做功？
3. 是否有摩擦或阻力导致机械能损失？
4. 弹性物体是否满足 Hooke 定律？

## 图示导读

![[assets/generated/mathematics/work-energy-power-and-elasticity.svg]]

这张图用来快速理解“功、能量、功率与弹性”：用功和弹性伸长解释能量转移。

## 学习范围

- 功、动能、重力势能和机械能。
- 功率和效率。
- 变力做功和力-位移图像面积。
- Hooke 定律、弹性势能和弹性绳/弹簧模型。

## 1. 功

恒力做功是

$$
W=Fs\cos\theta,
$$

其中 $\theta$ 是力和位移之间的夹角。

如果力与位移同方向，$W=Fs$；如果力与位移垂直，功为 0。

变力做功等于力-位移图像下的面积：

$$
W=\int F\,ds.
$$

## 2. 动能和势能

动能是

$$
KE=\frac{1}{2}mv^2.
$$

重力势能变化常写成

$$
\Delta GPE=mg\Delta h.
$$

功能关系是

$$
\text{work done by resultant force}=\Delta KE.
$$

如果没有非保守力做功，机械能守恒：

$$
KE+GPE=\text{constant}.
$$

有摩擦时，机械能会减少。减少的部分通常转化为热。

## 3. 功率

功率是做功的快慢：

$$
P=\frac{dW}{dt}.
$$

当力和速度同方向时，

$$
P=Fv.
$$

如果机器效率为 $\eta$，

$$
\eta=\frac{\text{useful power output}}{\text{power input}}.
$$

注意效率通常小于 1，也可以写成百分比。

## 4. Hooke 定律

弹簧或弹性绳在弹性限度内满足

$$
T=kx,
$$

其中 $x$ 是伸长量，$k$ 是劲度系数。

弹性势能是

$$
E=\frac{1}{2}kx^2.
$$

它也可以理解为拉力-伸长图像下的面积。

弹性题要分清“长度”和“伸长量”。若自然长度是 $l$，当前长度是 $L$，伸长量是

$$
x=L-l.
$$

## 5. 能量方法怎么选

如果题目只关心初末速度、高度或伸长量，中间细节不重要，能量方法通常更好。

如果题目问加速度、张力或某一瞬间的合力，可能需要 $F=ma$。

很多题需要两者结合：先用能量求速度，再用牛顿第二定律求某一点的加速度或张力。

## 6. 常见错误

- 把位移方向和力方向夹角弄错。
- 有摩擦时还直接用机械能守恒。
- 把功率 $P=Fv$ 用在力和速度不同方向的情况。
- 弹性题把总长度当伸长量。
- 忘记弹性势能是 $\frac{1}{2}kx^2$，不是 $kx$。

## 快速自查

- 我能不能判断一个力是否做功？
- 我能不能区分动能、重力势能和弹性势能？
- 我能不能说明什么时候机械能守恒？
- 我能不能从力-位移图像读出做功？
