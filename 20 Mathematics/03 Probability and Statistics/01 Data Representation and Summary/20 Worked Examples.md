---
title: Data Representation and Summary Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/01 Data Representation and Summary/00 Overview|Data Representation and Summary]]"
status: active
tags:
  - mathematics/statistics
  - worked-examples
---

# Data Representation and Summary Worked Examples

These examples model the 9709 S1 route through suitable displays, histograms,
cumulative frequency, box plots, summary statistics, coded data, and comparison
of distributions.

## Source Route

- CAIE Mathematics 9709 section 5.1: selecting representations, stem-and-leaf
  diagrams, box-and-whisker plots, histograms, cumulative frequency graphs,
  mean, median, mode, range, interquartile range, standard deviation, grouped
  data, and coded totals.

## Example 1: Choosing a Representation

**Prompt.** Choose a suitable representation for each data set: favourite
subject of students, reaction times measured in seconds, and number of books
read in a month.

**Solution.**

Favourite subject is qualitative categorical data, so a bar chart or pie chart
is suitable. Reaction time is continuous quantitative data, so a histogram,
box plot, or cumulative frequency graph may be suitable depending on the
question. Number of books is discrete quantitative data, so a bar chart,
stem-and-leaf diagram, or dot plot is suitable for a small data set.

**Check.** The representation must match both the data type and the question.

## Example 2: Raw Data Summaries

**Prompt.** For the data set

$$
12,\ 15,\ 15,\ 18,\ 20,\ 21,\ 22,\ 24,\ 28,
$$

find the mean, median, quartiles, range, interquartile range, and standard
deviation.

**Solution.**

The mean is

$$
\bar x=\frac{175}{9}=19.4\quad \text{to 3 s.f.}
$$

The median is the fifth value:

$$
20.
$$

The lower half is $12,15,15,18$, so

$$
Q_1=15.
$$

The upper half is $21,22,24,28$, so

$$
Q_3=23.
$$

Thus

$$
\text{range}=28-12=16,\qquad IQR=23-15=8.
$$

Using

$$
\sigma=\sqrt{\frac{\sum x^2}{n}-\bar x^2},
$$

the standard deviation is

$$
4.72\quad \text{to 3 s.f.}
$$

**Check.** The mean is slightly below the median because the lower tail pulls
the balance point down.

## Example 3: Histogram Frequency Density

**Prompt.** A grouped data set has classes and frequencies:

| Class | Frequency |
|---|---:|
| $0\le x<10$ | 12 |
| $10\le x<20$ | 18 |
| $20\le x<40$ | 10 |
| $40\le x<50$ | 5 |

Find the frequency densities.

**Solution.**

Use

$$
\text{frequency density}=\frac{\text{frequency}}{\text{class width}}.
$$

The densities are

| Class | Width | Frequency density |
|---|---:|---:|
| $0\le x<10$ | 10 | 1.2 |
| $10\le x<20$ | 10 | 1.8 |
| $20\le x<40$ | 20 | 0.5 |
| $40\le x<50$ | 10 | 0.5 |

**Check.** The $20\le x<40$ class has lower height than the previous class
even though its frequency is not much smaller, because its width is larger.

## Example 4: Grouped Mean and Standard Deviation

**Prompt.** Estimate the mean and standard deviation for this grouped data:

| Class | Frequency |
|---|---:|
| $0\le x<10$ | 4 |
| $10\le x<20$ | 9 |
| $20\le x<30$ | 7 |

**Solution.**

Use midpoints $5,15,25$.

$$
\sum f=20,\qquad \sum fx=330,\qquad \sum fx^2=6500.
$$

Thus

$$
\bar x=\frac{330}{20}=16.5.
$$

The estimated variance is

$$
\frac{6500}{20}-16.5^2=52.75.
$$

So the estimated standard deviation is

$$
7.26\quad \text{to 3 s.f.}
$$

**Check.** The answer is an estimate because class midpoints stand in for the
unknown raw values.

## Example 5: Quartiles from Cumulative Frequency

**Prompt.** A cumulative frequency table is:

| Upper boundary | 10 | 20 | 30 | 40 |
|---:|---:|---:|---:|---:|
| Cumulative frequency | 5 | 17 | 29 | 40 |

Estimate $Q_1$, the median, and $Q_3$.

**Solution.**

There are $40$ observations. The quartile positions are $10$, $20$, and $30$.

$Q_1$ is in the $10$ to $20$ class:

$$
Q_1=10+\frac{10-5}{12}(10)=14.2.
$$

The median is in the $20$ to $30$ class:

$$
\text{median}=20+\frac{20-17}{12}(10)=22.5.
$$

$Q_3$ is in the $30$ to $40$ class:

$$
Q_3=30+\frac{30-29}{11}(10)=30.9.
$$

**Check.** These are estimates, because the values inside each class are not
known exactly.

## Example 6: Coded Data

**Prompt.** For $50$ observations, $y=(x-50)/10$, $\sum y=120$, and
$\sum y^2=420$. Find the mean and standard deviation of $x$.

**Solution.**

The mean of $y$ is

$$
\bar y=\frac{120}{50}=2.4.
$$

Since $x=50+10y$,

$$
\bar x=50+10(2.4)=74.
$$

For $y$,

$$
\sigma_y=\sqrt{\frac{420}{50}-2.4^2}
=1.62\quad \text{to 3 s.f.}
$$

Therefore

$$
\sigma_x=10\sigma_y=16.2\quad \text{to 3 s.f.}
$$

**Check.** Adding $50$ changes the mean but not the standard deviation;
scaling by $10$ scales the standard deviation by $10$.

## Example 7: Comparing Box Plots

**Prompt.** Two data sets have five-number summaries:

| Data set | Min | $Q_1$ | Median | $Q_3$ | Max |
|---|---:|---:|---:|---:|---:|
| A | 10 | 14 | 18 | 22 | 30 |
| B | 8 | 12 | 19 | 28 | 40 |

Compare the distributions.

**Solution.**

Data set B has a slightly higher median, $19$ compared with $18$. It is much
more spread out: its IQR is

$$
28-12=16,
$$

while A has IQR

$$
22-14=8.
$$

B also has a larger range, $32$ compared with $20$. So B is slightly higher in
centre but much more variable.

**Check.** A comparison should mention both centre and spread.

## Example 8: Outlier Rule

**Prompt.** A data set has $Q_1=20$ and $Q_3=35$. Use the $1.5IQR$ rule to
decide whether $62$ is an outlier.

**Solution.**

The interquartile range is

$$
IQR=35-20=15.
$$

The upper fence is

$$
35+1.5(15)=57.5.
$$

Since

$$
62>57.5,
$$

$62$ is an outlier by this rule.

**Check.** The rule flags unusual values; it does not prove the value is an
error.
