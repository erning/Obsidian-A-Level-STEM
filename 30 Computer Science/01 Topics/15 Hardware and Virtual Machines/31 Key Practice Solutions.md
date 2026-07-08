---
title: Hardware and Virtual Machines Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/00 Overview|Hardware and Virtual Machines]]"
status: active
tags:
  - computerscience/computer-systems
  - solutions
---

# Hardware and Virtual Machines Key Practice Solutions

These solutions correspond to [[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/30 Key Practice Problems|Key Practice Problems]].

## A. Processors and architectures

### Problem 1

| Aspect | RISC | CISC |
|---|---|---|
| Instruction set | Small, simple, fixed-purpose instructions | Large, rich, specialised instructions |
| Cycles per instruction | Typically one cycle per instruction | Often several cycles per instruction |
| Pipelining | Easy and effective; fixed-length instructions keep the pipeline flowing | Harder; variable-length instructions stall the pipeline |

Examples: RISC is ARM (used in phones, Apple Silicon, Raspberry Pi); CISC is Intel x86 or AMD (used in PCs and servers).

### Problem 2

CISC is recommended. The PC must run a large body of legacy x86 software, and CISC's rich instruction set means fewer instructions are needed per task, which keeps the legacy code compatible and efficient. CISC processors such as Intel x86 and AMD are exactly the platforms that run this software natively. RISC would require translating or recompiling the legacy code, because RISC uses a smaller, simpler instruction set and needs more instructions to do the same work; it also lacks the specialised instructions the legacy software may rely on. RISC suits battery-powered or fixed-purpose devices, not a PC running a large legacy codebase.

### Problem 3

A RISC processor has many general-purpose registers, so the CPU can keep operands in registers instead of spilling them to slow main memory. Because the operands are already on-chip, the CPU does not have to perform load and store operations on the bus for every calculation, which reduces memory traffic and lets the pipeline run at full speed. In short, many registers cut load/store traffic and keep the pipeline fed.

### Problem 4

On a CISC processor a single instruction may take many cycles and access memory several times, so an interrupt that arrives mid-instruction has to wait longer for the instruction to finish, and the saved state is more complex. On a RISC processor instructions are short and atomic (typically one cycle each), so the CPU reaches a clean interrupt point quickly and the context to save is smaller. RISC therefore handles interrupts with less delay and less overhead.

### Problem 5

- a) **SISD** (Single Instruction, Single Data). One instruction stream acts on one data stream at a time, the classic uniprocessor.
- b) **SIMD** (Single Instruction, Multiple Data). One instruction is applied to many data items in parallel, which is data parallelism and the model behind GPU vector processing.
- c) **MIMD** (Multiple Instruction, Multiple Data). Each core runs its own instruction stream on its own data, which is full parallelism and the model behind every multi-core CPU.
- d) **MISD** (Multiple Instruction, Single Data). Many instruction streams act on the same data item, which is rare in practice and seen in fault-tolerant systems that run redundant checks on one input and vote on the result.

### Problem 6

Two characteristics of a massively parallel computer:

- It links hundreds or thousands of processors (cores or nodes), each with its own local distributed memory rather than one shared store.
- The nodes coordinate by message passing over a high-speed interconnect, because they cannot all read one memory.

Communication overhead limits speed-up because the time spent moving data between nodes does not contribute to the computation itself. As more nodes are added, the fraction of time spent communicating grows, so a problem only scales well when it can be split into chunks that barely need to talk to each other. Beyond the point where communication dominates, adding more nodes gives little or no benefit.

## B. Virtual machines

### Problem 7

A virtual machine (VM) is a software simulation of a complete computer. A program called the hypervisor (or virtual machine monitor) runs on the real **host** hardware and presents each **guest** with the illusion that it has its own CPU, memory, disks, and network. The guest runs its own full operating system unaware that the hardware underneath is shared.

### Problem 8

The developer installs a hypervisor (such as VirtualBox or VMware) on the Windows PC. The Windows PC is the host, the hypervisor is the virtual machine monitor, and the Linux system running inside it is the guest. The hypervisor presents the guest with the illusion that it has its own CPU, memory, disks, and network, so Linux runs as if it owned the hardware while the host hardware is actually shared.

Benefits:

- The guest runs on any host with a compatible hypervisor, so the developer tests on Linux without buying a second physical machine.
- The guest is isolated from the host, so a crash or a malicious test program inside Linux cannot easily harm the Windows system.

Limitation:

