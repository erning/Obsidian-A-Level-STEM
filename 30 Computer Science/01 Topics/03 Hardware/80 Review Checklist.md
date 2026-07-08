---
title: Hardware Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/03 Hardware/00 Overview|Hardware]]"
status: active
tags:
  - computerscience/computer-systems
  - review-checklist
---

# Hardware Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can classify components, explain mechanisms, trace systems, and build logic tables without prompting.

## Ideas to Recall

- [ ] Distinguish input devices, output devices, primary memory, secondary storage, and removable storage by role.
- [ ] Explain why a computer needs both primary memory and secondary storage.
- [ ] Recall what a buffer does between devices that operate at different speeds.
- [ ] Distinguish RAM from ROM by volatility, write access, and typical use.
- [ ] Distinguish SRAM from DRAM by storage mechanism, refresh, speed, cost, density, and use.
- [ ] Recall how PROM, EPROM, and EEPROM differ in programming and erasing.
- [ ] Recall the principal operations of laser printers, 3D printers, microphones, speakers, HDDs, SSDs, optical discs, touchscreens, and VR headsets.
- [ ] Define embedded system, firmware, monitoring system, control system, sensor, ADC, actuator, and feedback.
- [ ] Recall the functions and truth tables of NOT, AND, OR, NAND, NOR, and XOR.
- [ ] Explain the difference between a Boolean expression, a logic circuit, and a truth table.

## Skills to Perform

- [ ] Classify a named component as input, output, primary memory, secondary storage, or both input and output.
- [ ] Compare RAM and ROM, SRAM and DRAM, or PROM, EPROM, and EEPROM for a named use.
- [ ] Choose a suitable storage device or memory type for a scenario and justify it against an alternative.
- [ ] Outline the operation of a laser printer from charged drum to fused page.
- [ ] Outline how a microphone produces digital data from sound, including the ADC.
- [ ] Compare magnetic hard disks and solid state drives using moving parts, speed, durability, and wear.
- [ ] Decide whether a scenario is monitoring or control and identify the sensor, ADC, actuator, and feedback path.
- [ ] Translate a problem statement into a Boolean expression with correct parentheses.
- [ ] Convert a Boolean expression into a circuit description.
- [ ] Build a truth table with all $2^n$ rows and intermediate columns for each gate output.

## Things to Trace or Explain

- [ ] Trace how data moves from input device to primary memory, through processing, and out through an output device.
- [ ] Explain why primary memory must be fast and directly addressable, while secondary storage must be persistent and large.
- [ ] Trace how a buffer lets a fast CPU send data to a slow printer without waiting after every line.
- [ ] Explain why DRAM is chosen for main memory while SRAM is chosen for cache.
- [ ] Trace the erase/update route for PROM, EPROM, and EEPROM.
- [ ] Explain how flash memory is related to EEPROM and why repeated writes matter.
- [ ] Trace a control loop from physical quantity to sensor, ADC, computer decision, actuator, changed quantity, and feedback.
- [ ] Explain why a smoke alarm that only warns is monitoring, while a system that changes the environment is control.
- [ ] Trace a logic circuit row by row from inputs through intermediate gate outputs to final output.
- [ ] Connect gates, RAM, ROM, and buses to [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]].

## Common Errors to Avoid

- [ ] Saying RAM and ROM differ only by volatility without mentioning write access and use.
- [ ] Choosing SRAM for main memory only because it is faster, while ignoring cost and density.
- [ ] Confusing EPROM's UV bulk erase with EEPROM's electrical in-circuit erase.
- [ ] Treating flash memory as if it had moving parts.
- [ ] Describing a control system without an actuator.
- [ ] Forgetting that feedback is what lets a control system adjust its next action.
- [ ] Confusing NAND with NOR, or XOR with OR.
- [ ] Dropping parentheses when translating a statement such as $A \cdot (B + C)$.
- [ ] Building a truth table with too few rows.
- [ ] Drawing a circuit that does not match the expression you derived.

## Ready to Move On When

- [ ] I can classify components by role and explain why each role is needed in a complete computer system.
- [ ] I can compare memory and storage types by mechanism, performance, volatility, cost, and use.
- [ ] I can describe the principal operation of the required input, output, and storage devices without relying on a memorised label only.
- [ ] I can separate monitoring from control and explain the closed feedback loop in a control system.
- [ ] I can write and check the six basic gate truth tables from their meanings.
- [ ] I can move between statement, expression, circuit, and truth table in either direction.
- [ ] I can explain how this topic prepares for [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]].
- [ ] I can explain how logic circuits are extended in [[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/00 Overview|Hardware and Virtual Machines]].
- [ ] I can connect binary values in hardware to [[30 Computer Science/01 Topics/01 Information Representation/00 Overview|Information Representation]].
