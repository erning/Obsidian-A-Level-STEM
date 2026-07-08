---
title: System Software Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/05 System Software/00 Overview|System Software]]"
status: active
tags:
  - computerscience/computer-systems
  - practice
---

# System Software Key Practice Problems

These problems cover the core skills of 9618 AS Section 5. Attempt them on paper before reading [[30 Computer Science/01 Topics/05 System Software/31 Key Practice Solutions|the solutions]]. Most prompts are scenario-based, so aim to justify your answer against the alternatives rather than just naming a term. No answers are given here on purpose: the point is active recall and full written reasoning.

## A. Operating systems

1. Give two distinct reasons why a computer requires an Operating System rather than letting each application drive the hardware directly.

2. Name the five management tasks carried out by the OS, and state the resource each one manages.

3. State which OS management task handles each of the following, and justify each in one line.
   (a) Deciding which of several open programs gets the CPU next.
   (b) Keeping each program's data in RAM separate from every other program's.
   (c) Requiring a password before a user may read a file.
   (d) Providing a driver so that a program can send data to a printer.

4. A user opens many browser tabs until RAM is nearly full. Explain how the OS's memory management, together with virtual memory, keeps the programs running.

5. Explain why, without process management, two programs running at the same time could not both appear to make progress.

## B. Utility software and libraries

6. State what each of these utilities does: disk formatter, virus checker, defragmentation software, disk repair software, file compression, backup software.

7. For each situation, name a suitable utility and justify it against an unsuitable alternative.
   (a) Preparing a brand-new USB drive so that files can be saved on it.
   (b) Reducing a 5 GB folder of photos so it fits on a 4 GB flash drive.
   (c) Recovering a user's files after the hard disk fails.
   (d) Removing a known malicious program that has appeared on the disk.

8. Explain why defragmentation improves performance on a magnetic hard disk but is pointless and harmful on an SSD.

9. Give two benefits to a developer of using a program library rather than writing all of the code from scratch.

10. Give three distinct benefits to a developer of placing a shared routine in a DLL and linking dynamically, instead of copying the code into each executable (static linking). State one drawback of distributing a program that depends on DLLs.

## C. Language translators

11. Compare assembler, compiler, and interpreter under the headings source language, output produced, and execution speed of the finished program.

12. A company has finished developing an accounting application and will sell it to many users. Justify whether to use a compiler or an interpreter, giving three reasons tied to the scenario.

13. A teacher is still developing a program in class and wants to test each line as soon as it is written. Justify whether to use a compiler or an interpreter, giving two reasons.

14. Explain why a device driver written in assembly language must be translated with an assembler, and why neither a compiler nor an interpreter is suitable.

15. Describe the two steps that make Java partially compiled and partially interpreted. Name the intermediate form and the component that performs the second step, and state the main advantage of this approach.

## D. IDE features

16. For each IDE feature, name the development stage it serves: context-sensitive prompts, dynamic syntax checks, prettyprint, expand and collapse code blocks, single stepping, breakpoints, watch variables.

17. A programmer's loop runs forever and never exits. Explain how single stepping, a breakpoint, and a watch variable could be used together to locate the fault.

18. Give one IDE feature that helps during coding (before the program is run) and one that helps during debugging, and state the specific problem each one solves.

---

After finishing, check your working against [[30 Computer Science/01 Topics/05 System Software/31 Key Practice Solutions|the solutions]] and re-attempt any question you could not complete in full.
