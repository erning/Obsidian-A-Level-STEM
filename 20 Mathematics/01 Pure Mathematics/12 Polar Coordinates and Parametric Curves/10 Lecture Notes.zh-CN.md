---
title: Polar Coordinates and Parametric Curves 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/12 Polar Coordinates and Parametric Curves/00 Overview|Polar Coordinates and Parametric Curves]]"
status: draft
tags:
  - mathematics/pure
  - lecture-notes
  - zh-CN
---

# Polar Coordinates and Parametric Curves 中文讲义

这一章的主线是：同一条曲线不一定只能用 $y=f(x)$ 表示。极坐标用距离和角度描述点，参数方程用一个中间变量描述运动轨迹。换一种表示方式，很多曲线会变简单。

1. 曲线更适合用 $x,y$，还是用 $r,\theta$ 或参数 $t$？
2. 参数增加时，点沿曲线往哪个方向走？
3. 求斜率时应该用 $\frac{dy/dt}{dx/dt}$ 吗？
4. 极坐标曲线有没有重复描绘或特殊角度？

## 图示导读

![[assets/generated/mathematics/polar-coordinates-and-parametric-curves.svg]]

这张图用来快速理解“极坐标与参数曲线”：比较极坐标和参数式怎样描述曲线。

## 学习范围

- 极坐标点、极坐标曲线和简单曲线识别。
- 极坐标与直角坐标之间的转换。
- 参数方程、曲线方向和消参。
- 参数曲线的斜率、切线和面积思想。

## 1. 极坐标

直角坐标用 $(x,y)$ 描述点。极坐标用

$$
(r,\theta)
$$

描述点，其中 $r$ 是到原点的距离，$\theta$ 是与正 $x$ 轴的夹角。

两种坐标的关系是

$$
x=r\cos\theta,\qquad y=r\sin\theta.
$$

反过来，

$$
r^2=x^2+y^2,\qquad \tan\theta=\frac{y}{x}.
$$

求 $\theta$ 时仍然要看象限。

## 2. 极坐标曲线

极坐标曲线常写成

$$
r=f(\theta).
$$

这表示角度变时，点到原点的距离也跟着变。

例如

$$
r=a
$$

是以原点为圆心、半径为 $a$ 的圆。

$$
r=a\cos\theta
$$

可以化成

$$
r^2=ar\cos\theta,
$$

也就是

$$
x^2+y^2=ax.
$$

这是一个圆。

画极坐标图像时，先看特殊角度：$\theta=0,\frac{\pi}{2},\pi,\frac{3\pi}{2}$。再看 $r$ 什么时候为 0，什么时候最大或最小。

## 3. 参数方程

参数方程用一个参数 $t$ 同时描述 $x$ 和 $y$：

$$
x=x(t),\qquad y=y(t).
$$

参数 $t$ 可以理解成时间。随着 $t$ 变化，点在平面上移动，留下曲线。

例如

$$
x=\cos t,\qquad y=\sin t
$$

描述单位圆，因为

$$
x^2+y^2=\cos^2t+\sin^2t=1.
$$

## 4. 消参

消参就是把参数 $t$ 去掉，得到 $x$ 和 $y$ 的关系。

例如

$$
x=t+1,\qquad y=t^2.
$$

由 $x=t+1$ 得

$$
t=x-1.
$$

所以

$$
y=(x-1)^2.
$$

但消参以后要记得参数范围。若原来 $t\ge 0$，那么这里 $x\ge 1$。

## 5. 参数曲线的斜率

若

$$
x=x(t),\qquad y=y(t),
$$

则

$$
\frac{dy}{dx}=\frac{\frac{dy}{dt}}{\frac{dx}{dt}},
$$

前提是 $\frac{dx}{dt}\ne 0$。

求切线时先求参数对应的点，再求 $\frac{dy}{dx}$。不要把 $\frac{dy}{dt}$ 直接当斜率。

## 6. 常见错误

- 极坐标转直角坐标时忘记 $x=r\cos\theta$、$y=r\sin\theta$。
- 求 $\theta$ 时只看反正切，不看象限。
- 参数方程消参后忘记参数范围。
- 把 $\frac{dy}{dt}$ 当成 $\frac{dy}{dx}$。
- 画极坐标图时没有检查 $r=0$ 的点。

## 快速自查

- 我能不能在极坐标和直角坐标之间转换？
- 我能不能识别简单的极坐标圆和直线？
- 我能不能从参数方程判断曲线运动方向？
- 我能不能正确求参数曲线的切线斜率？
