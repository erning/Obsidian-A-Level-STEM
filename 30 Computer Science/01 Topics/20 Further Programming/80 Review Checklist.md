---
title: Further Programming Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/20 Further Programming/00 Overview|Further Programming]]"
status: active
tags:
  - computerscience/programming
  - review-checklist
---

# Further Programming Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can recall, trace, and explain the ideas without prompting.

## Ideas to Recall

- [ ] Define a programming paradigm as a style of building programs around particular concepts.
- [ ] Distinguish low-level, imperative, object-oriented, and declarative paradigms.
- [ ] Recall immediate, direct, indirect, indexed, and relative addressing modes.
- [ ] Explain imperative programming as step-by-step state change using variables, constructs, procedures, and functions.
- [ ] Recall OOP terms: class, object, instance, attribute, method, encapsulation, getter, setter, inheritance, polymorphism, and containment.
- [ ] Distinguish inheritance as "is-a" from containment as "has-a".
- [ ] Explain declarative programming using facts, rules, and goals.
- [ ] Distinguish serial, sequential, and random file organisations.
- [ ] Recall file modes: read, write, append, and random access operations.
- [ ] Define an exception as a run-time error condition that can be handled.
- [ ] Explain why the most specific exception handler should come before a general handler.

## Skills to Perform

- [ ] Classify a task by the paradigm that fits its central idea.
- [ ] Write one instruction for each addressing mode and state the effect on ACC or PC.
- [ ] Explain direct and indirect addressing using a short memory example.
- [ ] Write imperative code using loops, procedures, and functions without mixing paradigms unnecessarily.
- [ ] Design classes from a scenario by listing nouns, attributes, and methods.
- [ ] Write a class with private attributes, getters, and validated setters.
- [ ] Use inheritance only for a true "is-a" relationship and override a method where appropriate.
- [ ] Use containment when one object is made from or stores other objects.
- [ ] Write Prolog-style facts, rules, and goals from relationship data.
- [ ] Write pseudocode to read a sequential file until end of file.
- [ ] Write pseudocode to append to a serial or sequential file without destroying existing data.
- [ ] Write pseudocode to update a random file record using `SEEK`, `GETRECORD`, and `PUTRECORD`.
- [ ] Write exception-handling code in a chosen programming language with a useful recovery action.

## Things to Trace or Explain

- [ ] Explain why modern languages can support several paradigms while a single solution should stay consistent.
- [ ] Trace indexed addressing as base address plus index register.
- [ ] Trace indirect addressing as address to address to value.
- [ ] Explain how encapsulation protects object state through methods rather than public attributes.
- [ ] Trace object construction through a parent class and a subclass.
- [ ] Explain how polymorphism lets an overridden method respond differently for a subclass instance.
- [ ] Trace how a declarative system satisfies a goal by matching facts and applying rules.
- [ ] Explain why a sequential file is read from the start while a random file can seek directly.
- [ ] Trace an exception from the risky statement to the first matching handler.
- [ ] Connect low-level programming to [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]] by explaining how addressing modes locate operands.

## Common Errors to Avoid

- [ ] Mixing several paradigms in one solution without a clear reason.
- [ ] Confusing direct addressing with indirect addressing.
- [ ] Treating indexed addressing as a jump instead of an operand lookup.
- [ ] Making object attributes public and bypassing getters and setters.
- [ ] Using inheritance for a "has-a" relationship.
- [ ] Forgetting that a declarative rule's body must be satisfied for the head to be true.
- [ ] Opening a file for `WRITE` when existing data must be preserved.
- [ ] Forgetting to close a file after processing.
- [ ] Using sequential scanning for a task that needs direct random access.
- [ ] Catching a broad exception first so the specific handler is never reached.
- [ ] Handling an exception but providing no useful recovery action or message.

## Ready to Move On When

- [ ] I can identify the paradigm a task is asking for and stay within it.
- [ ] I can write and explain all five addressing modes.
- [ ] I can design a small OOP model with encapsulation, inheritance, polymorphism, and containment used appropriately.
- [ ] I can write declarative facts, rules, and goals and explain how a goal is satisfied.
- [ ] I can choose serial, sequential, or random file organisation from the access pattern.
- [ ] I can write file-processing code that opens in the correct mode, processes records, and closes the file.
- [ ] I can write exception-handling code that catches specific failures before general ones.
- [ ] I can connect this topic to [[30 Computer Science/01 Topics/11 Programming/00 Overview|Programming]] by explaining how procedural code is extended.
- [ ] I can connect this topic to [[30 Computer Science/01 Topics/12 Software Development/00 Overview|Software Development]] by explaining how robust programs are tested and maintained.
- [ ] I can connect this topic to [[30 Computer Science/01 Topics/13 Data Representation/00 Overview|Data Representation]] through file organisation and records.
