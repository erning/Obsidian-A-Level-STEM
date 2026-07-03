---
title: Trigonometry and Circular Measure 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/03 Trigonometry and Circular Measure/00 Overview|Trigonometry and Circular Measure]]"
status: draft
tags:
  - mathematics/pure
  - lecture-notes
  - zh-CN
---

# Trigonometry and Circular Measure 中文讲义

这一章的主线是：先把角从“多少度”改成“在单位圆上走了多长”，再用单位圆理解正弦、余弦和正切。三角函数不要只背公式。你要能在单位圆、图像、恒等式和方程之间来回切换。

1. 这个角最好用度数还是弧度表示？
2. 题目问的是边长、面积、图像、恒等式，还是方程的解？
3. 能不能用单位圆判断符号和周期？
4. 最后答案有没有落在题目给定的区间里？

## 图示导读

![[assets/generated/mathematics/trigonometry-and-circular-measure.svg]]

这张图用来快速理解“三角函数与弧度制”：把单位圆上的坐标和正弦图像连起来。

## 学习范围

- 弧度制、弧长和扇形面积。
- 正弦、余弦、正切的图像、周期和对称性。
- 基本三角恒等式和简单三角方程。
- 三角函数在坐标几何、微积分和简谐运动中的后续用法。

## 1. 弧度制

弧度制把角和圆上的弧长直接连起来。半径为 $r$、圆心角为 $\theta$ 的弧长是

$$
s=r\theta.
$$

这里的 $\theta$ 必须用弧度。一个完整圆周的弧长是 $2\pi r$，所以一整圈的角是

$$
2\pi \text{ radians}.
$$

因此

$$
180^\circ=\pi,\qquad 90^\circ=\frac{\pi}{2},\qquad 360^\circ=2\pi.
$$

扇形面积是

$$
A=\frac{1}{2}r^2\theta.
$$

做弧长和面积题时，第一步先检查角的单位。题目如果给的是度数，要先换成弧度再代公式。

## 2. 单位圆

单位圆半径为 1。角 $\theta$ 对应圆上的点

$$
(\cos\theta,\sin\theta).
$$

这句话很重要：余弦是横坐标，正弦是纵坐标。正切是

$$
\tan\theta=\frac{\sin\theta}{\cos\theta},
$$

只要 $\cos\theta\ne 0$。

单位圆最有用的地方是判断符号。第一象限正弦、余弦、正切都为正；第二象限正弦为正，余弦和正切为负；第三象限正切为正；第四象限余弦为正。

## 3. 基本恒等式

从单位圆可以直接得到

$$
\sin^2\theta+\cos^2\theta=1.
$$

这是最常用的三角恒等式。把它除以 $\cos^2\theta$，得到

$$
1+\tan^2\theta=\sec^2\theta.
$$

解题时不要为了变形而变形。看到 $\sin^2\theta+\cos^2\theta$，优先想到 1；看到 $\tan\theta$，优先想到 $\frac{\sin\theta}{\cos\theta}$。目标是把式子变成同一种函数，或者变成可以因式分解的形式。

## 4. 三角函数图像

$y=\sin x$ 和 $y=\cos x$ 的周期都是 $2\pi$，值域都是

$$
-1\le y\le 1.
$$

$y=\tan x$ 的周期是 $\pi$，在

$$
x=\frac{\pi}{2}+k\pi
$$

处没有定义。这里 $k$ 是整数。

图像题最容易漏的是定义域。比如只在 $0\le x\le 2\pi$ 上画图，就不能把其他周期的交点也写进答案。

## 5. 解三角方程

解三角方程的顺序可以这样做：

1. 先把方程化成基本形式，比如 $\sin x=a$、$\cos x=a$ 或 $\tan x=a$。
2. 找参考角。
3. 用单位圆判断哪些象限符合符号。
4. 写出题目指定区间内的所有解。

例如在 $0\le x<2\pi$ 内解

$$
\sin x=\frac{1}{2}.
$$

参考角是 $\frac{\pi}{6}$。正弦为正在第一、第二象限，所以

$$
x=\frac{\pi}{6},\frac{5\pi}{6}.
$$

不要只写第一个解。三角方程的主要陷阱就是周期和区间。

## 6. 常见错误

- 用弧长公式时忘记把度数换成弧度。
- 把 $\sin^{-1}x$ 当作 $\frac{1}{\sin x}$。反三角函数和倒数不是一回事。
- 解三角方程只写计算器给出的一个角。
- 图像平移后忘记周期、定义域和值域的变化。
- 忘记 $\tan x$ 在某些点没有定义。

## 快速自查

- 我能不能解释为什么 $s=r\theta$ 要求 $\theta$ 用弧度？
- 我能不能用单位圆判断三角函数的符号？
- 我能不能从图像说出周期、最大值和最小值？
- 我能不能在指定区间内找全三角方程的解？
