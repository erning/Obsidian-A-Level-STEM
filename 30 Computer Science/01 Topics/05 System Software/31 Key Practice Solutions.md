---
title: System Software Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/05 System Software/00 Overview|System Software]]"
status: active
tags:
  - computerscience/computer-systems
  - solutions
---

# System Software Key Practice Solutions

This note gives worked solutions for [[30 Computer Science/01 Topics/05 System Software/30 Key Practice Problems|System Software Key Practice Problems]]. Each solution shows the full reasoning so you can find the step where your argument diverged, not just compare final answers.

## A. Operating systems

### Problem 1

Two reasons a computer requires an Operating System:

1. The OS hides the hardware behind a stable interface, so application programmers write to that interface instead of to the raw machine. Without it, every application would have to contain its own code for reading the keyboard, writing to disk, claiming memory, and driving the screen.
2. The OS shares the processor, memory, and devices fairly and safely between programs, and keeps them isolated so that a fault in one cannot crash the others. Without it, no two applications could safely share the same machine.

### Problem 2

| Management task | Resource it manages |
|---|---|
| Memory management | RAM (and backing store through virtual memory) |
| File management | Data on backing store, organised into named files and directories |
| Security management | Access and integrity: who may log in and what each user may do |
| Hardware management | Input/output and peripherals: keyboards, screens, printers, disks, networks |
| Process management | Running programs (processes) and their use of the CPU |

### Problem 3

(a) **Process management.** It schedules which process uses the processor and when, giving each a fair share of CPU time.
(b) **Memory management.** It allocates each program a separate region of RAM and prevents one program from overwriting another's memory.
(c) **Security management.** It controls log-in and access rights, so only authorised users may read protected files.
(d) **Hardware management.** It provides device drivers so applications can send and receive data from peripherals without knowing the device's details.

### Problem 4

When RAM is nearly full, memory management cannot give every program all the RAM it wants at once. It uses **virtual memory**: the least recently used pages of memory are moved out of RAM onto backing store, and brought back into RAM only when the program actually needs them. This frees RAM for the active tab while keeping the others present on backing store, so all the programs keep running, although heavy use of virtual memory makes the system slow because moving pages to and from disk takes time.

### Problem 5

A single processor can execute only one stream of instructions at a time. Without process management, whichever program started running would keep the CPU until it finished, and every other open program would be stuck waiting. Process management (scheduling) switches the CPU between the running programs rapidly, giving each a fair time slice, so that to the user they all appear to make progress together.

## B. Utility software and libraries

### Problem 6

- **Disk formatter:** prepares a new disk or partition for use by dividing it into tracks and sectors and creating a file system on it.
- **Virus checker:** scans files and memory for known viruses and malware, removes or quarantines what it finds, and watches in real time for threats.
- **Defragmentation software:** reorganises a magnetic disk so the parts of each file are stored in contiguous sectors, reducing read/write head movement.
- **Disk repair software:** checks the disk for errors, reports what is stored and where, and attempts to repair corrupted sectors or a corrupted file system.
- **File compression:** reduces the size of files and groups of files so they take less storage and transmit faster, then restores them exactly.
- **Backup software:** makes copies of files or the whole disk so data can be recovered after loss, corruption, or failure.

### Problem 7

(a) **Disk formatter.** A new disk has no file system, so files cannot yet be saved or located; formatting creates the tracks, sectors, and file system that make it usable. A virus checker is unsuitable because it scans for malware but cannot prepare a disk.
(b) **File compression.** It reduces the folder below 4 GB so it fits, and restores the photos exactly when opened. Defragmentation is unsuitable because it reorders existing files but does not reduce their total size.
(c) **Backup software.** If a backup copy was made before the failure, the files can be restored from it. Disk repair software might recover some data from a faulty disk but is not a substitute for a prior backup.
(d) **Virus checker.** It scans for and removes or quarantines the malicious program, using up-to-date definitions. File compression is unsuitable because it does not detect or remove malware.

### Problem 8

