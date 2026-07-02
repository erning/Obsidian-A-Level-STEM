---
title: 数学工具与公式表
subject: Physics
syllabus: 9702
status: draft
tags:
  - physics/9702
  - reference
---

# 数学工具与公式表

物理里的数学不是另一个负担，而是压缩和检验想法的语言。学公式时，不要只记结果；要知道它来自什么模型、用了什么近似、能从图像中读出什么。

## 必备数学工具

### 代数

- 改变公式主语。
- 解简单方程和二元一次联立方程。
- 处理平方、平方根、负指数和科学记数法。
- 用近似估算检查答案数量级。
- 用百分比表达变化和不确定度。

### 三角与矢量

- 用 $\sin$、$\cos$、$\tan$ 分解矢量。
- 用勾股定理求合量。
- 用正弦定理和余弦定理处理非直角三角形。
- 会在度和弧度之间转换。
- 在圆周运动和振动中优先使用弧度。

### 图像

- 斜率：变化率，常对应速度、加速度、电阻、场强斜率或衰变常量。
- 截距：初始值、常量项或系统误差。
- 面积：累积量，常对应位移、做功、能量或电荷。
- 切线：曲线某点瞬时变化率。
- 线性化：把复杂关系变成直线，方便判断模型是否成立。

### 指数与对数

- $e^{-t/RC}$：电容器放电。
- $e^{-\lambda t}$：放射性衰变。
- $\ln y$ 对 $x$：检验指数关系。
- $\log y$ 对 $\log x$：检验幂律关系。

## 公式学习卡片

每条公式建议写成这种格式：

```markdown
## Formula

- Relationship:
- Meaning of symbols:
- Units:
- Assumptions:
- Graph connection:
- Common mistakes:
- One worked example:
```

## 常量

- $g = 9.81\,\mathrm{m\,s^{-2}}$
- $c = 3.00 \times 10^8\,\mathrm{m\,s^{-1}}$
- $e = 1.60 \times 10^{-19}\,\mathrm{C}$
- $1\,\mathrm{u} = 1.66 \times 10^{-27}\,\mathrm{kg}$
- $N_A = 6.02 \times 10^{23}\,\mathrm{mol^{-1}}$
- $R = 8.31\,\mathrm{J\,K^{-1}\,mol^{-1}}$
- $k = 1.38 \times 10^{-23}\,\mathrm{J\,K^{-1}}$
- $G = 6.67 \times 10^{-11}\,\mathrm{N\,m^2\,kg^{-2}}$
- $\varepsilon_0 = 8.85 \times 10^{-12}\,\mathrm{F\,m^{-1}}$
- $h = 6.63 \times 10^{-34}\,\mathrm{J\,s}$
- $\sigma = 5.67 \times 10^{-8}\,\mathrm{W\,m^{-2}\,K^{-4}}$

## 需要特别熟悉的关系

### 力学

- 匀加速度：$s = ut + \frac{1}{2}at^2$，$v^2 = u^2 + 2as$
- 牛顿第二定律：$F = ma$
- Momentum：$p = mv$
- Work：$W = Fs$
- 动能：$E_k = \frac{1}{2}mv^2$
- 近地引力势能：$\Delta E_p = mg\Delta h$
- Power：$P = \frac{W}{t}$，$P = Fv$

### 波与振动

- 波动方程：$v = f\lambda$
- Intensity：$I = \frac{P}{A}$
- 马吕斯定律（Malus's law）：$I = I_0\cos^2\theta$
- Double-slit：$\lambda = \frac{ax}{D}$
- 衍射光栅：$d\sin\theta = n\lambda$
- 简谐运动（SHM）：$a = -\omega^2x$

### 电磁学

- Charge flow：$Q = It$
- Potential difference：$V = \frac{W}{Q}$
- 欧姆定律：$V = IR$
- Resistivity：$R = \frac{\rho L}{A}$
- 电场：$F = qE$
- 匀强电场：$E = \frac{\Delta V}{\Delta d}$
- 库仑定律：$F = \frac{Q_1Q_2}{4\pi\varepsilon_0r^2}$
- Capacitance：$C = \frac{Q}{V}$
- 电容器能量：$W = \frac{1}{2}QV = \frac{1}{2}CV^2$
- 通电导线所受磁力：$F = BIL\sin\theta$
- 运动电荷所受磁力：$F = BQv\sin\theta$
- 法拉第电磁感应定律和楞次定律：变化的磁通量会感生反抗该变化的电动势.

### 热、量子与宇宙

- Ideal gas：$pV = nRT = NkT$
- Kinetic theory：$pV = \frac{1}{3}Nm\langle c^2 \rangle$
- 热力学第一定律：$\Delta U = q + W$
- 光子能量：$E = hf$
- 德布罗意波长：$\lambda = \frac{h}{p}$
- 质能：$E = mc^2$
- 放射性衰变：$x = x_0e^{-\lambda t}$
- 平方反比光度：$F = \frac{L}{4\pi d^2}$
- Stefan-Boltzmann：$L = 4\pi\sigma r^2T^4$
- 哈勃定律：$v \approx H_0d$

## 使用原则

- 先理解模型，再背公式。
- 先检查单位，再相信数值。
- 先画图像，再做复杂代数。
- 先估算数量级，再按计算器。
- 先问适用条件，再迁移到新情境。
