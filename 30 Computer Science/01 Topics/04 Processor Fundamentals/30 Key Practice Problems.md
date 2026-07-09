---
title: Processor Fundamentals Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[Processor Fundamentals](00%20Overview.md)"
status: active
tags:
  - computerscience/computer-systems
  - practice
---

# Processor Fundamentals Key Practice Problems

Work through these without looking at the solutions. Most prompts ask you to justify a choice or trace a program, so aim to reason rather than just name a term. For traces, draw a register-value table with one row per executed instruction before you commit to final values. For bit manipulation, always write the mask out in full binary next to the value.

## A. Architecture and registers

1. Name the four CPU components (ALU, CU, clock, IAS) and give the role of each in one sentence.

2. Distinguish a general-purpose register from a special-purpose register, with one example of each. State which register in this instruction set is the working register for every arithmetic result.

3. Distinguish the role of the MAR from the role of the MDR. Explain why the PC is incremented during fetch rather than during execute.

4. State the stored-program concept in one sentence, explain why it makes a computer general-purpose, and name the bottleneck it introduces.

5. Compare the USB, HDMI, and VGA ports under the headings purpose and signal type (digital or analogue).

6. A buyer is comparing two CPUs. For each of clock speed, cache, number of cores, and bus width, state how the factor affects performance.

## B. Fetch-execute and interrupts

7. Write the fetch, decode, and execute stages for the instruction `SUB 50` in register-transfer notation, assuming the operand is stored in memory.

8. Explain why a memory-addressed instruction such as `ADD 100` needs two memory reads within a single fetch-execute cycle.

9. Describe how a hardware interrupt is detected and handled, naming the ISR. State exactly when the CPU checks for a pending interrupt.

10. Give two causes of hardware interrupts and two causes of software interrupts.

## C. Assembly language tracing

11. Trace the program below and state the final values of M[102], M[103], and ACC. Memory holds M[100] = 12 and M[101] = 5.

```asm
        LDD 100
        ADD 101
        STO 102
        LDD 100
        SUB 101
        STO 103
        END
```

12. Trace the loop below. State the final value stored in M[200] and state how many times the loop body (the instructions from `DEC ACC` to `JMP LOOP`) runs. Memory holds M[202] = 5.

```asm
        LDM #0
        STO 200          ; total = 0
        LDM #3
        STO 201          ; counter = 3
LOOP:   LDD 201
        CMP #0
        JPE Done
        DEC ACC
        STO 201
        LDD 200
        ADD 202          ; total = total + M[202]
        STO 200
        JMP LOOP
Done:   LDD 200
        OUT
        END
```

13. For each instruction, state the addressing mode and the value loaded into ACC. Assume IX = 2, M[50] = 70, and M[70] = 3.

```asm
(a) LDM #8
(b) LDD 50
(c) LDI 50
(d) LDX 50
```

14. Define the terms **forward reference** and **symbol table**, and explain why an assembler needs two passes rather than one.

15. State the difference between `JPE` and `JPN` in terms of the compare flag. Explain what `CMP #0` does to the flag and to the ACC.

## D. Bit manipulation

16. Show the result of a logical left shift by 2 (`LSL #2`) on the byte 0010 1011. Give the result in binary and in denary, and state the denary meaning of the operation.

17. A signed byte holds 1100 0000. Show the result of an arithmetic right shift by 1, and explain why a logical right shift would give the wrong answer here.

18. A device control byte is 0100 1001. Show, with masks written in full binary, how to test whether bit 2 is set, and how to set bit 5 without disturbing the other bits. State whether bit 2 was set.

19. Explain, naming the operator and the mask in each case, how to clear bit 3 of a byte and how to toggle bit 6 of a byte.