On a magnetic hard disk, files become fragmented (scattered) across the platters as they are saved and edited. Defragmentation reorganises each file's parts into contiguous sectors, so the read/write head moves less and access is faster. An SSD has no moving parts; its blocks are accessed directly whatever their location, so scattered storage imposes no delay. Defragmentation on an SSD therefore gives no speed benefit, and the extra writes wear the flash memory and shorten the drive's life.

### Problem 9

Two benefits of using a program library:

1. It saves time and effort, because common functions do not have to be rewritten; the developer reuses pre-written, pre-compiled code.
2. It is reliable and maintainable, because library code has usually been tested thoroughly by many users, and a library can be updated to fix a bug with every program that uses it benefiting.

### Problem 10

Three benefits of placing a shared routine in a DLL with dynamic linking:

1. **Smaller executables.** The library code is not copied into each program, so each executable file is smaller.
2. **Memory saved when several programs run together.** They share one loaded copy of the DLL in RAM, rather than each holding its own copy.
3. **Updatable without recompiling.** A newer DLL placed on the system is picked up automatically by every program that uses it, with no recompilation or redistribution.

One drawback: the program now depends on the DLL file being present on the target machine. If the DLL is missing or is the wrong version, the program will not run.

## C. Language translators

### Problem 11

| Feature | Assembler | Compiler | Interpreter |
|---|---|---|---|
| Source language | Assembly language | High-level language | High-level language |
| Output | Machine code | A complete executable file | None; it runs the program directly |
| Execution speed | Fast (translated once) | Fast (translated once, then optimised) | Slow (each statement is re-translated every time it runs) |

### Problem 12

Use a **compiler**.

1. The compiler produces a single executable that the company can distribute while keeping the source code private. With an interpreter the source code would have to be shipped, exposing the company's work.
2. An accounting application does heavy calculation, and a compiled executable runs fast because it is translated once into optimised machine code. An interpreter is too slow for finished software of this kind.
3. The compiled executable runs on its own, so each customer need not install an interpreter.

### Problem 13

Use an **interpreter**.

1. It translates and executes one statement at a time and stops at the first error, so the teacher can find and fix bugs immediately as each line is added.
2. There is no need to compile the whole program before testing a small change, which suits the rapid edit-and-test cycle of classroom development. The slower execution speed does not matter while learning.

### Problem 14

The driver's source is written in assembly language, and only an assembler translates assembly language (one mnemonic per machine instruction) into machine code. A compiler and an interpreter both act on high-level languages, not assembly language, so neither can process this source at all. The assembler also produces the tight, direct machine code that gives the register-level control, small size, and speed a device driver requires.

### Problem 15

1. **Partial compile.** The Java compiler translates the source (`.java`) into an intermediate form called **bytecode** (`.class`), which is not the machine code of any particular processor and is therefore platform-independent.
2. **Partial interpret.** On the target machine, the **Java Virtual Machine (JVM)** reads the bytecode and interprets it, executing it one instruction at a time on that machine's processor.

The main advantage is portability: the same bytecode runs on any machine that has a JVM, so the program is written once and run anywhere. The cost is that interpretation is slower than running native machine code.

## D. IDE features

### Problem 16

| Feature | Development stage |
|---|---|
| Context-sensitive prompts | Coding |
| Dynamic syntax checks | Initial error detection |
| Prettyprint | Presentation |
| Expand and collapse code blocks | Presentation |
| Single stepping | Debugging |
| Breakpoints | Debugging |
| Watch variables | Debugging |

### Problem 17

All three are debugging features, used together. The programmer first sets a **breakpoint** on the first line inside the loop, so the program pauses there as soon as the loop begins instead of running away. From that point she uses **single stepping** to run one statement at a time through the loop body, watching exactly what happens on each iteration. She adds the loop counter and the exit condition as **watch variables**, displayed in a report window, so she can see their values change each iteration and spot the moment the exit condition never becomes true. The combination localises the fault to a specific statement and a specific value.

### Problem 18

- **During coding:** dynamic syntax checks. As the programmer types, the editor flags statements that break the language's grammar, catching errors before the program is ever compiled or run.
- **During debugging:** single stepping. It runs the program one statement at a time so the programmer can see exactly where execution goes wrong, which a whole-program run would hide.
