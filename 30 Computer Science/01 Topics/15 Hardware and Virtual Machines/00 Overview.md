---
title: 15 Hardware and Virtual Machines
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/computer-systems
---

# 15 Hardware and Virtual Machines

## Core Idea

This A Level topic extends sections 3 and 4 with processor architectures, parallelism, virtual machines, and the Boolean algebra needed to design and simplify logic circuits.

## Source Alignment

- 9618 A Level section 15 Hardware and Virtual Machines
- 15.1 Processors, Parallel Processing and Virtual Machines
- 15.2 Boolean Algebra and Logic Circuits
- Paper 3

## What to Learn

- RISC versus CISC processors; differences and interrupt handling on each.
- Pipelining and registers in RISC processors.
- Four basic architectures: SISD, SIMD, MISD, MIMD.
- Characteristics of massively parallel computers.
- Virtual machines: concept, role, benefits, and limitations.
- Truth tables for logic circuits including half adders and full adders; gates may have more than two inputs.
- Flip-flops (SR, JK) as data storage elements; drawing the circuit and deriving the truth table.
- Boolean algebra; De Morgan's laws; simplifying circuits and expressions.
- Karnaugh maps (K-maps): purpose, benefits, and solving logic problems.

## How to Study

- Place this after [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|4 Processor Fundamentals]] and [[30 Computer Science/01 Topics/03 Hardware/00 Overview|3 Hardware]].
- Simplify each circuit in two ways (Boolean algebra and K-map) and check the answers agree.
- Trace a flip-flop by watching its outputs across clock transitions.

## Practice Directions

- Compare RISC and CISC for a given use.
- Simplify a logic expression using De Morgan's laws and again using a K-map.
- Produce a truth table for a half adder or full adder.

## Learning Materials

- [[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/10 Lecture Notes|Lecture Notes]]
- [[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/10 Lecture Notes.zh-CN|中文讲义]]
- [[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/20 Worked Examples|Worked Examples]]
- [[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/30 Key Practice Problems|Key Practice Problems]]
- [[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/31 Key Practice Solutions|Key Practice Solutions]]
- [[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/80 Review Checklist|Review Checklist]]

## Connections and Extensions

- [[30 Computer Science/01 Topics/03 Hardware/00 Overview|Hardware]] supplies the logic gates, memory technologies, storage devices, and control ideas that are extended into adders, flip-flops, and larger processor systems.
- [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]] prepares the CPU, register, interrupt, and addressing ideas that become RISC/CISC comparisons and Flynn architectures here.
- [[30 Computer Science/01 Topics/16 System Software/00 Overview|System Software]] connects to virtual machines, interrupt handling, scheduling, memory management, and the way software uses processor and memory resources.
- [[30 Computer Science/01 Topics/01 Information Representation/00 Overview|Information Representation]] underpins the binary addition and Boolean behaviour used by adders, flip-flops, and logic simplification.

## Common Traps

- Misapplying De Morgan's law by forgetting to invert.
- Grouping K-map cells that do not share a variable.
- Treating a virtual machine as identical to an emulator.
