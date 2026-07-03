---
title: Vectors 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/08 Vectors/00 Overview|Vectors]]"
status: draft
tags:
  - mathematics/pure
  - lecture-notes
  - zh-CN
---

# Vectors 中文讲义

这一章的主线是：向量同时表示大小和方向。它可以描述位移、速度、力，也可以描述空间里的直线。向量题不要只算分量，要一直记住它背后的几何意义。

1. 这个向量表示位移、方向，还是某条直线？
2. 题目需要的是长度、夹角、投影，还是交点？
3. 用分量计算是否比画几何图更清楚？
4. 答案的方向和大小是否符合图像直觉？

## 图示导读

![[assets/generated/mathematics/vectors.svg]]

这张图用来快速理解“向量”：用向量加法和参数直线看方向与位置。

## 学习范围

- 向量的分量、大小和单位向量。
- 向量加减、数乘和几何意义。
- 点积、夹角和垂直关系。
- 空间直线的向量方程和交点判断。

## 1. 向量是什么

向量有大小和方向。平面向量可以写成

$$
\mathbf{a}=\begin{pmatrix}x\\y\end{pmatrix},
$$

空间向量可以写成

$$
\mathbf{a}=\begin{pmatrix}x\\y\\z\end{pmatrix}.
$$

它的大小是

$$
|\mathbf{a}|=\sqrt{x^2+y^2}
$$

或空间中的

$$
|\mathbf{a}|=\sqrt{x^2+y^2+z^2}.
$$

单位向量是长度为 1 的向量。沿 $\mathbf{a}$ 方向的单位向量是

$$
\frac{\mathbf{a}}{|\mathbf{a}|}.
$$

## 2. 向量加减

向量加法按分量相加：

$$
\begin{pmatrix}a\\b\end{pmatrix}
+
\begin{pmatrix}c\\d\end{pmatrix}
=
\begin{pmatrix}a+c\\b+d\end{pmatrix}.
$$

几何上，向量加法可以用“首尾相接”理解。先走 $\mathbf{a}$，再走 $\mathbf{b}$，总位移是 $\mathbf{a}+\mathbf{b}$。

从点 $A$ 到点 $B$ 的向量是

$$
\overrightarrow{AB}=\mathbf{b}-\mathbf{a},
$$

其中 $\mathbf{a}$、$\mathbf{b}$ 分别是 $A$、$B$ 的位置向量。

## 3. 点积

点积定义为

$$
\mathbf{a}\cdot\mathbf{b}=|\mathbf{a}||\mathbf{b}|\cos\theta.
$$

用分量算，就是

$$
\mathbf{a}\cdot\mathbf{b}=a_1b_1+a_2b_2+a_3b_3.
$$

点积最常用于求夹角：

$$
\cos\theta=\frac{\mathbf{a}\cdot\mathbf{b}}{|\mathbf{a}||\mathbf{b}|}.
$$

如果

$$
\mathbf{a}\cdot\mathbf{b}=0,
$$

并且两个向量都不是零向量，那么它们垂直。

## 4. 直线的向量方程

空间中一条直线可以写成

$$
\mathbf{r}=\mathbf{a}+t\mathbf{d}.
$$

这里 $\mathbf{a}$ 是直线上的一个点的位置向量，$\mathbf{d}$ 是方向向量，$t$ 是参数。

这句话的意思是：从点 $\mathbf{a}$ 出发，沿着方向 $\mathbf{d}$ 走任意倍数。

如果两条直线方向向量成比例，它们平行。若还共点，就是同一条直线；若不共点，就是平行不同线。

## 5. 交点与共线

判断两条参数直线是否相交，可以把坐标分别相等，解参数。

例如

$$
\mathbf{r}=\mathbf{a}+s\mathbf{d},\qquad
\mathbf{r}=\mathbf{b}+t\mathbf{e}.
$$

把三个分量分别列方程。若同一组 $s,t$ 同时满足所有分量，直线相交；若没有公共解，就不相交。

三维里两条直线不相交也不平行时，叫异面直线。不要把“没有交点”自动理解成“平行”。

## 6. 常见错误

- 把位置向量和位移向量混在一起。
- 求单位向量时忘记除以向量长度。
- 用点积求角度后没有判断角的范围。
- 判断空间直线相交时只检查两个分量，忘记第三个分量。
- 把三维里的不相交直线都当成平行线。

## 快速自查

- 我能不能从两个点写出位移向量？
- 我能不能用点积判断垂直和求夹角？
- 我能不能解释 $\mathbf{r}=\mathbf{a}+t\mathbf{d}$ 中每个符号的意义？
- 我能不能判断两条空间直线是相交、平行还是异面？
