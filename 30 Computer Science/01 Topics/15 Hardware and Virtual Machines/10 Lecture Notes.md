---
title: Hardware and Virtual Machines Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/00 Overview|Hardware and Virtual Machines]]"
status: active
tags:
  - computerscience/computer-systems
  - lecture-notes
---

# Hardware and Virtual Machines Lecture Notes

This A Level topic picks up where AS sections 3 (Hardware) and 4 (Processor
Fundamentals) left off. It zooms out from a single CPU to compare processor
families (RISC vs CISC), to classify whole computer architectures by how many
instruction and data streams run at once, and to run one machine inside another
as a virtual machine. It then comes back down to the gate level, building adders
and memory cells (flip-flops) and giving you two tools - Boolean algebra and
Karnaugh maps - to simplify the logic that comes out of them.

## Source Route

This note follows CAIE Computer Science 9618, A Level section 15:

- 15.1 Processors, Parallel Processing and Virtual Machines
- 15.2 Boolean Algebra and Logic Circuits

Section 15 is examined in Paper 3.

## 1. RISC versus CISC

Processors fall into two design families according to how rich their instruction
set is. **CISC (Complex Instruction Set Computer)** packs many specialised,
multi-step instructions into hardware; **RISC (Reduced Instruction Set Computer)**
keeps a small set of simple, fast instructions and lets software combine them.

| Aspect | RISC | CISC |
|---|---|---|
| Instruction set | Small, simple, fixed-purpose instructions | Large, rich, specialised instructions |
| Complexity | Complexity moved into the compiler (software) | Complexity built into the hardware / microcode |
| Instructions per task | More instructions needed (each does little) | Fewer instructions needed (each does more) |
| Cycles per instruction | Typically one cycle per instruction | Often several cycles per instruction |
| Instruction length | Fixed length | Variable length |
| Registers | Many general-purpose registers | Fewer registers |
| Addressing modes | Few, simple modes | Many modes |
| Pipelining | Easy and effective (one cycle → steady flow) | Harder (variable-length instructions stall the pipeline) |
| Power / cost | Lower power, cheaper hardware | More silicon, more power |
| Examples | ARM (phones, Apple Silicon, Raspberry Pi) | Intel x86, AMD (PCs and servers) |

### Pipelining and registers in RISC

**Pipelining** overlaps the stages of several instructions so that while one is
being executed, the next is being decoded and the one after that is being
fetched - like a factory assembly line. RISC suits pipelining because every
instruction takes roughly one cycle and has a fixed length, so the pipeline keeps
flowing with no stalls.

```text
Cycle:    1        2        3        4        5
Instr 1:  Fetch    Decode   Execute
Instr 2:           Fetch    Decode   Execute
Instr 3:                    Fetch    Decode   Execute
```

RISC processors also carry **many general-purpose registers**. Having lots of
fast on-chip storage means the CPU can keep operands in registers instead of
spilling them to slow main memory, and it reduces the load/store traffic on the
bus - both of which let the pipeline run at full speed.

### Interrupt handling on each

Both families handle interrupts the same way in principle - finish the current
instruction, save state (at least the PC), jump to an Interrupt Service Routine,
and return. The difference is cost. On a **CISC** processor a single instruction
may take many cycles and access memory several times, so an interrupt that
arrives mid-instruction has to wait longer and the saved state is more complex.
On a **RISC** processor instructions are short and atomic, so the CPU reaches a
clean interrupt point quickly and the context to save is smaller.

## 2. The four Flynn architectures

Michael Flynn classified computers by how many **instruction streams** and
**data streams** they process at once. Each combination is one architecture.

| Architecture | Instruction streams | Data streams | Description | Example |
|---|---|---|---|---|
| **SISD** | Single | Single | One instruction acts on one piece of data at a time - a classic single-core CPU | Traditional uniprocessor PC |
| **SIMD** | Single | Multiple | One instruction acts on many data items at once - data parallelism | GPU vector processing, image/pixel operations |
| **MISD** | Multiple | Single | Many instructions act on the same data - rare in practice | Fault-tolerant systems running redundant checks on one input |
| **MIMD** | Multiple | Multiple | Many instructions act on many data items - full parallelism | Multi-core CPUs, distributed systems, clusters |

SISD and MIMD are the two you meet most: SISD is the single-core serial machine,
and MIMD is the model behind every multi-core and multi-machine system. SIMD is
how GPUs and vector units process whole arrays of pixels or audio samples in one
go.

## 3. Massively parallel computers

A **massively parallel computer** (or massively parallel processor, MPP) pushes
MIMD to the extreme: it links hundreds or thousands of processors to attack one
problem at the same time. Weather forecasting, fluid dynamics, drug discovery and
large AI training all rely on this kind of machine.

Key characteristics:

