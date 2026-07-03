---
title: Data Representation and Summary Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/01 Data Representation and Summary/00 Overview|Data Representation and Summary]]"
status: draft
tags:
  - mathematics/statistics
  - lecture-notes
---

# Data Representation and Summary Lecture Notes

Statistics begins by turning raw observations into something readable. A good representation should show the shape of the data before you calculate summaries, and a good summary should answer a question about centre, spread, comparison, or unusual values.

## Source Route

- 9709 5.1 Representation of data
- Coursebook route: 9709 Probability and Statistics 1 chapters on representation and summary of data.

## Visual Guide

![[assets/generated/mathematics/data-representation-and-summary.svg]]

Figure: use the guide to connect histogram shape, box-and-whisker summaries, and outliers.

## 1. Start with the Data and the Question

Before drawing a graph or calculating a statistic, ask what kind of data you have.

- Qualitative data describe categories.
- Discrete quantitative data usually count things.
- Continuous quantitative data usually measure things.
- Grouped data replace individual observations by class intervals.

Then ask what the representation is meant to reveal. A graph for seeing shape is not always the same as a graph for comparing medians or estimating percentiles.

## 2. Statistical Diagrams

A stem-and-leaf diagram keeps the original values visible while showing the distribution. It is useful for small or medium-sized data sets. A back-to-back stem-and-leaf diagram compares two related data sets on the same stems.

A box-and-whisker plot summarises a distribution using

$$
\text{minimum},\quad Q_1,\quad \text{median},\quad Q_3,\quad \text{maximum}.
$$

It is particularly good for comparing centre, spread, skew, and possible outliers across two or more data sets.

A histogram is used for continuous grouped data. If class widths are unequal, the vertical axis must be frequency density:

$$
\text{frequency density}=\frac{\text{frequency}}{\text{class width}}.
$$

The area of each bar represents frequency. This is the main difference between a histogram and a bar chart.

A cumulative frequency graph is used to estimate medians, quartiles, percentiles, and proportions above or below a given value. It is read horizontally and vertically: from a cumulative frequency to a data value, or from a data value to a cumulative frequency.

## 3. Measures of Centre

The mean is the balance point of the data:

$$
\bar x=\frac{\sum x}{n}.
$$

For grouped data, use class midpoints as approximations:

$$
\bar x\approx\frac{\sum fx}{\sum f}.
$$

The median is the middle value after ordering. It is more resistant to extreme values than the mean. The mode is the most frequent value or class.

A useful habit is to compare mean and median. If the mean is greater than the median, the distribution may be positively skewed. If the mean is less than the median, it may be negatively skewed. Always confirm this against the graph.

## 4. Measures of Variation

Range is simple:

$$
\text{range}=\text{largest value}-\text{smallest value}.
$$

The interquartile range is

$$
IQR=Q_3-Q_1.
$$

It measures the spread of the middle half of the data and is less affected by outliers than the range.

Variance and standard deviation measure spread around the mean. A common formula is

$$
\sigma^2=\frac{\sum x^2}{n}-\bar x^2,
$$

and

$$
\sigma=\sqrt{\sigma^2}.
$$

For grouped data,

$$
\sigma^2\approx\frac{\sum f x^2}{\sum f}-\bar x^2,
$$

where $x$ is the class midpoint.

## 5. Coded Data

Coded totals reduce arithmetic. If

$$
y=x-a,
$$

then

$$
\bar x=\bar y+a.
$$

If

$$
y=\frac{x-a}{b},
$$

then

$$
x=a+by,\qquad \bar x=a+b\bar y,\qquad \sigma_x=|b|\sigma_y.
$$

Adding or subtracting a constant shifts the data but does not change spread. Multiplying by a factor scales the spread by the absolute value of that factor.

## 6. Comparing Data Sets

A comparison should mention centre and spread, and usually shape. Do not write only "data set A is bigger" unless you say what is bigger: the median, the mean, the IQR, the standard deviation, or the upper tail.

Use median and IQR when distributions are skewed or outliers are important. Use mean and standard deviation when the distribution is reasonably symmetric and the mean is an appropriate centre.

## Worked-Thinking Routine

1. Identify the data type and whether it is raw or grouped.
2. Choose a diagram that matches the question.
3. Describe shape before calculating.
4. Calculate centre and spread with clear units.
5. If grouped data are used, remember that midpoint calculations are estimates.
6. Interpret every summary in the context of the data.

## Common Mistakes

- Treating a histogram as a bar chart and ignoring class width.
- Forgetting that histogram area, not height alone, represents frequency.
- Using class midpoints without recognising the result as an estimate.
- Comparing means without considering spread.
- Letting an outlier dominate the interpretation.
- Applying coded-data transformations to standard deviation incorrectly.

## Quick Self-Check

- Can you choose between a histogram, cumulative frequency graph, box plot, and stem-and-leaf diagram?
- Can you explain why histogram area represents frequency?
- Can you estimate quartiles and percentiles from a cumulative frequency graph?
- Can you calculate mean and standard deviation from raw, grouped, or coded totals?
- Can you compare two distributions using centre, spread, and shape?

## Connections

- [[20 Mathematics/03 Probability and Statistics/06 Sampling Estimation and Hypothesis Tests/00 Overview|Sampling, Estimation and Hypothesis Tests]]

## Study Sequence

1. Practise choosing representations from short data descriptions.
2. Draw and interpret stem-and-leaf diagrams, box plots, histograms, and cumulative frequency graphs.
3. Calculate centre and spread for raw data.
4. Repeat with grouped data and coded totals.
5. Write short comparison paragraphs using centre, spread, shape, and context.
