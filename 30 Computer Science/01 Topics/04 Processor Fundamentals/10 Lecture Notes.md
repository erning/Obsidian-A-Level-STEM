---
title: Processor Fundamentals Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]]"
status: active
tags:
  - computerscience/computer-systems
  - lecture-notes
---

# Processor Fundamentals Lecture Notes

A computer is useful only because it can carry out a stored program one step at a
time. This topic is about the engine that does that work: how the CPU is built,
how it repeatedly fetches and executes instructions, how those instructions look
at the assembly level, and how it can manipulate individual bits to control real
devices. Get the fetch-execute cycle and the register roles straight here, and
tracing assembly programs becomes mechanical rather than mysterious.

## Source Route

This note follows CAIE Computer Science 9618, AS section 4:

- 4.1 CPU Architecture
- 4.2 Assembly Language
- 4.3 Bit manipulation

Section 4 is examined in Paper 1.

## 1. The Von Neumann model and CPU components

The **Von Neumann model** is the design idea behind almost every modern CPU: the
program (its instructions) and the data it works on are both stored in the same
main memory. This **stored-program concept** means a single piece of hardware can
do radically different jobs simply by loading different contents into memory. The
CPU does not need to be rewired for each task; it just reads a new sequence of
instructions and obeys them one at a time. Because instructions and data share
one memory and one set of buses, the CPU cannot fetch the next instruction and
read an operand at the exact same instant - this is sometimes called the Von
Neumann bottleneck, but the simplicity of the design outweighs the cost.

Inside the CPU there are four components to know by role.

- **ALU (Arithmetic Logic Unit).** The calculating part. It carries out all
  arithmetic (add, subtract, increment, decrement) and all logic (AND, OR, XOR,
  shifts, comparisons) the instruction set asks for.
- **Control Unit (CU).** The directing part. It decodes the instruction held in
  the Current Instruction Register and sends the control signals that tell every
  other component - ALU, memory, buses, registers - what to do and when.
- **System clock.** A crystal oscillator that produces a steady train of timing
  pulses. Every step of the fetch-execute cycle is synchronised to these ticks;
  one tick is one clock cycle, and clock speed is measured in cycles per second
  (Hz, GHz).
- **Immediate Access Store (IAS).** The storage that sits inside the CPU itself
  - its registers - so the processor can reach it without going out to main
  memory. The IAS holds the handful of values the CPU is working on right now.

## 2. Registers

A **register** is a very fast storage location inside the CPU, built from
flip-flops. They divide into two kinds.

- **General-purpose registers** can be used by the programmer for any holding
  job. In this instruction set there is exactly one general-purpose working
  register: the **Accumulator (ACC)**, which every calculation works through.
  The **Index Register (IX)** is separate: it is programmer-addressable, but
  its dedicated role is indexed addressing and it is often used as a counter.
- **Special-purpose registers** each have a single fixed role in the
  fetch-execute cycle and cannot be used for anything else.

| Register | Abbrev | Role |
|---|---|---|
| Program Counter | PC | Holds the address of the next instruction to be fetched |
| Memory Address Register | MAR | Holds the address in memory that is currently being read from or written to |
| Memory Data Register | MDR | Holds the data just read from memory or about to be written to memory (a.k.a. Memory Buffer Register) |
| Current Instruction Register | CIR | Holds the instruction currently being decoded and executed |
| Accumulator | ACC | The single general-purpose working register; every arithmetic and logic result is built here |
| Index Register | IX | Dedicated index register; holds an offset used in indexed addressing and often used as a loop counter |
| Status Register | - | Holds flag bits set by the ALU, e.g. the compare flag (result of CMP), zero flag, sign flag, overflow flag, carry flag |

The Status Register is sometimes called the flag register. Each bit records one
fact about the last ALU operation. The one that matters for assembly tracing is
the **compare flag**: a `CMP` instruction sets it to True (1) if the two values
are equal and False (0) otherwise, and `JPE`/`JPN` then test exactly this flag.

## 3. Buses, performance factors, and ports

The CPU talks to memory and peripherals over three buses, each carrying a
different kind of signal.

- **Address bus.** Carries the address that the CPU wants to read or write. In a
  Von Neumann machine it is normally **unidirectional** (CPU to memory).
- **Data bus.** Carries the actual data being read or written. It is
  **bidirectional**.
- **Control bus.** Carries timing and command signals such as read/write, clock,
  interrupt, and reset. It is bidirectional.

Five factors affect how fast a processor feels.

