---
title: System Software Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/05 System Software/00 Overview|System Software]]"
status: active
tags:
  - computerscience/computer-systems
  - review-checklist
---

# System Software Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can identify the software category, choose the right tool, and justify the choice from the scenario.

## Ideas to Recall

- [ ] Define operating system, utility software, program library, Dynamic Link Library (DLL), assembler, compiler, interpreter, and IDE.
- [ ] Recall why a computer needs an operating system rather than letting every application drive the hardware directly.
- [ ] Recall the five OS management tasks: memory, file, security, hardware, and process management.
- [ ] Distinguish utilities from the OS kernel.
- [ ] Recall the roles of disk formatter, virus checker, defragmentation software, disk analysis/repair software, file compression, and backup software.
- [ ] Distinguish a general program library from a DLL.
- [ ] Explain dynamic linking and contrast it with static linking.
- [ ] Distinguish assembler, compiler, and interpreter by source language, output, translation unit, speed, distribution, and error detection.
- [ ] Recall the Java pipeline: source code to bytecode, then bytecode interpreted by the JVM.
- [ ] Match IDE features to coding, error detection, presentation, and debugging stages.

## Skills to Perform

- [ ] Identify which OS management task applies to a scenario and state the resource being managed.
- [ ] Choose a utility for a maintenance task and justify why other utilities would not solve that task.
- [ ] Explain why defragmentation helps a magnetic hard disk but not an SSD.
- [ ] Give developer benefits of using a program library rather than writing all code from scratch.
- [ ] Explain DLL benefits from dynamic linking: smaller executables, shared RAM copy, easier updates, and cross-language use.
- [ ] State a drawback of depending on a DLL and link it to a missing or incompatible file.
- [ ] Choose a compiler or interpreter for a scenario using speed, privacy, distribution, and debugging needs.
- [ ] Identify when an assembler is required from the source language.
- [ ] Describe Java as partially compiled and partially interpreted, naming bytecode and the JVM.
- [ ] Choose IDE features to debug a loop or support code writing, checking, formatting, and inspection.

## Things to Trace or Explain

- [ ] Trace how the OS shares CPU time, memory, files, and devices safely between programs.
- [ ] Explain how memory management prevents one program from overwriting another's memory.
- [ ] Trace why a file saved on backing store needs file management metadata before it can be found again.
- [ ] Explain how a device driver lets applications use a peripheral without knowing its hardware details.
- [ ] Trace what happens when two running programs use the same DLL file.
- [ ] Explain why an interpreter stops at the first error while a compiler reports errors after translating the program.
- [ ] Trace the Java route from `.java` source to `.class` bytecode to execution on a target machine.
- [ ] Explain how single stepping, breakpoints, and watch variables work together during debugging.
- [ ] Connect OS hardware management to [[30 Computer Science/01 Topics/03 Hardware/00 Overview|Hardware]].
- [ ] Connect translators to [[30 Computer Science/01 Topics/11 Programming/00 Overview|Programming]] and CPU execution in [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]].

## Common Errors to Avoid

- [ ] Listing utilities such as virus checkers and defragmenters as if they were OS kernel tasks.
- [ ] Treating backup software as the same thing as disk repair software.
- [ ] Saying defragmentation improves SSD performance.
- [ ] Giving only general library benefits when the question asks specifically about DLLs.
- [ ] Forgetting that dynamic linking creates a run-time dependency on the DLL being present.
- [ ] Claiming a compiler runs each line directly or that an interpreter produces a stand-alone executable.
- [ ] Choosing a compiler for debugging just because compiled programs run faster.
- [ ] Saying Java is only compiled or only interpreted.
- [ ] Confusing an assembler with a compiler for high-level languages.
- [ ] Naming an IDE feature without tying it to the development stage or problem it solves.

## Ready to Move On When

- [ ] I can explain why the OS is needed as a resource manager and hardware abstraction layer.
- [ ] I can name the five OS management tasks and classify examples under the correct task.
- [ ] I can choose and justify utility software for maintenance, security, compression, recovery, or disk preparation.
- [ ] I can explain libraries and DLLs as code reuse, and distinguish general library benefits from dynamic-linking benefits.
- [ ] I can compare assembler, compiler, and interpreter from source language through output and run-time behaviour.
- [ ] I can justify compiler versus interpreter choices from a scenario rather than from a memorised list.
- [ ] I can describe the Java bytecode and JVM route without losing either step.
- [ ] I can map IDE features to coding, error detection, presentation, and debugging.
- [ ] I can explain how this topic prepares for [[30 Computer Science/01 Topics/16 System Software/00 Overview|System Software]].
- [ ] I can connect translators and IDEs to source code in [[30 Computer Science/01 Topics/11 Programming/00 Overview|Programming]].
