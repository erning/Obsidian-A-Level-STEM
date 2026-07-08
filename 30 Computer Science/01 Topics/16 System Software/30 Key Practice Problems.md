---
title: System Software Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/16 System Software/00 Overview|System Software]]"
status: active
tags:
  - computerscience/computer-systems
  - practice
---

# System Software Key Practice Problems

These problems cover the core skills of 9618 A Level Section 16: process states and scheduling, virtual memory, paging and segmentation, the stages of compilation, BNF, and RPN. Attempt them on paper before reading [[30 Computer Science/01 Topics/16 System Software/31 Key Practice Solutions|the solutions]]. For every trace question, draw the full table and compute the required average before checking. No answers are given here on purpose: the point is active recall and full written working.

## A. Process management

1. State the three process states and, for each, one circumstance in which a process is in that state.

2. A process is running when it requests a value the user must type. Describe, in order, the two state transitions the process undergoes, naming the event that triggers the transition back toward running.

3. Distinguish multi-tasking from running a single program, and explain what makes each of several open programs appear to make progress at the same time on a single CPU.

4. Four processes arrive with the times below. Using first come first served (FCFS), draw the trace table and compute the average waiting time.

| Process | Arrival time | Burst time |
|---|---|---|
| P1 | 0 | 5 |
| P2 | 1 | 7 |
| P3 | 2 | 3 |
| P4 | 3 | 6 |

5. Using the same four processes as in Problem 4, draw the trace table for non-preemptive shortest job first (SJF) and compute the average waiting time. State which scheduling routine gives the lower average waiting time for this set.

6. Three processes arrive with the times below. Using round robin with a time quantum of 3, draw the trace table and compute the average waiting time.

| Process | Arrival time | Burst time |
|---|---|---|
| P1 | 0 | 5 |
| P2 | 0 | 4 |
| P3 | 2 | 2 |

7. Explain how a hardware timer interrupt and the kernel together drive low-level scheduling when a running process's time slice ends. State what is saved and where, so that the process can later resume.

## B. Memory management

8. Explain how virtual memory allows a computer to run programs whose total size exceeds the installed RAM, naming the two storage media involved.

9. Distinguish paging from segmentation under the headings: how the address space is divided; whether the units are of fixed or variable size; whether the division is visible to the programmer.

10. A system uses demand paging with the LRU page replacement policy. The frames can hold three pages, and the page reference string is:

```
3 4 2 3 4 5 3 5 2 4
```

Draw the trace table showing the contents of the frames after each reference, and state the total number of page faults.

11. Explain what disk thrashing is, why it occurs, and one action a user or administrator can take to reduce it.

## C. Compilation

12. Describe each of the four stages of compilation in the correct order, and state what each stage produces.

13. For the statement `total ← x + y - z`, give an example output of (a) lexical analysis and (b) code generation, in the same style as the worked example.

14. State two ways in which an interpreter executes a program without first producing a translated version, and one disadvantage of this approach compared with compilation.

15. Give two distinct benefits of the optimisation stage of compilation.

## D. BNF and RPN

16. Write a BNF definition for a `<signed integer>` that consists of an optional sign (`+` or `-`) followed by one or more digits.

17. Write a BNF definition for a `<variable>` that is a letter followed by zero or more letters or digits, and use it to write a rule for `<factor>` that is either an unsigned integer, a variable, or a bracketed expression.

18. Convert each infix expression to Reverse Polish Notation.

   (a) `A + B - C`

   (b) `A + B * C`

   (c) `( A + B ) * ( C - D )`

19. Evaluate the RPN expression below using a stack. Show the stack after each token and state the final result.

```
6 2 3 + - 4 *
```

20. Explain why Reverse Polish Notation needs no brackets and no rule of operator precedence, and state the two stack operations used when evaluating an RPN expression.

---

After finishing, check your working against [[30 Computer Science/01 Topics/16 System Software/31 Key Practice Solutions|the solutions]] and re-attempt any question you could not complete in full.
