---
title: System Software Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[System Software](00%20Overview.md)"
status: active
tags:
  - computerscience/computer-systems
  - lecture-notes
---

# System Software Lecture Notes

These notes cover **A Level section 16 (System Software)**, examined in Paper 3. The topic extends **AS section 5 (System Software)**, so you should already be comfortable with the basic roles of an operating system and the distinction between systems software and applications software. Here we go deeper into how an OS manages resources and processes, how memory is organised with paging and segmentation, and how high-level source code is translated by interpreters and compilers.

## Source Route

These notes follow the CAIE 9618 syllabus points directly:

- **16.1** Purposes of an Operating System - resource use, user interface, process management, scheduling, interrupt handling, virtual memory, paging and segmentation.
- **16.2** Translation Software - interpreters, compilation stages, grammar (syntax diagrams and BNF), and Reverse Polish Notation (RPN).

## 1. Operating system: maximising resources and hiding hardware

An **operating system (OS)** is systems software that manages the computer's hardware and software resources and provides common services for applications. Its core purpose is to **maximise the use of resources** so that the CPU, memory, storage and I/O devices are kept busy and shared fairly between many programs and users.

The OS maximises resource use by:

- **Multi-programming / multi-tasking** - keeping several processes in memory so that while one waits for I/O another can use the CPU; the CPU is rarely idle.
- **Memory management** - allocating RAM to processes, sharing memory between them, and using virtual memory so a machine with limited RAM can still run large programs.
- **I/O management** - buffering and spooling input/output so slow devices do not hold up the CPU (for example, a printer spooler accepts print jobs and queues them).
- **File management** - organising data on backing storage so disk space is used efficiently and files are retrieved quickly.
- **Resource scheduling** - giving each process a fair share of processor time according to a scheduling policy.
- **Providing a platform** - presenting a consistent interface so that application programmers do not have to deal with hardware details.

### How the user interface hides the hardware

The **user interface (UI)** sits between the user and the hardware so that the user never has to deal with the raw machine. It hides complexity by:

- **Abstracting hardware** - the user manipulates files, folders and icons rather than disk blocks, tracks and sectors.
- **Hiding machine code** - the user gives commands in a GUI (clicks, windows, menus) or types shell commands instead of binary instructions.
- **Managing peripherals** - the user clicks "Print"; the OS handles device drivers, ports and buffers.
- **Providing utilities** - copy, delete, search and configuration tools mean the user never edits raw storage.
- **Error handling** - meaningful messages ("File not found") replace cryptic hardware codes.

The result is that the user can treat the computer as a tool without understanding registers, memory addresses or interrupt vectors.

## 2. Process management: multi-tasking, processes and states

A **process** is a program in execution - the program code plus its current activity (program counter, registers, stack, data and state). **Multi-tasking** is the OS technique that allows several processes to appear to run at the same time by rapidly switching the CPU between them.

Each process exists in one of three **process states** (CAIE uses three; some texts add "new" and "terminated" entry/exit states, but the syllabus focuses on three):

- **Running** - the process is currently being executed on the CPU. On a single-core machine, only one process can be in this state at any instant.
- **Ready** - the process is loaded and able to run, but is waiting for its turn because another process is using the CPU.
- **Blocked** (also called waiting) - the process cannot proceed until some event occurs, such as the completion of an I/O operation or the arrival of a signal.

The transitions between states are:

- **Running → Ready** - the process has used up its allotted time slice (a timer interrupt pre-empts it).
- **Ready → Running** - the scheduler dispatches the process (it is chosen to run next).
- **Running → Blocked** - the process requests I/O or waits on an event and suspends itself.
- **Blocked → Ready** - the awaited event completes (for example, I/O finishes) and the process becomes eligible to run again.

```text
        dispatch                 time slice expires
     Ready ─────────────► Running ───────────────► Ready
       ▲                       │
       │ event                 │ request I/O /
       │ complete              ▼ wait for event
       └──────────────────── Blocked
```

The **need for scheduling** follows directly from this: because many processes are ready but only one CPU core can run them, the OS must choose which ready process to dispatch next. The component that makes this choice is the **scheduler**, which uses a **scheduling algorithm** to maximise throughput, fairness and response time.

## 3. Scheduling routines

The syllabus expects you to know four scheduling routines, how each picks the next process, and their benefits and drawbacks.

