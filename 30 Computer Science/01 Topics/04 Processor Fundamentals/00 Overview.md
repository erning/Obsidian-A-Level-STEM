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

- [[30 Computer Science/01 Topics/04 Processor Fundamentals/10 Lecture Notes|Lecture Notes]]
- [[30 Computer Science/01 Topics/04 Processor Fundamentals/10 Lecture Notes.zh-CN|中文讲义]]
- [[30 Computer Science/01 Topics/04 Processor Fundamentals/20 Worked Examples|Worked Examples]]
- [[30 Computer Science/01 Topics/04 Processor Fundamentals/30 Key Practice Problems|Key Practice Problems]]
- [[30 Computer Science/01 Topics/04 Processor Fundamentals/31 Key Practice Solutions|Key Practice Solutions]]
- [[30 Computer Science/01 Topics/04 Processor Fundamentals/80 Review Checklist|Review Checklist]]

## Connections and Extensions

- [[30 Computer Science/01 Topics/03 Hardware/00 Overview|Hardware]] supplies the gates, memory technologies, ports, and buses that this topic turns into CPU execution.
- [[30 Computer Science/01 Topics/01 Information Representation/00 Overview|Information Representation]] and [[30 Computer Science/01 Topics/13 Data Representation/00 Overview|Data Representation]] support the binary, hexadecimal, signed-value, and bit-pattern work used in machine code, shifts, and masks.
- [[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/00 Overview|Hardware and Virtual Machines]] extends this topic into RISC/CISC design, parallel architectures, and virtual machines.
- [[30 Computer Science/01 Topics/20 Further Programming/00 Overview|Further Programming]] revisits low-level execution ideas when programs work close to memory, data movement, and control flow.

## Common Traps

- Swapping MAR and MDR roles.
- Forgetting to update the Program Counter before fetching the next instruction.
- Confusing addressing modes when tracing assembly.
