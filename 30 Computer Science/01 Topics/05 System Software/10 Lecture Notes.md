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

Hardware on its own is inert: it can switch and store, but it has no idea how to
share itself between programs, keep files in order, or turn text a human wrote
into instructions it can run. System software is the layer that fills that gap.
It has two big parts: the operating system, which manages the machine on behalf
of every program running on it, and language translators, which convert source
code into a form the processor can execute. This note covers what each does and
why the distinction between the translator types matters in real development.

## Source Route

This note follows CAIE Computer Science 9618, AS section 5:

- 5.1 Operating Systems
- 5.2 Language Translators

Section 5 is examined in Paper 1.

## 1. Why a computer needs an Operating System

An Operating System (OS) is a system program that manages the hardware and
provides an environment in which applications can run. Without it, every
application would have to contain its own code for reading the keyboard, writing
to disk, claiming memory, and driving the screen, and no two applications could
safely share the same machine. The OS hides the hardware behind a stable
interface so that application programmers can write to that interface rather than
to the raw machine, and it shares the processor, memory, and devices fairly and
safely between whatever programs are running.

### The five management tasks

The OS carries out five management tasks. Keep them separate: each manages a
different resource.

| Task | What the OS manages | What it does |
|---|---|---|
| Memory management | RAM and (through virtual memory) backing store | Allocates RAM to programs so they have space to load and run; reclaims it when they finish; prevents one program from overwriting another's memory |
| File management | Data on backing store | Lets data be saved in named files, organised in directories; maintains filenames, attributes, and the file allocation table so files can be found, opened, and protected |
| Security management | Access and integrity | Controls who can log in and what each user may read, write, or run; provides passwords and access rights; guards against unauthorised access and data loss |
| Hardware management (input/output/peripherals) | Keyboards, screens, printers, disks, networks | Provides device drivers so the OS and applications can send and receive data from peripherals without each program knowing the device's details |
| Process management | Running programs (processes) | Decides which process uses the processor and when (scheduling), so that several programs appear to run at the same time and each gets a fair share of CPU time |

The common thread is resource sharing and protection. The OS is the single
authority that decides who gets memory, who gets the processor, who may touch
which file and which device, and it keeps programs isolated so that a fault in
one cannot crash the others.

## 2. Utility software

Utility software is software that performs a specific, often housekeeping, task,
usually related to the management and maintenance of the computer system. Most
utilities are provided alongside the OS rather than being part of the kernel, and
each does one job.

| Utility | What it does |
|---|---|
| Disk formatter | Prepares a new disk (or partition) for use by dividing it into tracks and sectors and creating a file system on it, so that files can be stored and located |
| Virus checker | Scans files and memory for known viruses and malware, removes or quarantines what it finds, and watches in real time for threats; must be kept up to date with the latest definitions |
| Defragmentation software | Reorganises a magnetic disk so that the parts of each file are stored in contiguous sectors, reducing the movement of the read/write head and speeding up access |
| Disk contents analysis / disk repair software | Checks the disk for errors, reports what is stored and where, and attempts to repair corrupted sectors or a corrupted file system |
| File compression | Reduces the size of files (and groups of files) so they take less storage space and transmit faster, then restores them to their original form when needed |
| Back-up software | Makes copies of files (or the whole disk) so that data can be recovered after loss, corruption, or failure; may run full or incremental backups |

Two traps to avoid. First, utilities are not part of the OS kernel - they are
separate programs that come with or alongside it. Second, defragmentation is only
meaningful on a magnetic hard disk, where files become scattered across the
platters; on an SSD the blocks do not move, so defragmentation gives no benefit
and adds wear.

## 3. Program libraries and DLLs

A program library is a collection of pre-written, pre-compiled code that
performs common tasks (mathematical functions, input/output routines, window
controls) and that a developer can reuse instead of writing that code from
scratch. Software under development is very often constructed by combining the
developer's own code with existing code from one or more program libraries.

The benefits to the developer are the benefits of reuse:

- Saves time and effort: common functions do not have to be rewritten.
- Saves memory and file size, because the library code is written and tested
  once and can be shared by many programs.
- Reliable: library code has usually been tested thoroughly by many users.
- Maintainable: a library can be updated (for example to fix a bug) and every
  program using it benefits.
- Allows a developer to use code written by someone else without having to
  understand or reproduce every detail of it.

