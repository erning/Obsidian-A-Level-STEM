---
title: 04 Processor Fundamentals
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/computer-systems
---

# 04 Processor Fundamentals

## Core Idea

The processor turns the stored-program concept into action. This topic covers CPU architecture, the fetch-execute cycle, assembly language, and the bitwise operations the processor performs.

## Source Alignment

- 9618 AS section 4 Processor Fundamentals
- 4.1 Central Processing Unit (CPU) Architecture
- 4.2 Assembly Language
- 4.3 Bit manipulation
- Paper 1

## What to Learn

- Von Neumann model and the stored-program concept.
- Registers: PC, MDR, MAR, ACC, IX, CIR, Status Register; general purpose versus special purpose.
- ALU, Control Unit, system clock, and Immediate Access Store (IAS).
- Address, data, and control buses; how data moves between components.
- Performance factors: processor type, number of cores, bus width, clock speed, cache.
- Ports: USB, HDMI, VGA.
- Fetch-execute cycle stages; register-transfer notation.
- Interrupts: causes, Interrupt Service Routine (ISR), and how the cycle detects and handles them.
- Assembly language versus machine code; two-pass assembler stages.
- Tracing assembly programs; instruction groups and addressing modes (immediate, direct, indirect, indexed, relative).
- Bit manipulation: logical, arithmetic, and cyclic shifts; bit masking to test and set bits.

## How to Study

- Learn the role of each register before tracing the cycle.
- Walk the fetch-execute cycle step by step in register-transfer notation.
- Trace assembly programs using the instruction set table in the syllabus (LDM, LDD, ADD, SUB, JMP, CMP, JPE, JPN, and so on).

## Practice Directions

- Describe the fetch-execute cycle using register-transfer notation.
- Trace a given assembly program and state the final register values.
- Apply logical, arithmetic, and cyclic shifts and use bit masks.

## Learning Materials

- [Lecture Notes](10%20Lecture%20Notes.md)
- [中文讲义](10%20Lecture%20Notes.zh-CN.md)
- [Worked Examples](20%20Worked%20Examples.md)
- [Key Practice Problems](30%20Key%20Practice%20Problems.md)
- [Key Practice Solutions](31%20Key%20Practice%20Solutions.md)
- [Review Checklist](80%20Review%20Checklist.md)

## Connections and Extensions

- [Hardware](../03%20Hardware/00%20Overview.md) supplies the gates, memory technologies, ports, and buses that this topic turns into CPU execution.
- [Information Representation](../01%20Information%20Representation/00%20Overview.md) and [Data Representation](../13%20Data%20Representation/00%20Overview.md) support the binary, hexadecimal, signed-value, and bit-pattern work used in machine code, shifts, and masks.
- [Hardware and Virtual Machines](../15%20Hardware%20and%20Virtual%20Machines/00%20Overview.md) extends this topic into RISC/CISC design, parallel architectures, and virtual machines.
- [Further Programming](../20%20Further%20Programming/00%20Overview.md) revisits low-level execution ideas when programs work close to memory, data movement, and control flow.

## Common Traps

- Swapping MAR and MDR roles.
- Forgetting to update the Program Counter before fetching the next instruction.
- Confusing addressing modes when tracing assembly.
