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

- Place this after [5 System Software](../05%20System%20Software/00%20Overview.md).
- Trace a scheduling routine on a small set of processes with arrival and burst times.
- Move an expression through infix, BNF, RPN, and back to check each stage.

## Practice Directions

- Compare scheduling routines for a given set of processes.
- Explain the difference between paging and segmentation.
- Convert an expression to RPN and evaluate it.

## Learning Materials

- [Lecture Notes](10%20Lecture%20Notes.md)
- [中文讲义](10%20Lecture%20Notes.zh-CN.md)
- [Worked Examples](20%20Worked%20Examples.md)
- [Key Practice Problems](30%20Key%20Practice%20Problems.md)
- [Key Practice Solutions](31%20Key%20Practice%20Solutions.md)
- [Review Checklist](80%20Review%20Checklist.md)

## Connections and Extensions

- [System Software](../05%20System%20Software/00%20Overview.md) is the foundation for OS purposes, utilities, translators, libraries, and IDE support; this topic opens up the internal mechanisms.
- [Processor Fundamentals](../04%20Processor%20Fundamentals/00%20Overview.md) supplies interrupts, registers, program counter state, and fetch-execute ideas used when the kernel switches processes.
- [Hardware and Virtual Machines](../15%20Hardware%20and%20Virtual%20Machines/00%20Overview.md) connects through virtual machines, processor families, interrupt costs, and resource sharing.
- [Programming](../11%20Programming/00%20Overview.md) and [Further Programming](../20%20Further%20Programming/00%20Overview.md) connect to compilation, BNF grammar, RPN evaluation, and the source code that translators process.

## Common Traps

- Confusing paging with segmentation.
- Listing compilation stages out of order.
- Treating RPN as a notation only, rather than a stack-based evaluation method.
