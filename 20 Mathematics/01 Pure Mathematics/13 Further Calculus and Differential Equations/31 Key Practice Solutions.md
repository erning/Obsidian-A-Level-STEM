---
title: Further Calculus and Differential Equations Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Further Calculus and Differential Equations](00%20Overview.md)"
status: active
tags:
  - mathematics/pure
  - solutions
---

# Further Calculus and Differential Equations Key Practice Solutions

This note gives worked solutions for [Further Calculus and Differential Equations Key Practice Problems](30%20Key%20Practice%20Problems.md). Use it to check method choice, constants, domains, and final substitution back into the equation where possible.

## A. Hyperbolic Functions and Further Calculus

### Problem 1

Using

$$
\cosh x=\frac{e^x+e^{-x}}{2},
\qquad
\sinh x=\frac{e^x-e^{-x}}{2},
$$

we get

$$
\cosh^2x-\sinh^2x
=\frac{(e^x+e^{-x})^2-(e^x-e^{-x})^2}{4}=1.
$$

### Problem 2

Solve

$$
\frac{e^x-e^{-x}}{2}=3.
$$

Let $u=e^x$, where $u>0$. Then

$$
u-\frac1u=6,
$$

so

$$
u^2-6u-1=0.
$$

Thus

$$
u=3+\sqrt{10},
$$

and

$$
x=\ln(3+\sqrt{10}).
$$

### Problem 3

Solve

$$
\frac{e^x+e^{-x}}{2}=\frac52.
$$

Let $u=e^x$. Then

$$
u+\frac1u=5,
$$

so

$$
u^2-5u+1=0.
$$

Hence

$$
u=\frac{5\pm\sqrt{21}}{2}.
$$

Since $x\ge0$, $u=e^x\ge1$, so

$$
x=\ln\left(\frac{5+\sqrt{21}}{2}\right).
$$

### Problem 4

Use the quotient rule:

$$
\frac{d}{dx}\tanh x
=\frac{d}{dx}\left(\frac{\sinh x}{\cosh x}\right)
=\frac{\cosh^2x-\sinh^2x}{\cosh^2x}.
$$

Using $\cosh^2x-\sinh^2x=1$,

$$
\frac{d}{dx}\tanh x=\frac{1}{\cosh^2x}=\operatorname{sech}^2x.
$$

### Problem 5

Use

$$
e^x=1+x+\frac{x^2}{2}+\frac{x^3}{6}+\cdots
$$

and

$$
\cos x=1-\frac{x^2}{2}+\cdots.
$$

Multiplying and keeping terms up to $x^3$ gives

$$
e^x\cos x=1+x-\frac{x^3}{3}+\cdots.
$$

### Problem 6

Use the standard form

$$
\int\frac{dx}{\sqrt{a^2-x^2}}=\sin^{-1}\frac{x}{a}+C.
$$

With $a=3$,

$$
\int \frac{dx}{\sqrt{9-x^2}}
=\sin^{-1}\frac{x}{3}+C.
$$

### Problem 7

The reduction formula gives

$$
I_4=\frac34 I_2.
$$

Also

$$
I_2=\frac12I_0.
$$

Since

$$
I_0=\int_0^{\pi/2}1\,dx=\frac{\pi}{2},
$$

we get

$$
I_2=\frac{\pi}{4}
$$

and

$$
I_4=\frac34\cdot\frac{\pi}{4}=\frac{3\pi}{16}.
$$

### Problem 8

For $y=x^2$,

$$
\frac{dy}{dx}=2x.
$$

Arc length is

$$
L=\int_0^1\sqrt{1+\left(\frac{dy}{dx}\right)^2}\,dx
=\int_0^1\sqrt{1+4x^2}\,dx.
$$

Using the standard integral,

$$
L=\left[\frac{x}{2}\sqrt{1+4x^2}
+\frac14\sinh^{-1}(2x)\right]_0^1.
$$

So

$$
L=\frac{\sqrt5}{2}+\frac14\sinh^{-1}2.
$$

## B. Separable and First-Order Linear Differential Equations

### Problem 9

Separate variables:

$$
\frac1y\,dy=x\,dx.
$$

Integrate:

$$
\ln|y|=\frac{x^2}{2}+C.
$$

So

$$
y=Ae^{x^2/2}.
$$

Using $y(0)=2$ gives $A=2$. Hence

$$
y=2e^{x^2/2}.
$$

### Problem 10

Separate variables:

$$
\frac{1}{y^2}\,dy=(1+x)\,dx.
$$

Integrate:

$$
-\frac1y=x+\frac{x^2}{2}+C.
$$

Use $y(0)=1$:

$$
-1=C.
$$

Thus

$$
\frac1y=1-x-\frac{x^2}{2},
$$

so

$$
y=\frac{1}{1-x-\frac{x^2}{2}}.
$$

### Problem 11

The equation is separable:

$$
\frac1M\,dM=-k\,dt.
$$

Integrating gives

$$
M=Ae^{-kt}.
$$

Using $M(0)=100$ gives $A=100$. Using $M(5)=60$,

$$
60=100e^{-5k}.
$$

So

$$
e^{-5k}=\frac35,
\qquad
k=\frac15\ln\frac53.
$$

Therefore

$$
M(t)=100e^{-(\ln(5/3))t/5}.
$$

### Problem 12

The integrating factor is

$$
e^{\int2\,dx}=e^{2x}.
$$

Multiplying by $e^{2x}$ gives

$$
\frac{d}{dx}(e^{2x}y)=e^x.
$$

Integrate:

$$
e^{2x}y=e^x+C.
$$

Therefore

$$
y=e^{-x}+Ce^{-2x}.
$$

### Problem 13

The equation is

$$
\frac{dy}{dx}-2y=x.
$$

The integrating factor is

$$
e^{\int -2\,dx}=e^{-2x}.
$$

Then

$$
\frac{d}{dx}(e^{-2x}y)=xe^{-2x}.
$$

Integrating by parts,

$$
\int xe^{-2x}\,dx=-\frac{x}{2}e^{-2x}-\frac14e^{-2x}+C.
$$

So

$$
e^{-2x}y=-\frac{x}{2}e^{-2x}-\frac14e^{-2x}+C.
$$

Therefore

$$
y=Ce^{2x}-\frac{x}{2}-\frac14.
$$

## C. Constant-Coefficient Differential Equations

### Problem 14

The auxiliary equation is

$$
m^2-5m+6=0.
$$

So

$$
m=2,\qquad m=3.
$$

Hence

$$
y=Ae^{2x}+Be^{3x}.
$$

### Problem 15

The auxiliary equation is

$$
m^2-4m+4=0,
$$

so $m=2$ is a repeated root. Therefore

$$
y=(A+Bx)e^{2x}.
$$

### Problem 16

The auxiliary equation is

$$
m^2+4=0.
$$

So

$$
m=\pm2i.
$$

Therefore

$$
y=A\cos2x+B\sin2x.
$$

### Problem 17

The complementary function comes from

$$
m^2-3m+2=0,
$$

so

$$
y_c=Ae^x+Be^{2x}.
$$

Try

$$
y_p=ke^{3x}.
$$

Substitution gives

$$
(9k-9k+2k)e^{3x}=3e^{3x}.
$$

Thus $k=\frac32$, and

$$
y=Ae^x+Be^{2x}+\frac32e^{3x}.
$$

### Problem 18

From question 14,

$$
y=Ae^{2x}+Be^{3x}.
$$

Using $y(0)=1$ gives

$$
A+B=1.
$$

Also

$$
y'=2Ae^{2x}+3Be^{3x}.
$$

Using $y'(0)=0$ gives

$$
2A+3B=0.
$$

Solving,

$$
A=3,\qquad B=-2.
$$

Therefore

$$
y=3e^{2x}-2e^{3x}.
$$

## D. Substitution and Interpretation

### Problem 19

Let

$$
y=ux.
$$

Then

$$
\frac{dy}{dx}=u+x\frac{du}{dx}.
$$

The differential equation becomes

$$
u+x\frac{du}{dx}=\frac{1+u}{1-u}.
$$

So

$$
x\frac{du}{dx}=\frac{1+u^2}{1-u}.
$$

Separate:

$$
\frac{1-u}{1+u^2}\,du=\frac1x\,dx.
$$

Integrate:

$$
\tan^{-1}u-\frac12\ln(1+u^2)=\ln|x|+C.
$$

Substitute $u=\frac{y}{x}$:

$$
\tan^{-1}\frac{y}{x}
-\frac12\ln\left(1+\frac{y^2}{x^2}\right)
=\ln|x|+C.
$$

### Problem 20

As $t\to\infty$,

$$
e^{-(\ln2)t/10}\to0.
$$

Therefore

$$
T\to20.
$$

The limiting value is the room temperature in the cooling model.
