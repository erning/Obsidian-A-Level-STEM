---
title: System Software Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/05 System Software/00 Overview|System Software]]"
status: active
tags:
  - computerscience/computer-systems
  - worked-examples
---

# System Software Worked Examples

These worked examples show how to reason through scenario questions on operating systems, utility software, libraries and DLLs, language translators, and IDE features. The aim is method selection: name the right category first, then justify it from the details of the scenario. Cover each solution, attempt the prompt on paper, then compare.

## Source Route

- Syllabus **9618 AS Section 5 - System Software**.
- 5.1 Operating Systems: need, five management tasks, utility software, program libraries, DLLs.
- 5.2 Language Translators: assembler, compiler, interpreter; partial compile and partial interpret; IDE features.
- Assessed in **Paper 1**.

The recurring skill is method selection. For each scenario, name the category first (which OS task, which utility, which translator, which IDE feature), then justify it against the alternatives. Definitions alone are not enough; the marks are in the justification tied to the scenario.

## Example 1: Match an OS management task to a scenario

**Prompt.** State which of the five OS management tasks handles each of the following, and justify in one line.
(a) Two open programs must not overwrite each other's data in RAM.
(b) The OS decides which of three open programs gets the CPU next.
(c) A user must enter a password before reading a protected file.

**Solution.**
(a) **Memory management.** It allocates each program its own region of RAM and keeps the regions separate, so one program cannot overwrite another's memory.
(b) **Process management.** It schedules which process (running program) uses the processor and when, so several programs each get a fair share of CPU time and appear to run together.
(c) **Security management.** It controls who may log in and what each user may read, write, or run, using passwords and access rights to guard against unauthorised access.

**Check.** Match by the resource named in the prompt: RAM is memory, the CPU and running programs are processes, passwords and access rights are security.

## Example 2: Choose utility software for a need

**Prompt.** A photographer must (a) send a 5 GB folder of photos through an email service that rejects large attachments, and (b) protect the only copies against a disk failure. For each task, name a suitable utility and justify it against an unsuitable alternative.

**Solution.**
(a) **File compression.** It reduces the size of the files (and of a group of files) so they take less storage and transmit faster, then restores them exactly when opened. A virus checker would be unsuitable here because it scans for malware but does not shrink files; defragmentation is also unsuitable because it only reorders existing files and does not reduce their total size.
(b) **Backup software.** It makes copies of files (or the whole disk) so data can be recovered after loss, corruption, or failure. Defragmentation software would be unsuitable because it only reorders existing files for faster access and provides no copy to restore from; if the disk fails, defragmentation cannot bring the data back.

**Check.** Match the verb: "make smaller" is compression, "make a recoverable copy" is backup, "scan for malware" is virus checker, "prepare a new disk" is formatter, "repair corrupted sectors" is disk repair.

## Example 3: Explain a DLL benefit to a developer

**Prompt.** A developer writes three Windows applications that all need the same dialog-box routine. Give three distinct benefits of placing the routine in a DLL and linking dynamically, instead of copying the code into each executable (static linking).

**Solution.** Each benefit follows from the fact that a DLL is a separate file linked only when each program runs.
1. **Smaller executables.** The library code is not copied into each program, so each executable file is smaller.
2. **Memory saved when several programs run together.** When all three applications run at once, they share one loaded copy of the DLL in RAM, rather than each holding its own copy.
3. **Updatable without recompiling.** A newer DLL can be placed on the system and every application that uses it automatically gets the fix, without recompiling or redistributing each program.

**Check.** Each point must trace back to dynamic linking: the code lives in a separate file that is shared at run time. If a benefit does not depend on that, it is a general library benefit, not a DLL-specific one.

## Example 4: Justify compiler versus interpreter

**Prompt.** A company has finished developing a word processor and will sell it to thousands of users. Justify whether the company should use a compiler or an interpreter, giving three reasons tied to the scenario.

**Solution.** Use a **compiler**.
1. **Distribution and privacy.** The compiler produces a single executable file that the company can distribute, while the source code stays private. With an interpreter the source code itself would have to be distributed, exposing the company's work.
2. **Execution speed.** A word processor must respond instantly to typing; a compiled executable runs fast because it is translated once into optimised machine code. An interpreter re-translates each statement every time it runs, which is too slow for a finished product.
3. **No interpreter needed on the user's machine.** The compiled executable runs on its own; the user need not install an interpreter.

**Check.** Decide by speed, distribution and privacy, and debugging need. A finished commercial product for many users points to a compiler; an unfinished program being tested line by line points to an interpreter.

## Example 5: The Java partial-compile and partial-interpret pipeline

