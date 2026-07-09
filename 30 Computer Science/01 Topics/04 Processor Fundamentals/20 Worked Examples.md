---
title: Processor Fundamentals Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[Processor Fundamentals](00%20Overview.md)"
status: active
tags:
  - computerscience/computer-systems
  - worked-examples
---

# Processor Fundamentals Worked Examples

These examples show how to reason about register roles, the fetch-execute cycle, interrupts, assembly traces, addressing modes, bit manipulation, and performance factors. For each one, read the prompt, follow the working, then try the Check. Name a register or mode by its role first, trace in a table with one row per instruction, and write bit masks out in full binary.

## Source Route

- Syllabus: CAIE Computer Science 9618, AS Section 4 - Processor Fundamentals.
- Assessed in Paper 1.
- Topics: CPU architecture and registers; buses and performance factors; fetch-execute cycle and interrupts; assembly language, addressing modes, and program tracing; bit manipulation and masking.

## Example 1: Register Roles During an Instruction

**Prompt.** A program contains the instruction `ADD 100`. State which register holds the address of this instruction as it is fetched, which holds the instruction itself during decoding, which holds the operand address, and which holds the result. Justify each choice by role.

**Solution.**

- The **Program Counter (PC)** holds the address of the instruction being fetched.
- The **Memory Address Register (MAR)** receives that address so memory knows which location to read; MAR always holds an address.
- The instruction returns along the data bus into the **Memory Data Register (MDR)**, which holds data just read from memory, and is then copied into the **Current Instruction Register (CIR)**, which holds the instruction being decoded.
- When decoded, the operand address (100) is placed in the **MAR** again, so the operand is fetched from M[100] via the MDR.
- The result is formed in the **Accumulator (ACC)**, the working register through which every arithmetic result passes.

**Check.** MAR holds an address; MDR holds data. The ACC is the only register that holds a calculation result.

## Example 2: Fetch-Execute Cycle in Register-Transfer Notation

**Prompt.** Write the fetch, decode, and execute stages for the instruction `ADD 100` in register-transfer notation, assuming the operand is stored in memory. State how the PC is updated.

**Solution.**

```text
--- FETCH ---
MAR  ← PC               ; address of the instruction copied to MAR
MDR  ← [MAR]            ; control unit reads memory; instruction returns on the data bus
CIR  ← MDR              ; instruction held for decoding
PC   ← PC + 1           ; PC advanced to point at the next instruction

--- DECODE ---
CU    decodes opcode ADD, operand address 100
MAR  ← 100              ; operand address placed in MAR
MDR  ← [MAR]            ; operand value fetched from memory M[100]

--- EXECUTE ---
ACC  ← ACC + MDR        ; ALU adds; flags set in Status Register
```

The PC is incremented during fetch, before execute, so that by the time `ADD 100` finishes the PC already points at the next instruction. Two separate memory reads occur: one to fetch the instruction itself and one to fetch its operand at address 100.

**Check.** A memory-addressed instruction always needs a second read for its operand. If the operand were immediate (`ADD #100`) no operand fetch would be needed, because the value 100 sits inside the instruction.

## Example 3: Interrupt Handling for a Key Press

**Prompt.** A user presses a key while the CPU is mid-way through executing an instruction. Explain, naming the ISR, the sequence by which the key press is serviced and the interrupted program resumes.

**Solution.**

1. The CPU finishes the current fetch-execute cycle; it never abandons a half-completed instruction.
2. At the end of that cycle it checks for a pending interrupt and detects the keyboard signal, a hardware interrupt.
3. It saves the current state (the PC at minimum, usually the other registers) so the program can resume exactly where it stopped.
4. The PC is loaded with the address of the **Interrupt Service Routine (ISR)** for the keyboard, so the next fetch runs the ISR.
5. The ISR executes, reading the key code and storing it in an input buffer.
6. A return-from-interrupt instruction restores the saved PC and registers, and the program continues as though nothing had happened.

**Check.** The interrupt check happens between instructions, never during one, so no instruction is left half-finished.

## Example 4: Tracing the Addition of Two Numbers

**Prompt.** Trace the program below and state the value output. Memory holds M[100] = 7 and M[101] = 4.

```asm
        LDD 100      ; load the first number
        ADD 101      ; add the second number
        STO 102      ; store the sum
        OUT          ; output the sum
        END
```

**Solution.** Set up a table with one row per executed instruction.

