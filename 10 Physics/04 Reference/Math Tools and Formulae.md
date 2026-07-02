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
- 用 Pythagoras theorem 求合量。
- 用 sine rule 和 cosine rule 处理非直角三角形。
- 会在 degree 和 radian 之间转换。
- 在 circular motion 和 oscillations 中优先使用 radian。

### 图像

- 斜率：变化率，常对应速度、加速度、resistance、field gradient 或 decay constant。
- 截距：初始值、常量项或系统误差。
- 面积：累积量，常对应 displacement、work done、energy 或 charge。
- 切线：曲线某点瞬时变化率。
- 线性化：把复杂关系变成直线，方便判断模型是否成立。

### 指数与对数

- $e^{-t/RC}$：capacitor discharge。
- $e^{-\lambda t}$：radioactive decay。
- $\ln y$ against $x$：检验指数关系。
- $\log y$ against $\log x$：检验幂律关系。

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

- Uniform acceleration：$s = ut + \frac{1}{2}at^2$，$v^2 = u^2 + 2as$
- Newton's second law：$F = ma$
- Momentum：$p = mv$
- Work：$W = Fs$
- Kinetic energy：$E_k = \frac{1}{2}mv^2$
- Gravitational potential energy near Earth：$\Delta E_p = mg\Delta h$
- Power：$P = \frac{W}{t}$，$P = Fv$

### 波与振动

- Wave equation：$v = f\lambda$
- Intensity：$I = \frac{P}{A}$
- Malus's law：$I = I_0\cos^2\theta$
- Double-slit：$\lambda = \frac{ax}{D}$
- Diffraction grating：$d\sin\theta = n\lambda$
- SHM：$a = -\omega^2x$

### 电磁学

- Charge flow：$Q = It$
- Potential difference：$V = \frac{W}{Q}$
- Ohm's law：$V = IR$
- Resistivity：$R = \frac{\rho L}{A}$
- Electric field：$F = qE$
- Uniform field：$E = \frac{\Delta V}{\Delta d}$
- Coulomb's law：$F = \frac{Q_1Q_2}{4\pi\varepsilon_0r^2}$
- Capacitance：$C = \frac{Q}{V}$
- Capacitor energy：$W = \frac{1}{2}QV = \frac{1}{2}CV^2$
- Magnetic force on wire：$F = BIL\sin\theta$
- Magnetic force on charge：$F = BQv\sin\theta$
- Faraday's law and Lenz's law：changing flux induces e.m.f. opposing the change.

### 热、量子与宇宙

- Ideal gas：$pV = nRT = NkT$
- Kinetic theory：$pV = \frac{1}{3}Nm\langle c^2 \rangle$
- First law：$\Delta U = q + W$
- Photon energy：$E = hf$
- de Broglie wavelength：$\lambda = \frac{h}{p}$
- Mass-energy：$E = mc^2$
- Radioactive decay：$x = x_0e^{-\lambda t}$
- Inverse square luminosity：$F = \frac{L}{4\pi d^2}$
- Stefan-Boltzmann：$L = 4\pi\sigma r^2T^4$
- Hubble's law：$v \approx H_0d$

## 使用原则

- 先理解模型，再背公式。
- 先检查单位，再相信数值。
- 先画图像，再做复杂代数。
- 先估算数量级，再按计算器。
- 先问适用条件，再迁移到新情境。