- **Very many processors** - hundreds to hundreds of thousands of cores.
- **Distributed memory** - each processor (or node) has its own local memory
  rather than one shared store, which avoids the memory-bottleneck of a single
  shared bus.
- **High-speed interconnect** - processors exchange data over a fast network
  (e.g. InfiniBand) because they cannot all read one memory.
- **Message passing** - nodes coordinate by sending messages, not by reading
  shared variables.
- **Communication overhead** - the time spent moving data between nodes is the
  main limit on speed-up; a problem must be divisible into chunks that barely
  need to talk to each other to scale well.
- **Scalability** - adding more nodes increases total power, but only up to the
  point where communication overhead dominates.

## 4. Virtual machines

A **virtual machine (VM)** is a software simulation of a complete computer. A
program called a **hypervisor** (or virtual machine monitor) runs on the real
**host** hardware and presents each **guest** with the illusion that it has its
own CPU, memory, disks and network. The guest runs its own full operating system
unaware that the hardware underneath is shared.

The role and examples of virtual machines:

- **Running one OS inside another** - running Linux on a Windows laptop, or an
  old version of an OS for legacy software.
- **Sandboxing** - isolating an untrusted program so it cannot harm the host.
- **Server consolidation** - packing many small servers as VMs onto one physical
  box, improving utilisation.
- **Cross-platform development and testing** - build and test software on several
  OSes from one machine.
- **Cloud computing** - providers sell VMs to customers so each tenant gets an
  isolated environment.

Benefits:

- A guest can run on any host with a compatible hypervisor - hardware is
  abstracted away.
- Snapshots, cloning and migration make VMs easy to back up, copy and move.
- Strong isolation between guests improves security and reliability.
- Better hardware utilisation through consolidation.

Limitations:

- **Performance overhead** - the hypervisor adds a layer, so a VM is slower than
  running on bare metal (though near-native with hardware assist).
- **Resource sharing** - guests compete for the host's CPU, memory and I/O.
- **Hardware dependency** - a VM typically needs the host to provide compatible
  virtual hardware and a hypervisor.
- **Licensing and complexity** - running many OS instances can complicate
  licensing and management.

Note the distinction from an **emulator**: an emulator also simulates hardware,
but it usually translates a foreign CPU's instructions to the host's (e.g.
running an old games console on a PC), whereas a VM typically runs an OS written
for the same CPU family as the host.

## 5. Half adder and full adder

An **adder** is the circuit at the heart of the ALU that adds binary digits. The
simplest is the **half adder**, which adds two single bits and produces a sum
and a carry.

$$S = A \oplus B \qquad C = A \cdot B$$

| A | B | Sum (S) | Carry (C) |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

A half adder cannot take in a carry from a previous column, so on its own it
only adds the lowest bit. The **full adder** fixes this: it adds three bits
($A$, $B$, and a carry-in $C_{in}$) and produces a sum and a carry-out.

$$S = A \oplus B \oplus C_{in} \qquad C_{out} = A \cdot B + C_{in} \cdot (A \oplus B)$$

| A | B | C<sub>in</sub> | Sum (S) | C<sub>out</sub> |
|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

To add multi-bit numbers you **chain** full adders: the $C_{out}$ of each column
feeds the $C_{in}$ of the next column to the left, and the first column uses a
half adder (or a full adder with $C_{in}=0$). This ripple of carries gives the
arrangement its name, a **ripple-carry adder**.

## 6. Flip-flops

A **flip-flop** is a circuit that stores one bit. Its output holds its value
until an input changes it, so flip-flops are the building block of registers,
cache and RAM. The two CAIE asks for are the **SR** and the **JK**.

### SR flip-flop

The **SR (Set-Reset) flip-flop** has two inputs: **S** (set, forces output to 1)
and **R** (reset, forces output to 0). Output **Q** is the stored bit, and
**Q̄** is its complement.

```text
       +-----+
  S -->|     |
       | SR  |--> Q
  R -->|     |--> Q̄
       +-----+

   Truth table (level-triggered):
   S  R  | Q_next   Action
   --------------------------
   0  0  | Q        hold (no change)
   0  1  | 0        reset
   1  0  | 1        set
   1  1  | invalid  forbidden
```

The **invalid state** is $S=1, R=1$: both commands fight at once, Q and Q̄ both
try to become equal, and when S and R are released together the stored value is
unpredictable. Circuit designers must simply avoid this combination.

### JK flip-flop

The **JK flip-flop** removes that flaw. **J** acts like set, **K** like reset,
and when both are 1 the output **toggles** (flips to the opposite value) instead
of producing an invalid state.

