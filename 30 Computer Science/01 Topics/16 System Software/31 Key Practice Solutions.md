---
title: System Software Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[System Software](00%20Overview.md)"
status: active
tags:
  - computerscience/computer-systems
  - solutions
---

# System Software Key Practice Solutions

This note gives worked solutions for [System Software Key Practice Problems](30%20Key%20Practice%20Problems.md). Each solution shows the full reasoning, with trace tables and stack evaluations, so you can find the step where your working diverged, not just compare final answers.

## A. Process management

### Problem 1

The three process states:

- **Running.** The process is currently using the CPU. Only one process can be in this state at a time on a single-core CPU.
- **Ready.** The process could run but is waiting its turn in the ready queue, for example a program that has just been loaded or that has just finished waiting for input.
- **Blocked.** The process cannot proceed until some event occurs, for example a program waiting for a key press or for data to arrive from disk.

### Problem 2

1. Running to blocked. The process needs a value the user must type, so it cannot continue; it stops using the CPU and waits for that event.
2. Blocked to ready. When the user presses a key, the event occurs, so the process becomes able to run and joins the ready queue. It does not run immediately; it must wait to be dispatched. The transition from ready to running happens later, when the scheduler gives it the CPU.

### Problem 3

A single CPU executes only one stream of instructions at a time, so only one program is truly running at any instant. Multi-tasking is the rapid switching of the CPU between several ready processes, giving each a short time slice in turn. Because the slices are short and the switching is fast, each program makes progress often enough that, to the user, they all appear to run at once. Without multi-tasking, whichever program started would keep the CPU until it finished, and every other open program would be stuck.

### Problem 4

First come first served runs each process in arrival order.

| Process | Arrival | Burst | Start | Finish | Waiting |
|---|---|---|---|---|---|
| P1 | 0 | 5 | 0 | 5 | 0 |
| P2 | 1 | 7 | 5 | 12 | 4 |
| P3 | 2 | 3 | 12 | 15 | 10 |
| P4 | 3 | 6 | 15 | 21 | 12 |

Average waiting time = (0 + 4 + 10 + 12) / 4 = 26 / 4 = **6.5**.

### Problem 5

Shortest job first chooses, whenever the CPU is free, the arrived process with the smallest burst time. P1 runs first (only P1 has arrived at time 0) and finishes at 5.

| Process | Arrival | Burst | Start | Finish | Waiting |
|---|---|---|---|---|---|
| P1 | 0 | 5 | 0 | 5 | 0 |
| P3 | 2 | 3 | 5 | 8 | 3 |
| P4 | 3 | 6 | 8 | 14 | 5 |
| P2 | 1 | 7 | 14 | 21 | 13 |

At time 5, P2 (7), P3 (3), and P4 (6) have all arrived, so P3 runs first; then at time 8, P2 (7) and P4 (6) remain, so P4 runs next.

Average waiting time = (0 + 3 + 5 + 13) / 4 = 21 / 4 = **5.25**.

For this set of processes, SJF (5.25) gives a lower average waiting time than FCFS (6.5).

### Problem 6

Round robin with a time quantum of 3. P1 and P2 both arrive at time 0; P3 arrives at time 2.

| Time | Running | Remaining after slice | Ready queue (front first) |
|---|---|---|---|
| 0-3 | P1 | P1:2 | P2 |
| 3-6 | P2 | P2:1 | P1, P3 (P3 arrives at 2) |
| 6-8 | P1 | P1:0 (done) | P3, P2 |
| 8-10 | P3 | P3:0 (done) | P2 |
| 10-11 | P2 | P2:0 (done) | - |

Finish times: P1 = 8, P2 = 11, P3 = 10. Waiting time = finish time minus arrival time minus burst time.

| Process | Arrival | Burst | Finish | Waiting |
|---|---|---|---|---|
| P1 | 0 | 5 | 8 | 3 |
| P2 | 0 | 4 | 11 | 7 |
| P3 | 2 | 2 | 10 | 6 |

Average waiting time = (3 + 7 + 6) / 3 = 16 / 3 = **5.33**.

### Problem 7

When the time slice ends, a hardware timer raises an interrupt. The CPU stops the running process and control passes to the kernel, which acts as the interrupt handler. The kernel saves the state of the interrupted process, the values of its registers including the program counter, into a data structure called the process control block, so that the process can later resume exactly where it stopped. The kernel's scheduling routine then selects the next process from the ready queue, loads that process's saved register state into the CPU, and dispatches it. The interrupted process is placed at the back of the ready queue to await its next slice.

## B. Memory management

### Problem 8

Virtual memory gives each program the illusion that it has a large, contiguous area of memory, even though the physical RAM is smaller. It works by keeping only the parts of each program that are currently needed in **RAM**, while the rest is held on **backing store** (a hard disk or SSD). When the program touches a part that is not currently in RAM, the OS brings it in from backing store, displacing some less recently used part if RAM is full. In this way the computer can run programs whose total size exceeds the installed RAM, at the cost of slower access when pages must be fetched from backing store.

### Problem 9

| Aspect | Paging | Segmentation |
|---|---|---|
| How the address space is divided | Split into equal-sized pages; RAM is split into frames of the same size | Split into segments that match logical units such as code, data, and stack |
| Fixed or variable size | Fixed size, set by the hardware | Variable size, depending on each logical unit |
| Visible to the programmer | Invisible; the programmer does not define pages | Visible; the programmer or compiler deliberately groups code and data into segments |