| Routine | How the next process is chosen | Benefits | Drawbacks |
| --- | --- | --- | --- |
| **First Come First Served (FCFS)** | Processes run in the order they arrive (a FIFO queue). | Simple to implement; fair in a strict sense; no process can "jump the queue". | Long jobs make short jobs wait (the **convoy effect**); poor response time for interactive use; average waiting time can be high. |
| **Shortest Job First (SJF)** | The ready process with the **shortest expected burst time** runs next. | Gives the **minimum average waiting time**; efficient for batch workloads. | Needs to know burst times in advance (often impossible); long jobs can **starve**; non-pre-emptive, so a long job blocks everything once it starts. |
| **Round Robin (RR)** | Each ready process gets a fixed **time slice (quantum)** in turn; when the slice ends it goes to the back of the ready queue. | Fair - every process gets CPU time; good response time for interactive systems; no starvation. | If the quantum is too short, frequent context switches waste time; if too long it degenerates toward FCFS; average turnaround time can be worse than SJF. |
| **Shortest Remaining Time (SRT)** | Pre-emptive version of SJF: when a new process arrives, the one with the **shortest remaining time** runs, interrupting the current process if necessary. | Even better average waiting time than SJF; responsive to new short jobs. | Overhead of frequent context switches; still needs burst-time estimates; long jobs can starve; more complex to implement. |

### Worked example: trace SJF

Four processes arrive with these burst times (CPU time needed). Assume all arrive at time 0 and that SJF is non-pre-emptive.

| Process | Arrival time | Burst time |
| --- | --- | --- |
| P1 | 0 | 8 |
| P2 | 0 | 4 |
| P3 | 0 | 2 |
| P4 | 0 | 1 |

At time 0 all four are ready. SJF picks the **shortest burst first**:

```text
Order:   P4 (1)  ►  P3 (2)  ►  P2 (4)  ►  P1 (8)

Timeline:
time 0  1  2  3  4  5  6  7  8  9  10 11 12 13 14 15
     |P4|  P3   |     P2      |           P1            |
     1   2      3             4                         8
```

Waiting time (start − arrival):

- P4: 0 − 0 = 0
- P3: 1 − 0 = 1
- P2: 3 − 0 = 3
- P1: 7 − 0 = 7

Average waiting time = (0 + 1 + 3 + 7) / 4 = **2.75**.

Compare with FCFS in arrival order (P1, P2, P3, P4): waiting times would be 0, 8, 12, 14, average = **8.5**. SJF clearly minimises average waiting time here - that is the whole point of the algorithm.

## 4. The kernel and interrupt handling

The **kernel** is the core, always-resident part of the OS. It has privileged access to the hardware and provides the most fundamental services, including **interrupt handling** and low-level scheduling.

When an interrupt occurs (from a hardware timer, a peripheral, a software trap, or an I/O completion signal), the CPU does the following, under the control of the kernel:

1. **Suspend** the current process and save its state (registers, program counter, flags) onto its stack or process control block.
2. **Identify** the interrupt source using the interrupt vector, which points to the relevant **Interrupt Service Routine (ISR)**.
3. **Run** the ISR, which services the interrupt (for example, reads a keystroke, acknowledges a device, or moves a process from Blocked to Ready).
4. **Restore** the saved state of a process and resume execution.

This mechanism drives **low-level scheduling**:

- A **timer interrupt** fires at the end of a process's time slice. The kernel's timer ISR saves the running process's state, moves it from Running to Ready, and calls the scheduler to pick the next Ready process - this is exactly how Round Robin switching happens.
- An **I/O completion interrupt** lets the kernel move a Blocked process back to Ready once its data is available.
- A **hardware fault** or system call may force an immediate switch.

So the kernel acts as the interrupt handler that *triggers* scheduling decisions: interrupts are the events, and the scheduler is the policy that responds to them.

## 5. Virtual memory, paging and segmentation

### Concepts

- **Virtual memory** is a technique that lets a process use more memory than is physically available by storing parts of it on backing storage (disk) and bringing pieces into RAM only when needed. To the program it appears that a large, contiguous block of memory is available.
- **Paging** divides logical (virtual) memory and physical memory into **fixed-size blocks**. Virtual memory is split into **pages** and physical RAM into **frames** of the same size. The OS maps each page to a frame using a **page table**. A virtual address is split into a **page number** and an **offset**; the page number is looked up in the page table to find the frame number, and the offset locates the byte within the frame.
- **Segmentation** divides memory into **variable-size segments** that correspond to logical units of a program - for example, the code segment, data segment and stack segment. A logical address is a **segment number + offset**; the segment table stores each segment's base address and limit.

### Paging vs segmentation

