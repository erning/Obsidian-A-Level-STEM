---
title: Counting and Probability Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/02 Counting and Probability/00 Overview|Counting and Probability]]"
status: active
tags:
  - mathematics/statistics
  - solutions
---

# Counting and Probability Key Practice Solutions

This note gives worked solutions for [[20 Mathematics/03 Probability and Statistics/02 Counting and Probability/30 Key Practice Problems|Counting and Probability Key Practice Problems]]. Use it to check whether order matters, whether replacement occurs, and whether events overlap.

## A. Counting

### Problem 1

Ordered selections:

$$
{}^7P_3=7(6)(5)=210.
$$

Unordered selections:

$$
\binom73=35.
$$

### Problem 2

BALLOON has $7$ letters, with two Ls and two Os. Therefore the number of
distinct arrangements is

$$
\frac{7!}{2!2!}=1260.
$$

### Problem 3

Treat the four girls as one block. Then there are $6$ objects to arrange: the
girl block and five boys. The girls can be arranged inside their block in
$4!$ ways. Hence

$$
6!4!=17280.
$$

### Problem 4

Choose $2$ of the $4$ girls and $2$ of the $6$ boys:

$$
\binom42\binom62=6(15)=90.
$$

### Problem 5

Total arrangements:

$$
8!.
$$

Arrangements with the two particular people together: treat them as a block,
giving

$$
7!2!.
$$

Therefore the number not next to each other is

$$
8!-2(7!)=30240.
$$

### Problem 6

With repetition allowed, there are $9$ choices for the first digit and $10$
choices for each remaining digit:

$$
9(10^3)=9000.
$$

Without repetition, there are

$$
9(9)(8)(7)=4536
$$

codes.

## B. Elementary Probability

### Problem 7

Totals at least $10$ are $10$, $11$, and $12$. The numbers of outcomes are
$3$, $2$, and $1$, so there are $6$ favourable outcomes out of $36$.

$$
P=\frac{6}{36}=\frac16.
$$

### Problem 8

Use combinations:

$$
P(\text{all blue})=\frac{\binom53}{\binom93}
=\frac{10}{84}=\frac{5}{42}.
$$

### Problem 9

Use the complement. The probability of no red balls is

$$
\left(\frac{7}{10}\right)^2=\frac{49}{100}.
$$

Therefore

$$
P(\text{at least one red})=1-\frac{49}{100}=\frac{51}{100}.
$$

### Problem 10

$$
P(A\cup B)=0.40+0.35-0.12=0.63.
$$

Therefore

$$
P((A\cup B)')=1-0.63=0.37.
$$

Also

$$
P(A\mid B)=\frac{0.12}{0.35}=0.343
$$

to 3 s.f. Since

$$
P(A)P(B)=0.40(0.35)=0.14\ne0.12,
$$

the events are not independent.

## C. Tree Diagrams and Conditional Probability

### Problem 11

Same colour means both red or both blue:

$$
P=\frac{6}{10}\cdot\frac{5}{9}
+\frac{4}{10}\cdot\frac{3}{9}.
$$

Thus

$$
P=\frac{30+12}{90}=\frac{7}{15}.
$$

### Problem 12

Let $M$ be studying Mathematics and $P$ studying Physics.

$$
P(M\mid P)=\frac{18}{30}=0.6.
$$

$$
P(P\mid M)=\frac{18}{45}=0.4.
$$

### Problem 13

Independence gives

$$
P(A\cap B)=0.30(0.50)=0.15.
$$

Therefore

$$
P(A\cup B)=0.30+0.50-0.15=0.65.
$$

### Problem 14

Mutually exclusive events have zero intersection, so

$$
P(A\cup B)=0.20+0.45=0.65.
$$

They are not independent because

$$
P(A\cap B)=0
$$

but

$$
P(A)P(B)=0.09.
$$

### Problem 15

Choose the two positions for the heads:

$$
P=\binom42\left(\frac12\right)^4
=\frac{6}{16}=\frac38.
$$

## D. Mixed Review

### Problem 16

Exactly two aces means choosing $2$ of the $4$ aces and $3$ of the $48$
non-aces:

$$
P=\frac{\binom42\binom{48}{3}}{\binom{52}{5}}.
$$

This is

$$
\frac{103776}{2598960}=0.0399
$$

to 3 s.f.

### Problem 17

STATISTICS has $10$ letters, with three Ss, three Ts, and two Is. Therefore

$$
\frac{10!}{3!3!2!}=50400.
$$

### Problem 18

Choose the two positions with exactly one position between them:

$$
(1,3),(2,4),(3,5),(4,6),(5,7).
$$

There are $5$ such position pairs and $2$ orders for the two particular people.
The other five people can be arranged in $5!$ ways. Hence

$$
5(2)(5!)=1200.
$$

### Problem 19

The probability of a defective component is

$$
0.7(0.02)+0.3(0.05)=0.029.
$$

The probability of A and defective is

$$
0.7(0.02)=0.014.
$$

Therefore

$$
P(A\mid D)=\frac{0.014}{0.029}=0.483
$$

to 3 s.f.

### Problem 20

Given total score greater than $8$, the possible outcomes have sums $9$, $10$,
$11$, and $12$. There are

$$
4+3+2+1=10
$$

such outcomes.

Among these, outcomes with at least one $6$ are

$$
(3,6),(4,6),(5,6),(6,3),(6,4),(6,5),(6,6).
$$

There are $7$ favourable outcomes, so

$$
P=\frac{7}{10}.
$$