| Step | Instruction | ACC | M[102] | Note |
|---|---|---|---|---|
| 1 | `LDD 100` | 7 | – | ACC ← M[100] = 7 |
| 2 | `ADD 101` | 11 | – | ACC ← 7 + 4 |
| 3 | `STO 102` | 11 | 11 | M[102] ← ACC |
| 4 | `OUT` | 11 | 11 | output 11 |
| 5 | `END` | 11 | 11 | stop |

Final state: ACC = 11 and the value 11 is output. The store and output happen after the calculation, so the sum in memory and on the output device both read 11.

**Check.** Each arithmetic result lands in the ACC first; only a `STO` writes it back to memory and only `OUT` sends it to a peripheral.

## Example 5: Tracing a Loop with CMP and JPE

**Prompt.** Trace the loop below and state the final values of M[200] and M[201]. The loop adds 10 to a running total once for each unit of a counter that starts at 2.

```asm
        LDM #0       ; ACC = 0 (total)
        STO 200      ; M[200] = total
        LDM #2       ; ACC = 2 (counter)
        STO 201      ; M[201] = counter
LOOP:   LDD 201      ; load counter
        CMP #0       ; is counter 0?
        JPE Done     ; yes -> finished
        DEC ACC      ; counter = counter - 1
        STO 201      ; save counter
        LDD 200      ; load total
        ADD #10      ; total = total + 10
        STO 200      ; save total
        JMP LOOP     ; repeat
Done:   LDD 200
        OUT
        END
```

**Solution.**

| Step | Instruction | ACC | M[200] | M[201] | Flag | Note |
|---|---|---|---|---|---|---|
| 1 | `LDM #0` | 0 | – | – | – | total = 0 |
| 2 | `STO 200` | 0 | 0 | – | – | store total |
| 3 | `LDM #2` | 2 | 0 | – | – | counter = 2 |
| 4 | `STO 201` | 2 | 0 | 2 | – | store counter |
| 5 | `LDD 201` | 2 | 0 | 2 | – | load counter |
| 6 | `CMP #0` | 2 | 0 | 2 | F | 2 is not 0 |
| 7 | `JPE Done` | 2 | 0 | 2 | F | no jump |
| 8 | `DEC ACC` | 1 | 0 | 2 | F | counter - 1 |
| 9 | `STO 201` | 1 | 0 | 1 | F | save counter |
| 10 | `LDD 200` | 0 | 0 | 1 | F | load total |
| 11 | `ADD #10` | 10 | 0 | 1 | F | + 10 |
| 12 | `STO 200` | 10 | 10 | 1 | F | save total |
| 13 | `JMP LOOP` | 10 | 10 | 1 | F | loop back |
| 14 | `LDD 201` | 1 | 10 | 1 | F | load counter |
| 15 | `CMP #0` | 1 | 10 | 1 | F | 1 is not 0 |
| 16 | `JPE Done` | 1 | 10 | 1 | F | no jump |
| 17 | `DEC ACC` | 0 | 10 | 1 | F | counter - 1 |
| 18 | `STO 201` | 0 | 10 | 0 | F | save counter |
| 19 | `LDD 200` | 10 | 10 | 0 | F | load total |
| 20 | `ADD #10` | 20 | 10 | 0 | F | + 10 |
| 21 | `STO 200` | 20 | 20 | 0 | F | save total |
| 22 | `JMP LOOP` | 20 | 20 | 0 | F | loop back |
| 23 | `LDD 201` | 0 | 20 | 0 | F | load counter |
| 24 | `CMP #0` | 0 | 20 | 0 | T | 0 = 0 |
| 25 | `JPE Done` | 0 | 20 | 0 | T | flag True, jump |
| 26 | `LDD 200` | 20 | 20 | 0 | T | load total |
| 27 | `OUT` | 20 | 20 | 0 | T | output 20 |
| 28 | `END` | 20 | 20 | 0 | T | stop |

Final state: M[200] = 20, and 20 is output. The loop body (steps 8 to 13) ran twice, once for each unit of the counter, adding 10 each time, giving 2 x 10 = 20.

**Check.** `CMP #0` sets the flag True only when ACC equals 0. `JPE` jumps on True, so it exits the loop exactly when the counter reaches zero. Off-by-one errors come from testing before or after the decrement in the wrong order.

## Example 6: Identifying Addressing Modes

