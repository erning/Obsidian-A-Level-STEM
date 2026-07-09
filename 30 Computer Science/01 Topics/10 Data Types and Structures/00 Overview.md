---
title: 10 Data Types and Structures
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/programming
---

# 10 Data Types and Structures

## Core Idea

Programs act on data, and the way data is grouped changes what the program can do. This topic covers the basic pseudocode data types, records, arrays, files, and the first abstract data types.

## Source Alignment

- 9618 AS section 10 Data Types and Structures
- 10.1 Data Types and Records
- 10.2 Arrays
- 10.3 Files
- 10.4 Introduction to Abstract Data Types (ADT)
- Paper 2

## What to Learn

- Selecting appropriate data types: INTEGER, REAL, CHAR, STRING, BOOLEAN, DATE, ARRAY, FILE.
- Record structures: purpose, defining, reading, and writing in pseudocode.
- Arrays: index, upper and lower bound; 1D and 2D arrays; processing array data.
- Bubble sort and linear search.
- Text file handling in pseudocode.
- Abstract data types: a collection of data and a set of operations on it.
- Stack, queue, and linked list as ADTs; key features and justification for a given task.
- Adding, editing, and deleting data in these structures (no pseudocode required at AS).
- How a stack, queue, and linked list can be implemented using arrays.

## How to Study

- Pick the data type by asking what values are allowed and what operations are needed.
- Trace a bubble sort and a linear search on a small data set by hand.
- For each ADT, name the operations (push/pop, enqueue/dequeue, insert/delete) and the order they enforce.

## Practice Directions

- Define and use a record structure in pseudocode.
- Write pseudocode to process a 1D or 2D array.
- Describe how a queue or stack can be implemented using an array.

## Learning Materials

- [Lecture Notes](10%20Lecture%20Notes.md)
- [中文讲义](10%20Lecture%20Notes.zh-CN.md)
- [Worked Examples](20%20Worked%20Examples.md)
- [Key Practice Problems](30%20Key%20Practice%20Problems.md)
- [Key Practice Solutions](31%20Key%20Practice%20Solutions.md)
- [Review Checklist](80%20Review%20Checklist.md)

## Connections and Extensions

- [Algorithm Design and Problem-solving](../09%20Algorithm%20Design%20and%20Problem-solving/00%20Overview.md) supplies the pseudocode notation and tracing habits used to process these structures.
- [Programming](../11%20Programming/00%20Overview.md) uses these data types in declarations, expressions, procedures, and functions.
- [Computational Thinking and Problem-solving](../19%20Computational%20Thinking%20and%20Problem-solving/00%20Overview.md) turns stacks, queues, linked lists, trees, searches, and sorts into full algorithmic operations.
- [Databases](../08%20Databases/00%20Overview.md) connects records, fields, keys, and structured data storage to larger data management.
- [Data Representation](../13%20Data%20Representation/00%20Overview.md) extends the storage view into file organisation and user-defined types.

## Common Traps

- Choosing REAL where INTEGER is correct (or vice versa).
- Forgetting the upper and lower bounds of an array.
- Treating an ADT as identical to its array implementation.
