---
title: Data Representation and Summary Key Practice Solutions
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Data Representation and Summary](00%20Overview.md)"
status: active
tags:
  - mathematics/statistics
  - solutions
---

# Data Representation and Summary Key Practice Solutions

This note gives worked solutions for [Data Representation and Summary Key Practice Problems](30%20Key%20Practice%20Problems.md). Use it to check representation choice, midpoint estimates, coded transformations, and comparison language.

## A. Data Types and Diagrams

### Problem 1

Eye colour is qualitative data; a bar chart or pie chart is suitable. Number
of siblings is discrete quantitative data; a bar chart or dot plot is suitable.
Time to run $100\ \mathrm{m}$ is continuous quantitative data; a histogram,
box plot, or cumulative frequency graph may be suitable.

### Problem 2

A stem-and-leaf diagram is

```text
1 | 2 3 5 6 8
2 | 1 2 2 4 7
3 | 1 3
Key: 1 | 2 means 12 minutes
```

There are $12$ values, so the median is the mean of the 6th and 7th values:

$$
\frac{21+22}{2}=21.5\ \text{minutes}.
$$

### Problem 3

The sum is $72$, so

$$
\bar x=\frac{72}{8}=9.
$$

The median is

$$
\frac{7+9}{2}=8.
$$

The range is

$$
17-4=13.
$$

For the lower half $4,5,7,7$,

$$
Q_1=\frac{5+7}{2}=6.
$$

For the upper half $9,10,13,17$,

$$
Q_3=\frac{10+13}{2}=11.5.
$$

Thus

$$
IQR=11.5-6=5.5.
$$

### Problem 4

For $2,4,4,5,5,7,9$,

$$
\bar x=\frac{36}{7}=5.14\quad \text{to 3 s.f.}
$$

Also

$$
\sum x^2=216.
$$

So

$$
\sigma=\sqrt{\frac{216}{7}-\left(\frac{36}{7}\right)^2}
=2.10
$$

to 3 s.f.

### Problem 5

Frequency density is frequency divided by class width.

| Class | Width | Frequency density |
|---|---:|---:|
| $0\le x<5$ | 5 | 1.2 |
| $5\le x<15$ | 10 | 2.0 |
| $15\le x<30$ | 15 | 1.2 |

## B. Grouped Data and Cumulative Frequency

### Problem 6

Use midpoints $2.5$, $7.5$, and $15$.

$$
\sum f=20,\qquad \sum fx=210,\qquad \sum fx^2=2662.5.
$$

Thus

$$
\bar x=\frac{210}{20}=10.5.
$$

The estimated standard deviation is

$$
\sqrt{\frac{2662.5}{20}-10.5^2}=4.78
$$

to 3 s.f. These are estimates because the raw values are not known.

### Problem 7

There are $40$ observations, so use positions $10$, $20$, and $30$.

$$
Q_1=10+\frac{10-5}{12}(10)=14.2.
$$

$$
\text{median}=20+\frac{20-17}{12}(10)=22.5.
$$

$$
Q_3=30+\frac{30-29}{11}(10)=30.9.
$$

### Problem 8

For $y$,

$$
\bar y=\frac{-12}{40}=-0.3.
$$

Since $x=100+5y$,

$$
\bar x=100+5(-0.3)=98.5.
$$

For $y$,

$$
\sigma_y=\sqrt{\frac{196}{40}-(-0.3)^2}
=\sqrt{4.81}=2.19.
$$

Therefore

$$
\sigma_x=5(2.19)=11.0
$$

to 3 s.f.

### Problem 9

$$
IQR=48-32=16.
$$

The upper fence is

$$
48+1.5(16)=72.
$$

Since $75>72$, $75$ is an outlier by the $1.5\times\mathrm{IQR}$ rule.

### Problem 10

Data set A has the higher mean, so it has the higher average value. Data set B
has the larger standard deviation, so it is much more spread out. A typical
value from B is less predictable even though its mean is only slightly lower.

## C. Interpreting Representations

### Problem 11

A back-to-back stem-and-leaf diagram keeps the original values visible while
putting both data sets on the same stems. This makes centre, spread, clusters,
and unusual values easier to compare for small data sets.

### Problem 12

Between $30$ and $40$, cumulative frequency rises from $20$ to $36$. At $35$,
linear interpolation gives

$$
20+\frac{5}{10}(36-20)=28.
$$

So the estimated number greater than $35$ is

$$
50-28=22.
$$

The estimated proportion is

$$
\frac{22}{50}=0.44.
$$

### Problem 13

Class width is

$$
35-20=15.
$$

Frequency is area:

$$
1.6(15)=24.
$$

### Problem 14

The mean is

$$
\bar x=\frac{430}{25}=17.2.
$$

The standard deviation is

$$
\sigma=\sqrt{\frac{7820}{25}-17.2^2}.
$$

Thus

$$
\sigma=\sqrt{16.96}=4.12
$$

to 3 s.f.

### Problem 15

The combined mean is

$$
\frac{12(8)+18(11)}{12+18}
=\frac{294}{30}=9.8.
$$

## D. Mixed Review

### Problem 16

Since $x=3y+7$,

$$
\bar x=3\bar y+7=3(4)+7=19.
$$

Standard deviation is scaled by $3$:

$$
\sigma_x=3(2.5)=7.5.
$$

### Problem 17

Median and IQR are usually more useful for a strongly positively skewed salary
distribution because high earners can pull the mean and standard deviation
upwards. Median and IQR describe a typical salary and middle spread more
robustly.

### Problem 18

The distribution is positively skewed. The longer upper whisker and the median
closer to $Q_1$ suggest a longer upper tail.

### Problem 19

With unequal class widths, using frequency as height would make wider classes
look too large. In a histogram, area represents frequency, so the height must
be frequency density.

### Problem 20

Both data sets have mean $8$ and median $8$, so their centres are the same.
Data set A has range $4$ and IQR $3$. Data set B has range $12$ and IQR $9$.
Therefore B is much more spread out.
