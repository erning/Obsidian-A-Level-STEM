---
title: Further Programming Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[Further Programming](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - practice
---

# Further Programming Key Practice Problems

These problems cover A Level section 20 Further Programming: the four programming paradigms, object-oriented and declarative design, file processing for serial, sequential and random files, and exception handling. Attempt every problem on paper before checking the [solutions file](31%20Key%20Practice%20Solutions.md). No answers appear in this file so it can be used for active recall.

## A. Paradigms

1. For each task below, name the most appropriate paradigm (low-level, imperative/procedural, object-oriented, or declarative) and justify the choice in one sentence.
    (a) Stepping through the elements of an array stored at a base address using an index register.
    (b) Totaling a column of figures read from a sorted file using a loop.
    (c) Simulating a library that has books, members and loans.
    (d) Deciding whether one city can be reached from another using a set of flight connections.

2. Distinguish between an imperative program and a declarative program by stating what the programmer writes in each case.

3. Explain why a modern language such as Java or Python can be described as both imperative and object-oriented, and state why an exam answer should still stay inside a single paradigm.

4. State two characteristics of low-level code that distinguish it from high-level code.

5. Name the five addressing modes and, for each, write one load instruction (using `LDM`, `LDD`, `LDI`, `LDX` or a relative jump) together with the effect it has on `ACC` or `PC`.

6. Explain the difference between direct addressing and indirect addressing using a memory diagram or a worked example. State one situation where indirect addressing is useful.

## B. Object-oriented and declarative

7. Define each of the following OOP terms in one sentence: class, object, instance, attribute, method, encapsulation.

8. Explain the difference between inheritance and containment (aggregation), and give one example relationship for each.

9. Design a `BankAccount` class with a private attribute for the balance, a getter for the balance, and a setter that prevents the balance from being set below zero. Write the class in Java or Python.

10. Design a `SavingsAccount` class that inherits from `BankAccount` and adds a private interest rate attribute, with a getter and a validated setter (rate between 0 and 1 inclusive). Write an overridden `display` method and a small main section that creates an instance and calls it.

11. State what a getter and a setter are, and explain why making an attribute private and exposing it through a validated setter is preferred over making the attribute public.

12. Given the following facts, write a Prolog-style rule for `sibling(X, Y)` that is true when `X` and `Y` share at least one parent, and a rule for `cousin(X, Y)`. Do not let a person be their own sibling.

```prolog
parent(tom, bob).
parent(tom, kay).
parent(bob, ann).
parent(kay, lee).
```

13. Write a goal that succeeds and a goal that fails using the facts and rules from question 12. State the answer the system would give for each.

14. Explain what a fact, a rule and a goal are in declarative programming, and state how the system uses rules to satisfy a goal.

## C. File processing

15. A sequential file `Stock.dat` holds one product name per record, sorted by name. Write pseudocode that opens the file for reading, reads and outputs every record until the end of the file, and closes the file. State the mode and why it is used.

16. A log file `Events.dat` is a serial file. Write pseudocode that appends a new record `NewEntry` to the end of the file. State the mode and explain why `WRITE` would be wrong here.

17. A random-access file `Accounts.dat` holds fixed-length records. Write pseudocode that opens the file, seeks to the record at index `Idx`, reads it into `Rec`, changes its `Balance` field to zero, writes the record back, and closes the file.

18. State the difference between serial and sequential file organisation, and give one typical use for each.

19. State the three modes a file can be opened in, and explain what happens to existing data when a file is opened for `WRITE` as opposed to `APPEND`.

20. Describe one situation in which a random file is preferred over a sequential file, and justify your answer.

## D. Exception handling

21. Define the term exception, give two examples of conditions that can raise one, and state what happens if an exception is not handled.

22. Explain when it is appropriate to handle an exception rather than let the program stop, and give one situation in which catching an exception broadly would be a mistake.

23. Write program code in Java, Visual Basic .NET, or Python that inputs a number, divides 100 by it, and outputs the result. A division by zero must produce the message "Cannot divide by zero." instead of crashing, and any other invalid input must produce a different message.

24. Rewrite the program from question 23 in a different Paper 4 language, using the most specific exception handler first and a general exception handler second.

25. A program reads from a file whose name the user types in. Explain why this is a good candidate for exception handling, name the kind of exception that could occur, and describe a sensible recovery action.
