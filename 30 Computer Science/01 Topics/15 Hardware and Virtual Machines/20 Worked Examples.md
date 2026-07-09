---
title: Hardware and Virtual Machines Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[Hardware and Virtual Machines](00%20Overview.md)"
status: active
tags:
  - computerscience/computer-systems
  - worked-examples
---

# Hardware and Virtual Machines Worked Examples

These examples model how to reason through A Level questions on processor families, parallel architectures, virtual machines, adders, flip-flops, and Boolean simplification. The aim is to show method: build the comparison first, name the streams for a Flynn question, write the truth table before the expression, and simplify with both algebra and a K-map so the two answers agree.

## Source Route

- Syllabus: CAIE Computer Science 9618, A Level section 15 - Hardware and Virtual Machines.
- Assessed in Paper 3.
- Topics: RISC vs CISC; interrupt handling; pipelining and registers in RISC; SISD, SIMD, MISD, MIMD; massively parallel computers; virtual machines; half and full adders; SR and JK flip-flops; Boolean algebra and De Morgan's laws; Karnaugh maps.

## Example 1: RISC vs CISC for a Battery-Powered Device

**Prompt.** A company is choosing a processor for a battery-powered handheld scanner that runs a fixed, simple program. Compare RISC and CISC for this use and recommend one, giving three reasons.

**Solution.** RISC is recommended.

- RISC uses a small set of simple, fixed-length instructions that typically execute in one cycle, which keeps the hardware simple and the power consumption low. That suits a battery-powered device.
- RISC has many general-purpose registers, so the CPU keeps operands on-chip and rarely accesses slow main memory, which saves power and time.
- RISC pipelines easily because instructions are uniform length and one cycle each, so the pipeline flows without stalls.

CISC has a large, rich instruction set with variable-length instructions that often take several cycles. That complexity uses more silicon and more power, and the variable length makes pipelining harder. CISC suits a desktop PC where rich instructions cut the program count and compatibility with legacy code matters, not a small fixed-purpose scanner.

**Check.** If the question names battery power, a fixed simple task, or pipelining, lean RISC. If it names a PC running legacy x86 software with few instructions per task, lean CISC.

## Example 2: Classify Processors by Flynn Architecture

**Prompt.** For each scenario, state the Flynn architecture and justify it.

- a) A single-core CPU fetches one instruction at a time and acts on one data item.
- b) A GPU applies the same instruction to a whole block of pixels at once.
- c) A multi-core desktop runs several independent programs on different cores.

**Solution.**

- a) **SISD** (Single Instruction, Single Data). One instruction stream acts on one data stream at a time, which is the classic uniprocessor.
- b) **SIMD** (Single Instruction, Multiple Data). One instruction is applied to many data items in parallel, which is data parallelism and the model behind GPU vector processing.
- c) **MIMD** (Multiple Instruction, Multiple Data). Each core runs its own instruction stream on its own data, which is full parallelism and the model behind every multi-core CPU.

MISD, the fourth architecture, has many instructions acting on one data item and is rare in practice, seen in fault-tolerant systems that run redundant checks on a single input.

**Check.** State the streams in the order instruction then data: SISD is 1x1, SIMD is 1xmany, MISD is manyx1, MIMD is manyxmany.

## Example 3: Virtual Machine for Cross-Platform Testing

**Prompt.** A developer who uses a Windows PC needs to test software on Linux without buying a second computer. Explain how a virtual machine solves this, naming the host, hypervisor, and guest, and give two benefits and one limitation.

**Solution.** The developer installs a hypervisor (such as VirtualBox or VMware) on the Windows PC. The Windows PC is the **host**, the hypervisor is the **virtual machine monitor**, and the Linux system running inside it is the **guest**. The hypervisor presents the guest with the illusion that it has its own CPU, memory, disks, and network, so Linux runs as if it owned the hardware, while the host hardware is actually shared.

Benefits:

- The guest runs on any host with a compatible hypervisor, so the developer tests on Linux without a second physical machine.
- The guest is isolated from the host, so a crash or a malicious test program inside Linux cannot easily harm the Windows system.

Limitation:

- Performance overhead. The hypervisor adds a layer between the guest and the hardware, so the VM is slower than running on bare metal, and the guest competes with the host for CPU, memory, and I/O.

