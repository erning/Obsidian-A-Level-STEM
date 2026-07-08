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

- [[30 Computer Science/01 Topics/11 Programming/10 Lecture Notes|Lecture Notes]]
- [[30 Computer Science/01 Topics/11 Programming/10 Lecture Notes.zh-CN|中文讲义]]
- [[30 Computer Science/01 Topics/11 Programming/20 Worked Examples|Worked Examples]]
- [[30 Computer Science/01 Topics/11 Programming/30 Key Practice Problems|Key Practice Problems]]
- [[30 Computer Science/01 Topics/11 Programming/31 Key Practice Solutions|Key Practice Solutions]]
- [[30 Computer Science/01 Topics/11 Programming/80 Review Checklist|Review Checklist]]

## Connections and Extensions

- [[30 Computer Science/01 Topics/09 Algorithm Design and Problem-solving/00 Overview|Algorithm Design and Problem-solving]] supplies the designs, constructs, and refinement habits this topic implements as pseudocode.
- [[30 Computer Science/01 Topics/10 Data Types and Structures/00 Overview|Data Types and Structures]] supplies the types, arrays, records, files, and ADTs used in declarations and routines.
- [[30 Computer Science/01 Topics/12 Software Development/00 Overview|Software Development]] places programming inside a design, testing, and maintenance cycle.
- [[30 Computer Science/01 Topics/20 Further Programming/00 Overview|Further Programming]] extends this foundation into programming paradigms, file processing, and exception handling.
- Use the [[assets/syllabus/9618 - Computer Science/CAIE Computer Science 9618 Pseudocode Guide 2027-2029.pdf|Pseudocode Guide]] as the notation reference.

## Common Traps

- Confusing parameters passed by reference with those passed by value.
- Using a pre-condition loop where the body must run at least once.
- Forgetting that a function's return value replaces its call in an expression.
