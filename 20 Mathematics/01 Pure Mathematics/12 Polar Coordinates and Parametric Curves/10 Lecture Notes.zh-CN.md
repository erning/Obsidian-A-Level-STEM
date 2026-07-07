---
title: Polar Coordinates and Parametric Curves 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/12 Polar Coordinates and Parametric Curves/00 Overview|Polar Coordinates and Parametric Curves]]"
status: active
tags:
  - mathematics/pure
  - lecture-notes
  - zh-CN
---

# Polar Coordinates and Parametric Curves 中文讲义

同一条曲线不一定只能用 $y=f(x)$ 表示。极坐标用“距离 + 角度”描述点；参数方程用一个参数同时描述 $x$ 和 $y$。换一种表示方式，曲线的形状、方向和面积有时会变得更清楚。

做题时先问：

- 这个问题更适合直角坐标、极坐标，还是参数方程？
- 给定的角度或参数范围是什么？
- 曲线是否重复描绘？
- 求斜率、面积或弧长时，变量到底是谁？

## 图示导读

![[assets/generated/mathematics/polar-coordinates-and-parametric-curves.svg]]

这张图用来快速理解“极坐标与参数曲线”：比较极坐标和参数式怎样描述曲线。

## 来源范围

- 9231 1.5 Polar coordinates。
- 9709 parametric differentiation content。
- Coursebook route：9231 Further Mathematics Coursebook polar coordinate sections；9709 Pure Mathematics 2 and 3 parametric differentiation sections。

## 学习范围

- 极坐标点、极坐标曲线和简单曲线识别。
- 极坐标与直角坐标之间的转换。
- 极坐标面积公式。
- 参数方程、曲线方向和消参。
- 参数曲线的斜率、切线、二阶导和弧长思想。

## 1. 极坐标

直角坐标用 $(x,y)$ 描述点。极坐标用

$$
(r,\theta)
$$

描述点，其中 $r$ 是到原点的距离，$\theta$ 是与正 $x$ 轴的夹角。

9231 中通常采用 $r\ge0$ 的约定。

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

画极坐标图像时，先看：

- 角度区间；
- 对称性；
- $r=0$ 的角度；
- $r$ 的最大值和最小值；
- 与极轴（initial line）的交点；
- 曲线是否重复描绘。

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

描图小例：

$$
r=2+2\cos\theta,\qquad 0\le\theta\le\pi.
$$

先代关键角度：

$$
r(0)=4,\qquad r\left(\frac{\pi}{2}\right)=2,\qquad r(\pi)=0.
$$

在这个区间内 $r\ge0$，所以曲线从极轴上距离 4 的点出发，经过 $(2,\pi/2)$，最后到达极点。完整曲线关于极轴对称；这个区间只描出上半部分。

## 3. 极坐标面积

极坐标下，从 $\theta=\alpha$ 到 $\theta=\beta$ 扫过的面积是

$$
A=\frac{1}{2}\int_\alpha^\beta r^2\,d\theta.
$$

这个公式来自扇形面积 $\frac{1}{2}r^2\theta$。积分就是把很多很小的扇形加起来。

面积题一定先画图。上下限不能凭感觉取，尤其是曲线在一个区间内重复描绘时，积分可能把面积算多。

例如

$$
r=2a\cos\theta
$$

对应

$$
x^2+y^2=2ax.
$$

在 $r\ge0$ 的约定下，一次完整描绘对应

$$
-\frac{\pi}{2}\le\theta\le\frac{\pi}{2},
$$

因为两端 $r=0$，中间 $r>0$。面积为

$$
A=\frac{1}{2}\int_{-\pi/2}^{\pi/2}4a^2\cos^2\theta\,d\theta
=\pi a^2.
$$

这也正好是半径为 $a$ 的圆面积。

## 4. 参数方程

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

## 5. 消参

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

## 6. 参数曲线的斜率

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

二阶导数是

$$
\frac{d^2y}{dx^2}
=\frac{\frac{d}{dt}\left(\frac{dy}{dx}\right)}{\frac{dx}{dt}}.
$$