**Prompt.** For each instruction, state the addressing mode and what the CPU loads into ACC. Assume IX = 4, M[100] = 25, and M[25] = 9.

```asm
(a) LDM #5
(b) LDD 100
(c) LDI 100
(d) LDX 100
```

**Solution.**

- (a) **Immediate.** The operand is the value written in the instruction itself. ACC ← 5.
- (b) **Direct.** The operand is stored at the address given in the instruction. ACC ← M[100] = 25.
- (c) **Indirect.** The address given holds another address; the operand lives there. M[100] = 25, so ACC ← M[25] = 9.
- (d) **Indexed.** The operand is at (given address + IX). 100 + 4 = 104, so ACC ← M[104]. Its value depends on M[104], which is not given here.

**Check.** Indirect follows the pointer twice (address, then address, then value); indexed adds a register to an address once. Confusing the two is the classic tracing error.

## Example 7: Logical and Arithmetic Shifts

**Prompt.** Show the result of (a) a logical left shift by 2 on 0001 0011, (b) a logical right shift by 1 on 1011 0100, and (c) an arithmetic right shift by 1 on 1011 0100 treated as a signed value. Give the denary meaning where it is clean.

**Solution.**

(a) Logical left shift by 2 on 0001 0011 (19):

```text
0001 0011  (19)   LSL #2   ->   0100 1100  (76)
```

Each left shift multiplies by 2, so two shifts give 19 x 4 = 76. Zeros enter from the right and any bits shifted off the left are discarded.

(b) Logical right shift by 1 on 1011 0100:

```text
1011 0100   LSR #1   ->   0101 1010
```

A zero enters from the left. A logical shift always fills with 0, regardless of sign.

(c) Arithmetic right shift by 1 on 1011 0100 (signed):

```text
1011 0100   ASR #1   ->   1101 1010
```

The sign bit (1, the leftmost bit) is copied into the vacated position, so the value stays negative. A logical shift would have placed a 0 there and turned a negative number positive, which is wrong for signed halving.

**Check.** Use logical shifts for unsigned bit patterns and arithmetic shifts for signed values; only the arithmetic right shift preserves the sign.

## Example 8: Bit-Mask Test and Set

**Prompt.** A device control byte is 1011 0110. Show, with masks, how to test whether bit 4 is set, and how to set bit 3 without disturbing the other bits. Give the mask and the result in each case.

**Solution.**

Test bit 4 with AND. Use a mask that has a 1 only in bit position 4:

```text
Value   1011 0110
Mask  & 0001 0000   (bit 4)
Result  0001 0000   non-zero, so bit 4 IS set
```

If the result had been 0000 0000, bit 4 would have been clear.

Set bit 3 with OR. Use a mask with a 1 in bit position 3 and 0 elsewhere, so every other bit is unchanged:

```text
Value   1011 0110
Mask  | 0000 1000   (bit 3)
Result  1011 1110   bit 3 now 1, rest unchanged
```

AND can only clear or keep bits (AND with 0 forces 0); OR is the operator that turns a bit on. To clear a bit you would AND with the complement of the mask; to toggle a bit you would XOR with the mask.

**Check.** Write the mask in full binary next to the value so the bit-by-bit operation is visible, not done mentally. Bit 0 is the rightmost (least significant) bit.

## Example 9: Performance Factor Reasoning

**Prompt.** A buyer must choose between two desktop CPUs at the same price. CPU A has a higher clock speed but a small cache and a single core. CPU B has a lower clock speed but a large cache and four cores. For each of clock speed, cache, and number of cores, explain how the factor affects performance, and recommend a CPU for a user who runs several applications at once.

**Solution.**

- **Clock speed.** More cycles per second means more fetch-execute cycles per second, so more instructions completed in a given time. CPU A's higher clock speed gives it an edge on a single task that uses one core.
- **Cache.** Cache is small, fast SRAM between the CPU and RAM holding recently used data and instructions. A larger cache (CPU B) means fewer slow trips to RAM, so the CPU spends less time waiting.
- **Number of cores.** Each core runs its own instruction stream, so a four-core CPU (CPU B) can do parallel work on separate tasks; with several applications at once, the cores share the load instead of time-slicing on one core.

Recommendation: **CPU B.** For a user running several applications at once, the four cores and large cache matter more than raw clock speed. CPU A would win only for a single compute-heavy task that fits on one core.

**Check.** Clock speed helps a single thread; cores help parallel workloads; cache helps both by cutting memory wait.