**Prompt.** A student compiles a Java program on a Windows PC and later runs the resulting file on a Mac, without recompiling. Explain the two steps that make Java partially compiled and partially interpreted, naming the intermediate form and the component that performs the second step.

**Solution.**
1. **Partial compile.** The Java compiler translates the source code (`.java`) into an intermediate form called **bytecode** (`.class`). Bytecode is not the machine code of any particular processor, so it is platform-independent.
2. **Partial interpret.** On the Mac, the **Java Virtual Machine (JVM)** reads the bytecode and **interprets** it, executing it one instruction at a time on the Mac's processor.

The same bytecode runs on both machines because the JVM, not the bytecode, is the platform-specific part. The advantage is portability; the cost is that interpretation is slower than running native machine code.

**Check.** Both steps must appear: source to bytecode (compiled), bytecode to native execution inside the JVM (interpreted). Saying Java is "only compiled" or "only interpreted" misses one half.

## Example 6: Map an IDE feature to the problem it solves

**Prompt.** A programmer's loop produces a wrong running total. For each IDE feature, name the development stage it serves and state the specific problem it helps with here.
(a) Single stepping.
(b) Watch variables.
(c) Breakpoints.

**Solution.** All three belong to the **debugging** stage.
(a) **Single stepping** runs the program one statement at a time, so the programmer can see exactly which iteration of the loop first produces the wrong total. It isolates the fault to a single statement.
(b) **Watch variables** display the value of the running total (and of the loop counter and the exit condition) in a report window as the program runs, so the programmer can see precisely when the value goes wrong without adding print statements.
(c) **Breakpoints** pause execution at a chosen line (for example, just inside the loop), so the programmer can stop there and inspect the state before the error spreads further, instead of running the whole loop repeatedly.

Used together: set a breakpoint at the start of the loop to pause there, single-step through the body, and watch the running total until it goes wrong.

**Check.** Name the stage (debugging) first, then the feature. If a feature helped while typing rather than while running, it would be a coding or error-detection feature instead: context-sensitive prompts help coding, dynamic syntax checks help error detection, prettyprint helps presentation.

## Example 7: Defragmentation on HDD versus SSD

**Prompt.** A technician runs defragmentation on a magnetic hard disk (HDD) and on a solid state drive (SSD). Explain why it speeds up access on the HDD but gives no benefit on the SSD, and why it is actually harmful on the SSD.

**Solution.**
- **On the HDD**, files become scattered (fragmented) across the platters as they are saved and edited. The read/write head must physically move to each location, so a scattered file means many slow head movements. Defragmentation reorganises the parts of each file into contiguous sectors, so the head moves less and access is faster.
- **On the SSD**, there are no moving parts; blocks are accessed directly whatever their location, so scattered storage imposes no delay. Defragmentation therefore gives no speed benefit. Worse, the extra writes wear the flash memory, because SSD cells can be written only a limited number of times, so running defragmentation shortens the drive's life.

**Check.** Defragmentation is only meaningful on a magnetic disk with a moving read/write head. On an SSD it is pointless and harmful. If a question mentions wear life on flash, the cause is repeated writes, which defragmentation adds.

## Example 8: Justify an assembler for a hardware driver

**Prompt.** A device-driver writer needs code that controls a peripheral at the level of individual registers, and that runs as fast as possible in the smallest possible size. The source is written in assembly language. State which translator is required and justify why neither a compiler nor an interpreter is suitable.

**Solution.** Use an **assembler**. An assembler translates an assembly language program (one mnemonic per machine instruction) into machine code.

Neither a compiler nor an interpreter is suitable because both translate **high-level languages**, not assembly language, so they cannot process this source at all. In addition, the assembler produces tight machine code that gives the direct register-level control, the small size, and the speed the driver requires; a high-level translator would add an abstraction layer between the code and the hardware that the driver does not want. Assembly language is the natural choice whenever direct control of specific hardware is needed, and the assembler is the matching translator.

**Check.** The source language decides the translator. Assembly source requires an assembler; high-level source is the choice between compiler and interpreter, decided by speed, distribution and privacy, and debugging need.

## Study Routine

1. Identify the category first: OS management task, utility, library or DLL, translator, or IDE feature. The answer must match.
2. For OS questions, name the management task by the resource it manages before describing what it does.
3. For DLL benefits, start from dynamic linking and follow the consequences.
4. For compiler versus interpreter, decide on speed, distribution and privacy, and debugging, then justify from the scenario.
5. For Java, always give both steps: source to bytecode (compiled), bytecode to native execution in the JVM (interpreted).
6. For IDE features, name the development stage (coding, error detection, presentation, debugging) first, then the feature.
