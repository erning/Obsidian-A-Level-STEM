---
title: Counting and Probability Lecture Notes
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/02 Counting and Probability/00 Overview|Counting and Probability]]"
status: active
tags:
  - mathematics/statistics
  - lecture-notes
---

# Counting and Probability Lecture Notes

Probability becomes reliable only after the sample space is clear. Counting is the craft of describing that sample space without omissions or double counting. In this topic, do not begin with a formula; begin with the experiment, the event, and the structure of the outcomes.

## Source Route

- 9709 5.2 Permutations and combinations
- 9709 5.3 Probability
- Coursebook route: 9709 Probability and Statistics 1 chapters on permutations, combinations, and probability.

## Visual Guide

![[assets/generated/mathematics/counting-and-probability.svg]]

Figure: use the probability tree to see how multi-stage sample spaces branch.

## 1. Counting Decisions

Most counting problems start with three questions.

1. Does order matter?
2. Is repetition allowed?
3. Are there restrictions such as "together", "not together", or fixed positions?

If order matters, use arrangements or permutations. If order does not matter, use combinations.

For $r$ ordered choices from $n$ distinct objects without repetition,

$$
{}^nP_r=\frac{n!}{(n-r)!}.
$$

For $r$ unordered choices from $n$ distinct objects,

$$
{}^nC_r=\binom nr=\frac{n!}{r!(n-r)!}.
$$

If objects repeat, divide by the factorials of repeated counts. For example, NEEDLESS has eight letters, with three Es and two Ss, so the number of different arrangements is

$$
\frac{8!}{3!2!}.
$$

The division is only for identical objects. If the question is about arranging people, books, or labelled cards, the objects are normally distinct unless the wording says otherwise.

## 2. Multiplication and Addition in Counting

The multiplication principle applies when a process is made of stages. If stage one has $a$ choices and stage two has $b$ choices for each first choice, there are $ab$ outcomes.

The addition principle applies when cases are alternatives that do not overlap. If case A has $a$ outcomes, case B has $b$ outcomes, and no outcome is in both cases, there are $a+b$ outcomes.

Restrictions often become easier after splitting into cases. For "two people must sit together", treat them as a block first, then arrange within the block. For "two people must not sit together", it is often easier to count all arrangements and subtract the together case.

Example: six distinct people include Alex and Bea. The number of lines in which Alex and Bea are not next to each other is

$$
6!-2!5!,
$$

because $6!$ counts all lines and $2!5!$ counts the lines where the block Alex-Bea or Bea-Alex appears.

## 3. Probability Language

The sample space is the set of possible outcomes. An event is a subset of the sample space. If all elementary outcomes are equally likely, then

$$
P(A)=\frac{\text{number of outcomes in }A}{\text{number of outcomes in the sample space}}.
$$

The complement of $A$ is $A'$, and

$$
P(A')=1-P(A).
$$

For two events,

$$
P(A\cup B)=P(A)+P(B)-P(A\cap B).
$$

If $A$ and $B$ are mutually exclusive, they cannot happen together, so

$$
P(A\cap B)=0.
$$

## 4. Conditional Probability and Independence

Conditional probability changes the sample space. The probability of $A$ given that $B$ has happened is

$$
P(A\mid B)=\frac{P(A\cap B)}{P(B)}.
$$

Events $A$ and $B$ are independent if knowing that one has occurred does not change the probability of the other. Equivalently,

$$
P(A\cap B)=P(A)P(B),
$$

or

$$
P(A\mid B)=P(A).
$$

Mutually exclusive and independent are different ideas. Two non-empty mutually exclusive events are not independent, because one occurring makes the other impossible.

Example: one card is drawn from a standard deck. Let $A$ be "the card is a heart" and $B$ be "the card is a spade". These events are mutually exclusive, so $P(A\cap B)=0$, but they are not independent because $P(A)P(B)=\frac14\cdot\frac14\ne 0$.

By contrast, let $C$ be "the card is a heart" and $D$ be "the card is a queen". Then

$$
P(C\cap D)=\frac1{52},\qquad P(C)P(D)=\frac14\cdot\frac4{52}=\frac1{52},
$$

so $C$ and $D$ are independent, although they are not mutually exclusive because the queen of hearts is in both events.

## 5. Diagrams

Use a Venn diagram when events overlap. It makes $A\cap B$, $A\cup B$, and complements visible.

Use a tree diagram for multi-stage processes, especially when probabilities change after each stage. Along one path, multiply probabilities. Across alternative paths that lead to the same event, add the path probabilities.

Tree example: a bag contains $3$ red and $2$ blue counters. Two counters are drawn without replacement. The probability that the second counter is red is

$$
P(RR)+P(BR)=\frac35\cdot\frac24+\frac25\cdot\frac34=\frac35.
$$

The second-stage probabilities depend on the first draw, so the tree records the conditional probabilities directly.

A table is useful for two dice, two categorical variables, or any situation where enumeration is safer than clever algebra.

## Worked-Thinking Routine

1. Define the experiment and event in words.
2. Decide whether outcomes are equally likely.
3. If counting is needed, decide whether order matters and whether repetition is allowed.
4. Choose a representation: list, table, tree, Venn diagram, permutation, or combination.
5. Check for overlap before adding cases.
6. Interpret the probability in context.

## Common Mistakes

- Using permutations when combinations are needed.
- Assuming events are independent without evidence.
- Counting the same outcome twice.
- Adding overlapping cases without subtracting the overlap.
- Treating "without replacement" as if probabilities stay constant.
- Forgetting to divide arrangements by repeated identical objects.
- Confusing $P(A\mid B)$ with $P(B\mid A)$.

## Quick Self-Check

- Can you decide whether order matters?
- Can you count arrangements with repeated letters?
- Can you explain the difference between mutually exclusive and independent events?
- Can you build a tree diagram for sampling without replacement?
- Can you use conditional probability without changing the meaning of the event?

## Connections

- [[20 Mathematics/03 Probability and Statistics/03 Discrete Random Variables/00 Overview|Discrete Random Variables]]

## Study Sequence

1. Practise permutations and combinations separately.
2. Add repeated objects and restrictions.
3. Translate counting results into probabilities.
4. Work with complements, unions, intersections, and conditional probability.
5. Use tree diagrams for multi-stage probability.
