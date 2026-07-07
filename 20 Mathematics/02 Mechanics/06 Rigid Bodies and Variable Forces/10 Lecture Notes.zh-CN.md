---
title: Rigid Bodies and Variable Forces 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/02 Mechanics/06 Rigid Bodies and Variable Forces/00 Overview|Rigid Bodies and Variable Forces]]"
status: active
tags:
  - mathematics/mechanics
  - lecture-notes
  - zh-CN
---

# Rigid Bodies and Variable Forces 中文讲义

这一章把 Mechanics 往前推进两步。刚体题不能再把物体看成一个点，因为形状、长度和转动都会影响平衡；变力题也不能再套匀加速公式，因为加速度会随时间、位置或速度变化。

两类题看起来不一样，但共同点是：先选模型，再选方程。刚体先看力矩，变力先看变量。

## 来源范围

- 9231 3.2 Equilibrium of a rigid body
- 9231 3.5 Linear motion under a variable force
- 课本路线：9231 Further Mechanics 的 rigid-body 和 variable-force 内容。

## 图示导读

![[assets/generated/mathematics/rigid-bodies-and-variable-forces.svg]]

这张图把刚体的力矩平衡和变力的积分思想放在一起。前者靠几何和取矩点，后者靠微分方程或功的积分。

## 1. 质点和刚体的区别

质点模型只考虑合力，不考虑大小和形状。刚体有长度和形状，所以还要考虑力矩。平衡条件是

$$
\sum F_x=0,\qquad \sum F_y=0,\qquad \sum M=0.
$$

合力为 0 但合力矩不为 0，物体会转动；合力矩为 0 但合力不为 0，物体会平移。

取矩点可以自己选。通常选在未知力经过的点上，因为这个力对该点的力矩为 0，方程会少一个未知量。

## 2. 质心

刚体受到的重力可以等效为一个力 $mg$ 作用在质心。均匀物体的质心先看对称性：有对称轴，质心就在对称轴上。

组合物体的质心可以用加权平均：

$$
\bar x=\frac{\sum m_ix_i}{\sum m_i}.
$$

均匀薄片中，质量与面积成正比，所以可以用面积代替质量：

$$
\bar x=\frac{\sum A_ix_i}{\sum A_i}.
$$

如果是挖掉一块的图形，可以把被挖掉的部分看成负面积。计算时参考点不能变，所有位置都要相对同一个原点。

## 3. 滑动和倾覆

刚体接触地面或支撑面时，经常要判断它会先滑动还是先倾覆。

滑动看摩擦是否达到极限：

$$
F=\mu R.
$$

倾覆看支持力是否集中到边缘，通常对即将转动的边缘取矩。质心处重力的作用线决定重力产生怎样的转动趋势。

如果滑动和倾覆都可能发生，就分别求出临界条件，再比较哪个先达到。

一个简洁模型可以说明比较方法。设均匀长方体重为 $mg$，半宽为 $a$，在粗糙水平地面上受到水平拉力 $P$，拉力作用点离地高度为 $h$。若即将滑动，则

$$
P=\mu mg.
$$

若即将绕远侧下边缘倾覆，对该边缘取矩：

$$
Ph=mga,\qquad P=\frac{mga}{h}.
$$

比较 $\mu mg$ 和 $mga/h$，较小的那个对应先发生的临界状态。这样比凭图像直觉猜“先滑还是先翻”更可靠。

## 4. 变力与牛顿第二定律

力不是常数时，加速度通常也不是常数，匀加速公式就不能直接用。仍然从牛顿第二定律开始：

$$
ma=F.
$$

接着要根据题目里的变量选择加速度的写法。

如果力是时间的函数，用

$$
a=\frac{dv}{dt}.
$$

如果力是位移的函数，用链式法则

$$
a=v\frac{dv}{dx}.
$$

