---
title: Data Types and Structures Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[Data Types and Structures](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - review-checklist
---

# Data Types and Structures Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can recall, trace, and explain the ideas without prompting.

## Ideas to Recall

- [ ] Define a data type as the set of values allowed and the operations that make sense on them.
- [ ] Recall INTEGER, REAL, CHAR, STRING, BOOLEAN, DATE, ARRAY, and FILE, with one suitable use for each.
- [ ] Distinguish INTEGER from REAL, and CHAR from STRING.
- [ ] Explain why DATE is preferable to storing a calendar value as ordinary text.
- [ ] Define a record as fields of different data types grouped under one identifier.
- [ ] Distinguish a record from an array.
- [ ] Recall what an array index, lower bound, and upper bound mean.
- [ ] Distinguish a 1D array from a 2D array by the shape of the data.
- [ ] Recall the purpose and basic method of bubble sort and linear search.
- [ ] Explain why files are needed for persistent storage.
- [ ] Define an ADT as data plus the operations allowed on that data.
- [ ] Recall stack, queue, and linked list ordering rules and operations.

## Skills to Perform

- [ ] Choose an appropriate data type for each field in a scenario and justify it.
- [ ] Define a record with `TYPE ... ENDTYPE`, declare a variable of that type, and use dot notation.
- [ ] Declare a 1D array and process every valid index once.
- [ ] Declare a 2D array and use nested loops to process rows and columns.
- [ ] Initialise an accumulator before summing an array.
- [ ] Seed a best-so-far value from the first array element before finding a maximum or minimum.
- [ ] Trace one pass of a bubble sort, showing the array after each comparison.
- [ ] Write a linear search that stops when the target is found or the upper bound is passed.
- [ ] Open, read, write, append, and close text files using the correct file mode.
- [ ] Use `WHILE NOT EOF(...)` to read a whole text file safely.
- [ ] Justify choosing a stack, queue, or linked list from the ordering rule the task needs.
- [ ] Describe how a stack, queue, and linked list can be implemented with arrays and pointer variables.

## Things to Trace or Explain

- [ ] Trace an array loop and show the exact indexes visited.
- [ ] Explain why a loop over adjacent pairs stops at the upper bound minus one.
- [ ] Trace a linear search when the target is present and when it is absent.
- [ ] Explain why `FOR WRITE` can destroy existing file contents but `FOR APPEND` keeps them.
- [ ] Trace the state of a stack pointer through push and pop operations.
- [ ] Trace the front and rear pointers of a queue through enqueue and dequeue operations.
- [ ] Explain how a linked list uses data values and next-pointers.
- [ ] Explain why an ADT is not the same as its array implementation.
- [ ] Connect this topic to [Programming](../11%20Programming/00%20Overview.md) by explaining how data types appear in declarations, expressions, and routine headers.
- [ ] Connect this topic to [Computational Thinking and Problem-solving](../19%20Computational%20Thinking%20and%20Problem-solving/00%20Overview.md) by explaining how ADT descriptions become full algorithms.

## Common Errors to Avoid

- [ ] Choosing REAL for a count or index that can only be a whole number.
- [ ] Choosing INTEGER for a measurement where fractional values matter.
- [ ] Treating CHAR as if it could hold a whole word.
- [ ] Declaring an array without clear bounds.
- [ ] Looping from 0 when the lower bound is 1.
- [ ] Reading one element past the upper bound.
- [ ] Starting a maximum search with 0 when the array could hold only negative values.
- [ ] Letting a linear search continue after the target has already been found.
- [ ] Calling `READFILE` without checking for end of file.
- [ ] Forgetting to close a file after processing.
- [ ] Treating a stack as FIFO or a queue as LIFO.
- [ ] Describing linked-list deletion without repointing the previous node.

## Ready to Move On When

- [ ] I can choose data types from the values and operations required, not from the field name alone.
- [ ] I can define, read, and write a record in pseudocode.
- [ ] I can process 1D and 2D arrays without losing track of bounds.
- [ ] I can trace bubble sort and linear search by hand.
- [ ] I can write the standard text-file read pattern and explain every file mode.
- [ ] I can describe stack, queue, and linked-list behaviour independently of their storage.
- [ ] I can explain how arrays can be used to implement stack, queue, and linked-list ADTs.
- [ ] I can connect this topic to [Databases](../08%20Databases/00%20Overview.md) through records, fields, and structured data.
- [ ] I can connect this topic to [Data Representation](../13%20Data%20Representation/00%20Overview.md) through file organisation and stored data.
