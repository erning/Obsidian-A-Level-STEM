---
title: Processor Fundamentals Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[Processor Fundamentals](00%20Overview.md)"
status: active
tags:
  - computerscience/computer-systems
  - review-checklist
---

# Processor Fundamentals Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can recall, trace, and explain the ideas without prompting.

## Ideas to Recall

- [ ] Define the stored-program concept and explain why it makes a computer general-purpose.
- [ ] Recall the roles of the ALU, Control Unit, system clock, and Immediate Access Store.
- [ ] Distinguish general-purpose registers from special-purpose registers, including ACC, IX, PC, MAR, MDR, CIR, and the Status Register.
- [ ] State the purpose and direction of the address bus, data bus, and control bus.
- [ ] Recall how clock speed, cache, bus width, number of cores, and processor type affect performance.
- [ ] Distinguish USB, HDMI, and VGA by purpose and signal type.
- [ ] Explain what an interrupt is, why an ISR is needed, and when the CPU checks for interrupts.
- [ ] Recall why assembly language is translated by an assembler and why two passes are needed.
- [ ] Distinguish immediate, direct, indirect, indexed, and relative addressing.
- [ ] Recall the difference between logical, arithmetic, and cyclic shifts.

## Skills to Perform

- [ ] Write the fetch stage in register-transfer notation using PC, MAR, MDR, CIR, and the PC increment.
- [ ] Extend a fetch-execute trace for a memory-addressed instruction by showing the second memory read for the operand.
- [ ] Trace short assembly programs with one row per executed instruction and columns for ACC, IX, relevant memory cells, and the compare flag.
- [ ] Use `CMP`, `JPE`, and `JPN` correctly when tracing loops and conditional jumps.
- [ ] Identify the addressing mode used by a load or jump instruction and calculate the effective operand or target address.
- [ ] Build a symbol table for a short assembly fragment with labels and use it to resolve a forward reference.
- [ ] Apply logical left and right shifts to unsigned binary values and state the denary effect when no overflow changes the meaning.
- [ ] Apply an arithmetic right shift to a signed binary value while preserving the sign bit.
- [ ] Use AND with a bit mask to test whether a selected bit is set.
- [ ] Use OR, AND with a complemented mask, and XOR to set, clear, and toggle selected bits.

## Things to Trace or Explain

- [ ] Trace how an instruction moves from the address in PC to MAR, MDR, CIR, and then into decode.
- [ ] Explain why fetching an instruction and fetching a memory operand are separate bus transactions.
- [ ] Trace how the PC changes during ordinary execution, during a jump, and when an interrupt transfers control to an ISR.
- [ ] Explain the difference between data stored in main memory and values held in CPU registers or cache.
- [ ] Trace a loop that stores a counter in memory because ACC is needed for another calculation.
- [ ] Explain why `CMP` changes the compare flag but does not change ACC.
- [ ] Trace indirect addressing as "address to address to value" and indexed addressing as "base address plus IX".
- [ ] Explain how bit masks allow a program to monitor or control one device bit without disturbing the others.
- [ ] Connect CPU execution to [Hardware](../03%20Hardware/00%20Overview.md) by explaining which lower-level components make registers, buses, and cache possible.
- [ ] Connect bit patterns and masks to [Information Representation](../01%20Information%20Representation/00%20Overview.md) and [Data Representation](../13%20Data%20Representation/00%20Overview.md).

## Common Errors to Avoid

- [ ] Swapping MAR and MDR: MAR holds an address; MDR holds data.
- [ ] Forgetting that PC is incremented during fetch before the instruction executes.
- [ ] Treating the operand address in an instruction as if it were always the operand value.
- [ ] Confusing indirect addressing with indexed addressing.
- [ ] Reading `JPE` as "jump if positive" instead of "jump if the compare flag is equal/True".
- [ ] Assuming `CMP` stores a subtraction result in ACC.
- [ ] Saying that a one-pass assembler can always resolve labels that appear later in the program.
- [ ] Using a logical right shift for signed negative values.
- [ ] Trying to set a bit with AND instead of OR.
- [ ] Describing cache or registers as ordinary main memory without saying where each one is located.

## Ready to Move On When

- [ ] I can describe the CPU as a fetch-decode-execute machine using the stored-program concept.
- [ ] I can name each major register from its role and use it correctly in a register-transfer trace.
- [ ] I can explain how buses, cache, clock speed, cores, and processor type affect the rate at which instructions complete.
- [ ] I can describe interrupt handling from the end of the current instruction through the ISR and return to the original program.
- [ ] I can trace an assembly loop without losing the ACC value, memory updates, PC changes, or compare flag.
- [ ] I can choose the correct addressing mode and calculate the operand or jump target from the instruction and register values.
- [ ] I can use full binary masks to test, set, clear, and toggle individual bits.
- [ ] I can explain how this topic extends [Hardware](../03%20Hardware/00%20Overview.md) from components into execution.
- [ ] I can connect processor-level binary work to [Information Representation](../01%20Information%20Representation/00%20Overview.md) and [Data Representation](../13%20Data%20Representation/00%20Overview.md).
- [ ] I can see how assembly tracing prepares for lower-level programming ideas in [Further Programming](../20%20Further%20Programming/00%20Overview.md) and CPU design extensions in [Hardware and Virtual Machines](../15%20Hardware%20and%20Virtual%20Machines/00%20Overview.md).