| Factor | How it affects performance |
|---|---|
| Processor type | A RISC design runs simpler, faster, one-cycle instructions; a CISC design uses richer, slower instructions. Fewer cycles per instruction means more done per second. |
| Number of cores | Each core can run its own instruction stream, so a multi-core CPU can do genuinely parallel work on separate tasks or threads. |
| Bus width | A wider data bus moves more bits per transfer; a wider address bus can address more memory locations. Both reduce the number of transfers needed. |
| Clock speed | More cycles per second means more fetch-execute cycles per second, so more instructions completed in a given time. |
| Cache memory | Small, fast SRAM between the CPU and RAM holds recently used data and instructions, cutting the average time the CPU waits for memory. |

A **port** is a socket through which a peripheral connects to the computer.

- **USB (Universal Serial Bus).** A general-purpose serial port for almost any
  peripheral - mouse, keyboard, storage, printer. It is hot-pluggable, supplies
  power to small devices, and supports many device types through one connector.
- **HDMI (High-Definition Multimedia Interface).** A digital port carrying both
  high-quality video and audio to a monitor or TV.
- **VGA (Video Graphics Array).** An older, analogue video-only port, still found
  on projectors and legacy monitors.

## 4. The Fetch-Execute cycle

The CPU repeats the **fetch-decode-execute cycle** forever, one instruction at a
time. In register-transfer notation (where `←` means "is loaded from" and
`[MAR]` means "the contents of memory at the address held in MAR"):

```text
--- FETCH ---
MAR  ← PC                 ; address of next instruction copied to MAR
MDR  ← [MAR]              ; control unit issues a memory read;
                           ; the instruction travels back along the data bus
CIR  ← MDR                ; the fetched instruction is held for decoding
PC   ← PC + 1             ; PC advanced to point at the next instruction

--- DECODE ---
CU    decodes the opcode held in CIR
MAR  ← operand address of CIR     ; only if the instruction needs a memory operand
MDR  ← [MAR]                       ; the operand itself is fetched

--- EXECUTE (depends on the opcode) ---
; for example,  ADD <address>:
ACC  ← ACC + MDR
; the ALU sets flags in the Status Register as needed
```

Two details catch students out. First, the PC is incremented during fetch so that
by the time this instruction finishes, the PC already points at the next one.
Second, any instruction that needs a memory operand causes a second memory read
during decode/execute - fetching the instruction and fetching its operand are
separate bus transactions.

## 5. Interrupts

An **interrupt** is a signal telling the CPU that some event needs attention
right now. Causes fall into two groups.

- **Hardware interrupts** come from outside the CPU: an I/O device finishing a
  transfer, a hardware timer expiring, a key being pressed, or a power-fail
  warning.
- **Software interrupts** (exceptions/traps) come from inside the running
  program: division by zero, arithmetic overflow, or an explicit system call.

When the CPU receives an interrupt, it does not stop mid-instruction. It
finishes the current fetch-execute cycle, then runs a small routine called an
**Interrupt Service Routine (ISR)** that deals with the event. The full sequence
is:

1. The CPU completes the instruction currently in the execute stage.
2. It detects the pending interrupt (this check happens at the end of each
   fetch-execute cycle, before the next instruction is fetched).
3. It saves the current state - at least the PC, and usually the other registers
   - so the interrupted program can resume exactly where it left off.
4. The PC is loaded with the address of the ISR, so the next fetch runs the ISR.
5. The ISR executes, servicing the device or handling the exception.
6. At the end of the ISR, a return-from-interrupt instruction restores the saved
   registers and PC, and the original program continues as if nothing happened.

## 6. Assembly language

### Machine code and the two-pass assembler

At the hardware level every instruction is just a binary pattern - **machine
code**. **Assembly language** is the human-readable form of the same thing: each
line is one short **mnemonic** (such as `ADD`) plus its operands, and each
mnemonic maps directly onto one machine-code instruction. A program called an
**assembler** translates assembly into machine code.

The translation is done in **two passes** because a program can jump to a label
that has not yet been defined - a **forward reference**.

- **Pass 1.** The assembler scans the program in order, assigns each instruction
  its memory address, and builds a **symbol table** recording the address of
  every label. It also reports any label that is defined twice.
- **Pass 2.** The assembler scans the program a second time and translates each
  instruction into machine code, looking up every label in the symbol table to
  replace it with its address.

Without two passes, a jump to a label further down the file could not be resolved
on a single forward scan, because that label's address would not yet be known.

