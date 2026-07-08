---
title: 03 Hardware
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/computer-systems
---

# 03 Hardware

## Core Idea

This topic covers the physical components a computer uses to take in data, hold it, and produce output, together with the gates that turn switches into logic.

## Source Alignment

- 9618 AS section 3 Hardware
- 3.1 Computers and their components
- 3.2 Logic Gates and Logic Circuits
- Paper 1

## What to Learn

- Need for input, output, primary memory, and secondary (including removable) storage.
- Embedded systems: benefits and drawbacks.
- Principal operations of hardware devices: laser printer, 3D printer, microphone, speakers, magnetic hard disk, solid state (flash) memory, optical disc reader/writer, touchscreen, VR headset.
- Use of buffers.
- RAM versus ROM; SRAM versus DRAM and the reasons for choosing each.
- PROM, EPROM, and EEPROM.
- Monitoring versus control systems: sensors, actuators, and feedback.
- Logic gates: NOT, AND, OR, NAND, NOR, XOR; their functions and truth tables.
- Converting between problem statement, logic expression, logic circuit, and truth table.

## How to Study

- Group devices by role (input, output, storage, processing) before learning operations.
- Build every gate's truth table from its definition, not from memory.
- Practise converting in both directions: statement to circuit, circuit to expression, expression to truth table.

## Practice Directions

- Compare SRAM and DRAM for a given device.
- Construct a logic circuit from a problem statement and derive its truth table.
- Simplify a description into a logic expression and then a circuit.

## Learning Materials

- [[30 Computer Science/01 Topics/03 Hardware/10 Lecture Notes|Lecture Notes]]
- [[30 Computer Science/01 Topics/03 Hardware/10 Lecture Notes.zh-CN|中文讲义]]
- [[30 Computer Science/01 Topics/03 Hardware/20 Worked Examples|Worked Examples]]
- [[30 Computer Science/01 Topics/03 Hardware/30 Key Practice Problems|Key Practice Problems]]
- [[30 Computer Science/01 Topics/03 Hardware/31 Key Practice Solutions|Key Practice Solutions]]
- [[30 Computer Science/01 Topics/03 Hardware/80 Review Checklist|Review Checklist]]

## Connections and Extensions

- [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]] puts these memory types, buses, registers, logic gates, and storage ideas inside the CPU execution model.
- [[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/00 Overview|Hardware and Virtual Machines]] extends the logic-circuit work into Boolean algebra, adders, flip-flops, processor architectures, and virtual machines.
- [[30 Computer Science/01 Topics/05 System Software/00 Overview|System Software]] depends on the OS being able to manage hardware devices, memory, files, and peripheral input/output.
- [[30 Computer Science/01 Topics/01 Information Representation/00 Overview|Information Representation]] explains the binary values that storage devices, sensors, ADCs, and logic circuits ultimately hold and manipulate.

## Common Traps

- Mixing up RAM and ROM, or SRAM and DRAM.
- Forgetting that every gate in this topic except NOT has exactly two inputs.
- Drawing a circuit that does not match the derived expression.
