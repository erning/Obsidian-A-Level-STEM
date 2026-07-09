---
title: Logarithms, Exponentials and Numerical Methods Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
parent: "[Logarithms, Exponentials and Numerical Methods](00%20Overview.md)"
status: active
tags:
  - mathematics/pure
  - solutions
---

# Logarithms, Exponentials and Numerical Methods Key Practice Solutions

Use these solutions to check method choice and algebra for [Key Practice Problems](30%20Key%20Practice%20Problems.md).

## A. Logarithms and Exponentials

1. Use logarithm laws:

   $$
   \ln8+\ln4-\ln2=\ln\frac{8\cdot4}{2}=\ln16.
   $$

2. The domain is $x>1$. Combine logarithms:

   $$
   \ln((x-1)(x+2))=\ln12.
   $$

   Hence

   $$
   x^2+x-14=0.
   $$

   Therefore

   $$
   x=\frac{-1+\sqrt{57}}{2}.
   $$

3. Rearrange first:

   $$
   e^{3x}=\frac{7}{2}.
   $$

   Taking logarithms gives

   $$
   x=\frac{1}{3}\ln\frac{7}{2}.
   $$

4. Take logarithms:

   $$
   (x+1)\ln5=2x\ln3.
   $$

   Hence

   $$
   x=\frac{\ln5}{2\ln3-\ln5}.
   $$

5. Since $\ln x$ is increasing on $x>0$,

   $$
   2x-1>\ln4.
   $$

   Therefore

   $$
   x>\frac{1+\ln4}{2}.
   $$

6. Rewrite with base $3$:

   $$
   3^{-x}\le3^2.
   $$

   Since $3^u$ is increasing,

   $$
   -x\le2.
   $$

   Therefore

   $$
   x\ge-2.
   $$

7. The arguments must be positive:

   $$
   x-2>0,\qquad 5-x>0.
   $$

   Hence

   $$
   2<x<5.
   $$

8. The domain is $2<x<5$. Combine logarithms:

   $$
   (x-2)(5-x)=2.
   $$

   This gives

   $$
   x^2-7x+12=0.
   $$

   Therefore

   $$
   x=3,\ 4.
   $$

   Both values are in the domain.

## B. Modelling and Linear Form

9. For $y=kx^n$,

   $$
   \ln y=\ln k+n\ln x.
   $$

   Thus

   $$
   n=\frac{5}{2},\qquad k=3.
   $$

   The relationship is

   $$
   y=3x^{\frac{5}{2}}.
   $$

10. For $y=ke^{bx}$,

    $$
    \ln y=\ln k+bx.
    $$

    Hence $b=-0.2$ and $k=80$, so

    $$
    y=80e^{-0.2x}.
    $$

11. From

    $$
    y=kx^n,
    $$

    use the two points:

    $$
    12=k2^n,\qquad 96=k8^n.
    $$

    Divide:

    $$
    8=4^n.
    $$

    Thus

    $$
    n=\frac{3}{2}.
    $$

    Then

    $$
    k=\frac{12}{2^{3/2}}=3\sqrt2.
    $$

12. Since $y=ka^x$ passes through $(0,5)$,

    $$
    k=5.
    $$

    Using $(3,40)$:

    $$
    40=5a^3.
    $$

    Hence

    $$
    a=2.
    $$

13. Solve

    $$
    40=100e^{-0.07t}.
    $$

    Then

    $$
    e^{-0.07t}=0.4.
    $$

    Therefore

    $$
    t=\frac{\ln0.4}{-0.07}\approx13.1.
    $$

14. Doubling in $8$ years means

    $$
    500=250e^{8k}.
    $$

    So

    $$
    k=\frac{\ln2}{8}.
    $$

    After $12$ years,

    $$
    P=250e^{12k}=250\cdot2^{3/2}=500\sqrt2\approx707.1.
    $$

## C. Numerical Solution of Equations

15. Evaluate

    $$
    f(1)=-1,\qquad f(2)=5.
    $$

    Since the signs are different and $f$ is continuous, there is a root in
    $(1,2)$.

16. Evaluate

    $$
    f(1.3)=1.3^3-1.3-1=-0.103
    $$

    and

    $$
    f(1.4)=1.4^3-1.4-1=0.344.
    $$

    Therefore the root lies in $(1.3,1.4)$.

17. Iterate:

    $$
    x_1=(1.3+1)^{1/3}\approx1.320006,
    $$

    $$
    x_2\approx1.323822,
    $$

    $$
    x_3\approx1.324548.
    $$

18. If

    $$
    x=(x+1)^{1/3},
    $$

    then cubing both sides gives

    $$
    x^3=x+1.
    $$

    Hence

    $$
    x^3-x-1=0.
    $$

19. Let $g(x)=e^{-x}-x$. Then

    $$
    g(0)=1
    $$

    and

    $$
    g(1)=e^{-1}-1<0.
    $$

    So there is a root in $(0,1)$.

20. Iterating gives

    $$
    x_1\approx0.606531,
    $$

    $$
    x_2\approx0.545239,
    $$

    $$
    x_3\approx0.579703,
    $$

    $$
    x_4\approx0.560065.
    $$

21. Taking logarithms:

    $$
    x\ln2=\ln10.
    $$

    Therefore

    $$
    x=\frac{\ln10}{\ln2}\approx3.322.
    $$

22. Newton iteration uses

    $$
    x_{n+1}=x_n-\frac{x_n^3-x_n-1}{3x_n^2-1}.
    $$

    Starting with $x_0=1.3$ gives

    $$
    x_1\approx1.325307,\qquad x_2\approx1.324718.
    $$

23. An iteration may fail to converge if the rearrangement is unsuitable, if
    the starting value is poor, or if the values move away from the fixed
    point instead of settling.

24. The logarithm is defined only when its argument is positive. Therefore

    $$
    x^2-4>0,
    $$

    so

    $$
    x<-2\quad\text{or}\quad x>2.
    $$