### Problem 10

LRU replaces the page whose most recent use was the longest time ago. Frames shown left to right with the most recently used at the right.

| Reference | Frames before | Hit/Miss | Frames after | Evicted |
|---|---|---|---|---|
| 3 | - | Miss | 3 | - |
| 4 | 3 | Miss | 3 4 | - |
| 2 | 3 4 | Miss | 3 4 2 | - |
| 3 | 3 4 2 | Hit | 4 2 3 | - |
| 4 | 4 2 3 | Hit | 2 3 4 | - |
| 5 | 2 3 4 | Miss | 3 4 5 | 2 |
| 3 | 3 4 5 | Hit | 4 5 3 | - |
| 5 | 4 5 3 | Hit | 4 3 5 | - |
| 2 | 4 3 5 | Miss | 3 5 2 | 4 |
| 4 | 3 5 2 | Miss | 5 2 4 | 3 |

Total page faults = **6** (the six misses above).

### Problem 11

Disk thrashing is the state in which the system spends more time moving pages between RAM and backing store than executing instructions. It occurs when too many processes are active for the amount of RAM available: a page is paged out, then almost immediately needed again, so it is paged back in, displacing a page another process is about to need. The disk is constantly busy and the CPU is mostly idle. To reduce thrashing, a user can close some running programs so fewer pages compete for RAM, or an administrator can install more RAM.

## C. Compilation

### Problem 12

1. **Lexical analysis.** The source is read character by character and split into tokens; whitespace and comments are discarded and invalid symbols are reported. It produces a token stream and contributes to the symbol table.
2. **Syntax analysis.** The token stream is checked against the grammar of the language (syntax diagrams or BNF) and built into a parse tree that captures nesting and precedence. It produces the parse tree and reports syntax errors.
3. **Code generation.** The parse tree is translated into machine code, or an intermediate form, using the target instruction set. It produces the program's object code.
4. **Optimisation.** The generated code is improved to run faster or use less memory. It produces improved code (for example, with redundant loads removed).

### Problem 13

(a) Lexical analysis output:

```
identifier(total), assign, identifier(x), plus, identifier(y), minus, identifier(z)
```

(b) Code generation output (illustrative, left-to-right same-precedence operators):

```
LOAD  x
LOAD  y
ADD        ; x + y
LOAD  z
SUB        ; (x + y) - z
STORE total
```

### Problem 14

An interpreter executes a program without producing a translated version in two ways:

1. It reads each statement and immediately carries it out, translating and executing one statement at a time, without creating a separate executable file.
2. It can run partially written code, executing statements as they are reached, which makes it well suited to interactive testing.

One disadvantage is speed: because each statement is re-translated every time it is encountered (for example, every pass through a loop), interpreted programs run more slowly than compiled programs that have been translated once into optimised machine code.

### Problem 15

Two benefits of optimisation:

1. Faster execution, for example by evaluating constant expressions once at compile time, removing redundant loads and stores, or keeping frequently used values in registers instead of memory.
2. Smaller code size, for example by removing unreachable instructions or merging identical sections, which can also improve cache use.

## D. BNF and RPN

### Problem 16

```
<signed integer> ::= <sign> <unsigned integer> | <unsigned integer>
<sign>           ::= "+" | "-"
<unsigned integer> ::= <digit> | <unsigned integer> <digit>
<digit>          ::= "0" | "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9"
```

### Problem 17

```
<variable>  ::= <letter> | <variable> <letter> | <variable> <digit>
<letter>    ::= "A" | "B" | "C" | "D" | "E" | "F" | "G" | "H" | "I" | "J"
              | "K" | "L" | "M" | "N" | "O" | "P" | "Q" | "R" | "S" | "T"
              | "U" | "V" | "W" | "X" | "Y" | "Z"
<digit>     ::= "0" | "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9"
<factor>    ::= <unsigned integer> | <variable> | "(" <expression> ")"
```

### Problem 18

(a) `A + B - C` becomes `A B + C -`

(b) `A + B * C` becomes `A B C * +`

(c) `( A + B ) * ( C - D )` becomes `A B + C D - *`

### Problem 19

Reading `6 2 3 + - 4 *` left to right: on an operand, push it; on an operator, pop two operands, apply, push the result.

| Step | Token | Stack (top on right) | Action |
|---|---|---|---|
| 1 | 6 | 6 | push |
| 2 | 2 | 6 2 | push |
| 3 | 3 | 6 2 3 | push |
| 4 | + | 6 5 | pop 3, pop 2, push 2 + 3 |
| 5 | - | 1 | pop 5, pop 6, push 6 - 5 |
| 6 | 4 | 1 4 | push |
| 7 | * | 4 | pop 4, pop 1, push 1 * 4 |

Final result: **4**. This equals the infix value: (6 - (2 + 3)) * 4 = (6 - 5) * 4 = 4.

### Problem 20

RPN needs no brackets and no precedence rule because each operator is written immediately after the operands it applies to, so the order of evaluation is fixed entirely by the position of the operators. To evaluate an RPN expression, only two stack operations are needed: **push**, used for every operand to place it on the stack, and **pop**, used when an operator is met to remove its two operands (the result is then pushed back).
