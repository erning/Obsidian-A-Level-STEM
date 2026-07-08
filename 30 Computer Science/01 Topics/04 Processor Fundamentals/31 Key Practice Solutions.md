---
title: Processor Fundamentals Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]]"
status: active
tags:
  - computerscience/computer-systems
  - solutions
---

# Processor Fundamentals Key Practice Solutions

These solutions correspond to [[30 Computer Science/01 Topics/04 Processor Fundamentals/30 Key Practice Problems|Key Practice Problems]]. Trace tables give one row per executed instruction; bit manipulation is shown with masks in full binary.

## A. Architecture and registers

### Problem 1

- **ALU (Arithmetic Logic Unit).** The calculating part; it carries out every arithmetic and logic operation the instruction set requires.
- **Control Unit (CU).** The directing part; it decodes the instruction in the CIR and sends the control signals that tell every other component what to do and when.
- **System clock.** A crystal oscillator producing timing pulses that synchronise every step of the fetch-execute cycle.
- **Immediate Access Store (IAS).** The storage inside the CPU itself (its registers), reached without going out to main memory.

### Problem 2

A general-purpose register can be used by the programmer for any holding job. In this instruction set the **Accumulator (ACC)** is the single general-purpose working register, and every arithmetic and logic result passes through it. The **Index Register (IX)** should be described separately: it is programmer-addressable, but its dedicated role is indexed addressing and it is often used as a counter. Other special-purpose registers have a single fixed role in the fetch-execute cycle, for example the PC or the MAR.

### Problem 3

The MAR holds the address in memory currently being read from or written to; it always holds an address. The MDR holds the data just read from memory or about to be written to memory; it always holds data. The PC is incremented during fetch so that, before execute even begins, the PC already points at the next instruction. This guarantees that the next fetch reads the correct instruction regardless of what execute does, and it avoids any risk of fetching the same instruction twice if an interrupt or other event intervenes.

### Problem 4

The stored-program concept is that the program (its instructions) and the data it works on are both stored in the same main memory. It makes a computer general-purpose because the same hardware can do radically different jobs simply by loading different contents into memory; the CPU does not need to be rewired for each task. The bottleneck it introduces is the **Von Neumann bottleneck**: because instructions and data share one memory and one set of buses, the CPU cannot fetch the next instruction and read an operand at the same instant.

### Problem 5

- **USB.** A general-purpose serial port for almost any peripheral (mouse, keyboard, storage, printer). It carries digital signals, is hot-pluggable, and supplies power to small devices.
- **HDMI.** A digital port carrying both high-quality video and audio to a monitor or TV.
- **VGA.** An older analogue port carrying video only, still found on projectors and legacy monitors.

### Problem 6

- **Clock speed.** More cycles per second means more fetch-execute cycles per second, so more instructions completed in a given time.
- **Cache.** Small, fast SRAM between the CPU and RAM that holds recently used data and instructions, cutting the average time the CPU waits for memory.
- **Number of cores.** Each core runs its own instruction stream, so a multi-core CPU can do genuinely parallel work on separate tasks or threads.
- **Bus width.** A wider data bus moves more bits per transfer; a wider address bus can address more memory locations. Both reduce the number of transfers needed for a given job.

## B. Fetch-execute and interrupts

### Problem 7

```text
--- FETCH ---
MAR  ← PC               ; address of the instruction copied to MAR
MDR  ← [MAR]            ; control unit reads memory; instruction returns on the data bus
CIR  ← MDR              ; instruction held for decoding
PC   ← PC + 1           ; PC advanced to point at the next instruction

--- DECODE ---
CU    decodes opcode SUB, operand address 50
MAR  ← 50               ; operand address placed in MAR
MDR  ← [MAR]            ; operand value fetched from memory M[50]

--- EXECUTE ---
ACC  ← ACC - MDR        ; ALU subtracts; flags set in Status Register
```

### Problem 8

