---
title: 16 System Software
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/computer-systems
---

# 16 System Software

## Core Idea

This A Level topic extends section 5 with the internals of an operating system (process scheduling and memory management) and the stages by which translators turn source code into executable form.

## Source Alignment

- 9618 A Level section 16 System Software
- 16.1 Purposes of an Operating System (OS)
- 16.2 Translation Software
- Paper 3

## What to Learn

- How an OS maximises the use of resources.
- How the user interface hides hardware complexity from the user.
- Process management: multi-tasking and the concept of a process; process states (running, ready, blocked).
- Scheduling routines: round robin, shortest job first, first come first served, shortest remaining time; their function and benefits.
- The kernel as an interrupt handler and how interrupt handling manages low-level scheduling.
- Virtual memory, paging, and segmentation; the difference between paging and segmentation; page replacement; disk thrashing.
- How an interpreter can execute programs without producing a translated version.
- Stages of compilation: lexical analysis, syntax analysis, code generation, and optimisation.
- Expressing the grammar of a language using syntax diagrams or Backus-Naur Form (BNF).
- Reverse Polish Notation (RPN) for evaluating expressions.

## How to Study

- Place this after [[30 Computer Science/01 Topics/05 System Software/00 Overview|5 System Software]].
- Trace a scheduling routine on a small set of processes with arrival and burst times.
- Move an expression through infix, BNF, RPN, and back to check each stage.

## Practice Directions

- Compare scheduling routines for a given set of processes.
- Explain the difference between paging and segmentation.
- Convert an expression to RPN and evaluate it.

## Learning Materials

- [[30 Computer Science/01 Topics/16 System Software/10 Lecture Notes|Lecture Notes]]
- [[30 Computer Science/01 Topics/16 System Software/10 Lecture Notes.zh-CN|中文讲义]]
- [[30 Computer Science/01 Topics/16 System Software/20 Worked Examples|Worked Examples]]
- [[30 Computer Science/01 Topics/16 System Software/30 Key Practice Problems|Key Practice Problems]]
- [[30 Computer Science/01 Topics/16 System Software/31 Key Practice Solutions|Key Practice Solutions]]
- [[30 Computer Science/01 Topics/16 System Software/80 Review Checklist|Review Checklist]]

## Connections

- [[30 Computer Science/01 Topics/05 System Software/00 Overview|5 System Software]] is the AS foundation this topic extends.
- [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|4 Processor Fundamentals]] supplies the interrupts and registers the scheduler uses.

## Common Traps

- Confusing paging with segmentation.
- Listing compilation stages out of order.
- Treating RPN as a notation only, rather than a stack-based evaluation method.