### Instruction groups

| Group | Purpose | Examples |
|---|---|---|
| Data movement | Move data between ACC, IX, and memory | `LDD`, `LDX`, `STO`, `MOV` |
| Input / output | Read from or send to a peripheral | `IN`, `OUT` |
| Arithmetic | Perform calculations | `ADD`, `SUB`, `INC`, `DEC` |
| Unconditional control transfer | Always jump | `JMP` |
| Conditional control transfer | Jump based on the compare flag | `JPE`, `JPN` |
| Compare | Set the compare flag by comparing two values | `CMP`, `CMI` |
| Bit manipulation | Bitwise logic and shifts | `AND`, `OR`, `XOR`, `LSL`, `LSR` |

### Addressing modes

The **addressing mode** is the rule the CPU uses to work out where the operand
is. Each mode below is shown with the load instruction that uses it.

| Mode | How the operand is found | Example | Effect |
|---|---|---|---|
| Immediate | The operand is the value written in the instruction itself | `LDM #5` | ACC ← 5 |
| Direct | The operand is stored at the address given in the instruction | `LDD 100` | ACC ← M[100] |
| Indirect | The address given holds another address; the operand is there | `LDI 100` | ACC ← M[M[100]] |
| Indexed | The operand is at the address (given address + IX) | `LDX 100` | ACC ← M[100 + IX] |
| Relative | The address is given as an offset from the current PC | `JMP +3` (concept) | jump to PC + offset |

Relative addressing is used for short, position-independent jumps: the target is
calculated from wherever the program happens to be loaded, so the same code runs
unchanged at any address.

### Full instruction set reference

In operands, `#` means a denary value, `B` means binary, and `&` means
hexadecimal.

| Mnemonic | Operand | Action |
|---|---|---|
| `LDM` | `#n` | Load the immediate value n into ACC |
| `LDD` | `<address>` | Load the contents of address into ACC (direct) |
| `LDI` | `<address>` | Load the contents of the address held at address into ACC (indirect) |
| `LDX` | `<address>` | Load the contents of (address + IX) into ACC (indexed) |
| `LDR` | `#n` | Load the value n into IX |
| `MOV` | `IX` | Copy the contents of ACC into IX |
| `STO` | `<address>` | Store the contents of ACC at address |
| `ADD` | `<address>` or `#n` | Add to ACC (memory contents or immediate) |
| `SUB` | `<address>` or `#n` | Subtract from ACC |
| `INC` | `<register>` | Increment ACC or IX by 1 |
| `DEC` | `<register>` | Decrement ACC or IX by 1 |
| `JMP` | `<address>` | Jump unconditionally to address |
| `CMP` | `<address>` or `#n` | Compare ACC with operand; set compare flag True if equal |
| `CMI` | `<address>` | Compare ACC with the contents of the address held at address (indirect) |
| `JPE` | `<address>` | Jump if the compare flag is True (equal) |
| `JPN` | `<address>` | Jump if the compare flag is False (not equal) |
| `IN` | - | Key in a character and store its ASCII value in ACC |
| `OUT` | - | Output the character whose ASCII value is stored in ACC |
| `AND` | `#n`/`Bn`/`&n` or `<address>` | Bitwise AND of ACC with the operand |
| `OR` | `#n`/`Bn`/`&n` or `<address>` | Bitwise OR of ACC with the operand |
| `XOR` | `#n`/`Bn`/`&n` or `<address>` | Bitwise XOR of ACC with the operand |
| `LSL` | `#n` | Logical left shift of ACC by n places |
| `LSR` | `#n` | Logical right shift of ACC by n places |
| `END` | - | Stop execution |

## 7. Worked assembly trace: multiplication by repeated addition

The program below multiplies two numbers by adding the multiplicand to itself
once for each unit of the multiplier. The multiplicand is at address 100, the
multiplier (used as a count) at address 101, and the running product is kept at
address 200, with address 201 used as scratch to save the count. With
M[100] = 5 and M[101] = 2 the result should be 10.

```asm
        LDD 101         ; ACC = multiplier (the count)
LOOP:   CMP #0          ; is the count 0?
        JPE Done        ; if yes, multiplication is finished
        DEC ACC         ; count = count - 1
        STO 201         ; save the count in M[201]
        LDD 200         ; ACC = running product
        ADD 100         ; ACC = product + multiplicand
        STO 200         ; store the new product
        LDD 201         ; ACC = saved count
        JMP LOOP        ; go back and test again
Done:   LDD 200         ; ACC = final product
        OUT             ; output the product
        END
```

