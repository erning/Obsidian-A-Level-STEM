---
title: Matrices and Transformations 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/10 Matrices and Transformations/00 Overview|Matrices and Transformations]]"
status: draft
tags:
  - mathematics/pure
  - lecture-notes
  - zh-CN
---

# Matrices and Transformations 中文讲义

这一章的主线是：矩阵不只是数字排成的表，它可以表示线性变换。一个 $2\times 2$ 矩阵作用在平面向量上，会把整个平面拉伸、旋转、反射或剪切。

1. 这个矩阵是在做计算，还是在表示几何变换？
2. 矩阵相乘的顺序是否和变换顺序一致？
3. 行列式是否为 0？这个变换能不能反过来？
4. 图形上的关键点变到哪里去了？

## 图示导读

![[assets/generated/mathematics/matrices-and-transformations.svg]]

这张图用来快速理解“矩阵与变换”：观察矩阵怎样把一个网格变形。

## 学习范围

- 矩阵加减、数乘和乘法。
- 单位矩阵、逆矩阵和行列式。
- 二维线性变换：反射、旋转、伸缩、剪切。
- 复合变换和变换矩阵的构造。

## 1. 矩阵乘向量

一个 $2\times 2$ 矩阵

$$
A=\begin{pmatrix}a&b\\c&d\end{pmatrix}
$$

作用在向量

$$
\begin{pmatrix}x\\y\end{pmatrix}
$$

上，得到

$$
A\begin{pmatrix}x\\y\end{pmatrix}
=
\begin{pmatrix}ax+by\\cx+dy\end{pmatrix}.
$$

几何上，这表示点 $(x,y)$ 被送到另一个点。整个图形的变换，就是每个点都这样变过去。

## 2. 矩阵乘法顺序

矩阵乘法一般不能交换：

$$
AB\ne BA.
$$

如果先做 $B$，再做 $A$，总变换是

$$
AB.
$$

这是因为向量在右边：

$$
A(B\mathbf{x})=(AB)\mathbf{x}.
$$

做复合变换题时，顺序非常重要。文字里说“先反射，再旋转”，写矩阵时通常是旋转矩阵乘反射矩阵。

## 3. 单位矩阵和逆矩阵

单位矩阵是

$$
I=\begin{pmatrix}1&0\\0&1\end{pmatrix}.
$$

它不改变向量。

如果矩阵 $A$ 有逆矩阵 $A^{-1}$，那么

$$
AA^{-1}=A^{-1}A=I.
$$

对

$$
A=\begin{pmatrix}a&b\\c&d\end{pmatrix},
$$

行列式是

$$
\det A=ad-bc.
$$

如果 $\det A\ne 0$，逆矩阵是

$$
A^{-1}=\frac{1}{ad-bc}\begin{pmatrix}d&-b\\-c&a\end{pmatrix}.
$$

如果 $\det A=0$，变换把平面压扁到一条线或一个点，不能唯一反过来。

## 4. 常见二维变换

关于 $x$ 轴反射：

$$
\begin{pmatrix}1&0\\0&-1\end{pmatrix}.
$$

关于 $y$ 轴反射：

$$
\begin{pmatrix}-1&0\\0&1\end{pmatrix}.
$$

逆时针旋转 $\theta$：

$$
\begin{pmatrix}\cos\theta&-\sin\theta\\
\sin\theta&\cos\theta\end{pmatrix}.
$$

在 $x$ 方向放大 $k$ 倍：

$$
\begin{pmatrix}k&0\\0&1\end{pmatrix}.
$$

记矩阵时不要死背。看它把基向量

$$
\begin{pmatrix}1\\0\end{pmatrix},\quad
\begin{pmatrix}0\\1\end{pmatrix}
$$

送到哪里，矩阵的两列就是这两个新向量。

## 5. 用关键点检查图形变换

变换多边形时，只需要变换顶点，再连线。比如三角形的三个顶点变完，整个三角形就确定了。

如果结果看起来奇怪，检查两个基向量的去向。很多矩阵错误其实是把列写成了行，或把变换顺序写反。

## 6. 常见错误

- 把 $AB$ 和 $BA$ 当成一样。
- 求逆矩阵时忘记除以行列式。
- 行列式为 0 时还强行求逆。
- 复合变换顺序写反。
- 构造变换矩阵时把基向量的像写成行，而不是列。

## 快速自查

- 我能不能解释矩阵的两列表示什么？
- 我能不能判断一个矩阵是否可逆？
- 我能不能根据文字描述写出复合变换矩阵？
- 我能不能用关键点检查图形变换是否合理？