**Check.** Always name host, hypervisor, and guest in that order, and separate benefits from limitations into two lists.

## Example 4: Half-Adder Truth Table

**Prompt.** A half adder takes two single-bit inputs A and B and produces a sum S and a carry C. Derive the Boolean expressions and build the truth table.

**Solution.** The sum is 1 when exactly one input is 1, which is XOR. The carry is 1 only when both inputs are 1, which is AND.

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

**Check.** The sum column reads 0, 1, 1, 0, which is XOR. The carry column reads 0, 0, 0, 1, which is AND.

## Example 5: Full-Adder Truth Table

**Prompt.** A full adder takes three single-bit inputs A, B, and a carry-in $C_{in}$, and produces a sum S and a carry-out $C_{out}$. Derive the expressions and build the truth table.

**Solution.** The sum is 1 when an odd number of inputs are 1, which is the XOR of all three. The carry-out is 1 when at least two inputs are 1.

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

To add two n-bit numbers, chain full adders: the $C_{out}$ of each column feeds the $C_{in}$ of the next column to the left, forming a ripple-carry adder.

**Check.** The sum column reads 0, 1, 1, 0, 1, 0, 0, 1, which is parity (odd count of 1s). The carry-out column reads 0, 0, 0, 1, 0, 1, 1, 1, which is the majority function.

## Example 6: SR Flip-Flop Behaviour

**Prompt.** Draw the SR flip-flop, give its truth table, and explain why the state $S=1, R=1$ is forbidden.

**Solution.** The SR (Set-Reset) flip-flop has inputs S (set) and R (reset), and outputs Q and $\overline{Q}$. Q is the stored bit.

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

The state $S=1, R=1$ is forbidden because set and reset fight at once: both try to drive Q and $\overline{Q}$ to the same value, and when S and R are released together the stored value is unpredictable. Circuit designers must simply avoid this combination. The JK flip-flop fixes this by toggling the output when both inputs are 1 instead of producing an invalid state.

**Check.** If the question asks about SR, always state the forbidden state and why it is unpredictable. If it asks about JK, state the toggle case instead.

## Example 7: Simplify with De Morgan's Law

**Prompt.** Simplify $Z = \overline{\overline{A} \cdot \overline{B}}$ into a plain OR of A and B, showing each step.

**Solution.** Apply De Morgan's law to the outer overbar: break the bar, swap the AND for an OR, and invert each variable inside.

```text
Z = ¬(¬A · ¬B)        ; given
  = ¬¬A + ¬¬B          ; De Morgan: break bar, AND -> OR, invert each
  = A + B              ; double negation cancels (¬¬A = A, ¬¬B = B)
```

So

$$
Z = A + B
$$

This is more than a manipulation trick. NAND and NOR are the cheapest gates to build in silicon, so converting any expression to use only them is how real circuits get minimised. Here the original NAND-of-complements is equivalent to a simple OR.

**Check.** Apply De Morgan by remembering the rule in words: break the bar, swap the operator, invert each variable. The common error is to forget the inversion and write $\overline{A \cdot B} = A + B$, which is wrong; the correct form is $\overline{A \cdot B} = \overline{A} + \overline{B}$.

## Example 8: Solve a Logic Problem with a Karnaugh Map

**Prompt.** Simplify the function whose truth table is given below, using a Karnaugh map. Show the groups and the final expression.

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

**Solution.** Copy the truth table into a 3-variable K-map. The columns use Gray-code order (00, 01, 11, 10) so that moving one step changes exactly one variable. The 1s sit in the two columns where $C=1$.

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

The simplified expression is therefore

$$
X = C
$$

Sanity check with algebra. The minterms are 1, 3, 5, 7:

$$
X = \overline{A}\,\overline{B}C + \overline{A}BC + A\overline{B}C + ABC
$$

Factor $C$ out of every term:

$$
X = C \cdot (\overline{A}\,\overline{B} + \overline{A}B + A\overline{B} + AB)
$$

The bracket is every combination of $A$ and $B$, so it equals 1:

$$
X = C \cdot 1 = C
$$

The K-map and the algebra agree.

**Check.** Confirm the K-map columns are in Gray-code order, not binary order, or the adjacency the method relies on is lost. Confirm each group is a power of two in size; here the group of 4 is valid.