| Aspect | Paging | Segmentation |
| --- | --- | --- |
| Block size | **Fixed** - every page and frame is the same size. | **Variable** - each segment is as large as the logical unit it holds. |
| How a logical address is formed | Page number + offset; page table maps page → frame. | Segment number + offset; segment table stores base + limit. |
| Visibility to programmer | Invisible - done by the OS/hardware, no logical meaning. | Visible - segments reflect program structure (code, data, stack). |
| Fragmentation | Suffers from **internal** fragmentation (last page of a process may be partly unused). | Suffers from **external** fragmentation (free gaps between segments may be too small to use). |
| Sharing/protection | Harder (a page has no logical meaning). | Easier (a whole segment like shared library code can be shared or protected). |

### Page replacement

When a process needs a page that is **not** currently in RAM, a **page fault** occurs. The OS must fetch the page from disk; if all frames are full, it must first **replace** an existing page. Common replacement policies:

- **FIFO (First In First Out)** - replace the page that was loaded earliest. Simple, but may evict a heavily used page.
- **LRU (Least Recently Used)** - replace the page that has not been used for the longest time. Closer to optimal but more expensive to track.
- (Optimal, mentioned for comparison, replaces the page that will not be used for the longest time in the future - impossible to implement but useful as a benchmark.)

### Disk thrashing

**Disk thrashing** occurs when the OS spends more time **paging** (moving pages between RAM and disk) than executing processes. It happens when too many processes compete for too little physical memory: each process continually faults, evicts a page another process needs, which then faults in turn, and so on. The disk light flickers constantly, the CPU is largely idle waiting for I/O, and throughput collapses. The usual fixes are to **run fewer processes** or to **install more RAM**.

## 6. Interpreters

An **interpreter** executes a high-level program **statement by statement** without first producing a separate translated (compiled) file. For each statement it:

1. **Reads** the statement.
2. **Analyses** it (checks syntax, identifies tokens and meaning).
3. **Executes** it directly, often translating into an internal form line by line.
4. **Reports an error immediately** and stops when a faulty statement is reached.

Because it never stores a complete translated version, the source code must be present every time the program runs. This makes interpreters slower in execution (each line is re-analysed each run) but excellent for **debugging and development** - errors are caught at once and code can be tested interactively. Many modern languages (Python, JavaScript) combine a compile-to-bytecode step with a virtual-machine interpreter.

## 7. Stages of compilation

A compiler translates a whole high-level program into machine code (or object code) **before** it runs. CAIE lists four stages:

| Stage | What it does | Example output |
| --- | --- | --- |
| **Lexical analysis** | Reads source code character by character, removes white space and comments, and groups characters into **tokens** (keywords, identifiers, operators, literals). Reports invalid symbols. | `total := price * 3 ;` becomes tokens: `IDENT(total) ASSIGN IDENT(price) MULTIPLY NUMBER(3) SEMICOLON` |
| **Syntax analysis** | Checks that the tokens form grammatically correct statements according to the language's grammar, and builds a **parse tree** (or syntax tree) showing structure. Reports syntax errors. | A tree with root `:=`, children `total` and `*`, where `*` has children `price` and `3`. |
| **Code generation** | Walks the parse tree and emits **target (object) code** - machine code or an intermediate form. Allocates registers and memory. | `LOAD price; LIT 3; MULT; STORE total` (then real machine code). |
| **Optimisation** | Rewrites the generated code to make it faster or smaller, while preserving behaviour. Includes removing redundant code, simplifying constants, reusing registers, and unrolling loops. | `x := 2 * 3;` folded to `x := 6;`; a redundant `LOAD` removed. |

A symbol table is maintained throughout, recording each identifier's name, type, scope and memory address.

## 8. Grammar: syntax diagrams and BNF

A language's **grammar** defines which strings of tokens are legal. Two notations are required:

- **Syntax diagrams (railroad diagrams)** - pictorial flowcharts using arrows, ovals for terminals (actual symbols) and rectangles for non-terminals (defined elsewhere). Easy to read but not compact.
- **Backus-Naur Form (BNF)** - a textual set of production rules. A non-terminal is defined using `::=` and alternatives are separated by `|`. Terminals are usually quoted.

Example: a simple unsigned integer is one or more digits.

```bnf
<digit>      ::= "0" | "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9"
<integer>    ::= <digit> | <integer> <digit>
```

A slightly richer grammar for a number with an optional sign:

```bnf
<sign>       ::= "+" | "-"
<digit>      ::= "0" | "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9"
<unsigned>   ::= <digit> | <unsigned> <digit>
<number>     ::= <unsigned> | <sign> <unsigned>
```

A grammar for a simple assignment `IDENT := expression ;`:

