---
title: Complex Numbers 中文讲义
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/09 Complex Numbers/00 Overview|Complex Numbers]]"
status: active
tags:
  - mathematics/pure
  - lecture-notes
  - zh-CN
---

# Complex Numbers 中文讲义

复数把实数轴扩展成复平面。它既是代数对象，也是几何对象。代数形式 $x+iy$ 适合加减、比较实部虚部和解方程；模辐角形式、指数形式适合乘除、幂、根和旋转。

复数题先问：应该用哪种形式？

- 加减、共轭、实部虚部：用 Cartesian form；
- 乘除、幂、根：用 polar/exponential form；
- 模、辐角、轨迹：先画 Argand diagram。

## 图示导读

![[assets/generated/mathematics/complex-numbers.svg]]

这张图用来快速理解“复数”：在复平面上看模和辐角。

## 来源范围

- 9709 3.9 Complex numbers。
- 9231 2.5 Complex numbers。
- Coursebook route：9709 Pure Mathematics 2 and 3 Chapter 11；9231 Further Mathematics complex numbers content。

## 学习范围

- 复数的代数形式、共轭、模和辐角。
- 复平面上的几何解释。
- 极坐标形式、乘除法、幂和根。
- 复数方程和简单轨迹。
- 9231 中的 de Moivre's theorem、单位根和多角公式应用。

## 1. 复数的基本形式

复数写成

$$
z=a+bi,
$$

其中 $a$ 是实部，$b$ 是虚部，$i^2=-1$。

复数可以看成复平面上的点 $(a,b)$。横轴是实轴，纵轴是虚轴。

记号上，

$$
\operatorname{Re}z=a,\qquad \operatorname{Im}z=b.
$$

注意 $\operatorname{Im}z$ 是 $b$，不是 $bi$。

共轭复数是

$$
z^*=a-bi.
$$

一个重要关系是

$$
zz^*=a^2+b^2.
$$

除法时通常乘共轭：

$$
\frac{1}{3+2i}
=\frac{3-2i}{(3+2i)(3-2i)}
=\frac{3-2i}{13}.
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

几何上，乘以 $re^{i\theta}$ 就是先把长度乘以 $r$，再旋转 $\theta$。

## 4. 实系数多项式方程和共轭根

如果一个多项式方程的系数都是实数，那么非实复根成共轭对出现。比如 $2+3i$ 是根，那么 $2-3i$ 也是根。

这在解三次、四次方程时很有用。若根是 $2\pm3i$，对应的二次因式是

$$
(x-(2+3i))(x-(2-3i))
=((x-2)-3i)((x-2)+3i)
=(x-2)^2+9.
$$

求复数平方根时，可以设

$$
(a+bi)^2=x+iy,
$$

然后比较实部和虚部。平方根通常有两个。

## 5. 幂、de Moivre 和根

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

$n$ 次单位根是

$$
z^n=1
$$

的所有根。它们都在单位圆上，角度为

$$
\frac{2k\pi}{n},\qquad k=0,1,\ldots,n-1.
$$

9231 中，de Moivre's theorem 还可以用来推多角公式、把 $\sin^n\theta$ 或 $\cos^n\theta$ 改写成多角项，以及求三角级数和。

## 6. 复数轨迹

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

再如

$$
\arg(z-a)=\alpha
$$

表示从固定点 $a$ 指向 $z$ 的射线与正实轴夹角为 $\alpha$。

看到绝对值或辐角，不要先展开。先问它表示距离还是方向。

## 做题顺序

### 选择形式

- 加减、比较实部虚部、用共轭除法：用 $x+iy$。
- 乘除、幂、根：用 $re^{i\theta}$ 或 $r(\cos\theta+i\sin\theta)$。
- 模、辐角、轨迹：先画 Argand diagram。

### 求根

1. 先把目标复数写成指数形式。
2. 把辐角写成 $\theta+2k\pi$。
3. 模开 $n$ 次方，辐角除以 $n$。
4. 列出 $k=0,1,\ldots,n-1$。
5. 画图检查根是否在圆上等间隔分布。

### 轨迹

1. 把 $|z-a|$ 翻译成到固定点的距离。
2. 把 $\arg(z-a)$ 翻译成从固定点出发的方向。
3. 先画图，再决定是否需要代数化。
4. 不等式表示圆内外、半平面或角域，要注意边界是否包含。
5. 多个轨迹同时出现时，先找图像交点。

## 常见错误

- 把虚部 $b$ 和项 $bi$ 混淆。
- 求辐角时只看反正切，不看象限。
- 复数除法忘记乘共轭。
- 求根时只写一个根。
- 复数轨迹题过早展开，丢掉几何意义。
- 有实系数多项式时忘记非实根成共轭对。
- 模辐角形式里度数和弧度混用。
- $\arg(z-a)$ 里的固定点看错。

## 快速自查

- 我能不能把 $a+bi$ 在复平面上画出来？
- 我能不能从图像判断模和辐角的大致范围？
- 我能不能用极坐标形式解释乘法为什么是旋转加伸缩？
- 我能不能把 $|z-a|=r$ 翻译成几何图形？
- 我能不能找全 $n$ 次根？
- 我能不能说明 de Moivre's theorem 的用途？

## 关联内容

- [[20 Mathematics/01 Pure Mathematics/03 Trigonometry and Circular Measure/00 Overview|Trigonometry and Circular Measure]]：复数的极坐标形式和 de Moivre's theorem 依赖三角函数语言。
- [[20 Mathematics/01 Pure Mathematics/04 Sequences Series and Binomial Expansions/00 Overview|Sequences, Series and Binomial Expansions]]：幂、根和展开式会在复数恒等式与根的结构中继续出现。
