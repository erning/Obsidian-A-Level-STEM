---
title: 11 Programming
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/programming
---

# 11 Programming

## Core Idea

This topic turns algorithm designs into working pseudocode. It covers variables and operators, the standard constructs, and the use of procedures and functions to structure code.

## Source Alignment

- 9618 AS section 11 Programming
- 11.1 Programming Basics
- 11.2 Constructs
- 11.3 Structured Programming
- Paper 2

## What to Learn

- Declaring and initialising constants; declaring variables; assigning values.
- Expressions with arithmetic and logical operators; input from keyboard and output to console.
- Built-in functions and library routines (any not in the pseudocode guide will be provided; string functions are always given).
- IF (with ELSE and nested IF) and CASE structures.
- Count-controlled, post-condition, and pre-condition loops; justifying one loop over another.
- Defining and using procedures; parameters passed by reference or by value.
- Defining and using functions; the return value replacing the call.
- Terminology: procedure/function header, interface, parameter, argument, return value.
- Writing efficient pseudocode.

## How to Study

- Decide the construct before writing it: is this a choice (selection) or a repeat (iteration)?
- For each loop, identify the counter, the condition, and where the body changes the counter.
- Choose procedure versus function by asking whether a value must be returned.

## Practice Directions

- Implement pseudocode from a flowchart or structured English description.
- Write each loop type for a suitable task.
- Write procedures and functions with parameters and use them correctly.

## Learning Materials

- [Lecture Notes](10%20Lecture%20Notes.md)
- [中文讲义](10%20Lecture%20Notes.zh-CN.md)
- [Worked Examples](20%20Worked%20Examples.md)
- [Key Practice Problems](30%20Key%20Practice%20Problems.md)
- [Key Practice Solutions](31%20Key%20Practice%20Solutions.md)
- [Review Checklist](80%20Review%20Checklist.md)

## Connections and Extensions

- [Algorithm Design and Problem-solving](../09%20Algorithm%20Design%20and%20Problem-solving/00%20Overview.md) supplies the designs, constructs, and refinement habits this topic implements as pseudocode.
- [Data Types and Structures](../10%20Data%20Types%20and%20Structures/00%20Overview.md) supplies the types, arrays, records, files, and ADTs used in declarations and routines.
- [Software Development](../12%20Software%20Development/00%20Overview.md) places programming inside a design, testing, and maintenance cycle.
- [Further Programming](../20%20Further%20Programming/00%20Overview.md) extends this foundation into programming paradigms, file processing, and exception handling.
- Use the [Pseudocode Guide](../../../assets/syllabus/9618%20-%20Computer%20Science/CAIE%20Computer%20Science%209618%20Pseudocode%20Guide%202027-2029.pdf) as the notation reference.

## Common Traps

- Confusing parameters passed by reference with those passed by value.
- Using a pre-condition loop where the body must run at least once.
- Forgetting that a function's return value replaces its call in an expression.
