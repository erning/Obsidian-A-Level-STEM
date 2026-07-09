---
title: Sequences, Series and Binomial Expansions Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Sequences, Series and Binomial Expansions](00%20Overview.md)"
status: active
tags:
  - mathematics/pure
  - solutions
---

# Sequences, Series and Binomial Expansions Key Practice Solutions

Use these solutions to check method choice and algebra for [Key Practice Problems](30%20Key%20Practice%20Problems.md).

## A. Arithmetic and Geometric Progressions

1. For an arithmetic progression,

   $$
   u_n=a+(n-1)d.
   $$

   Hence

   $$
   u_{20}=7+19(3)=64.
   $$

   The sum is

   $$
   S_{20}=\frac{20}{2}\left(2(7)+19(3)\right)
   =10(71)=710.
   $$

2. Use

   $$
   u_n=a+(n-1)d.
   $$

   The given terms give

   $$
   a+4d=18,\qquad a+11d=46.
   $$

   Subtracting gives

   $$
   7d=28,
   $$

   so $d=4$. Then $a=2$. Therefore

   $$
   S_{20}=\frac{20}{2}(2(2)+19(4))=800.
   $$

3. For three consecutive arithmetic terms,

   $$
   2(2x+1)=(x-2)+(5x-1).
   $$

   Thus

   $$
   4x+2=6x-3,
   $$

   so

   $$
   x=\frac{5}{2}.
   $$

4. For a geometric progression,

   $$
   u_n=ar^{n-1}.
   $$

   Hence

   $$
   u_6=5(3^5)=1215.
   $$

   The finite sum is

   $$
   S_6=\frac{5(3^6-1)}{3-1}=1820.
   $$

5. Since

   $$
   u_2=ar=6,\qquad u_5=ar^4=162,
   $$

   divide the equations:

   $$
   r^3=27.
   $$

   So $r=3$ and $a=2$. The sum is

   $$
   S_5=\frac{2(3^5-1)}{3-1}=242.
   $$

6. For three consecutive geometric terms,

   $$
   6^2=x(x+9).
   $$

   Therefore

   $$
   x^2+9x-36=0,
   $$

   so

   $$
   (x-3)(x+12)=0.
   $$

   The possible values are

   $$
   x=3,\ -12.
   $$

7. Since $|-\frac{1}{3}|<1$,

   $$
   S_\infty=\frac{12}{1-\left(-\frac{1}{3}\right)}=9.
   $$

8. Use

   $$
   S_\infty=\frac{a}{1-r}.
   $$

   Thus

   $$
   20=\frac{5}{1-r}.
   $$

   Hence

   $$
   r=\frac{3}{4}.
   $$

   The fourth term is

   $$
   u_4=5\left(\frac{3}{4}\right)^3=\frac{135}{64}.
   $$

## B. Positive-Integer Binomial Expansions

9. The term in $x^3$ uses $r=3$:

   $$
   \binom{5}{3}(2x)^3=80x^3.
   $$

   The coefficient is $80$.

10. The term in $x^2$ uses $r=2$:

    $$
    \binom{6}{2}3^4(-2)^2=4860.
    $$

11. The general term is

    $$
    T_{r+1}=\binom{6}{r}(2x)^{6-r}\left(-\frac{1}{x}\right)^r.
    $$

    The power of $x$ is $6-2r$. For the constant term, $6-2r=0$, so $r=3$.
    The constant term is

    $$
    \binom{6}{3}2^3(-1)^3=-160.
    $$

12. The coefficient of $x^4$ in $(1+x)^8(1-2x)$ is

    $$
    \binom{8}{4}-2\binom{8}{3}.
    $$

    Hence the coefficient is

    $$
    70-112=-42.
    $$

13. The general term is

    $$
    T_{r+1}=\binom{9}{r}(x^2)^{9-r}\left(\frac{2}{x}\right)^r.
    $$

    The power of $x$ is

    $$
    18-3r.
    $$

    For the term independent of $x$, $18-3r=0$, so $r=6$. The term is

    $$
    \binom{9}{6}2^6=5376.
    $$

## C. Non-Integer Binomial Expansions and Partial Fractions

14. This is a geometric expansion:

    $$
    (1-2x)^{-1}=1+2x+4x^2+8x^3+\cdots.
    $$

    The validity condition is

    $$
    |2x|<1,
    $$

    or

    $$
    |x|<\frac{1}{2}.
    $$

15. Use the binomial expansion with $n=\frac{1}{2}$ and $u=3x$:

    $$
    (1+3x)^{\frac{1}{2}}
    =1+\frac{3}{2}x-\frac{9}{8}x^2+\frac{27}{16}x^3+\cdots.
    $$

    The validity condition is

    $$
    |3x|<1,
    $$

    so

    $$
    |x|<\frac{1}{3}.
    $$

