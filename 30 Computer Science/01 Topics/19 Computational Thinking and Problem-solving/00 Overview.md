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

- Place this after [[30 Computer Science/01 Topics/09 Algorithm Design and Problem-solving/00 Overview|9 Algorithm Design and Problem-solving]] and [[30 Computer Science/01 Topics/10 Data Types and Structures/00 Overview|10 Data Types and Structures]].
- Trace every search and sort on a small data set before analysing it.
- For recursion, draw the call stack and watch each call push and then unwind.

## Practice Directions

- Write and trace linear and binary search and insertion and bubble sort.
- Write algorithms to insert, find, and delete from named ADTs.
- Express the time and space complexity of an algorithm in Big O.

## Learning Materials

- [[30 Computer Science/01 Topics/19 Computational Thinking and Problem-solving/10 Lecture Notes|Lecture Notes]]
- [[30 Computer Science/01 Topics/19 Computational Thinking and Problem-solving/10 Lecture Notes.zh-CN|中文讲义]]
- [[30 Computer Science/01 Topics/19 Computational Thinking and Problem-solving/20 Worked Examples|Worked Examples]]
- [[30 Computer Science/01 Topics/19 Computational Thinking and Problem-solving/30 Key Practice Problems|Key Practice Problems]]
- [[30 Computer Science/01 Topics/19 Computational Thinking and Problem-solving/31 Key Practice Solutions|Key Practice Solutions]]
- [[30 Computer Science/01 Topics/19 Computational Thinking and Problem-solving/80 Review Checklist|Review Checklist]]

## Connections and Extensions

- [[30 Computer Science/01 Topics/09 Algorithm Design and Problem-solving/00 Overview|Algorithm Design and Problem-solving]] is the foundation this topic extends: abstraction, decomposition, constructs, pseudocode, and tracing all carry forward.
- [[30 Computer Science/01 Topics/10 Data Types and Structures/00 Overview|Data Types and Structures]] supplies the arrays, stacks, queues, linked lists, and files that these algorithms operate on.
- [[30 Computer Science/01 Topics/11 Programming/00 Overview|Programming]] supplies the routine structure, parameter passing, and control-flow fluency needed to write these algorithms cleanly.
- [[30 Computer Science/01 Topics/20 Further Programming/00 Overview|Further Programming]] reuses the same algorithmic thinking in paradigms, files, exception handling, and low-level links.
- [[30 Computer Science/01 Topics/18 Artificial Intelligence/00 Overview|Artificial Intelligence]] depends on algorithm choice, data representation, and complexity limits when systems scale.

## Common Traps

- Applying binary search to unsorted data.
- Inserting into a queue at the wrong end.
- Forgetting the base case that stops recursion.