The trick is that ACC is the only working register, so the running product has
to live in memory (address 200). Each iteration the count is decremented in ACC,
saved to 201, the product is pulled into ACC, the multiplicand is added, the
product is stored back, and the saved count is reloaded so the loop test can run
again.

Walking it through, with M[100] = 5, M[101] = 2, M[200] = 0:

| Step | Instruction | ACC | M[200] | M[201] | Flag | Note |
|---|---|---|---|---|---|---|
| 1 | `LDD 101` | 2 | 0 | – | – | load the count |
| 2 | `CMP #0` | 2 | 0 | – | F | 2 ≠ 0 |
| 3 | `JPE Done` | 2 | 0 | – | F | flag False, no jump |
| 4 | `DEC ACC` | 1 | 0 | – | F | count down |
| 5 | `STO 201` | 1 | 0 | 1 | F | save count |
| 6 | `LDD 200` | 0 | 0 | 1 | F | load product |
| 7 | `ADD 100` | 5 | 0 | 1 | F | + 5 |
| 8 | `STO 200` | 5 | 5 | 1 | F | store product |
| 9 | `LDD 201` | 1 | 5 | 1 | F | restore count |
| 10 | `JMP LOOP` | 1 | 5 | 1 | F | loop back |
| 11 | `CMP #0` | 1 | 5 | 1 | F | 1 ≠ 0 |
| 12 | `JPE Done` | 1 | 5 | 1 | F | no jump |
| 13 | `DEC ACC` | 0 | 5 | 1 | F | count down |
| 14 | `STO 201` | 0 | 5 | 0 | F | save count |
| 15 | `LDD 200` | 5 | 5 | 0 | F | load product |
| 16 | `ADD 100` | 10 | 5 | 0 | F | + 5 |
| 17 | `STO 200` | 10 | 10 | 0 | F | store product |
| 18 | `LDD 201` | 0 | 10 | 0 | F | restore count |
| 19 | `JMP LOOP` | 0 | 10 | 0 | F | loop back |
| 20 | `CMP #0` | 0 | 10 | 0 | T | 0 = 0 |
| 21 | `JPE Done` | 0 | 10 | 0 | T | flag True, jump |
| 22 | `LDD 200` | 10 | 10 | 0 | T | load final product |
| 23 | `OUT` | 10 | 10 | 0 | T | output 10 |
| 24 | `END` | 10 | 10 | 0 | T | stop |

Final state: ACC = 10, M[200] = 10, and 10 is output. The loop body ran twice
(once for each unit of the multiplier 2), adding the multiplicand 5 each time,
giving 5 × 2 = 10.

## 8. Bit manipulation

### Binary shifts

A shift moves every bit of a value one or more places left or right. There are
three kinds.

**Logical shift** - vacated positions are filled with 0, and the bit that falls
off the end is discarded. Left and right behave symmetrically.

```text
LSL #1 on   0001 0011  (19)   ->   0010 0110  (38)      ; 19 x 2
LSR #1 on   0010 0110  (38)   ->   0001 0011  (19)      ; 38 / 2
```

**Arithmetic shift** - used for signed numbers. A right shift copies the sign
bit (the leftmost bit) into the vacated positions, so a negative number stays
negative. It is the correct way to halve a signed value.

```text
ASR #1 on   1001 0110  (signed negative)
         -> 1100 1011                        ; sign bit 1 is copied in
```

**Cyclic (rotate) shift** - no bits are lost. The bit that falls off one end is
moved to the other end.

```text
Rotate right 1 on   1011 0011   ->   1101 1001     ; last bit wraps to the front
Rotate left  1 on   1011 0011   ->   0110 0111     ; first bit wraps to the back
```

### Bit masking: test and set a bit

A **bit mask** is a pattern of bits used with a bitwise operator to reach one
particular bit of a value. This is how a program monitors or controls a device:
each bit of an input or output byte stands for one sensor or one switch.

**Test a bit** with AND. AND the value with a mask that has a 1 only in the bit
position of interest; if the result is non-zero, that bit was set.

```text
Value   1011 0110   Is bit 5 set?
Mask  & 0010 0000   (bit 5 = 1)
Result  0010 0000   non-zero -> bit 5 IS set
```

**Set a bit** (turn it on) with OR. OR the value with a mask that has a 1 in the
target position; every other bit is left unchanged.

```text
Value   1011 0010   Set bit 3
Mask  | 0000 1000
Result  1011 1010   bit 3 now 1, the rest unchanged
```

