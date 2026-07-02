---
title: 数学工具与公式表
subject: Mathematics
syllabus:
  - 9709
  - 9231
status: draft
tags:
  - mathematics/reference
---

# 数学工具与公式表

数学公式不是要背的墙纸，而是压缩后的结构。每条公式都要知道它来自什么定义、解决什么问题、需要什么条件，以及能用什么方式检查。

## 公式卡片

每条公式建议写成这种格式：

```markdown
## Formula

- Object:
- Relationship:
- Conditions:
- Graph or geometric meaning:
- Typical use:
- Check:
- Common mistakes:
```

## 常用检查

- **代回检查**：解方程后代回原式。
- **定义域检查**：logarithm、root、fraction、inverse function 都先看定义域。
- **图像检查**：根、极值、渐近线、面积和概率都能在图像上看出大致范围。
- **极端情况检查**：参数趋近 0、1、无穷大或边界值时，结果是否合理。
- **单位检查**：Mechanics 中每个量都带单位。
- **概率检查**：概率在 0 到 1 之间，density 下的总面积为 1。

## 核心工具

### Algebra

- Completing the square：把 quadratic 写成顶点形式。
- Factor theorem：用根和因式连接 polynomial。
- Partial fractions：把 rational function 拆成可积分或可展开的形式。
- Modulus：表示距离，解题时常分区间讨论。

### Functions and Graphs

- Composite function：`fg(x) = f(g(x))`
- Inverse function：交换输入输出，图像关于 `y = x` 对称。
- Transformations：平移、伸缩、反射都应能从表达式读出。
- Asymptotes：vertical、horizontal、oblique asymptotes 说明函数边界行为。

### Calculus

- Derivative：局部变化率和 tangent gradient。
- Integral：累积量、面积和反导数。
- Chain rule：复合结构的求导。
- Product/quotient rules：乘积和商的求导。
- Integration by substitution：变量替换，把复杂结构还原成已知积分。
- Integration by parts：来自 product rule，适合乘积积分。

### Vectors and Matrices

- Dot product：长度、夹角、投影。
- Cross product：垂直方向、面积、法向量。
- Matrix multiplication：复合线性变换。
- Determinant：面积/体积缩放和 invertibility。
- Eigenvectors：在线性变换后方向不变的向量。

### Probability and Statistics

- Expectation：长期平均或分布中心。
- Variance：离散程度。
- Standardisation：把 normal variable 转成 standard normal。
- Confidence interval：用样本估计总体参数的不确定范围。
- Hypothesis test：用数据判断一个假设是否与观察冲突。
- PGF：用函数编码 discrete distribution。

## 和 Physics 的连接

- Differentiation：velocity、acceleration、rate of change。
- Integration：displacement、work、charge、probability。
- Exponential functions：decay、capacitor discharge、cooling model。
- Vectors：force components、fields、relative motion。
- Differential equations：growth/decay、SHM、variable-force motion。
- Statistics：实验误差、数据判断和模型拟合。
