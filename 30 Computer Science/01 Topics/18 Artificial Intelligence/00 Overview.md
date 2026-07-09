---
title: 18 Artificial Intelligence
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/advanced
---

# 18 Artificial Intelligence

## Core Idea

This A Level topic covers the core ideas behind modern AI: graphs as a structure for search, the algorithms that find paths through them, and the learning methods that let systems improve from data.

## Source Alignment

- 9618 A Level section 18 Artificial Intelligence (AI)
- 18.1 Artificial Intelligence
- Paper 3

## What to Learn

- How graphs aid AI: purpose and structure of a graph.
- A\* and Dijkstra's algorithms for graph search (candidates are not required to write algorithms to set up, access, or search graphs).
- How artificial neural networks have supported machine learning.
- Deep Learning, Machine Learning, and Reinforcement Learning, and the reasons for using each.
- Machine learning categories: supervised and unsupervised learning.
- Back propagation of errors and regression methods in machine learning.

## How to Study

- Note that AI also appears in [7 Ethics and Ownership](../07%20Ethics%20and%20Ownership/00%20Overview.md) as impact and applications; this topic is the technical basis.
- Compare Dijkstra and A\* on what each guarantees (shortest path versus heuristic-guided search).
- Place learning methods on a spectrum: supervised (labelled data), unsupervised (unlabelled), and reinforcement (reward signal).

## Practice Directions

- Describe the structure of a graph used for search.
- Compare Dijkstra and A\* for a given problem.
- Distinguish supervised from unsupervised learning for a given data set.

## Learning Materials

- [Lecture Notes](10%20Lecture%20Notes.md)
- [中文讲义](10%20Lecture%20Notes.zh-CN.md)
- [Worked Examples](20%20Worked%20Examples.md)
- [Key Practice Problems](30%20Key%20Practice%20Problems.md)
- [Key Practice Solutions](31%20Key%20Practice%20Solutions.md)
- [Review Checklist](80%20Review%20Checklist.md)

## Connections and Extensions

- [9 Algorithm Design and Problem-solving](../09%20Algorithm%20Design%20and%20Problem-solving/00%20Overview.md) prepares the tracing discipline used when following Dijkstra's algorithm and A\* step by step.
- [19 Computational Thinking and Problem-solving](../19%20Computational%20Thinking%20and%20Problem-solving/00%20Overview.md) treats the graph as an abstract data type: the structure searched here is the structure implemented and reasoned about there.
- [13 Data Representation](../13%20Data%20Representation/00%20Overview.md) connects to the way learning systems turn examples, labels, weights, and continuous predicted values into data that can be stored and processed.
- [15 Hardware and Virtual Machines](../15%20Hardware%20and%20Virtual%20Machines/00%20Overview.md) extends the performance side: larger search spaces and neural-network models depend on processing power, memory, and sometimes parallel execution.
- [7 Ethics and Ownership](../07%20Ethics%20and%20Ownership/00%20Overview.md) covers the social, economic, environmental, and responsibility questions raised by these technical methods.

## Common Traps

- Writing code for graph structures when the syllabus only asks for understanding.
- Confusing Machine Learning with Deep Learning.
- Forgetting that back propagation is about errors, not rewards.