The first memory read fetches the instruction itself from the address held in the PC; the instruction travels back into the CIR. The second memory read fetches the operand, because the operand lives at the address given in the instruction (address 100), which is a separate memory word from the instruction. Because the Von Neumann machine shares one memory and one data bus between instructions and data, the two reads must happen one after the other and cannot be combined.

### Problem 9

The CPU finishes the instruction currently in the execute stage; it never abandons a half-completed instruction. It checks for a pending interrupt at the end of each fetch-execute cycle, before the next instruction is fetched. On detecting an interrupt, it saves the current state (the PC at minimum, and usually the other registers), loads the PC with the address of the **Interrupt Service Routine (ISR)**, and runs the ISR. At the end of the ISR a return-from-interrupt instruction restores the saved PC and registers, and the original program resumes exactly where it left off.

### Problem 10

- Hardware interrupts: an I/O device finishing a transfer; a hardware timer expiring; a key being pressed; a power-fail warning.
- Software interrupts (exceptions or traps): division by zero; arithmetic overflow; an explicit system call generated by the running program.

## C. Assembly language tracing

### Problem 11

| Step | Instruction | ACC | M[102] | M[103] | Note |
|---|---|---|---|---|---|
| 1 | `LDD 100` | 12 | – | – | ACC ← 12 |
| 2 | `ADD 101` | 17 | – | – | 12 + 5 |
| 3 | `STO 102` | 17 | 17 | – | store sum |
| 4 | `LDD 100` | 12 | 17 | – | reload 12 |
| 5 | `SUB 101` | 7 | 17 | – | 12 - 5 |
| 6 | `STO 103` | 7 | 17 | 7 | store difference |
| 7 | `END` | 7 | 17 | 7 | stop |

Final values: M[102] = 17, M[103] = 7, ACC = 7.

### Problem 12

With M[202] = 5, the counter runs from 3 down to 0, and 5 is added once per iteration.

| Step | Instruction | ACC | M[200] | M[201] | Flag | Note |
|---|---|---|---|---|---|---|
| 1 | `LDM #0` | 0 | – | – | – | total = 0 |
| 2 | `STO 200` | 0 | 0 | – | – | store total |
| 3 | `LDM #3` | 3 | 0 | – | – | counter = 3 |
| 4 | `STO 201` | 3 | 0 | 3 | – | store counter |
| 5 | `LDD 201` | 3 | 0 | 3 | – | load counter |
| 6 | `CMP #0` | 3 | 0 | 3 | F | 3 is not 0 |
| 7 | `JPE Done` | 3 | 0 | 3 | F | no jump |
| 8 | `DEC ACC` | 2 | 0 | 3 | F | counter - 1 |
| 9 | `STO 201` | 2 | 0 | 2 | F | save counter |
| 10 | `LDD 200` | 0 | 0 | 2 | F | load total |
| 11 | `ADD 202` | 5 | 0 | 2 | F | + M[202] = 5 |
| 12 | `STO 200` | 5 | 5 | 2 | F | save total |
| 13 | `JMP LOOP` | 5 | 5 | 2 | F | loop back |
| 14 | `LDD 201` | 2 | 5 | 2 | F | load counter |
| 15 | `CMP #0` | 2 | 5 | 2 | F | 2 is not 0 |
| 16 | `JPE Done` | 2 | 5 | 2 | F | no jump |
| 17 | `DEC ACC` | 1 | 5 | 2 | F | counter - 1 |
| 18 | `STO 201` | 1 | 5 | 1 | F | save counter |
| 19 | `LDD 200` | 5 | 5 | 1 | F | load total |
| 20 | `ADD 202` | 10 | 5 | 1 | F | + 5 |
| 21 | `STO 200` | 10 | 10 | 1 | F | save total |
| 22 | `JMP LOOP` | 10 | 10 | 1 | F | loop back |
| 23 | `LDD 201` | 1 | 10 | 1 | F | load counter |
| 24 | `CMP #0` | 1 | 10 | 1 | F | 1 is not 0 |
| 25 | `JPE Done` | 1 | 10 | 1 | F | no jump |
| 26 | `DEC ACC` | 0 | 10 | 1 | F | counter - 1 |
| 27 | `STO 201` | 0 | 10 | 0 | F | save counter |
| 28 | `LDD 200` | 10 | 10 | 0 | F | load total |
| 29 | `ADD 202` | 15 | 10 | 0 | F | + 5 |
| 30 | `STO 200` | 15 | 15 | 0 | F | save total |
| 31 | `JMP LOOP` | 15 | 15 | 0 | F | loop back |
| 32 | `LDD 201` | 0 | 15 | 0 | F | load counter |
| 33 | `CMP #0` | 0 | 15 | 0 | T | 0 = 0 |
| 34 | `JPE Done` | 0 | 15 | 0 | T | flag True, jump |
| 35 | `LDD 200` | 15 | 15 | 0 | T | load total |
| 36 | `OUT` | 15 | 15 | 0 | T | output 15 |
| 37 | `END` | 15 | 15 | 0 | T | stop |