- Performance overhead. The hypervisor adds a layer between the guest and the hardware, so the VM is slower than running on bare metal, and the guest competes with the host for CPU, memory, and I/O.

### Problem 9

A virtual machine runs an operating system written for the same CPU family as the host; the hypervisor mostly manages resources rather than translating instructions, so it runs fast. An emulator also simulates hardware, but it translates a foreign CPU's instructions into the host's instruction set, which is needed when the guest CPU family differs from the host's.

An emulator is the better choice when the software targets a different CPU architecture, for example running an old games console's ARM or MIPS code on an x86 PC. A VM cannot do this directly because the guest OS expects the host's CPU family.

### Problem 10

Benefits:

- Better hardware utilisation. Many small servers that would each sit idle on separate physical boxes are packed onto one machine, so the host's CPU, memory, and I/O are used more fully.
- Easy management. VMs can be snapshotted, cloned, and migrated to other hosts, which simplifies backup, recovery, and load balancing.

Limitations:

- Performance overhead. The hypervisor adds a layer, so each VM is slower than running on bare metal.
- Resource sharing and complexity. Guests compete for the host's CPU, memory, and I/O, and running many OS instances complicates licensing and management.

## C. Logic circuits and flip-flops

### Problem 11

The sum is 1 when exactly one input is 1, which is XOR. The carry is 1 only when both inputs are 1, which is AND.

$$
S = A \oplus B \qquad C = A \cdot B
$$

| A | B | S | C |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

The half adder cannot accept a carry from a previous column, so on its own it only adds the lowest bit.

### Problem 12

The sum is 1 when an odd number of inputs are 1, which is the XOR of all three. The carry-out is 1 when at least two inputs are 1.

$$
S = A \oplus B \oplus C_{in} \qquad C_{out} = A \cdot B + C_{in} \cdot (A \oplus B)
$$

| A | B | $C_{in}$ | S | $C_{out}$ |
|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

### Problem 13

To add two n-bit numbers, full adders are chained in a ripple-carry adder. The $C_{out}$ of each column feeds the $C_{in}$ of the next column to the left, so a carry propagates from the least significant bit up to the most significant. The first column uses a half adder, or a full adder with $C_{in}=0$. The arrangement is called a ripple-carry adder because the carry ripples from one column to the next.

### Problem 14

The SR (Set-Reset) flip-flop has inputs S (set) and R (reset), and outputs Q and $\overline{Q}$. Q is the stored bit.

```text
       +-----+
  S -->|     |
       | SR  |--> Q
  R -->|     |--> Q̄
       +-----+
```

Truth table (level-triggered):

| S | R | $Q_{next}$ | Action |
|---|---|---|---|
| 0 | 0 | Q | hold (no change) |
| 0 | 1 | 0 | reset |
| 1 | 0 | 1 | set |
| 1 | 1 | invalid | forbidden |

The state $S=1, R=1$ is forbidden because set and reset fight at once: both try to drive Q and $\overline{Q}$ to the same value, and when S and R are released together the stored value is unpredictable. Circuit designers must simply avoid this combination.

### Problem 15

The JK flip-flop has inputs J (set) and K (reset), and outputs Q and $\overline{Q}$. It is usually edge-triggered, changing only on a clock transition.

```text
       +-----+
  J -->|     |
       | JK  |--> Q
  K -->|     |--> Q̄
  clk->|     |
       +-----+
```

Truth table (on the clock edge):

| J | K | $Q_{next}$ | Action |
|---|---|---|---|
| 0 | 0 | Q | hold (no change) |
| 0 | 1 | 0 | reset |
| 1 | 0 | 1 | set |
| 1 | 1 | $\overline{Q}$ | toggle |

When $J=1, K=1$ the output toggles (flips to the opposite value) instead of producing an invalid state. This is the improvement over SR: the JK removes the forbidden state by making the both-1 case useful, which is why feeding the output back through the toggle case turns a JK into a T (toggle) flip-flop, the basis of counters.

## D. Boolean algebra and K-maps

### Problem 16

De Morgan's laws:

$$
\overline{A \cdot B} = \overline{A} + \overline{B} \qquad \overline{A + B} = \overline{A} \cdot \overline{B}
$$

The rule in words: break the bar, swap the operator, and invert each variable inside.

Simplify $Z = \overline{\overline{A} \cdot \overline{B}}$:

```text
Z = ¬(¬A · ¬B)        ; given
  = ¬¬A + ¬¬B          ; De Morgan: break bar, AND -> OR, invert each
  = A + B              ; double negation cancels
```