它不是 $\frac{d^2y/dt^2}{d^2x/dt^2}$。

例如

$$
x=t^2,\qquad y=t^3.
$$

当 $t\ne0$ 时，

$$
\frac{dy}{dx}
=\frac{3t^2}{2t}
=\frac{3t}{2}.
$$

$t=1$ 时点为 $(1,1)$，切线斜率为 $\frac{3}{2}$，所以切线是

$$
y-1=\frac{3}{2}(x-1).
$$

法线斜率是负倒数 $-\frac{2}{3}$，所以法线是

$$
y-1=-\frac{2}{3}(x-1).
$$

如果 $\frac{dx}{dt}=0$ 而 $\frac{dy}{dt}\ne0$，不要硬除；这通常表示切线平行于 $y$ 轴。

## 7. 弧长和进一步内容

参数曲线的弧长可以用

$$
\frac{ds}{dt}
=\sqrt{\left(\frac{dx}{dt}\right)^2+\left(\frac{dy}{dt}\right)^2}.
$$

因此

$$
L=\int_{t_1}^{t_2}
\sqrt{\left(\frac{dx}{dt}\right)^2+\left(\frac{dy}{dt}\right)^2}\,dt.
$$

例如圆弧

$$
x=a\cos t,\qquad y=a\sin t,\qquad 0\le t\le\frac{\pi}{2}
$$

有

$$
\frac{ds}{dt}
=\sqrt{a^2\sin^2t+a^2\cos^2t}
=a,
$$

所以

$$
L=\int_0^{\pi/2}a\,dt=\frac{\pi a}{2}.
$$

后续进一步积分中，极坐标弧长常用

$$
L=\int_\alpha^\beta \sqrt{r^2+\left(\frac{dr}{d\theta}\right)^2}\,d\theta.
$$

原则一样：先确认变量、区间和几何意义，再积分。

## 做题顺序

### 极坐标描图

1. 写出角度区间。
2. 看对称性。
3. 解 $r=0$。
4. 找 $r$ 的最大值和最小值。
5. 代入关键角度，画出大致形状。

### 极坐标面积

1. 先画区域。
2. 从图中选 $\theta$ 的上下限。
3. 用 $A=\frac{1}{2}\int r^2\,d\theta$。
4. 检查是否重复描绘。

### 参数曲线

1. 看参数范围。
2. 代关键参数值找关键点。
3. 必要时消参，但保留范围限制。
4. 求斜率用 $\frac{dy/dt}{dx/dt}$。
5. 求切线时先求点，再求斜率。

## 常见错误

- 极坐标转直角坐标时忘记 $x=r\cos\theta$、$y=r\sin\theta$。
- 求 $\theta$ 时只看反正切，不看象限。
- 参数方程消参后忘记参数范围。
- 把 $\frac{dy}{dt}$ 当成 $\frac{dy}{dx}$。
- 画极坐标图时没有检查 $r=0$ 的点。
- 极坐标面积题重复描绘却没有分辨。
- 求二阶导数时把参数二阶导直接相除。
- 在 $\frac{dx}{dt}=0$ 的位置硬套除法，漏掉垂直切线。

## 快速自查

- 我能不能在极坐标和直角坐标之间转换？
- 我能不能识别简单的极坐标圆和直线？
- 我能不能用关键角度和 $r=0$ 画极坐标草图？
- 我能不能用 $\frac{1}{2}\int r^2\,d\theta$ 求极坐标面积？
- 我能不能从参数方程判断曲线运动方向？
- 我能不能正确求参数曲线的切线和法线？
- 我能不能用正确区间求参数曲线或极坐标曲线的弧长？

## 关联内容

- [[20 Mathematics/01 Pure Mathematics/02 Coordinate Geometry and Graphs/00 Overview|Coordinate Geometry and Graphs]]：极坐标和参数方程都是坐标几何中描述曲线的延伸。
- [[20 Mathematics/01 Pure Mathematics/05 Differentiation/00 Overview|Differentiation]]：参数曲线的切线、法线和二阶导都依赖微分。
