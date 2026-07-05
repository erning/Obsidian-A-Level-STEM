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

向量同时表示大小和方向。它可以描述位移、速度、力，也可以描述空间里的直线、平面、夹角和距离。向量题不要只算分量，要一直问：这个向量在几何上代表什么？

最容易混的几类向量是：

- 位置向量：从原点指向某个点；
- 位移向量：从一个点指向另一个点；
- 方向向量：说明一条直线沿哪个方向走；
- 法向量：垂直于某个平面。

## 图示导读

![[assets/generated/mathematics/vectors.svg]]

这张图用来快速理解“向量”：用向量加法和参数直线看方向与位置。

## 学习范围

- 向量的分量、大小和单位向量。
- 向量加减、数乘和几何意义。
- 数量积、夹角和垂直关系。
- 空间直线的向量方程和交点判断。
- 9231 中的向量积、平面方程、距离和角。

## 1. 向量记号、大小和单位向量

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

单位向量保留方向，把长度缩放成 1。

## 2. 位置向量和位移向量

如果点 $A$ 的位置向量是 $\mathbf a$，点 $B$ 的位置向量是 $\mathbf b$，那么从 $A$ 到 $B$ 的位移向量是

$$
\overrightarrow{AB}=\mathbf b-\mathbf a.
$$

这是本章最重要的基本操作。位置向量依赖原点；位移向量只关心从哪个点到哪个点。

中点的位置向量是

$$
\frac{1}{2}(\mathbf a+\mathbf b).
$$

向量加法的几何意义是“首尾相接”。先走 $\mathbf a$，再走 $\mathbf b$，总位移就是 $\mathbf a+\mathbf b$。在平行四边形问题里，这个图像特别有用。

## 3. 直线的向量方程

空间直线可以写成

$$
\mathbf r=\mathbf a+t\mathbf d.
$$

这里 $\mathbf a$ 是直线上某一点的位置向量，$\mathbf d$ 是方向向量，$t$ 是实参数。意思是：从点 $\mathbf a$ 出发，沿 $\mathbf d$ 方向走任意倍数。

如果直线经过位置向量为 $\mathbf a$ 和 $\mathbf b$ 的两个点，那么方向向量可以取

$$
\mathbf b-\mathbf a,
$$

所以直线方程可以写成

$$
\mathbf r=\mathbf a+t(\mathbf b-\mathbf a).
$$

判断两条直线关系时：

- 方向向量成比例：平行或重合；
- 方向向量不成比例：可能相交，也可能异面；
- 把分量分别相等，解参数，能同时满足所有分量才是相交。

三维里“不相交”不等于“平行”。不平行也不相交的两条直线叫异面直线。

## 4. 数量积

数量积定义为

$$
\mathbf{a}\cdot\mathbf{b}=|\mathbf{a}||\mathbf{b}|\cos\theta.
$$

用分量算，就是

$$
\mathbf{a}\cdot\mathbf{b}=a_1b_1+a_2b_2+a_3b_3.
$$

数量积最常用于求夹角：

$$
\cos\theta=\frac{\mathbf{a}\cdot\mathbf{b}}{|\mathbf{a}||\mathbf{b}|}.
$$

如果

$$
\mathbf{a}\cdot\mathbf{b}=0,
$$

并且两个向量都不是零向量，那么它们垂直。

数量积还可以求投影。$\mathbf a$ 在 $\mathbf b$ 方向上的标量投影是

$$
\frac{\mathbf a\cdot\mathbf b}{|\mathbf b|}.
$$

这类思想可以用来求点到直线的垂足、线与线的夹角等。

## 5. 进一步的空间向量

下面主要是 9231 的内容。

向量积 $\mathbf a\times\mathbf b$ 垂直于 $\mathbf a$ 和 $\mathbf b$，它的大小是

$$
|\mathbf a\times\mathbf b|=|\mathbf a||\mathbf b|\sin\theta.
$$

向量积常用于：

- 求平行四边形面积；
- 求平面的法向量；
- 处理三维最短距离问题。

平面可以写成法向量形式

$$
(\mathbf r-\mathbf a)\cdot\mathbf n=0,
$$

其中 $\mathbf a$ 是平面上一点的位置向量，$\mathbf n$ 是法向量。

也可以写成 Cartesian form：

$$
ax+by+cz=d,
$$

或者参数形式：

$$
\mathbf r=\mathbf a+s\mathbf u+t\mathbf v.
$$

这里 $\mathbf u$ 和 $\mathbf v$ 是平面内两个不平行方向。

线和平面的交点通常用代入法：把直线的 $\mathbf r=\mathbf a+t\mathbf d$ 代入平面方程，解参数 $t$。点到平面的距离、线面角、面面角，都要先找对法向量。

异面直线的最短距离沿着共同垂线方向。两个方向向量的向量积给出一个同时垂直于两条直线的方向。

## 做题套路

### 直线问题

1. 找直线上一点和方向向量。
2. 写 $\mathbf r=\mathbf a+t\mathbf d$。
3. 判断相交时，把各分量相等，解参数。
4. 三个分量都要检查。
5. 分类为相交、平行、重合或异面。

### 角度和垂直

1. 选出要比较的两个方向向量。
2. 用数量积。
3. 数量积为 0 表示垂直。
4. 求角度时先算 $\cos\theta$，再判断题目要锐角、钝角还是实际夹角。

### 平面问题

1. 判断题目给的是法向量，还是平面内两个方向向量。
2. 有法向量时用 $(\mathbf r-\mathbf a)\cdot\mathbf n=0$。
3. 有两个方向向量时可用参数式，或用向量积求法向量。
4. 求交点用代入。
5. 求角和距离时先找法向量。

## 常见错误

- 把位置向量和位移向量混在一起。
- 求单位向量时忘记除以向量长度。
- 用数量积求角度后没有判断角的范围。
- 判断空间直线相交时只检查两个分量，忘记第三个分量。
- 把三维里的不相交直线都当成平行线。
- 把方向向量误当成直线上的点。
- 平面题里没有分清方向向量和法向量。
- 需要向量积求法向量时只用了数量积。

## 快速自查

- 我能不能从两个点写出位移向量？
- 我能不能用数量积判断垂直和求夹角？
- 我能不能解释 $\mathbf{r}=\mathbf{a}+t\mathbf{d}$ 中每个符号的意义？
- 我能不能判断两条空间直线是相交、平行还是异面？
- 我能不能说明向量积和平面法向量的作用？
