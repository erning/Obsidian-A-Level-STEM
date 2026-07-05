---
title: Counting and Probability Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/03 Probability and Statistics/02 Counting and Probability/00 Overview|Counting and Probability]]"
status: active
tags:
  - mathematics/statistics
  - worked-examples
---

# Counting and Probability Worked Examples

These examples model the 9709 S1 route through permutations, combinations,
repeated objects, restrictions in a line, elementary probability, tree
diagrams, Venn diagrams, independence, and conditional probability.

## Source Route

- CAIE Mathematics 9709 sections 5.2 and 5.3: selections, arrangements in a
  line, repeated objects, restrictions, enumeration of equally likely outcomes,
  addition and multiplication of probabilities, exclusive and independent
  events, and simple conditional probability.

## Example 1: Permutation or Combination

**Prompt.** From $8$ students, choose $3$ for a committee. Then choose a
president, secretary, and treasurer from the same $8$ students. How many
outcomes are possible in each case?

**Solution.**

For the committee, order does not matter:

$$
\binom83=56.
$$

For the three roles, order matters:

$$
{}^8P_3=8(7)(6)=336.
$$

**Check.** The role count is larger because the same three students can be
assigned to roles in different ways.

## Example 2: Repeated Letters

**Prompt.** How many different arrangements are there of the letters in
NEEDLESS?

**Solution.**

There are $8$ letters, with $3$ Es and $2$ Ss. Divide by the factorials of the
repeated counts:

$$
\frac{8!}{3!2!}=3360.
$$

**Check.** Without division, identical Es and Ss would be overcounted.

## Example 3: People Together and Not Together

**Prompt.** Six people stand in a line. How many arrangements have Alex and
Bo together? How many have Alex and Bo not together?

**Solution.**

For together, treat Alex and Bo as one block. There are $5$ objects to arrange
and $2$ orders inside the block:

$$
5!2=240.
$$

Total arrangements are

$$
6!=720.
$$

Therefore the number with Alex and Bo not together is

$$
720-240=480.
$$

**Check.** "Not together" is easier by complement.

## Example 4: Enumerating Dice Outcomes

**Prompt.** Two fair dice are thrown. Find the probability that the sum is $7$
or the dice show a double.

**Solution.**

There are $36$ equally likely ordered outcomes. The sum is $7$ in $6$ cases:

$$
(1,6),(2,5),(3,4),(4,3),(5,2),(6,1).
$$

A double occurs in $6$ cases:

$$
(1,1),(2,2),(3,3),(4,4),(5,5),(6,6).
$$

The two events do not overlap, so

$$
P=\frac{6+6}{36}=\frac13.
$$

**Check.** No double has sum $7$.

## Example 5: Tree Diagram Without Replacement

**Prompt.** A bag contains $5$ red and $3$ blue balls. Two balls are drawn
without replacement. Find the probability that both are red, and the
probability that the colours are different.

**Solution.**

Both red:

$$
\frac58\cdot\frac47=\frac{5}{14}.
$$

Different colours can happen in two orders:

$$
RB \quad \text{or}\quad BR.
$$

Thus

$$
P(\text{different})
=\frac58\cdot\frac37+\frac38\cdot\frac57
=\frac{15}{28}.
$$

**Check.** Probabilities change after the first draw because there is no
replacement.

## Example 6: Venn Diagram and Independence

**Prompt.** Events $A$ and $B$ have $P(A)=0.6$, $P(B)=0.5$, and
$P(A\cap B)=0.3$. Find $P(A\cup B)$ and $P(A\mid B)$. Are $A$ and $B$
independent?

**Solution.**

Use the addition rule:

$$
P(A\cup B)=0.6+0.5-0.3=0.8.
$$

Conditional probability gives

$$
P(A\mid B)=\frac{P(A\cap B)}{P(B)}
=\frac{0.3}{0.5}=0.6.
$$

Since

$$
P(A)P(B)=0.6(0.5)=0.3=P(A\cap B),
$$

the events are independent.

**Check.** $P(A\mid B)=P(A)$ also confirms independence.

## Example 7: Conditional Probability from a Tree

**Prompt.** A component comes from machine A with probability $0.7$ and from
machine B with probability $0.3$. Machine A makes defective components with
probability $0.02$, and machine B with probability $0.05$. Find the
probability that a defective component came from A.

**Solution.**

The probability of a defective component is

$$
P(D)=0.7(0.02)+0.3(0.05)=0.029.
$$

The probability that it came from A and is defective is

$$
0.7(0.02)=0.014.
$$

Therefore

$$
P(A\mid D)=\frac{0.014}{0.029}=0.483
$$

to 3 s.f.

**Check.** This is not $0.7$, because conditioning on defect changes the
sample space.

## Example 8: Exclusive Is Not the Same as Independent

**Prompt.** Events $A$ and $B$ are mutually exclusive, with $P(A)=0.2$ and
$P(B)=0.3$. Are they independent?

**Solution.**

Mutually exclusive means

$$
P(A\cap B)=0.
$$

But

$$
P(A)P(B)=0.2(0.3)=0.06.
$$

Since

$$
P(A\cap B)\ne P(A)P(B),
$$

the events are not independent.

**Check.** If $A$ happens, $B$ cannot happen, so knowing $A$ has occurred does
change the probability of $B$.
