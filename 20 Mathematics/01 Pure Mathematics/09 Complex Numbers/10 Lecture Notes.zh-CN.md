---
title: Complex Numbers 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/09 Complex Numbers/00 Overview|Complex Numbers]]"
status: draft
tags:
  - mathematics/pure
  - lecture-notes
  - zh-CN
---

# Complex Numbers 中文讲义

这一章的主线是：把数轴扩展成复平面。复数不是“虚”的小技巧，而是一个可以同时表示长度和旋转的对象。做复数题时，代数形式适合计算，极坐标形式适合看大小、角度和幂。

1. 这个复数适合用 $a+bi$，还是用 $r(\cos\theta+i\sin\theta)$？
2. 题目问的是模、辐角、共轭、根，还是轨迹？
3. 乘除法是否可以从旋转和伸缩来理解？
4. 辐角是否写在题目要求的范围内？

## 图示导读

![[assets/generated/mathematics/complex-numbers.svg]]

这张图用来快速理解“复数”：在复平面上看模和辐角。

## 学习范围

- 复数的代数形式、共轭、模和辐角。
- 复平面上的几何解释。
- 极坐标形式、乘除法、幂和根。
- 复数方程和简单轨迹。

## 1. 复数的基本形式

复数写成

$$
z=a+bi,
$$

其中 $a$ 是实部，$b$ 是虚部，$i^2=-1$。

复数可以看成复平面上的点 $(a,b)$。横轴是实轴，纵轴是虚轴。

共轭复数是

$$
\overline{z}=a-bi.
$$

一个重要关系是

$$
z\overline{z}=a^2+b^2.
$$

## 2. 模和辐角

复数的模是它到原点的距离：

$$
|z|=\sqrt{a^2+b^2}.
$$

辐角是从正实轴转到这个点的角，记作

$$
\arg z.
$$

主辐角通常取在

$$
-\pi<\arg z\le \pi
$$

或题目指定的范围内。求辐角时不要只按 $\tan^{-1}\frac{b}{a}$ 机械计算，还要看点在哪个象限。

## 3. 极坐标形式

如果 $|z|=r$、$\arg z=\theta$，那么

$$
z=r(\cos\theta+i\sin\theta).
$$

也可以写成

$$
z=re^{i\theta}.
$$

极坐标形式的优势是乘除法很清楚：

$$
r_1e^{i\theta_1}\cdot r_2e^{i\theta_2}
=r_1r_2e^{i(\theta_1+\theta_2)}.
$$

也就是说，模相乘，辐角相加。除法则是模相除，辐角相减。

## 4. 幂和根

De Moivre 公式是

$$
(\cos\theta+i\sin\theta)^n=\cos n\theta+i\sin n\theta.
$$

所以如果

$$
z=re^{i\theta},
$$

那么

$$
z^n=r^ne^{in\theta}.
$$

求 $n$ 次根时，要记得有 $n$ 个根。若

$$
w^n=re^{i\theta},
$$

则

$$
w=r^{1/n}e^{i(\theta+2k\pi)/n},\qquad k=0,1,\ldots,n-1.
$$

漏根是复数根题里最常见的问题。

## 5. 复数轨迹

复数轨迹其实是平面几何。

例如

$$
|z-a|=r
$$

表示点 $z$ 到点 $a$ 的距离恒为 $r$，所以是一条圆。

又如

$$
|z-a|=|z-b|
$$

表示点 $z$ 到 $a$ 和 $b$ 的距离相等，所以是线段 $ab$ 的垂直平分线。

看到绝对值，不要先展开。先问它表示哪两个点之间的距离。

## 6. 常见错误

- 把虚部 $b$ 和项 $bi$ 混淆。
- 求辐角时只看反正切，不看象限。
- 复数除法忘记乘共轭。
- 求根时只写一个根。
- 复数轨迹题过早展开，丢掉几何意义。

## 快速自查

- 我能不能把 $a+bi$ 在复平面上画出来？
- 我能不能从图像判断模和辐角的大致范围？
- 我能不能用极坐标形式解释乘法为什么是旋转加伸缩？
- 我能不能把 $|z-a|=r$ 翻译成几何图形？
