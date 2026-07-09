---
title: Rigid Bodies and Variable Forces Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Rigid Bodies and Variable Forces](00%20Overview.md)"
status: active
tags:
  - mathematics/mechanics
  - solutions
---

# Rigid Bodies and Variable Forces Key Practice Solutions

This note gives worked solutions for [Rigid Bodies and Variable Forces Key Practice Problems](30%20Key%20Practice%20Problems.md). Check moment points, centre-of-mass reference axes, integration variables, and initial conditions.

## A. Rigid Bodies and Centre of Mass

### Problem 1

Let the reactions at the left and right supports be $R_A$ and $R_B$. Moments
about the left end give

$$
6R_B=120(3)+180(2).
$$

Thus

$$
R_B=120\ \mathrm{N}.
$$

Vertical equilibrium gives

$$
R_A+R_B=300,
$$

so

$$
R_A=180\ \mathrm{N}.
$$

### Problem 2

Let the vertical support reaction at the far end be $R_B$ and the vertical
hinge reaction be $R_A$. Taking moments about the hinge,

$$
5R_B=100(2.5)+150(4).
$$

So

$$
R_B=170\ \mathrm{N}.
$$

Vertical equilibrium gives

$$
R_A+170=250,
$$

hence

$$
R_A=80\ \mathrm{N}.
$$

### Problem 3

The $4$ by $2$ rectangle has area $8$ and centre $(2,1)$. The $2$ by $3$
rectangle has area $6$ and centre $(1,3.5)$.

Therefore

$$
\bar x=\frac{8(2)+6(1)}{14}=\frac{11}{7},
$$

and

$$
\bar y=\frac{8(1)+6(3.5)}{14}=\frac{29}{14}.
$$

The centre of mass is

$$
\left(\frac{11}{7},\frac{29}{14}\right).
$$

### Problem 4

Treat the removed square as negative area. The full rectangle has area $24$
and centre $(3,2)$. The removed square has area $4$ and centre $(5,3)$.

The remaining area is $20$. Hence

$$
\bar x=\frac{24(3)-4(5)}{20}=\frac{52}{20}=2.6,
$$

and

$$
\bar y=\frac{24(2)-4(3)}{20}=\frac{36}{20}=1.8.
$$

The centre of mass is

$$
(2.6,1.8).
$$

### Problem 5

Sliding threshold:

$$
P=\mu R=0.30(400)=120\ \mathrm{N}.
$$

Toppling threshold about the lower edge:

$$
P(1.5)=400(0.5).
$$

Thus

$$
P=133\ \mathrm{N}\quad \text{to 3 s.f.}
$$

Since $120<133$, the block slides first.

## B. Work Done by a Variable Force

### Problem 6

$$
W=\int_0^3 5x^2\,dx
=\left[\frac{5x^3}{3}\right]_0^3=45\ \mathrm{J}.
$$

### Problem 7

$$
W=\int_0^5(20-2x)\,dx
=\left[20x-x^2\right]_0^5=75\ \mathrm{J}.
$$

### Problem 8

Initial kinetic energy is

$$
\frac12(3)(2^2)=6\ \mathrm{J}.
$$

Final kinetic energy is

$$
6+75=81\ \mathrm{J}.
$$

So

$$
\frac12(3)v^2=81,
$$

and

$$
v=7.35\ \mathrm{m\ s^{-1}}
$$

to 3 s.f.

### Problem 9

$$
W=\int_0^4(10+4x)\,dx
=\left[10x+2x^2\right]_0^4=72\ \mathrm{J}.
$$

### Problem 10

Work done from $x=1$ to $x=3$ is

$$
\int_1^3 6x\,dx
=\left[3x^2\right]_1^3=24\ \mathrm{J}.
$$

Initial kinetic energy is

$$
\frac12(2)(4^2)=16\ \mathrm{J}.
$$

Final kinetic energy is $40\ \mathrm{J}$, so

$$
\frac12(2)v^2=40.
$$

Thus

$$
v=6.32\ \mathrm{m\ s^{-1}}
$$

to 3 s.f.

## C. Variable-Force Differential Equations

