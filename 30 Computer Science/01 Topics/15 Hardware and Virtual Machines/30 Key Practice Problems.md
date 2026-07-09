---
title: Hardware and Virtual Machines Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[Hardware and Virtual Machines](00%20Overview.md)"
status: active
tags:
  - computerscience/computer-systems
  - practice
---

# Hardware and Virtual Machines Key Practice Problems

Work through these without looking at the solutions. Most prompts are scenario-based, so aim to justify your answer against the alternatives rather than just naming a term. For logic questions, write the truth table before the expression, and simplify with both Boolean algebra and a K-map so the two answers agree.

## A. Processors and architectures

1. Compare RISC and CISC under the headings instruction set, cycles per instruction, and pipelining. Give one example processor of each.

2. A company is choosing a processor for a desktop PC that must run a large body of legacy x86 software with as few instructions per task as possible. Recommend RISC or CISC and justify your choice against the other.

3. Explain why a RISC processor benefits from having many general-purpose registers, and state how this affects memory traffic.

4. Describe how interrupt handling differs in cost between RISC and CISC, and state why RISC reaches a clean interrupt point more quickly.

5. For each scenario, state the Flynn architecture and justify your answer.

   - a) A single-core CPU fetches one instruction at a time and acts on one data item.
   - b) A GPU applies the same instruction to a whole block of pixels at once.
   - c) A multi-core desktop runs several independent programs on different cores.
   - d) A flight-control system runs three different programs that each check the same sensor reading and vote on the result.

6. State two characteristics of a massively parallel computer, and explain why communication overhead limits the speed-up it can achieve.

## B. Virtual machines

7. Define a virtual machine, and name its host, hypervisor, and guest.

8. A developer who uses a Windows PC needs to test software on Linux without buying a second computer. Explain how a virtual machine solves this, and give two benefits and one limitation.

9. Distinguish a virtual machine from an emulator, and give one situation where an emulator is the better choice.

10. Give two benefits and two limitations of using virtual machines for server consolidation in a data centre.

## C. Logic circuits and flip-flops

11. A half adder takes two single-bit inputs A and B and produces a sum S and a carry C. Derive the Boolean expressions and build the truth table.

12. A full adder takes three single-bit inputs A, B, and a carry-in $C_{in}$, and produces a sum S and a carry-out $C_{out}$. Derive the expressions and build the truth table.

13. Explain how full adders are chained to add two n-bit numbers, naming the arrangement and the role of the carry signal between columns.

14. Draw the SR flip-flop, give its truth table, and state why the state $S=1, R=1$ is forbidden.

15. Draw the JK flip-flop, give its truth table, and explain how it improves on the SR flip-flop when both inputs are 1.

## D. Boolean algebra and K-maps

16. State both forms of De Morgan's laws, and use them to simplify $Z = \overline{\overline{A} \cdot \overline{B}}$ into a plain OR.

17. Simplify $X = A \cdot B + A \cdot \overline{B} + \overline{A} \cdot B$ using Boolean algebra, showing each step, and describe the simplified circuit.

18. Simplify $Y = \overline{A + \overline{B}}$ using De Morgan's law, showing each step.

19. Using a Karnaugh map, simplify the function whose truth table is given below. Show the groups and the final expression.

| A | B | C | X |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 |
| 0 | 1 | 0 | 0 |
| 0 | 1 | 1 | 1 |
| 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 |
| 1 | 1 | 0 | 0 |
| 1 | 1 | 1 | 1 |

20. Using a Karnaugh map, simplify the function whose truth table is given below. Show the groups and the final expression, and confirm the result with Boolean algebra.

| A | B | C | D | X |
|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 1 | 1 |
| 0 | 0 | 1 | 0 | 0 |
| 0 | 0 | 1 | 1 | 1 |
| 0 | 1 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 0 |
| 0 | 1 | 1 | 1 | 1 |
| 1 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 1 | 1 |
| 1 | 0 | 1 | 0 | 0 |
| 1 | 0 | 1 | 1 | 1 |
| 1 | 1 | 0 | 0 | 0 |
| 1 | 1 | 0 | 1 | 0 |
| 1 | 1 | 1 | 0 | 0 |
| 1 | 1 | 1 | 1 | 1 |
