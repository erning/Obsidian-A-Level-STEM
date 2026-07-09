---
title: 05 System Software
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/computer-systems
---

# 05 System Software

## Core Idea

System software sits between the hardware and the user's programs. This topic covers what an operating system does and how language translators turn source code into something the processor can run.

## Source Alignment

- 9618 AS section 5 System Software
- 5.1 Operating Systems
- 5.2 Language Translators
- Paper 1

## What to Learn

- Why a computer needs an Operating System.
- OS management tasks: memory, file, security, hardware (input/output/peripherals), and process management.
- Utility software: disk formatter, virus checker, defragmentation, disk contents analysis/repair, file compression, backup.
- Program libraries and Dynamic Link Library (DLL) files and their benefits.
- The need for assemblers, compilers, and interpreters; benefits and drawbacks of each.
- Partial compilation and partial interpretation (for example, Java in console mode).
- IDE features: context-sensitive prompts, dynamic syntax checks, prettyprint, expand/collapse, single stepping, breakpoints, watch variables and expressions.

## How to Study

- Group OS tasks by what is being managed (memory, files, processes, hardware, security).
- Justify compiler versus interpreter for a given scenario rather than memorising a list.
- Map each IDE feature to a stage of development (writing, checking, presenting, debugging).

## Practice Directions

- Justify the choice of compiler or interpreter for a given use.
- Describe how a DLL benefits a developer.
- Match IDE features to the problem they solve.

## Learning Materials

- [Lecture Notes](10%20Lecture%20Notes.md)
- [中文讲义](10%20Lecture%20Notes.zh-CN.md)
- [Worked Examples](20%20Worked%20Examples.md)
- [Key Practice Problems](30%20Key%20Practice%20Problems.md)
- [Key Practice Solutions](31%20Key%20Practice%20Solutions.md)
- [Review Checklist](80%20Review%20Checklist.md)

## Connections and Extensions

- [System Software](../16%20System%20Software/00%20Overview.md) extends this topic from OS roles and translator types into process scheduling, virtual memory, compilation stages, BNF, and RPN.
- [Programming](../11%20Programming/00%20Overview.md) produces the source code that assemblers, compilers, interpreters, IDEs, and libraries support.
- [Hardware](../03%20Hardware/00%20Overview.md) supplies the memory, storage, input/output devices, and peripherals that the OS manages through drivers and utilities.
- [Processor Fundamentals](../04%20Processor%20Fundamentals/00%20Overview.md) explains why translated programs must become instructions that the CPU can fetch, decode, execute, and interrupt.

## Common Traps

- Listing utility software as if it were part of the OS kernel.
- Claiming Java is "only compiled" or "only interpreted".
- Confusing library files with application files.