### Problem 11

Newton's second law gives

$$
3\frac{dv}{dt}=6t.
$$

So

$$
\frac{dv}{dt}=2t.
$$

Integrating and using $v(0)=0$,

$$
v=t^2.
$$

At $t=4$,

$$
v=16\ \mathrm{m\ s^{-1}}.
$$

### Problem 12

$$
2\frac{dv}{dt}=12-4t,
$$

so

$$
\frac{dv}{dt}=6-2t.
$$

Integrate:

$$
v=6t-t^2+C.
$$

Using $v(0)=3$ gives

$$
v=3+6t-t^2.
$$

Therefore

$$
v(3)=3+18-9=12\ \mathrm{m\ s^{-1}}.
$$

### Problem 13

The resistance acts opposite to motion:

$$
\frac{dv}{dt}=-3v.
$$

Separate variables:

$$
\frac1v\,dv=-3\,dt.
$$

Using $v(0)=9$,

$$
v=9e^{-3t}.
$$

### Problem 14

Use $a=v\,dv/dx$:

$$
2v\frac{dv}{dx}=4x.
$$

So

$$
v\,dv=2x\,dx.
$$

Integrate from $x=0$, $v=1$ to $x=3$, $v=V$:

$$
\frac12(V^2-1)=9.
$$

Thus

$$
V=\sqrt{19}=4.36\ \mathrm{m\ s^{-1}}
$$

to 3 s.f.

### Problem 15

Use $a=v\,dv/dx$:

$$
v\frac{dv}{dx}=6-2x.
$$

Separate and integrate from $x=0$, $v=0$:

$$
\frac12v^2=6x-x^2.
$$

So

$$
v^2=12x-2x^2.
$$

The maximum speed occurs where the force changes sign, at $x=3$:

$$
v^2=36-18=18,
$$

so

$$
v=4.24\ \mathrm{m\ s^{-1}}
$$

to 3 s.f. The next rest position satisfies

$$
12x-2x^2=0.
$$

Hence

$$
x=6\ \mathrm{m}.
$$

## D. Mixed Review

### Problem 16

Sliding threshold:

$$
P=0.50(300)=150\ \mathrm{N}.
$$

Toppling threshold:

$$
P(1.0)=300(0.40).
$$

So

$$
P=120\ \mathrm{N}.
$$

Since $120<150$, the block topples first.

### Problem 17

The rod's mass acts at its midpoint, $2\ \mathrm{m}$ from the $1\ \mathrm{kg}$
end. The centre of mass is

$$
\bar x=\frac{1(0)+2(2)+3(4)}{1+2+3}.
$$

Thus

$$
\bar x=\frac{16}{6}=\frac83\ \mathrm{m}.
$$

### Problem 18

Newton's second law gives

$$
10\frac{dv}{dt}=-5v.
$$

So

$$
\frac1v\,dv=-\frac12\,dt.
$$

Using $v(0)=20$,

$$
v=20e^{-t/2}.
$$

For the speed to halve,

$$
10=20e^{-t/2}.
$$

Thus

$$
t=2\ln2=1.39\ \mathrm{s}
$$

to 3 s.f.

### Problem 19

Work done by the driving force is

$$
\int_0^{10}(30-2x)\,dx
=\left[30x-x^2\right]_0^{10}=200\ \mathrm{J}.
$$

Work done against resistance is

$$
5(10)=50\ \mathrm{J}.
$$

The gain in kinetic energy is $150\ \mathrm{J}$:

$$
\frac12(4)v^2=150.
$$

Therefore

$$
v=8.66\ \mathrm{m\ s^{-1}}
$$

to 3 s.f.

### Problem 20

Use $a=v\,dv/dx$:

$$
2v\frac{dv}{dx}=\frac{16}{x}.
$$

So

$$
v\,dv=8\frac{dx}{x}.
$$

Integrate from $x=1$, $v=3$ to $x=e$, $v=V$:

$$
\frac12(V^2-9)=8\ln e=8.
$$

Thus

$$
V^2=25,
$$

so

$$
V=5\ \mathrm{m\ s^{-1}}.
$$