16. First write

    $$
    (4+x)^{-2}=\frac{1}{16}\left(1+\frac{x}{4}\right)^{-2}.
    $$

    Hence

    $$
    (4+x)^{-2}
    =\frac{1}{16}-\frac{x}{32}+\frac{3x^2}{256}+\cdots.
    $$

    The validity condition is

    $$
    \left|\frac{x}{4}\right|<1,
    $$

    so

    $$
    |x|<4.
    $$

17. Substitute $x=0.1$ into the expansion from question 15:

    $$
    \sqrt{1.3}
    \approx1+\frac{3}{2}(0.1)-\frac{9}{8}(0.1)^2
    +\frac{27}{16}(0.1)^3.
    $$

    Therefore

    $$
    \sqrt{1.3}\approx1.1404375.
    $$

18. Use partial fractions:

    $$
    \frac{1}{r(r+1)}=\frac{1}{r}-\frac{1}{r+1}.
    $$

19. Use partial fractions:

    $$
    \frac{2}{(r+1)(r+3)}
    =\frac{1}{r+1}-\frac{1}{r+3}.
    $$

20. First decompose:

    $$
    \frac{1}{(1-x)(2+x)}
    =\frac{1}{3}\left(\frac{1}{1-x}+\frac{1}{2+x}\right).
    $$

    Then

    $$
    \frac{1}{1-x}=1+x+x^2+\cdots
    $$

    and

    $$
    \frac{1}{2+x}
    =\frac{1}{2}\left(1-\frac{x}{2}+\frac{x^2}{4}+\cdots\right).
    $$

    Therefore

    $$
    \frac{1}{(1-x)(2+x)}
    =\frac{1}{2}+\frac{x}{4}+\frac{3x^2}{8}+\cdots.
    $$

    The validity condition is

    $$
    |x|<1.
    $$

## D. Standard Sums and Method of Differences

21. Use standard sums:

    $$
    \sum_{r=1}^{n}(3r^2-2r+1)
    =3\sum_{r=1}^{n}r^2-2\sum_{r=1}^{n}r+\sum_{r=1}^{n}1.
    $$

    Hence

    $$
    \sum_{r=1}^{n}(3r^2-2r+1)
    =\frac{n(2n^2+n+1)}{2}.
    $$

22. Compute directly from standard sums:

    $$
    \sum_{r=1}^{10}(2r+5)
    =2\sum_{r=1}^{10}r+5(10)
    =2(55)+50
    =160.
    $$

23. Since $r(r+1)=r^2+r$,

    $$
    \sum_{r=1}^{n}r(r+1)
    =\sum_{r=1}^{n}r^2+\sum_{r=1}^{n}r.
    $$

    Therefore

    $$
    \sum_{r=1}^{n}r(r+1)
    =\frac{n(n+1)(n+2)}{3}.
    $$

24. From question 18,

    $$
    \frac{1}{r(r+1)}=\frac{1}{r}-\frac{1}{r+1}.
    $$

    Therefore

    $$
    S_n=1-\frac{1}{n+1}
    =\frac{n}{n+1}.
    $$

    Hence

    $$
    S_\infty=1.
    $$

25. From question 19,

    $$
    \frac{2}{(r+1)(r+3)}
    =\frac{1}{r+1}-\frac{1}{r+3}.
    $$

    The surviving boundary terms are

    $$
    S_n=\frac{1}{2}+\frac{1}{3}-\frac{1}{n+2}-\frac{1}{n+3}.
    $$

    Thus

    $$
    S_n=\frac{5}{6}-\frac{1}{n+2}-\frac{1}{n+3},
    $$

    and

    $$
    S_\infty=\frac{5}{6}.
    $$

26. The series telescopes immediately:

    $$
    \sum_{r=1}^{n}\left((r+1)^3-r^3\right)
    =(2^3-1^3)+(3^3-2^3)+\cdots+((n+1)^3-n^3).
    $$

    All middle terms cancel, so

    $$
    \sum_{r=1}^{n}\left((r+1)^3-r^3\right)
    =(n+1)^3-1.
    $$

27. For $n\ge2$,

    $$
    u_n=S_n-S_{n-1}.
    $$

    Hence

    $$
    u_n=\left(5-\frac{3}{n+2}\right)
    -\left(5-\frac{3}{n+1}\right)
    =\frac{3}{(n+1)(n+2)}.
    $$

    Since

    $$
    \frac{3}{n+2}\to0
    $$

    as $n\to\infty$, the sum to infinity is

    $$
    5.
    $$

28. This is a geometric series with

    $$
    a=10,\qquad r=-\frac{1}{2}.
    $$

    Since $|r|<1$,

    $$
    S_\infty=\frac{10}{1-\left(-\frac{1}{2}\right)}
    =\frac{20}{3}.
    $$
