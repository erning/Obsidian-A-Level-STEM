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

- 用 `sin`、`cos`、`tan` 分解矢量。
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

- `e^(-t/RC)`：capacitor discharge。
- `e^(-lambda t)`：radioactive decay。
- `ln y` against `x`：检验指数关系。
- `log y` against `log x`：检验幂律关系。

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

- `g = 9.81 m s^-2`
- `c = 3.00 x 10^8 m s^-1`
- `e = 1.60 x 10^-19 C`
- `1 u = 1.66 x 10^-27 kg`
- `N_A = 6.02 x 10^23 mol^-1`
- `R = 8.31 J K^-1 mol^-1`
- `k = 1.38 x 10^-23 J K^-1`
- `G = 6.67 x 10^-11 N m^2 kg^-2`
- `epsilon_0 = 8.85 x 10^-12 F m^-1`
- `h = 6.63 x 10^-34 J s`
- `sigma = 5.67 x 10^-8 W m^-2 K^-4`

## 需要特别熟悉的关系

### 力学

- Uniform acceleration：`s = ut + 1/2 at^2`，`v^2 = u^2 + 2as`
- Newton's second law：`F = ma`
- Momentum：`p = mv`
- Work：`W = Fs`
- Kinetic energy：`E_k = 1/2 mv^2`
- Gravitational potential energy near Earth：`Delta E_p = mg Delta h`
- Power：`P = W/t`，`P = Fv`

### 波与振动

- Wave equation：`v = f lambda`
- Intensity：`I = P/A`
- Malus's law：`I = I_0 cos^2 theta`
- Double-slit：`lambda = ax/D`
- Diffraction grating：`d sin theta = n lambda`
- SHM：`a = -omega^2 x`

### 电磁学

- Charge flow：`Q = It`
- Potential difference：`V = W/Q`
- Ohm's law：`V = IR`
- Resistivity：`R = rho L/A`
- Electric field：`F = qE`
- Uniform field：`E = Delta V / Delta d`
- Coulomb's law：`F = Q_1 Q_2 / (4 pi epsilon_0 r^2)`
- Capacitance：`C = Q/V`
- Capacitor energy：`W = 1/2 QV = 1/2 CV^2`
- Magnetic force on wire：`F = BIL sin theta`
- Magnetic force on charge：`F = BQv sin theta`
- Faraday's law and Lenz's law：changing flux induces e.m.f. opposing the change.

### 热、量子与宇宙

- Ideal gas：`pV = nRT = NkT`
- Kinetic theory：`pV = 1/3 Nm<c^2>`
- First law：`Delta U = q + W`
- Photon energy：`E = hf`
- de Broglie wavelength：`lambda = h/p`
- Mass-energy：`E = mc^2`
- Radioactive decay：`x = x_0 e^(-lambda t)`
- Inverse square luminosity：`F = L / (4 pi d^2)`
- Stefan-Boltzmann：`L = 4 pi sigma r^2 T^4`
- Hubble's law：`v ≈ H_0 d`

## 使用原则

- 先理解模型，再背公式。
- 先检查单位，再相信数值。
- 先画图像，再做复杂代数。
- 先估算数量级，再按计算器。
- 先问适用条件，再迁移到新情境。

