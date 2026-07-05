---
title: Integration Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/01 Pure Mathematics/06 Integration/00 Overview|Integration]]"
status: active
tags:
  - mathematics/pure
  - solutions
---

# Integration Key Practice Solutions

Use these solutions to check method choice and algebra for [[20 Mathematics/01 Pure Mathematics/06 Integration/30 Key Practice Problems|Key Practice Problems]].

## A. Reverse Differentiation

1. Integrate term by term:

   $$
   \int (6x^2-4x+3)\,dx=2x^3-2x^2+3x+C.
   $$

2. Reverse the chain rule:

   $$
   \int (2x+1)^5\,dx=\frac{(2x+1)^6}{12}+C.
   $$

3. Divide by the coefficient of $x$ in the exponent:

   $$
   \int e^{3x-1}\,dx=\frac{1}{3}e^{3x-1}+C.
   $$

4. Use the logarithmic form:

   $$
   \int \frac{1}{4x+5}\,dx=\frac{1}{4}\ln|4x+5|+C.
   $$

5. Reverse the derivative of cosine:

   $$
   \int \sin(2x)\,dx=-\frac{1}{2}\cos(2x)+C.
   $$

6. Reverse the derivative of tangent:

   $$
   \int \sec^2(3x)\,dx=\frac{1}{3}\tan(3x)+C.
   $$

7. Integrate:

   $$
   y=x^2+3x+C.
   $$

   Use $(1,4)$:

   $$
   4=1+3+C,
   $$

   so $C=0$. The curve is

   $$
   y=x^2+3x.
   $$

## B. Definite Integrals, Areas, and Volumes

8. Use an antiderivative:

   $$
   \int_0^2(3x^2+1)\,dx
   =\left[x^3+x\right]_0^2=10.
   $$

9. The definite integral is

   $$
   \int_0^3(x^2-4x)\,dx
   =\left[\frac{x^3}{3}-2x^2\right]_0^3=-9.
   $$

   The curve is below the $x$-axis on $0<x<3$, so the geometric area is

   $$
   9.
   $$

10. Intersections satisfy

    $$
    4-x^2=x+2,
    $$

    so

    $$
    x=-2,\ 1.
    $$

    The area is

    $$
    \int_{-2}^{1}\left((4-x^2)-(x+2)\right)\,dx
    =\int_{-2}^{1}(2-x-x^2)\,dx.
    $$

    Hence

    $$
    \text{area}=\frac{9}{2}.
    $$

11. For rotation about the $x$-axis,

    $$
    V=\pi\int_0^2(x+1)^2\,dx.
    $$

    Therefore

    $$
    V=\pi\left[\frac{x^3}{3}+x^2+x\right]_0^2
    =\frac{26\pi}{3}.
    $$

12. Treat the integral as a limit:

    $$
    \int_1^\infty \frac{1}{x^2}\,dx
    =\lim_{b\to\infty}\left[-\frac{1}{x}\right]_1^b.
    $$

    This gives

    $$
    1.
    $$

13. Treat the endpoint $x=0$ as a limit:

    $$
    \int_0^1 \frac{1}{\sqrt{x}}\,dx
    =\lim_{a\to0^+}\left[2\sqrt{x}\right]_a^1=2.
    $$

## C. Integration Techniques

14. Let $u=x^2+1$, so $du=2x\,dx$. Then

    $$
    \int 2x(x^2+1)^5\,dx=\frac{(x^2+1)^6}{6}+C.
    $$

15. Let $u=x^2+1$, so $du=2x\,dx$. Change the limits:

    $$
    x=0\Rightarrow u=1,\qquad x=1\Rightarrow u=2.
    $$

    Hence

    $$
    \int_0^1 \frac{2x}{x^2+1}\,dx
    =\int_1^2\frac{1}{u}\,du=\ln2.
    $$

16. Use integration by parts with $u=x$ and $\frac{dv}{dx}=e^{2x}$:

    $$
    \int x e^{2x}\,dx
    =\frac{x}{2}e^{2x}-\frac{1}{4}e^{2x}+C.
    $$

17. Use integration by parts with $u=\ln x$ and $\frac{dv}{dx}=1$:

    $$
    \int \ln x\,dx=x\ln x-x+C.
    $$

18. Use integration by parts with $u=x$ and $\frac{dv}{dx}=\sin x$:

    $$
    \int_0^{\frac{\pi}{2}}x\sin x\,dx
    =\left[-x\cos x\right]_0^{\frac{\pi}{2}}
    +\int_0^{\frac{\pi}{2}}\cos x\,dx.
    $$

    Therefore

    $$
    \int_0^{\frac{\pi}{2}}x\sin x\,dx=1.
    $$

19. Decompose:

    $$
    \frac{3x+5}{(x+1)(x+2)}
    =\frac{2}{x+1}+\frac{1}{x+2}.
    $$

    Hence

    $$
    \int \frac{3x+5}{(x+1)(x+2)}\,dx
    =2\ln|x+1|+\ln|x+2|+C.
    $$

20. Write $\tan x=\frac{\sin x}{\cos x}$. Then

    $$
    \int \tan x\,dx=-\ln|\cos x|+C.
    $$

21. Use

    $$
    \sin^2x=\frac{1-\cos2x}{2}.
    $$

    Thus

    $$
    \int \sin^2x\,dx=\frac{x}{2}-\frac{\sin2x}{4}+C.
    $$

22. Use

    $$
    \cos^2x=\frac{1+\cos2x}{2}.
    $$

    Then

    $$
    \int_0^{\frac{\pi}{2}}\cos^2x\,dx=\frac{\pi}{4}.
    $$

## D. Numerical and Further Integration

23. With four strips,

    $$
    h=\frac{1}{2}.
    $$

    The values of $x^2+1$ at $0,\frac{1}{2},1,\frac{3}{2},2$ are

    $$
    1,\frac{5}{4},2,\frac{13}{4},5.
    $$

    Therefore the trapezium estimate is

    $$
    \frac{1}{4}\left(1+2\cdot\frac{5}{4}+2(2)+2\cdot\frac{13}{4}+5\right)
    =\frac{19}{4}.
    $$

24. Since

    $$
    y=x^2+1
    $$

    bends upward, the trapezia lie above the curve. The estimate is an
    over-estimate.

25. Reverse the derivative of $\cosh(2x)$:

    $$
    \int \sinh(2x)\,dx=\frac{1}{2}\cosh(2x)+C.
    $$

26. Use

    $$
    \int \frac{1}{1+x^2}\,dx=\tan^{-1}x+C.
    $$

    Hence

    $$
    \int_0^1\frac{1}{1+x^2}\,dx
    =\frac{\pi}{4}.
    $$

27. For arc length,

    $$
    L=\int_0^4\sqrt{1+\left(\frac{dy}{dx}\right)^2}\,dx.
    $$

    Since

    $$
    y=x^{\frac{3}{2}},
    $$

    we have

    $$
    \frac{dy}{dx}=\frac{3}{2}\sqrt{x}.
    $$

    Therefore

    $$
    L=\int_0^4\sqrt{1+\frac{9x}{4}}\,dx
    =\frac{8}{27}\left(10\sqrt{10}-1\right).
    $$

28. Use integration by parts twice, or use the known result after doing so:

    $$
    \int x^2e^x\,dx=e^x(x^2-2x+2)+C.
    $$

    Hence

    $$
    \int_0^1 x^2e^x\,dx
    =e-2.
    $$