```text
       +-----+
  J -->|     |
       | JK  |--> Q
  K -->|     |--> Q̄
  clk->|     |
       +-----+

   Truth table (on the clock edge):
   J  K  | Q_next   Action
   --------------------------
   0  0  | Q        hold (no change)
   0  1  | 0        reset
   1  0  | 1        set
   1  1  | Q̄        toggle
```

The JK is usually **edge-triggered**: it only changes on a clock transition,
which lets many flip-flops in a circuit change together in a controlled way. By
feeding a JK's output back through the toggle case it becomes a **T
(toggle) flip-flop**, the basis of counters. As storage elements, flip-flops are
what registers are made of - string enough of them together and you have an
n-bit register.

## 7. Boolean algebra and De Morgan's laws

**Boolean algebra** manipulates logic expressions the way ordinary algebra
manipulates numbers. The values are 0 and 1, and the operators are AND ($\cdot$),
OR ($+$), and NOT ($\overline{\phantom{x}}$). The core identities:

| Law | Form |
|---|---|
| Identity | $A + 0 = A$; $\;A \cdot 1 = A$ |
| Null | $A + 1 = 1$; $\;A \cdot 0 = 0$ |
| Idempotent | $A + A = A$; $\;A \cdot A = A$ |
| Complement | $A + \overline{A} = 1$; $\;A \cdot \overline{A} = 0$ |
| Commutative | $A + B = B + A$; $\;A \cdot B = B \cdot A$ |
| Associative | $(A + B) + C = A + (B + C)$; analogously for AND |
| Distributive | $A \cdot (B + C) = A \cdot B + A \cdot C$; $\;A + B \cdot C = (A + B)(A + C)$ |
| Absorption | $A + A \cdot B = A$; $\;A \cdot (A + B) = A$ |

### De Morgan's laws

These two laws let you convert ANDs into ORs and vice versa by pushing a NOT
through the brackets. They are the key tool for converting between sum-of-products
and product-of-sums, and for turning a NAND/NOR-only circuit into any logic.

$$\overline{A \cdot B} = \overline{A} + \overline{B} \qquad \text{(NAND = NOR of the complements)}$$

$$\overline{A + B} = \overline{A} \cdot \overline{B} \qquad \text{(NOR = AND of the complements)}$$

The rule in words: break the bar, swap the operator, and each variable is
inverted. To cancel a double bar, $\overline{\overline{A}} = A$.

### Worked simplification using De Morgan

Simplify $Z = \overline{\overline{A} \cdot \overline{B}}$ into a plain OR.

```text
Z = ¬(¬A · ¬B)        ; given
  = ¬¬A + ¬¬B          ; De Morgan: break bar, AND -> OR, invert each
  = A + B              ; double negation cancels
```

So $Z = A + B$. This is more than a parlour trick: NAND and NOR are the cheapest
gates to build in silicon, so converting any expression to use only them is how
real circuits get minimised.

## 8. Karnaugh maps

A **Karnaugh map (K-map)** is a grid that lays out a truth table so that adjacent
cells differ in only one variable. Because neighbours differ by one input, a
group of adjacent 1s corresponds to a term in which that variable can be dropped
- the visual equivalent of the absorption law. K-maps work for 2, 3 and 4
variables; beyond that they get unwieldy.

The benefit: you minimise by eye, **without** grinding through algebra, and it
shows the simplest sum-of-products form directly. It is also harder to make the
"forgot a term" mistake that bedevils algebra.

### Layout

Cells are labelled with **Gray-code** order (00, 01, 11, 10) so that moving one
step changes exactly one bit. A 3-variable map (inputs $A,B,C$) looks like:

```text
           BC
       00  01  11  10
   0 |   |   |   |   |
A  1 |   |   |   |   |
```

### Grouping rules

- Group only cells that contain a 1 (the minterms), and group in sizes that are
  powers of two: 1, 2, 4, 8.
- Make groups as large as possible - bigger groups drop more variables.
- Cells on opposite edges wrap around (the map is a torus).
- Each 1 must be covered by at least one group; reuse is allowed.

### Worked example

Simplify $X = \sum m(1,3,5,7)$ for inputs $A,B,C$.

Truth table (X = 1 at minterms 1, 3, 5, 7):

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

K-map (the 1s sit in both columns where $C=1$):

```text
           BC
       00  01  11  10
   0 | 0 | 1 | 1 | 0 |
A  1 | 0 | 1 | 1 | 0 |
```

All four 1s form one group of 4 (the whole right half of the map, columns 01 and
11). Within that group, $A$ takes both 0 and 1 (so drop $A$) and $B$ takes both 0
and 1 (so drop $B$); only $C$ stays fixed at 1.

$$X = C$$

Sanity check with algebra: $X = \overline{A}\,\overline{B}C + \overline{A}BC + A\overline{B}C + ABC = (\overline{A}+A)(\overline{B}+B)C = 1 \cdot 1 \cdot C = C$. The two methods agree - the K-map just showed it at a glance.

