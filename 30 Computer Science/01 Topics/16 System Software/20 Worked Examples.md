---
title: System Software Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[System Software](00%20Overview.md)"
status: active
tags:
  - computerscience/computer-systems
  - worked-examples
---

# System Software Worked Examples

These worked examples cover the A Level internals of an operating system and of translators: process states and scheduling, interrupt handling, paging and segmentation, disk thrashing, the stages of compilation, BNF, and Reverse Polish Notation (RPN). The aim is method, not memorising. Cover each solution, attempt the prompt on paper, then compare.

## Source Route

- Syllabus **9618 A Level Section 16 - System Software**.
- 16.1 Purposes of an Operating System: process states, scheduling routines (FCFS, SJF, round robin, SRT), the kernel as interrupt handler, virtual memory, paging, segmentation, page replacement, disk thrashing.
- 16.2 Translation Software: interpreter execution without a translated version; stages of compilation (lexical analysis, syntax analysis, code generation, optimisation); grammar via syntax diagrams or BNF; RPN for expression evaluation.
- Assessed in **Paper 3**.

The recurring skill is tracing. For scheduling, draw the trace table and compute average waiting time. For memory, contrast fixed pages against logical segments. For translation, walk source through each compilation stage. For expressions, move through infix to BNF to RPN to a stack evaluation.

## Example 1: Describe a process state and a transition

**Prompt.** A program is waiting for the user to press a key. State the process's state, name the two other process states, and describe the transition that occurs the moment the key is pressed and the transition that occurs when the process is given the CPU.

**Solution.** The process is **blocked**: it cannot proceed until an event (the key press) occurs, so it gives up the CPU and waits. The other two states are **running** (the process currently using the CPU) and **ready** (the process could use the CPU but is waiting its turn).

Transitions:
1. Blocked to ready. When the key is pressed, the event the process was waiting for has happened, so it becomes able to run and joins the ready queue. It does not run immediately.
2. Ready to running. When the scheduler picks this process and gives it the CPU, it becomes the running process.

**Check.** A process only enters the running state from the ready state (dispatch), and only enters the blocked state from the running state (it asked for something it must wait for, such as input). It never goes straight from blocked to running.

## Example 2: Trace a shortest-job-first scheduler

**Prompt.** Four processes arrive with the times below. Using non-preemptive shortest job first (SJF), draw a trace table showing start and finish for each process, and compute the average waiting time.

| Process | Arrival time | Burst time |
|---|---|---|
| P1 | 0 | 6 |
| P2 | 1 | 3 |
| P3 | 2 | 8 |
| P4 | 3 | 4 |

**Solution.** At each decision point, choose from the processes that have already arrived the one with the smallest burst time.

| Time | Event | Running |
|---|---|---|
| 0 | P1 arrives; it is the only choice | P1 |
| 6 | P1 finishes; P2, P3, P4 are ready; P2 has the smallest burst (3) | P2 |
| 9 | P2 finishes; P3 (8), P4 (4) ready; P4 has the smallest burst (4) | P4 |
| 13 | P4 finishes; only P3 remains | P3 |
| 21 | P3 finishes | - |

Waiting time = start time minus arrival time.

| Process | Arrival | Start | Waiting |
|---|---|---|---|
| P1 | 0 | 0 | 0 |
| P2 | 1 | 6 | 5 |
| P3 | 2 | 13 | 11 |
| P4 | 3 | 9 | 6 |

Average waiting time = (0 + 5 + 11 + 6) / 4 = 22 / 4 = **5.5**.

**Check.** At time 6, all of P2, P3, P4 have arrived, so the choice between them is purely on burst time (3, 8, 4); P2 wins. The average is the sum of waiting times divided by the number of processes, not by total time.

## Example 3: Trace a round-robin scheduler

**Prompt.** Three processes arrive with the times below. Using round robin with a time quantum of 4, draw the trace table and compute the average waiting time.

| Process | Arrival time | Burst time |
|---|---|---|
| P1 | 0 | 7 |
| P2 | 1 | 4 |
| P3 | 2 | 5 |

**Solution.** Each process runs for at most one quantum, then goes to the back of the ready queue if it is not finished.

| Time | Running | Remaining after slice | Ready queue (front first) |
|---|---|---|---|
| 0-4 | P1 | P1:3 | P2, P3 |
| 4-8 | P2 | P2:0 (done) | P3, P1 |
| 8-12 | P3 | P3:1 | P1, P3 |
| 12-15 | P1 | P1:0 (done) | P3 |
| 15-16 | P3 | P3:0 (done) | - |

Finish times: P2 = 8, P3 = 16, P1 = 15. Waiting time = finish time minus arrival time minus burst time.

| Process | Arrival | Burst | Finish | Waiting |
|---|---|---|---|---|
| P1 | 0 | 7 | 15 | 15 - 0 - 7 = 8 |
| P2 | 1 | 4 | 8 | 8 - 1 - 4 = 3 |
| P3 | 2 | 5 | 16 | 16 - 2 - 5 = 9 |

Average waiting time = (8 + 3 + 9) / 3 = 20 / 3 = **6.67**.

**Check.** When a process's slice ends but it is not finished, it rejoins the back of the queue, not the front. A newly arrived process also joins the back. Count every unit of time exactly once.

## Example 4: Kernel interrupt handling for scheduling

**Prompt.** A running process's time slice expires. Explain the role of the kernel and of interrupts in switching the CPU to the next process.