$$
Z = A + B
$$

### Problem 17

$$
X = A \cdot B + A \cdot \overline{B} + \overline{A} \cdot B
$$

Combine the first two terms by factoring out A:

$$
A \cdot B + A \cdot \overline{B} = A \cdot (B + \overline{B}) = A \cdot 1 = A
$$

So the expression reduces to

$$
X = A + \overline{A} \cdot B
$$

Now use the absorption identity $A + \overline{A} \cdot B = A + B$ (when A is 1 the output is 1 regardless of B; when A is 0 the output is B):

$$
X = A + B
$$

Simplified circuit: a single OR gate taking inputs A and B. The output is 1 whenever at least one input is 1.

### Problem 18

$$
Y = \overline{A + \overline{B}}
$$

Apply De Morgan's law to the overbar: break the bar, swap the OR for an AND, and invert each variable inside.

```text
Y = ¬(A + ¬B)         ; given
  = ¬A · ¬¬B           ; De Morgan: break bar, OR -> AND, invert each
  = ¬A · B             ; double negation cancels (¬¬B = B)
```

$$
Y = \overline{A} \cdot B
$$

The output is 1 only when $A=0$ and $B=1$.

### Problem 19

Copy the truth table into a 3-variable K-map with Gray-code columns (00, 01, 11, 10). The 1s sit in the two columns where $C=1$.

```text
           BC
       00  01  11  10
   0 | 0 | 1 | 1 | 0 |
A  1 | 0 | 1 | 1 | 0 |
```

Group the four 1s as one group of 4 (the whole right half of the map, columns 01 and 11). Within that group:

- $A$ takes both 0 and 1, so drop $A$.
- $B$ takes both 0 and 1, so drop $B$.
- $C$ stays fixed at 1, so keep $C$.

$$
X = C
$$

Algebra check: $X = \overline{A}\,\overline{B}C + \overline{A}BC + A\overline{B}C + ABC = C \cdot (\overline{A}\,\overline{B} + \overline{A}B + A\overline{B} + AB) = C \cdot 1 = C$. The two methods agree.

### Problem 20

The 1s are at minterms 1, 3, 7, 9, 11, 15. Copy the truth table into a 4-variable K-map with Gray-code order on both axes (rows AB: 00, 01, 11, 10; columns CD: 00, 01, 11, 10).

```text
            CD
        00  01  11  10
    00 | 0 | 1 | 1 | 0 |
AB  01 | 0 | 0 | 1 | 0 |
    11 | 0 | 0 | 1 | 0 |
    10 | 0 | 1 | 1 | 0 |
```

Two groups cover all the 1s:

- **Group 1 (group of 4):** the whole column CD = 11, rows 00, 01, 11, 10, covering minterms 3, 7, 11, 15. Within it $A$ takes both 0 and 1 (drop $A$) and $B$ takes both 0 and 1 (drop $B$); $C=1$ and $D=1$ stay fixed. Term: $C \cdot D$.
- **Group 2 (group of 4):** the 2x2 block at rows AB = 00 and AB = 10 (adjacent by top-to-bottom wraparound) and columns CD = 01 and CD = 11, covering minterms 1, 3, 9, 11. Within it $A$ takes both 0 and 1 (drop $A$) and $C$ takes both 0 and 1 (drop $C$); $B=0$ and $D=1$ stay fixed. Term: $\overline{B} \cdot D$.

All six 1s are covered (minterms 3 and 11 are reused, which is allowed). The simplified expression is

$$
X = C \cdot D + \overline{B} \cdot D = D \cdot (C + \overline{B})
$$

Algebra check, starting from the minterms:

$$
X = \overline{A}\,\overline{B}\,\overline{C}D + \overline{A}\,\overline{B}CD + \overline{A}BCD + A\overline{B}\,\overline{C}D + A\overline{B}CD + ABCD
$$

Group the terms with $B=0$ and the terms with $CD$:

$$
X = \overline{B}D(\overline{A}\,\overline{C} + \overline{A}C + A\overline{C} + AC) + BCD(\overline{A} + A)
$$

The first bracket is every combination of $A$ and $C$, so it equals 1; the second bracket also equals 1:

$$
X = \overline{B}D + BCD = D(\overline{B} + BC) = D(\overline{B} + C) = \overline{B}D + CD
$$

using the identity $\overline{B} + BC = \overline{B} + C$. The K-map and the algebra agree.
