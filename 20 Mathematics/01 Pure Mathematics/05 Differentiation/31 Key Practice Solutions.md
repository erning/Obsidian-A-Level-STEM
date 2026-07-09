---
title: Differentiation Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Differentiation](00%20Overview.md)"
status: active
tags:
  - mathematics/pure
  - solutions
---

# Differentiation Key Practice Solutions

Use these solutions to check method choice and algebra for [Key Practice Problems](30%20Key%20Practice%20Problems.md).

## A. Differentiating Explicit Functions

1. Use the power rule term by term:

   $$
   \frac{dy}{dx}=20x^3+6x^{-3}+\frac{7}{2}x^{-\frac{1}{2}}.
   $$

2. Use the chain rule:

   $$
   \frac{dy}{dx}=5(2x-1)^4\cdot2=10(2x-1)^4.
   $$

3. Use the product rule:

   $$
   \frac{dy}{dx}=2x\ln x+x^2\cdot\frac{1}{x}.
   $$

   Hence

   $$
   \frac{dy}{dx}=2x\ln x+x.
   $$

4. Use the product rule:

   $$
   \frac{dy}{dx}=3e^{3x}\sin x+e^{3x}\cos x.
   $$

   Therefore

   $$
   \frac{dy}{dx}=e^{3x}(3\sin x+\cos x).
   $$

5. Use the quotient rule:

   $$
   \frac{dy}{dx}
   =\frac{2x(x-2)-(x^2+1)}{(x-2)^2}.
   $$

   Hence

   $$
   \frac{dy}{dx}=\frac{x^2-4x-1}{(x-2)^2}.
   $$

6. Use the chain rule:

   $$
   \frac{dy}{dx}=\frac{3}{1+9x^2}.
   $$

7. Differentiate term by term:

   $$
   \frac{dy}{dx}=2\cosh(2x)-\sinh x.
   $$

8. Use the chain rule:

   $$
   \frac{dy}{dx}
   =\frac{\frac{1}{2}}{\sqrt{1-\left(\frac{x}{2}\right)^2}}
   =\frac{1}{\sqrt{4-x^2}}.
   $$

## B. Tangents, Normals, and Graph Shape

9. The point at $x=2$ is

   $$
   (2,1).
   $$

   Since

   $$
   \frac{dy}{dx}=3x^2-4,
   $$

   the tangent gradient at $x=2$ is $8$. The tangent is

   $$
   y-1=8(x-2).
   $$

   The normal gradient is $-\frac{1}{8}$, so the normal is

   $$
   y-1=-\frac{1}{8}(x-2).
   $$

10. Differentiate:

    $$
    f'(x)=3x^2-6x-9=3(x-3)(x+1).
    $$

    Stationary points occur at $x=-1$ and $x=3$. The coordinates are

    $$
    (-1,9),\qquad (3,-23).
    $$

    Since

    $$
    f''(x)=6x-6,
    $$

    we have $f''(-1)<0$ and $f''(3)>0$. Therefore $(-1,9)$ is a local maximum
    and $(3,-23)$ is a local minimum.

11. Differentiate:

    $$
    f'(x)=3x^2-12x+9=3(x-1)(x-3).
    $$

    Hence $f'(x)>0$ for $x<1$ and $x>3$, while $f'(x)<0$ for $1<x<3$.
    Therefore the function is increasing on

    $$
    (-\infty,1)\cup(3,\infty)
    $$

    and decreasing on

    $$
    (1,3).
    $$

12. The derivative is

    $$
    \frac{dy}{dx}=2x+a.
    $$

    At $x=2$, the gradient is $4+a$. So

    $$
    4+a=7,
    $$

    giving

    $$
    a=3.
    $$

13. At $x=1$,

    $$
    y=\ln1=0.
    $$

    The tangent gradient is

    $$
    \frac{dy}{dx}=\frac{1}{x}=1.
    $$

    The normal gradient is $-1$, so the normal is

    $$
    y=-(x-1),
    $$

    or

    $$
    y=1-x.
    $$

14. First derivative:

    $$
    \frac{dy}{dx}=6x(x^2+1)^2.
    $$

    Differentiate again:

    $$
    \frac{d^2y}{dx^2}
    =6(x^2+1)^2+24x^2(x^2+1).
    $$

    So

    $$
    \frac{d^2y}{dx^2}=6(x^2+1)(5x^2+1).
    $$

    At $x=0$,

    $$
    \frac{d^2y}{dx^2}=6.
    $$

## C. Rates and Optimisation

15. Since

    $$
    A=\pi r^2,
    $$

    we have

    $$
    \frac{dA}{dt}=\frac{dA}{dr}\frac{dr}{dt}=2\pi r\frac{dr}{dt}.
    $$

    At $r=5$ and $\frac{dr}{dt}=0.2$,

    $$
    \frac{dA}{dt}=2\pi.
    $$

