---
title: Computational Thinking and Problem-solving Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/19 Computational Thinking and Problem-solving/00 Overview|Computational Thinking and Problem-solving]]"
status: active
tags:
  - computerscience/programming
  - practice
---

# Computational Thinking and Problem-solving Key Practice Problems

These problems cover the 9618 A Level section 19 syllabus: linear and binary search, insertion and bubble sort, abstract data type operations, the graph as an ADT, implementing one ADT from another, Big O notation, and recursion. Attempt every problem on paper before checking the [[31 Key Practice Solutions|solutions file]].

## A. Searching

1. Write a linear search that reports whether `TargetValue` is present in `Data[1..Upper]`. State its worst-case time complexity in Big O notation and justify it from the loop structure.

2. State the three conditions that must hold before a binary search can be used on a data set.

3. Write pseudocode for a binary search on a sorted array `Data[1..Upper]` searching for `TargetValue`. Output the position found or a "not found" message.

4. Trace a binary search for `9` in the sorted array `Data = [2, 5, 7, 9, 12, 15, 18]`. Show the values of `Lower`, `Higher`, and `Mid` at each step.

5. A sorted array holds 1 000 000 elements. State the worst-case number of comparisons made by a linear search and by a binary search, and explain why binary search is faster for large data.

## B. Sorting

6. Write a bubble sort that orders `Data[1..Upper]` into ascending order. Include the early-exit flag and explain its purpose.

7. Trace the first pass of a bubble sort on `Data = [4, 2, 7, 1, 3]` into ascending order. Show the array after each comparison.

8. Write an insertion sort that orders `Data[1..Upper]` into ascending order.

9. Trace the single step of an insertion sort on `Data = [2, 5, 7, 1]` when `Index = 4`. Show the array after each shift.

10. Complete the table of best, average, and worst-case time complexity for bubble sort and insertion sort. State the space complexity of each and justify why both are $O(1)$ in space.

## C. Abstract data types

11. Write pseudocode to find a node holding `TargetValue` in a linked list whose head is `Head`. Output "Found" or "Not found".

12. Write pseudocode to insert a new node holding `NewValue` into a linked list immediately after the node pointed to by `CurrentPointer`.

13. Write pseudocode to delete the node holding `TargetValue` from a linked list, using a trailing `PreviousPointer`. Include the special case where the target is the head node.

14. Write pseudocode for `Push(NewValue)` and `Pop` on a stack stored in `Stack[1..MaxSize]` with `TopPointer`. Include overflow and underflow checks.

15. Write pseudocode for `Enqueue(NewValue)` and `Dequeue` on a circular queue stored in `Queue[1..MaxSize]` with `FrontPointer`, `RearPointer`, and `NumberOfItems`. Include full and empty checks.

16. Describe the key features of a graph as an abstract data type. Give two real-world situations where a graph is a more suitable structure than an array or a binary tree, and justify each choice.

17. For each of the following ADTs, name a built-in type or another ADT it can be implemented from: stack, queue, linked list, dictionary, binary tree.

## D. Recursion and complexity

18. State the three essential features of a recursive subroutine. Explain what happens if the recursive case does not converge to the base case.

19. Write a recursive function `Factorial(N : INTEGER) RETURNS INTEGER` that returns $n!$.

20. Trace `Factorial(4)` on the call stack. Show each frame being pushed and then unwinding, and state the final result.

21. Explain how a compiler translates a recursive subroutine using the call stack. Define the term "unwinding" and state what each stack frame stores.

22. Give two situations in which recursion is a beneficial design choice, and one situation in which it is a poor choice. Justify each answer.