A Dynamic Link Library (DLL) is a particular kind of library used in Windows
systems. Its key feature is in the name - **dynamic** and **link**. Instead of
the library code being copied into each executable file at compile time (**static
linking**), the program is linked to the DLL only when it runs (**dynamic
linking**). The DLL is a separate file that sits on the system, and many programs
can share the single copy at run time.

The benefits of DLLs follow directly from this:

- The executable file is smaller, because the library code is not copied into
  every program.
- Memory is saved when several programs run at once, because they all share one
  loaded copy of the DLL in RAM.
- The DLL can be updated (a newer version placed on the system) and every program
  that uses it automatically gets the new version, without recompiling each
  program.
- Different programs written in different languages can use the same DLL.

The trade-off is that the program now depends on the DLL file being present on
the target machine. If the DLL is missing or is the wrong version, the program
will not run.

## 4. Language translators: assembler, compiler, interpreter

Source code is written in a high-level or assembly language; the processor
executes only machine code. A language translator converts the one into the
other. There are three kinds, and the choice depends on the source language and
on what the program is for.

- An **assembler** translates an **assembly language** program (one mnemonic per
  machine instruction) into machine code.
- A **compiler** translates a **high-level language** program into machine code
  all at once, producing an executable file that can be run later.
- An **interpreter** translates and executes a **high-level language** program
  one statement at a time, without producing a separate executable.

### Comparison

| Feature | Assembler | Compiler | Interpreter |
|---|---|---|---|
| Source language | Assembly language | High-level language | High-level language |
| Output | Machine code | A complete executable file | None - it runs the program directly |
| Translation unit | Whole program | Whole program | One statement / line at a time |
| Execution speed | Fast (translated once) | Fast (translated once; optimised) | Slow (each line re-translated each time it runs) |
| Distribution | Distribute the assembled program | Distribute the executable; source stays private | Must distribute the source and the interpreter |
| Error detection | Errors found when assembled | All errors reported after compiling the whole program | Errors found one at a time, at run time; program stops at the first error |
| Debugging | Harder | Harder (errors found at the end) | Easier (stops at first error, good while developing) |

### Justifying compiler versus interpreter for a given scenario

Do not memorise a fixed answer; pick by what the scenario needs.

- **Use a compiler when** the program is to be distributed to users, when
  execution speed matters, and when the source code must stay private. The
  compiler produces a single executable that runs fast and reveals nothing about
  the source.
- **Use an interpreter when** the program is still being developed, when each
  statement is to be tested immediately, or when an interactive environment is
  wanted. The interpreter stops at the first error, which makes finding and
  fixing bugs quicker during development.
- **Use an assembler when** the program is written in assembly language, which is
  used when direct control of specific hardware is needed or when the smallest,
  fastest code is required.

A typical exam question gives a situation - "a teacher developing a program in
class", "a company selling a word processor" - and asks which translator to use.
Match the situation to speed, privacy, and debugging needs, then justify.

## 5. Partial compilation and partial interpretation (Java)

Some languages are neither purely compiled nor purely interpreted. Java (in
console mode) is the syllabus example: its source is partially compiled and then
partially interpreted.

The pipeline is:

1. The Java **source code** (`.java`) is **compiled** by the Java compiler, but
   not into the machine code of any particular processor. It is compiled into an
   intermediate form called **bytecode** (`.class`).
2. The **bytecode** is platform-independent: the same bytecode can be sent to any
   machine.
3. On the target machine, the **Java Virtual Machine (JVM)** reads the bytecode
   and **interprets** it, executing it one instruction at a time on that
   machine's processor.

So the two halves are: a compile step (source to bytecode) that produces a
portable intermediate, and an interpret step (bytecode to native execution) that
runs inside the JVM. The advantage is portability - write once, run anywhere
there is a JVM. The cost is that interpretation is slower than running native
machine code.

This is why Java is described as **partially compiled and partially
interpreted**, not as "only compiled" or "only interpreted". The first step is a
compile, but the output is bytecode rather than machine code; the second step is
interpretation by the JVM.

## 6. Integrated Development Environment (IDE) features

An Integrated Development Environment (IDE) is a single application that brings
together the tools a programmer needs to write, check, present, and debug code:
an editor, a compiler or interpreter, and debugging tools in one package. The
syllabus features group by the stage of development they help with.