In practice the CPU does a read-modify-write: it loads the current port value,
applies the mask, and stores the result back, so that setting bit 3 does not
disturb the other seven device bits. AND with the complement of a mask clears a
bit, and XOR with a mask toggles it.

## Worked-Thinking Routine

1. For any CPU question, name the component by its role first (ALU calculates,
   CU directs, clock synchronises, IAS stores inside the CPU), then add detail.
2. For register questions, separate the single general-purpose working
   register (ACC), the Index Register (IX), and the other special-purpose
   registers; never confuse MAR (the address) with MDR (the data).
3. When describing the fetch-execute cycle, write it in register-transfer
   notation and tick off PC → MAR → MDR → CIR → PC+1 in that order.
4. For assembly tracing, set up a table with one column per register and per
   relevant memory cell, and fill one row per executed instruction.
5. Before tracing, note the loop test and which flag JPE/JPN actually read.
6. For bit manipulation, write the mask out in full binary next to the value so
   the AND/OR is visible, not done in your head.

## Common Mistakes

- Swapping MAR and MDR. MAR always holds an address; MDR always holds data.
- Forgetting to increment the PC during fetch, so the next fetch reads the same
  instruction forever.
- Treating `JPE` as "jump if positive". It means jump if the **compare flag is
  True**, i.e. the last `CMP` found the two values equal.
- Calling a register or cache "memory" without distinguishing it from main
  memory. The IAS is inside the CPU; RAM is outside it.
- Confusing the addressing modes - especially indirect (the address holds an
  address) with indexed (the address is added to IX).
- Doing only one assembler pass and then being unable to resolve a forward jump.
  Two passes exist precisely to handle forward references.
- Applying a logical right shift to a signed number and claiming it halves it;
  use an arithmetic shift so the sign bit is preserved.
- Setting a bit with AND instead of OR. AND can only clear or keep bits; OR is
  what turns a bit on.

## Quick Self-Check

You are ready to move on when you can answer these without notes.

1. State the stored-program concept in one sentence, and say why it makes a
   computer general-purpose.
2. Name the four CPU components and give the role of each.
3. Distinguish a general-purpose register from a special-purpose register, with
   one example of each.
4. Write the fetch stage of the fetch-execute cycle in register-transfer
   notation.
5. Why are there separate address, data, and control buses rather than one?
6. List five factors that affect CPU performance and say how each one helps.
7. Describe how an interrupt is detected and handled, naming the ISR.
8. Why does an assembler need two passes?
9. Give one example each of immediate, direct, indirect, and indexed addressing.
10. Trace a short loop that uses `CMP` and `JPN` to repeat until a counter
    reaches zero.
11. Show, with masks, how to test bit 4 of a byte and how to set bit 4.
12. Why is an arithmetic right shift used for signed numbers but a logical one
    is not?

## Connections

- [[30 Computer Science/01 Topics/03 Hardware/00 Overview|Hardware]] supplies the
  logic gates, flip-flops, and SRAM/DRAM that the registers, cache, and buses in
  this topic are built from.
- [[30 Computer Science/01 Topics/01 Information Representation/00 Overview|Information Representation]]
  and [[30 Computer Science/01 Topics/13 Data Representation/00 Overview|Data Representation]]
  supply the binary, hexadecimal, signed-value, and bit-pattern ideas used in
  machine code, shifts, and masks.
- [[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/00 Overview|Hardware and Virtual Machines]]
  takes this CPU further into RISC versus CISC, parallel processing, and the
  relationship between virtual machines and real hardware; [[30 Computer Science/01 Topics/20 Further Programming/00 Overview|Further Programming]]
  reuses the same low-level ideas when reasoning about memory, data movement,
  and control flow.

## Study Sequence

1. Read sections 1 and 2 to fix the Von Neumann idea and the role of every
   register before anything else.
2. Learn the three buses and the five performance factors in section 3 as
   matched pairs (factor → effect).
3. Memorise the fetch-execute cycle in section 4 as register-transfer notation
   you can write out from blank.
4. Make the interrupt sequence in section 5 concrete by walking through one
   hardware example (e.g. a key press) end to end.
5. Memorise the instruction-set and addressing-mode tables in section 6, then
   work the multiplication trace in section 7 line by line.
6. Practise the three shift types and the test/set masking in section 8 until
   the masks are obvious on sight.
7. Self-check against the questions above before connecting to Hardware and
   Virtual Machines.