Final value: M[200] = 15. The loop body ran three times (counter 3 to 0), adding 5 each time, giving 3 x 5 = 15.

### Problem 13

- (a) `LDM #8` - **immediate**. The operand is the value in the instruction. ACC ← 8.
- (b) `LDD 50` - **direct**. The operand is at the address given. ACC ← M[50] = 70.
- (c) `LDI 50` - **indirect**. The address given holds another address. M[50] = 70, so ACC ← M[70] = 3.
- (d) `LDX 50` - **indexed**. The operand is at (given address + IX). 50 + 2 = 52, so ACC ← M[52]. Its value depends on M[52], which is not given.

### Problem 14

A **forward reference** is a jump to a label that is defined later in the program, so its address is not yet known when the jump is first met. The **symbol table** is a table built by the assembler that records the memory address of every label. Pass 1 scans the program, assigns each instruction its address, and builds the symbol table. Pass 2 scans the program again and translates each instruction into machine code, looking up every label in the symbol table to replace it with its address. A single forward pass cannot resolve a forward reference, because the target label's address would not be known when the jump was met; the second pass exists precisely to handle this.

### Problem 15

`JPE` jumps if the compare flag is True (the two values compared were equal). `JPN` jumps if the compare flag is False (the two values were not equal). `CMP #0` compares the value in ACC with 0; it sets the compare flag to True if ACC equals 0 and to False otherwise. The comparison does not change the ACC, which keeps the value it had before the compare.

## D. Bit manipulation

### Problem 16

```text
0010 1011  (43)   LSL #2   ->   1010 1100  (172)
```

Each left shift multiplies by 2, so two shifts give 43 x 4 = 172. Two zero bits enter from the right and the two bits shifted off the left are discarded.

### Problem 17

Arithmetic right shift by 1 on 1100 0000:

```text
1100 0000   ASR #1   ->   1110 0000
```

The sign bit (1) is copied into the vacated position, so the value stays negative. A logical right shift would place a 0 in the vacated position, giving 0110 0000, which is positive. That changes the sign of a signed value and gives the wrong result for halving, so an arithmetic shift must be used for signed numbers.

### Problem 18

Test bit 2 with AND, using a mask with a 1 only in bit position 2:

```text
Value   0100 1001
Mask  & 0000 0100   (bit 2)
Result  0000 0000   zero, so bit 2 is NOT set
```

Set bit 5 with OR, using a mask with a 1 only in bit position 5:

```text
Value   0100 1001
Mask  | 0010 0000   (bit 5)
Result  0110 1001   bit 5 now 1, rest unchanged
```

Bit 2 was not set, because the AND gave zero.

### Problem 19

- **Clear bit 3** with AND. Use the complement of the bit-3 mask. The bit-3 mask is 0000 1000, so its complement is 1111 0111; AND the byte with 1111 0111 to force bit 3 to 0 while leaving every other bit unchanged.
- **Toggle bit 6** with XOR. Use a mask with a 1 only in bit position 6, which is 0100 0000; XOR the byte with 0100 0000 to flip bit 6 (1 becomes 0, 0 becomes 1) while leaving every other bit unchanged.