| Feature | Development stage | What it does |
|---|---|---|
| Context-sensitive prompts | Coding | The editor offers completions or suggestions that depend on what the programmer has just typed (for example, listing the methods of an object) |
| Dynamic syntax checks | Initial error detection | The editor flags syntax errors as the programmer types, before compiling, by checking against the language's grammar |
| Prettyprint | Presentation | Automatically formats the code with consistent indentation and spacing so it is readable |
| Expand and collapse code blocks | Presentation | Lets the programmer hide the body of a function or block, showing only its header, to keep large files navigable |
| Single stepping | Debugging | Runs the program one statement at a time so the programmer can watch what happens after each line |
| Breakpoints | Debugging | Marks a line where the program will pause, so the programmer can stop at a point of interest and inspect the state |
| Watch variables and expressions (report window) | Debugging | Lets the programmer track the values of chosen variables and expressions as the program runs, in a report window |

The pattern to remember is the four stages: **coding, error detection,
presentation, debugging**. Map each feature to the stage it serves, and you can
answer any IDE question by naming the stage first and the feature second.

## Worked-Thinking Routine

Use this routine for any system software question.

1. Identify whether the question is about the OS, a utility, a library/DLL, a
   translator, or the IDE. They are different things and the answer must match.
2. For OS questions, name the management task (memory, file, security, hardware,
   process) before describing what it does. Do not list utilities here.
3. For a DLL benefit, start from "dynamic linking" and follow the consequences:
   smaller executable, shared in RAM, updatable, usable across languages.
4. For compiler versus interpreter, decide on speed, distribution/privacy, and
   debugging, then justify the choice from the scenario.
5. For Java, always give both steps: source to bytecode (compiled), bytecode to
   native execution in the JVM (interpreted).
6. For IDE features, name the development stage (coding / error detection /
   presentation / debugging) first, then the feature.

## Common Mistakes

- Listing utility software (defragmenter, virus checker) as if it were part of
  the OS kernel. Utilities are separate programs that come with the OS.
- Saying defragmentation is needed on an SSD. Files are not scattered on an SSD,
  so it gives no benefit and adds wear.
- Confusing static and dynamic linking. Static linking copies library code into
  the executable; dynamic linking (DLL) links at run time to a shared file.
- Claiming Java is "only compiled" or "only interpreted". It is partially
  compiled to bytecode, then partially interpreted by the JVM.
- Mixing up compiler and interpreter output. A compiler produces an executable
  file; an interpreter produces nothing and runs the program directly.
- Forgetting that an interpreter re-translates each statement every time it runs,
  which is why it is slower.
- Listing IDE features without tying each to a development stage.
- Answering "why a DLL" with only "saves memory". Give the consequences of
  dynamic linking: smaller executable, shared in RAM, updatable, cross-language.

## Quick Self-Check

You are ready to move on when you can answer these without notes.

1. Why does a computer system require an Operating System? Give two reasons.
2. Name the five management tasks carried out by the OS and what each manages.
3. State what each of these utilities does: disk formatter, virus checker,
   defragmentation, back-up software.
4. Why is defragmentation not useful on an SSD?
5. What is a program library, and give two benefits to a developer of using one.
6. What is dynamic linking, and how does a DLL save memory when several programs
   run at once?
7. State one benefit and one drawback of distributing a program that uses DLLs.
8. Compare compiler and interpreter on output, speed, and error detection.
9. Justify a compiler for a company selling a word processor.
10. Describe the two steps that make Java partially compiled and partially
    interpreted.
11. Name an IDE feature for each of the four development stages: coding, error
    detection, presentation, debugging.

## Connections

- [System Software](../16%20System%20Software/00%20Overview.md)
  extends this at A Level with process scheduling, virtual memory, and the stages
  of compilation (lexical, syntax, semantic, optimisation, code generation).
- [Programming](../11%20Programming/00%20Overview.md)
  produces the source code that the translators in this note convert into a
  runnable program, and uses the IDE features described here.

## Study Sequence

1. Read section 1 and fix the five OS management tasks by the resource each one
   manages.
2. Learn the utility software table in section 2, and note why defragmentation is
   for magnetic disks only.
3. Make the dynamic-versus-static linking contrast in section 3 concrete by
   tracing what happens to a DLL file when two programs use it.
4. Memorise the assembler/compiler/interpreter table, then practise justifying
   the translator choice for a given scenario.
5. Be able to state the Java bytecode pipeline in two steps without notes.
6. Map each IDE feature to one of the four development stages.
7. Self-check against the questions above before connecting to the A Level System
   Software topic.