如果力是速度的函数，两种写法都可能有用：$m\,dv/dt=F(v)$ 适合求速度随时间的变化；$m v\,dv/dx=F(v)$ 适合求速度和位移的关系。题目最后要的是时间还是距离，通常决定选哪一种。

9231 这里的微分方程通常是可分离变量的。列好方程后，把同类变量放在同一边，再积分。

## 5. 变力做功

如果力随位移变化，做功不能用简单的 $W=Fs$，而要用

$$
W=\int_a^b F(x)\,dx.
$$

图像上，这就是力-位移图像下的面积。

例如

$$
F=2x+1
$$

从 $x=0$ 到 $x=3$ 做功为

$$
\int_0^3(2x+1)\,dx
=\left[x^2+x\right]_0^3=12.
$$

如果单位是 SI，这里的功就是 $12\text{ J}$。

## 6. 变力和能量

变力做功仍然可以接到能量方程：

$$
W=\Delta KE
$$

或者接到机械能变化。关键是把所有做功的力都算进去。

如果力是阻力，方向与位移相反，做功为负。符号要通过力与位移方向判断。

也可以直接写成

$$
\int_a^b F(x)\,dx=\frac12mv^2-\frac12mu^2.
$$

这条关系在力是位置函数时很有用，因为它不一定需要先求出 $v(t)$。

## 7. 简短变力例子

如果质点从静止开始运动，合力为 $F=kt$，应使用

$$
m\frac{dv}{dt}=kt.
$$

积分并代入 $t=0$ 时 $v=0$，得到

$$
v=\frac{k}{2m}t^2.
$$

如果质点在 $x=0$ 处速度为 $u$，合力为 $F=kx$，应使用

$$
m v\frac{dv}{dx}=kx.
$$

分离变量并积分：

$$
\frac12m(v^2-u^2)=\frac12kx^2,
$$

所以

$$
v^2=u^2+\frac{k}{m}x^2.
$$

## 做题顺序

1. 刚体题先画受力图和尺寸，标出质心。
2. 选方便的取矩点，尽量消掉未知力。
3. 判断是否涉及滑动或倾覆。
4. 变力题先看力是 $t$ 的函数还是 $x$ 的函数。
5. 根据变量选择 $a=dv/dt$ 或 $a=v\,dv/dx$。
6. 分离变量、积分，并代入初始条件。

## 常见错误

- 刚体题只写合力平衡，忘记力矩平衡。
- 力矩距离没有取垂直距离。
- 组合质心中质量和位置没有对应。
- 滑动和倾覆都可能发生时，只求其中一个临界条件。
- 变力题还用 $W=Fs$，没有积分或求面积。
- 变力运动还套匀加速公式。
- 该用 $v\,dv/dx$ 时硬用 $dv/dt$，导致变量分不开。
- 阻力做功符号写错。

## 快速自查

- 我能不能判断题目是否必须考虑转动？
- 我能不能选一个方便的取矩点？
- 我能不能用加权平均求质心？
- 我能不能区分滑动临界和倾覆临界？
- 我能不能把变力做功写成积分或图像面积？
- 我能不能根据题目变量选择正确的加速度形式？

## 关联内容

- [[20 Mathematics/02 Mechanics/01 Forces and Equilibrium/00 Overview|Forces and Equilibrium]]
- [[20 Mathematics/02 Mechanics/04 Work Energy Power and Elasticity/00 Overview|Work, Energy, Power and Elasticity]]
- [[20 Mathematics/01 Pure Mathematics/06 Integration/00 Overview|Integration]]
- [[20 Mathematics/01 Pure Mathematics/13 Further Calculus and Differential Equations/00 Overview|Further Calculus and Differential Equations]]

## 学习顺序

1. 先回顾刚体力矩平衡。
2. 练习简单复合物体的质心。
3. 比较滑动和倾覆的临界条件。
4. 复习可分离变量微分方程。
5. 建立变力运动方程。
6. 当力是位置函数时，用功能关系作为另一条路线。
