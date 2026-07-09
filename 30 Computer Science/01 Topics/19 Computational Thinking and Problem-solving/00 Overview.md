---
title: 19 Computational Thinking and Problem-solving
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/programming
---

# 19 Computational Thinking and Problem-solving

## Core Idea

This A Level topic extends section 9 with the standard searching and sorting algorithms, the operations on abstract data types, recursion, and the Big O notation used to compare algorithms.

## Source Alignment

- 9618 A Level section 19 Computational thinking and Problem-solving
- 19.1 Algorithms
- 19.2 Recursion
- Paper 3 and Paper 4 (except low-level and declarative programming)

## What to Learn

- Linear and binary search; writing each; the conditions for binary search; how performance varies with data size.
- Insertion sort and bubble sort; writing each; how performance depends on initial order and data size.
- Abstract data types: finding an item in a linked list and a binary tree; inserting into a stack, queue, linked list, and binary tree; deleting from a stack, queue, and linked list.
- The graph as an ADT; its key features and justification for a given task (no code required).
- Implementing ADTs from built-in types or other ADTs: stack, queue, linked list, dictionary, binary tree.
- Comparing algorithms by time taken and memory used; Big O notation for time and space complexity.
- Recursion: essential features, expression in a language, writing and tracing, and when it is beneficial.
- How a compiler translates recursive code using stacks and unwinding.

## How to Study

- Place this after [9 Algorithm Design and Problem-solving](../09%20Algorithm%20Design%20and%20Problem-solving/00%20Overview.md) and [10 Data Types and Structures](../10%20Data%20Types%20and%20Structures/00%20Overview.md).
- Trace every search and sort on a small data set before analysing it.
- For recursion, draw the call stack and watch each call push and then unwind.

## Practice Directions

- Write and trace linear and binary search and insertion and bubble sort.
- Write algorithms to insert, find, and delete from named ADTs.
- Express the time and space complexity of an algorithm in Big O.

## Learning Materials

- [Lecture Notes](10%20Lecture%20Notes.md)
- [中文讲义](10%20Lecture%20Notes.zh-CN.md)
- [Worked Examples](20%20Worked%20Examples.md)
- [Key Practice Problems](30%20Key%20Practice%20Problems.md)
- [Key Practice Solutions](31%20Key%20Practice%20Solutions.md)
- [Review Checklist](80%20Review%20Checklist.md)

## Connections and Extensions

- [Algorithm Design and Problem-solving](../09%20Algorithm%20Design%20and%20Problem-solving/00%20Overview.md) is the foundation this topic extends: abstraction, decomposition, constructs, pseudocode, and tracing all carry forward.
- [Data Types and Structures](../10%20Data%20Types%20and%20Structures/00%20Overview.md) supplies the arrays, stacks, queues, linked lists, and files that these algorithms operate on.
- [Programming](../11%20Programming/00%20Overview.md) supplies the routine structure, parameter passing, and control-flow fluency needed to write these algorithms cleanly.
- [Further Programming](../20%20Further%20Programming/00%20Overview.md) reuses the same algorithmic thinking in paradigms, files, exception handling, and low-level links.
- [Artificial Intelligence](../18%20Artificial%20Intelligence/00%20Overview.md) depends on algorithm choice, data representation, and complexity limits when systems scale.

## Common Traps

- Applying binary search to unsorted data.
- Inserting into a queue at the wrong end.
- Forgetting the base case that stops recursion.