```bnf
<assignment> ::= <identifier> ":=" <expression> ";"
<expression> ::= <term> | <expression> "+" <term> | <expression> "-" <term>
<term>       ::= <factor> | <term> "*" <factor> | <term> "/" <factor>
<factor>     ::= <identifier> | "(" <expression> ")"
```

Here `expression` is **left-recursive**, which mirrors how the parser builds the tree and (handily) how operator precedence is encoded: `*` and `/` bind more tightly than `+` and `-` because they sit deeper in the rules.

## 9. Reverse Polish Notation (RPN)

**Reverse Polish Notation (RPN)**, or postfix notation, writes the **operator after** its operands. So `A + B` becomes `A B +`, and `(A + B) * C` becomes `A B + C *`. No brackets are ever needed because the order of operands and operators alone determines the meaning.

RPN suits **stack-based evaluation** perfectly:

- Scan the expression left to right.
- If you see an **operand**, **push** it onto the stack.
- If you see an **operator**, **pop** the required number of operands, apply the operator, and **push** the result back.

### Converting infix `(A + B) * C` to RPN

Using the **shunting-yard** method, the queue collects output and the stack holds operators:

| Read | Action | Stack (top right) | Output (RPN) |
| --- | --- | --- | --- |
| `(` | push `(` | `(` | |
| `A` | operand → output | `(` | `A` |
| `+` | push `+` | `( +` | `A` |
| `B` | operand → output | `( +` | `A B` |
| `)` | pop until `(`: pop `+` to output, discard `(` | (empty) | `A B +` |
| `*` | push `*` | `*` | `A B +` |
| `C` | operand → output | `*` | `A B + C` |
| end | pop remaining: pop `*` | (empty) | `A B + C *` |

Final RPN: **`A B + C *`**.

### Evaluating `A B + C *` on a stack

Let `A = 3`, `B = 5`, `C = 2`.

| Read | Action | Stack (top right) |
| --- | --- | --- |
| `A` | push 3 | `3` |
| `B` | push 5 | `3 5` |
| `+` | pop 5 and 3; 3 + 5 = 8; push 8 | `8` |
| `C` | push 2 | `8 2` |
| `*` | pop 2 and 8; 8 * 2 = 16; push 16 | `16` |

Result: **16**, which matches `(3 + 5) * 2`. The whole evaluation uses only pushes and pops - no brackets, no precedence rules at run time. This is why compilers convert expressions to RPN before generating stack-machine or one-pass machine code.

## Worked-Thinking Routine

1. **Read the command word.** "Describe" = explain features; "show understanding" = explain the *how* and *why*; "compare" = a balanced table.
2. **For scheduling questions**, write the timeline first, then compute each waiting time as *start − arrival*, then average.
3. **For memory questions**, state whether the question is about paging (fixed) or segmentation (variable) before writing addresses.
4. **For compilation**, name the stage, say what it does, and give an example of its output (token, parse tree, code).
5. **For BNF/RPN**, draw or write the steps explicitly - examiners award method marks even if the final answer is wrong.

## Common Mistakes

- Confusing a **process** (program in execution) with a **program** (code on disk).
- Listing process states as four or five when the syllabus focuses on **running / ready / blocked**.
- Saying SJF needs the **arrival** time - it actually needs the **burst (expected run) time**.
- Mixing up **internal** fragmentation (paging) with **external** fragmentation (segmentation).
- Forgetting that RPN evaluation pushes operands and only pops on an operator.
- Writing a BNF rule with terminals unquoted, or using `=` instead of `::=`.

## Quick Self-Check

1. State the three process states and give one cause of each transition.
2. Why does Round Robin need a carefully chosen time quantum?
3. Distinguish paging from segmentation in terms of block size.
4. Name the four stages of compilation and one output of each.
5. Convert `A * (B + C)` to RPN and evaluate it for `A=4, B=2, C=3`.
6. Explain why disk thrashing causes the CPU to be idle even though the system is busy.

## Connections

- [System Software](../05%20System%20Software/00%20Overview.md) - the AS foundation: roles of the OS and the difference between systems and applications software.
- [Processor Fundamentals](../04%20Processor%20Fundamentals/00%20Overview.md) - registers, the fetch-execute cycle and interrupts, which underpin process management and kernel handling here.

## Study Sequence

1. Read these notes once for overview.
2. Re-read sections 2-4 (processes and scheduling) and reproduce the state diagram from memory.
3. Practise one scheduling trace (FCFS, SJF and RR) from past-paper questions.
4. Memorise the paging vs segmentation table and write a one-line cause of each fragmentation type.
5. Drill the four compilation stages until you can name each and give an output example.
6. Practise two BNF and two RPN questions, showing full working.
7. Attempt timed past-paper questions on Paper 3 for this topic.