**Solution.**
1. A hardware timer generates an **interrupt** when the time slice ends. The currently running process is paused.
2. Control passes to the **kernel**, which is the interrupt handler. The kernel saves the state of the interrupted process (the values of its registers, including the program counter) into its process control block, so the process can later resume exactly where it stopped.
3. The kernel's scheduling routine then selects the next process from the ready queue, loads that process's saved state into the CPU registers, and resumes it.
4. The old process is placed at the back of the ready queue (round robin) or handled according to whichever scheduling policy is in use.

This is how low-level scheduling is driven by interrupts handled by the kernel.

**Check.** The interrupt is the trigger; the kernel is the handler; the saved register set (in the process control block) is what lets each process resume. Without saving state, a resumed process would continue from the wrong instruction.

## Example 5: Compare paging and segmentation

**Prompt.** Distinguish paging from segmentation under the headings: how the address space is divided, whether the units are fixed or variable, and what each is used for.

**Solution.**

| Aspect | Paging | Segmentation |
|---|---|---|
| How memory is divided | The virtual address space is split into equal-sized **pages**; RAM is split into equal-sized **frames** of the same size | The address space is split into **segments** that correspond to logical units such as the code segment, data segment, and stack |
| Size of units | Fixed size, set by the hardware (for example 4 KB) | Variable size, depending on the size of each logical unit |
| Visibility to the programmer | Invisible; the programmer does not define pages | Visible; the programmer or compiler deliberately groups code and data into segments |
| Main use | Lets the OS move fixed pages between RAM and backing store to implement virtual memory | Groups memory by logical purpose, so related items share an access-controlled region |

**Check.** Paging is fixed and invisible (a mechanism for virtual memory); segmentation is variable and logical (a mechanism for organising memory). A page is a physical unit; a segment is a logical unit.

## Example 6: Explain how disk thrashing occurs

**Prompt.** A user opens many large programs until the disk light stays on continuously and the system almost stops responding. Explain how disk thrashing occurs and state one consequence.

**Solution.** Each running process needs some of its pages to be in RAM to make progress. When too many processes are active, the total demand for RAM exceeds what is available, so the OS constantly moves pages out to backing store and brings them back.

A process is then paged out, and almost immediately needs a page that has just been paged out, so it must be paged in again, displacing another page that a third process is about to need. The system spends more time moving pages to and from disk than executing instructions. The disk light stays on because of the constant page traffic, and effective work nearly stops.

One consequence is a severe drop in throughput: the CPU is mostly idle waiting for pages, while the disk is saturated.

**Check.** Thrashing is the failure mode of virtual memory. It is caused by too little RAM for the load, and its symptom is constant disk activity with little CPU work. The cure is to reduce the number of running processes or add RAM.

## Example 7: The four stages of compilation with example outputs

**Prompt.** For the assignment statement `sum ← a + b * c`, describe each of the four stages of compilation and give an example of what each stage produces.

**Solution.**
1. **Lexical analysis.** The source is read character by character and split into tokens. Whitespace and comments are discarded; invalid symbols are reported. Output: the token stream `identifier(sum), assign, identifier(a), plus, identifier(b), multiply, identifier(c)`.
2. **Syntax analysis.** The token stream is checked against the grammar of the language (expressed as syntax diagrams or BNF) and built into a structure that captures nesting and precedence. Output: a parse tree whose top node is `assign`, with `sum` on the left and an expression `a + (b * c)` on the right (multiplication binds tighter than addition).
3. **Code generation.** The structure is translated into machine code (or an intermediate form), using the target processor's instruction set and a run-time stack for the expression. Output (illustrative):

```
LOAD  b
LOAD  c
MUL        ; b * c
LOAD  a
ADD        ; a + (b * c)
STORE sum
```

4. **Optimisation.** The generated code is improved so it runs faster or uses less memory, for example removing redundant loads, simplifying constant expressions, or keeping a value in a register instead of reloading it.

**Check.** Order matters: lexical analysis (tokens) before syntax analysis (structure), syntax analysis before code generation (instructions), optimisation improving the generated code. Symbol tables are built mainly during the first two stages and used by the later ones.

## Example 8: Convert infix to RPN and evaluate on a stack

**Prompt.** Convert `( 4 + 5 ) * 2 - 6` to Reverse Polish Notation, then evaluate it step by step using a stack.

**Solution.** Applying the operators after their operands, respecting the brackets first and then left-to-right precedence:

```
4 5 + 2 * 6 -
```

Stack evaluation, reading the RPN left to right. On an operand, push it; on an operator, pop two operands, apply, and push the result.

| Step | Token | Stack (top on right) | Action |
|---|---|---|---|
| 1 | 4 | 4 | push |
| 2 | 5 | 4 5 | push |
| 3 | + | 9 | pop 5, pop 4, push 4 + 5 |
| 4 | 2 | 9 2 | push |
| 5 | * | 18 | pop 2, pop 9, push 9 * 2 |
| 6 | 6 | 18 6 | push |
| 7 | - | 12 | pop 6, pop 18, push 18 - 6 |

Final result: **12**, which matches the infix value ((4 + 5) * 2 - 6 = 18 - 6 = 12).

**Check.** RPN needs no brackets because the order of operations is fixed by the position of each operator. The two popped operands are applied in the order they were pushed, which matters for subtraction and division: for `18 6 -`, compute 18 - 6 = 12, not 6 - 18.

## Study Routine

1. For process states, draw the three states and recall that a process only enters running from ready, and only enters blocked from running.
2. For scheduling, always build the trace table before computing waiting time. At each decision point, list which processes have arrived, then apply the rule.
3. For paging versus segmentation, contrast fixed/invisible with variable/logical.
4. For thrashing, link it to too little RAM, constant page traffic, and a saturated disk.
5. For compilation, keep the four stages in order and give an example output for each.
6. For RPN, convert first, then evaluate on a stack, reading left to right and pushing operands.
