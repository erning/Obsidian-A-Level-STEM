---
title: Hardware and Virtual Machines Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/00 Overview|Hardware and Virtual Machines]]"
status: active
tags:
  - computerscience/computer-systems
  - review-checklist
---

# Hardware and Virtual Machines Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can compare architectures, trace logic, and simplify circuits without prompting.

## Ideas to Recall

- [ ] Distinguish RISC and CISC by instruction set, cycles per instruction, instruction length, registers, addressing modes, pipelining, power, and examples.
- [ ] Explain why RISC benefits from many general-purpose registers.
- [ ] Recall how interrupt handling differs in cost between short RISC instructions and longer CISC instructions.
- [ ] Define SISD, SIMD, MISD, and MIMD using instruction streams and data streams.
- [ ] Recall the characteristics and limits of massively parallel computers.
- [ ] Define virtual machine, host, hypervisor, guest, and emulator.
- [ ] Recall benefits and limitations of virtual machines.
- [ ] Recall half-adder and full-adder inputs, outputs, expressions, and truth-table patterns.
- [ ] Define SR flip-flop, JK flip-flop, hold, set, reset, forbidden state, toggle, and edge-triggering.
- [ ] Recall core Boolean algebra identities and both forms of De Morgan's laws.
- [ ] Explain the purpose, layout, and grouping rules of Karnaugh maps.

## Skills to Perform

- [ ] Build a RISC/CISC comparison table for the rows a scenario asks about.
- [ ] Recommend RISC or CISC for a use case and justify the recommendation against the other family.
- [ ] Classify a scenario as SISD, SIMD, MISD, or MIMD and give the stream counts.
- [ ] Explain why communication overhead limits massively parallel speed-up.
- [ ] Identify host, hypervisor, and guest in a virtual-machine scenario.
- [ ] Distinguish a VM from an emulator and choose which is needed for a foreign CPU architecture.
- [ ] Derive the half-adder expressions $S=A\oplus B$ and $C=A\cdot B$ from the truth table.
- [ ] Derive the full-adder truth table and explain how carry-out feeds the next column.
- [ ] Draw SR and JK flip-flop boxes and complete their truth tables.
- [ ] Simplify Boolean expressions using complement, idempotent, absorption, distributive laws, and De Morgan's laws.
- [ ] Copy a truth table into a 3- or 4-variable K-map in Gray-code order.
- [ ] Form valid K-map groups and write the simplified expression from fixed variables.

## Things to Trace or Explain

- [ ] Trace how a RISC pipeline overlaps fetch, decode, and execute stages.
- [ ] Explain why variable-length CISC instructions make pipelining harder.
- [ ] Trace the interrupt route from current instruction completion to saved state, ISR, and return.
- [ ] Explain SIMD as one instruction applied to many data items and MIMD as many independent instruction streams.
- [ ] Trace how a massively parallel problem is split across nodes and where message passing becomes a cost.
- [ ] Explain how a hypervisor presents virtual CPU, memory, disk, and network to a guest.
- [ ] Trace a ripple-carry adder by following $C_{out}$ from one column into $C_{in}$ of the next.
- [ ] Explain why $S=1, R=1$ is forbidden in an SR flip-flop and why $J=1, K=1$ toggles in a JK flip-flop.
- [ ] Trace De Morgan's law as "break the bar, swap the operator, invert each term".
- [ ] Explain why K-map edge wrapping and power-of-two groups preserve valid adjacencies.
- [ ] Connect adders and flip-flops to [[30 Computer Science/01 Topics/03 Hardware/00 Overview|Hardware]] and CPU work in [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]].

## Common Errors to Avoid

- [ ] Swapping RISC and CISC features, especially registers, instruction richness, and pipelining ease.
- [ ] Saying a RISC task always uses fewer instructions than a CISC task.
- [ ] Confusing SIMD with MIMD.
- [ ] Ignoring communication overhead when describing massively parallel computers.
- [ ] Treating a VM as identical to an emulator.
- [ ] Building a half adder when the question requires a full adder with carry-in.
- [ ] Claiming the SR forbidden state has a predictable stored value.
- [ ] Forgetting that JK toggles when both inputs are 1.
- [ ] Applying De Morgan's law without inverting the internal variables.
- [ ] Arranging K-map columns as ordinary binary order instead of Gray-code order.
- [ ] Grouping K-map cells in sizes such as 3 or 6, or grouping cells that are not adjacent.

## Ready to Move On When

- [ ] I can compare RISC and CISC and explain how the design affects pipelining, interrupts, power, and software.
- [ ] I can classify a computer architecture from instruction-stream and data-stream wording.
- [ ] I can explain massively parallel computing as many nodes plus distributed memory, message passing, and communication overhead.
- [ ] I can describe a virtual machine with host, hypervisor, and guest, and separate VM benefits from limitations.
- [ ] I can build and explain half-adder and full-adder truth tables and chain full adders into a ripple-carry adder.
- [ ] I can draw SR and JK flip-flop truth tables and explain hold, set, reset, forbidden, and toggle cases.
- [ ] I can simplify a Boolean expression using algebra and check it with a K-map.
- [ ] I can explain how this topic extends [[30 Computer Science/01 Topics/03 Hardware/00 Overview|Hardware]] and [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]].
- [ ] I can connect virtual machines and interrupt costs to [[30 Computer Science/01 Topics/16 System Software/00 Overview|System Software]].
