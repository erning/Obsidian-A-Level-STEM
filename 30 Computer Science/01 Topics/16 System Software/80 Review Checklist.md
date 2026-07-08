---
title: System Software Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/16 System Software/00 Overview|System Software]]"
status: active
tags:
  - computerscience/computer-systems
  - review-checklist
---

# System Software Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can trace processes, memory, translation, grammar, and stack evaluation without prompting.

## Ideas to Recall

- [ ] Explain how an OS maximises resource use and hides hardware complexity through a user interface.
- [ ] Define process, multi-tasking, scheduler, scheduling routine, time slice, and context switch.
- [ ] Recall the three process states: running, ready, and blocked.
- [ ] Recall the rules, benefits, and drawbacks of FCFS, SJF, Round Robin, and SRT scheduling.
- [ ] Define kernel, interrupt, interrupt vector, ISR, process control block, and low-level scheduling.
- [ ] Define virtual memory, page, frame, page table, page fault, page replacement, segment, and disk thrashing.
- [ ] Distinguish paging from segmentation by block size, logical meaning, visibility, and fragmentation.
- [ ] Recall how interpreters execute statements without producing a separate translated version.
- [ ] Recall the four compilation stages: lexical analysis, syntax analysis, code generation, and optimisation.
- [ ] Define token, parse tree, symbol table, object code, syntax diagram, BNF, terminal, non-terminal, and RPN.

## Skills to Perform

- [ ] Draw the running, ready, and blocked state diagram and label each transition.
- [ ] Trace FCFS, non-preemptive SJF, Round Robin, and SRT on a small set of processes.
- [ ] Calculate waiting time and average waiting time from a scheduling trace.
- [ ] Explain how a timer interrupt causes the kernel to save state and dispatch another process.
- [ ] Compare paging and segmentation in a table.
- [ ] Trace a page-reference string with a given replacement policy such as LRU and count page faults.
- [ ] Explain how disk thrashing occurs and how reducing active processes or adding RAM helps.
- [ ] List the compilation stages in order and give an example output of each stage.
- [ ] Write BNF rules using `::=`, alternatives with `|`, quoted terminals, and non-terminals in angle brackets.
- [ ] Convert infix expressions to RPN and evaluate RPN with a stack.

## Things to Trace or Explain

- [ ] Trace why a process waiting for input is blocked, then moves to ready when the event occurs, then running when dispatched.
- [ ] Explain why multi-tasking is rapid switching on a single CPU rather than true simultaneous execution.
- [ ] Trace Round Robin by moving an unfinished process to the back of the ready queue after its time slice.
- [ ] Explain why SJF and SRT can reduce average waiting time but may starve long jobs.
- [ ] Trace what is saved in the process control block during an interrupt: registers, program counter, and flags.
- [ ] Explain how virtual memory uses RAM and backing store to give a process the illusion of a larger memory space.
- [ ] Trace an LRU page replacement by updating the most recently used order after hits and misses.
- [ ] Explain why paging causes internal fragmentation and segmentation causes external fragmentation.
- [ ] Trace source code through tokens, parse tree, generated code, and optimised code.
- [ ] Explain why BNF can express the grammar used by syntax analysis.
- [ ] Trace an RPN expression by pushing operands and popping operands only when an operator is read.
- [ ] Connect process switching to interrupts and registers in [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]].

## Common Errors to Avoid

- [ ] Confusing a program stored on disk with a process in execution.
- [ ] Moving a process directly from blocked to running instead of blocked to ready.
- [ ] Calculating waiting time from finish time alone without subtracting arrival time and burst time when needed.
- [ ] Treating Round Robin as FCFS by forgetting the time quantum.
- [ ] Saying SJF chooses the earliest arrival rather than the shortest burst among arrived processes.
- [ ] Forgetting that frequent context switches create overhead.
- [ ] Confusing paging with segmentation, especially fixed versus variable block sizes.
- [ ] Mixing internal fragmentation with external fragmentation.
- [ ] Describing disk thrashing as "the disk is busy" without explaining repeated page faults.
- [ ] Listing compilation stages out of order.
- [ ] Writing BNF with `=` instead of `::=` or leaving terminals unquoted.
- [ ] Reversing operand order when evaluating subtraction or division in RPN.

## Ready to Move On When

- [ ] I can explain how the OS keeps CPU, memory, storage, and I/O resources shared and busy.
- [ ] I can trace process state changes and explain the event that causes each transition.
- [ ] I can build scheduling traces and calculate average waiting time for FCFS, SJF, Round Robin, and SRT-style decisions.
- [ ] I can describe kernel interrupt handling from timer event to saved state, scheduler decision, and resumed process.
- [ ] I can compare paging and segmentation and explain page faults, replacement, fragmentation, and thrashing.
- [ ] I can describe how an interpreter runs code without producing a stored translated program.
- [ ] I can name each compilation stage, say what it consumes and produces, and link syntax analysis to grammar.
- [ ] I can write simple BNF rules and check whether a string matches them.
- [ ] I can convert and evaluate RPN expressions using a stack without adding hidden precedence rules.
- [ ] I can explain how this topic extends [[30 Computer Science/01 Topics/05 System Software/00 Overview|System Software]].
- [ ] I can connect scheduling and interrupts to [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]] and virtualisation to [[30 Computer Science/01 Topics/15 Hardware and Virtual Machines/00 Overview|Hardware and Virtual Machines]].
