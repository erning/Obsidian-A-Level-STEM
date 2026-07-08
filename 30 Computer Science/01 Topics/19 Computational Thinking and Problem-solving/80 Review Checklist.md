---
title: Computational Thinking and Problem-solving Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/19 Computational Thinking and Problem-solving/00 Overview|Computational Thinking and Problem-solving]]"
status: active
tags:
  - computerscience/programming
  - review-checklist
---

# Computational Thinking and Problem-solving Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can recall, trace, and explain the ideas without prompting.

## Ideas to Recall

- [ ] Define linear search and state why it works on unsorted data.
- [ ] State the three conditions required for binary search.
- [ ] Explain why binary search halves the remaining range at each step.
- [ ] Recall how bubble sort moves the largest unsorted value to its final position on each pass.
- [ ] Recall how insertion sort shifts larger sorted values to make room for the current item.
- [ ] Define Big O notation as order of growth, not an exact operation count.
- [ ] Distinguish time complexity from space complexity.
- [ ] Recall best, average, and worst-case complexity for linear search, binary search, bubble sort, and insertion sort.
- [ ] Recall the ADT operations required for linked lists, binary trees, stacks, and queues.
- [ ] Describe a graph as vertices plus edges, with optional direction and weighting.
- [ ] Recall ways to implement stack, queue, linked list, dictionary, and binary tree ADTs.
- [ ] State the three essential features of recursion: base case, recursive case, and convergence.
- [ ] Explain how a call stack supports recursive calls and unwinding.

## Skills to Perform

- [ ] Write and trace a linear search with a found case and an absent case.
- [ ] Write and trace a binary search using `Lower`, `Higher`, and `Mid`.
- [ ] Compare linear and binary search using data size and preconditions.
- [ ] Write bubble sort with a `Swapped` flag and an inner loop ending at `Upper - 1`.
- [ ] Trace a bubble-sort pass, showing the array after every adjacent comparison.
- [ ] Write insertion sort and trace the shifts for one inserted item.
- [ ] Justify Big O complexity from loop structure or a halving pattern.
- [ ] Write linked-list find, insert, and delete operations using pointer changes.
- [ ] Write stack push and pop with overflow and underflow checks.
- [ ] Write circular-queue enqueue and dequeue with full and empty checks.
- [ ] Justify using a graph for a connection or route problem.
- [ ] Write a simple recursive function and trace the call stack down and back up.

## Things to Trace or Explain

- [ ] Trace binary search until the range is empty and explain why the target is absent.
- [ ] Explain why binary search is invalid on unsorted data or a structure without direct access.
- [ ] Trace how the `Swapped` flag gives bubble sort an early exit.
- [ ] Trace how insertion sort preserves the current item while shifting values right.
- [ ] Explain why both simple sorts can be $O(n)$ on already ordered data but $O(n^2)$ in the worst case.
- [ ] Trace linked-list insertion and explain why the new node must adopt the old successor first.
- [ ] Trace linked-list deletion when the target is the head node and when it is not.
- [ ] Explain how circular queue pointers wrap using `MOD`.
- [ ] Trace recursive factorial by pushing frames to the base case and unwinding return values.
- [ ] Connect this topic to [[30 Computer Science/01 Topics/09 Algorithm Design and Problem-solving/00 Overview|Algorithm Design and Problem-solving]] by explaining how earlier constructs become larger algorithms.

## Common Errors to Avoid

- [ ] Applying binary search before checking that the data is sorted.
- [ ] Forgetting that binary search also needs direct indexed access.
- [ ] Updating `Lower` or `Higher` without moving past `Mid`.
- [ ] Running the bubble-sort inner loop to the upper bound and reading past the end.
- [ ] Omitting the `Swapped` flag when early exit is part of the method.
- [ ] Overwriting the current item during insertion sort.
- [ ] Stating Big O as a precise count instead of a growth class.
- [ ] Treating an ADT as identical to one storage implementation.
- [ ] Repointing a linked-list node in the wrong order and losing the rest of the list.
- [ ] Mixing up the stack top with the queue front or rear.
- [ ] Writing recursion with no base case or no movement toward the base case.
- [ ] Tracing recursion only downward and forgetting the unwinding stage.

## Ready to Move On When

- [ ] I can choose linear or binary search from the data conditions and justify the choice.
- [ ] I can write and trace both search algorithms without losing boundary values.
- [ ] I can write and trace bubble sort and insertion sort on small arrays.
- [ ] I can derive time and space complexity from the algorithm structure.
- [ ] I can draw before-and-after pointer states for linked-list operations.
- [ ] I can implement stack and queue operations while checking full and empty states.
- [ ] I can describe graphs and justify them for network-style data.
- [ ] I can trace recursive code through stack frames and explain unwinding.
- [ ] I can connect this topic to [[30 Computer Science/01 Topics/10 Data Types and Structures/00 Overview|Data Types and Structures]] by explaining how earlier ADT descriptions become algorithms.
- [ ] I can connect this topic to [[30 Computer Science/01 Topics/20 Further Programming/00 Overview|Further Programming]] through recursion, ADTs, and implementation choices.