## Worked-Thinking Routine

1. For a RISC-vs-CISC question, build the comparison table in your head first
   (instruction set, cycles, pipelining, registers), then write the rows the
   question actually asks for.
2. For a Flynn architecture question, state the streams (instruction × data) in
   that order, then give a concrete example - that pair is the whole answer.
3. For a virtual-machine question, name the host, the hypervisor, and the guest,
   and separate benefits from limitations into two lists.
4. For an adder, write the truth table first, then read off the sum (XOR) and
   carry (AND) outputs. Remember a full adder adds three inputs, not two.
5. For a flip-flop question, draw the box with inputs and outputs, give the
   truth table, and explicitly state the SR forbidden state or the JK toggle.
6. For Boolean simplification, apply the identity laws first (complement,
   idempotent, absorption), then use De Morgan to remove nested bars.
7. For a K-map, copy the truth table into Gray-code order, then hunt for the
   biggest power-of-two groups before writing any term.
8. Cross-check a K-map result against Boolean algebra when you have time; they
   must agree.

## Common Mistakes

- Listing RISC features as CISC features, especially "many registers" (RISC) and
  "rich instructions" (CISC).
- Mixing up SIMD and MIMD: SIMD shares **one** instruction across many data;
  MIMD runs **many** instructions on many data.
- Forgetting the communication overhead when describing massively parallel
  computers - speed-up is limited by how much nodes must talk.
- Treating a VM as identical to an emulator. A VM runs an OS for the same CPU
  family; an emulator translates a different CPU's instructions.
- Building a half adder where the question asks for a full adder, so the
  carry-in input is missed.
- Entering the SR forbidden state ($S=R=1$) and claiming a defined output, or
  forgetting that JK toggles on $J=K=1$.
- Applying De Morgan's law but forgetting to invert the variables inside -
  $\overline{A \cdot B}$ is $\overline{A}+\overline{B}$, not $A+B$.
- Grouping K-map cells in non-power-of-two sizes (3 or 6), or cells that do not
  share a single changing variable.
- Ordering K-map columns as 00, 01, 10, 11 instead of Gray code, which destroys
  the adjacency the method relies on.

## Quick Self-Check

You are ready to move on when you can answer these without notes.

1. Give three differences between RISC and CISC, including how each handles
   pipelining.
2. Why does a RISC processor benefit from having many general-purpose registers?
3. Describe how interrupt handling differs in cost between RISC and CISC.
4. Name the four Flynn architectures and give one example of each.
5. Why is MISD rare in practice?
6. State two characteristics and one limitation of massively parallel computers.
7. Define a virtual machine, and name its host, hypervisor and guest.
8. Give two benefits and two limitations of virtual machines.
9. Draw the truth table for a half adder and for a full adder.
10. Explain how full adders are chained to add two n-bit numbers.
11. Draw the truth table for an SR flip-flop and state why $S=R=1$ is forbidden.
12. How does a JK flip-flop behave when $J=K=1$, and why is that an improvement
    over SR?
13. State both forms of De Morgan's laws.
14. Simplify $Y = \overline{A + \overline{B}}$ using De Morgan.
15. Using a K-map, simplify a given 3- or 4-variable truth table and state the
    groupings you used.

## Connections

- [[30 Computer Science/01 Topics/03 Hardware/00 Overview|Hardware]] supplies the
  logic gates (AND, OR, NOT, NAND, NOR, XOR) from which the adders and flip-flops
  in this topic are built, and the SRAM/DRAM cells that flip-flops scale up into.
- [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]]
  is the AS foundation this topic extends: the single Von Neumann CPU studied
  there becomes SISD here, the registers are shown to be built from flip-flops,
  and RISC/CISC explain why different processors have different instruction sets.

## Study Sequence

1. Read section 1 and commit the RISC-vs-CISC table to memory, including the
   interrupt-handling row.
2. Learn the four Flynn architectures in section 2 as instruction-stream ×
   data-stream, each with one example.
3. In section 3, fix the idea that massively parallel means many processors plus
   distributed memory plus communication overhead.
4. For virtual machines in section 4, separate benefits from limitations and
   keep the host/hypervisor/guest distinction sharp.
5. Build the half-adder and full-adder truth tables in section 5 until they are
   automatic, and explain the chaining of full adders.
6. For flip-flops in section 6, draw both SR and JK, write their truth tables,
   and be able to state the SR forbidden state and the JK toggle case.
7. Memorise the Boolean identities and De Morgan's laws in section 7, then work
   the simplification until breaking the bar becomes automatic.
8. Practise K-maps in section 8 on 3- and 4-variable examples, always using
   Gray-code order and power-of-two groups.
9. Cross-check each K-map answer against Boolean algebra before self-checking
   against the questions above.