16. Since

    $$
    V=\frac{4}{3}\pi r^3,
    $$

    we have

    $$
    \frac{dV}{dt}=4\pi r^2\frac{dr}{dt}.
    $$

    At $r=10$ and $\frac{dr}{dt}=0.05$,

    $$
    \frac{dV}{dt}=20\pi.
    $$

17. The rectangle has height $y=12-2x$, so its area is

    $$
    A=x(12-2x)=12x-2x^2.
    $$

    Differentiate:

    $$
    \frac{dA}{dx}=12-4x.
    $$

    Set this equal to zero:

    $$
    x=3.
    $$

    Then $y=6$ and the maximum area is

    $$
    18.
    $$

    This is a maximum because

    $$
    \frac{d^2A}{dx^2}=-4<0.
    $$

18. Differentiate:

    $$
    f'(x)=1-\frac{4}{x^2}.
    $$

    Set $f'(x)=0$:

    $$
    x^2=4.
    $$

    Since $x>0$, $x=2$. The second derivative is

    $$
    f''(x)=\frac{8}{x^3}>0
    $$

    for $x>0$, so this is a minimum. The minimum value is

    $$
    f(2)=4.
    $$

## D. Implicit and Parametric Differentiation

19. Differentiate implicitly:

    $$
    2x+2y\frac{dy}{dx}=y+x\frac{dy}{dx}.
    $$

    Therefore

    $$
    \frac{dy}{dx}=\frac{y-2x}{2y-x}.
    $$

    At $(3,1)$,

    $$
    \frac{dy}{dx}=5.
    $$

    The tangent is

    $$
    y-1=5(x-3).
    $$

20. From

    $$
    x^2+y^2=25,
    $$

    implicit differentiation gives

    $$
    \frac{dy}{dx}=-\frac{x}{y}.
    $$

    Differentiating again gives

    $$
    \frac{d^2y}{dx^2}=-\frac{25}{y^3}.
    $$

    At $(3,4)$,

    $$
    \frac{d^2y}{dx^2}=-\frac{25}{64}.
    $$

21. First,

    $$
    \frac{dx}{dt}=2t,\qquad \frac{dy}{dt}=3t^2-1.
    $$

    Hence

    $$
    \frac{dy}{dx}=\frac{3t^2-1}{2t}.
    $$

    At $t=2$,

    $$
    \frac{dy}{dx}=\frac{11}{4}.
    $$

    The point is

    $$
    (x,y)=(5,6).
    $$

    The tangent is

    $$
    y-6=\frac{11}{4}(x-5).
    $$

22. From question 21,

    $$
    \frac{dy}{dx}=\frac{3t}{2}-\frac{1}{2t}.
    $$

    Therefore

    $$
    \frac{d}{dt}\left(\frac{dy}{dx}\right)
    =\frac{3}{2}+\frac{1}{2t^2}.
    $$

    Then

    $$
    \frac{d^2y}{dx^2}
    =\frac{\frac{d}{dt}\left(\frac{dy}{dx}\right)}{\frac{dx}{dt}}.
    $$

    At $t=2$,

    $$
    \frac{d^2y}{dx^2}=\frac{13}{32}.
    $$

23. Since

    $$
    \frac{dx}{dt}=e^t,\qquad \frac{dy}{dt}=2t,
    $$

    we have

    $$
    \frac{dy}{dx}=\frac{2t}{e^t}.
    $$

24. Differentiate implicitly:

    $$
    2y\frac{dy}{dx}=3x^2.
    $$

    Hence

    $$
    \frac{dy}{dx}=\frac{3x^2}{2y}.
    $$

## E. 9231 Extensions

25. Use the chain rule:

    $$
    \frac{dy}{dx}=\frac{2}{\sqrt{(2x)^2-1}}
    =\frac{2}{\sqrt{4x^2-1}}.
    $$

    The derivative is defined for $x>\frac{1}{2}$.

26. Use the chain rule:

    $$
    \frac{dy}{dx}=\frac{2x}{1-(x^2)^2}
    =\frac{2x}{1-x^4}.
    $$

    This uses the domain $|x|<1$ for $\tanh^{-1}(x^2)$.

27. From the Maclaurin formula,

    $$
    f(x)=f(0)+xf'(0)+\frac{x^2}{2!}f''(0)
    +\frac{x^3}{3!}f'''(0)+\cdots.
    $$

    For $f(x)=\ln(1+2x)$,

    $$
    f(0)=0,\quad f'(0)=2,\quad f''(0)=-4,\quad f'''(0)=16.
    $$

    Hence

    $$
    \ln(1+2x)=2x-2x^2+\frac{8}{3}x^3+\cdots.
    $$

28. For $f(x)=e^{2x}$,

    $$
    f(0)=1,\quad f'(0)=2,\quad f''(0)=4,\quad f'''(0)=8.
    $$

    Therefore

    $$
    e^{2x}=1+2x+2x^2+\frac{4}{3}x^3+\cdots.
    $$
