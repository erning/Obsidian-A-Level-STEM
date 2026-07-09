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

- Place this after [4 Processor Fundamentals](../04%20Processor%20Fundamentals/00%20Overview.md) and [3 Hardware](../03%20Hardware/00%20Overview.md).
- Simplify each circuit in two ways (Boolean algebra and K-map) and check the answers agree.
- Trace a flip-flop by watching its outputs across clock transitions.

## Practice Directions

- Compare RISC and CISC for a given use.
- Simplify a logic expression using De Morgan's laws and again using a K-map.
- Produce a truth table for a half adder or full adder.

## Learning Materials

- [Lecture Notes](10%20Lecture%20Notes.md)
- [中文讲义](10%20Lecture%20Notes.zh-CN.md)
- [Worked Examples](20%20Worked%20Examples.md)
- [Key Practice Problems](30%20Key%20Practice%20Problems.md)
- [Key Practice Solutions](31%20Key%20Practice%20Solutions.md)
- [Review Checklist](80%20Review%20Checklist.md)

## Connections and Extensions

- [Hardware](../03%20Hardware/00%20Overview.md) supplies the logic gates, memory technologies, storage devices, and control ideas that are extended into adders, flip-flops, and larger processor systems.
- [Processor Fundamentals](../04%20Processor%20Fundamentals/00%20Overview.md) prepares the CPU, register, interrupt, and addressing ideas that become RISC/CISC comparisons and Flynn architectures here.
- [System Software](../16%20System%20Software/00%20Overview.md) connects to virtual machines, interrupt handling, scheduling, memory management, and the way software uses processor and memory resources.
- [Information Representation](../01%20Information%20Representation/00%20Overview.md) underpins the binary addition and Boolean behaviour used by adders, flip-flops, and logic simplification.

## Common Traps

- Misapplying De Morgan's law by forgetting to invert.
- Grouping K-map cells that do not share a variable.
- Treating a virtual machine as identical to an emulator.
