---
title: Computational Thinking and Problem-solving Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[Computational Thinking and Problem-solving](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - worked-examples
---

# Computational Thinking and Problem-solving Worked Examples

This page steps through worked examples that cover the 9618 A Level section 19 syllabus: the standard search and sort algorithms, abstract data type operations, recursion, and Big O notation. Each example follows the same pattern: a prompt in CAIE style, a full pseudocode solution, and a short check of the points to remember in an exam.

## Source Route

Worked from the CAIE 9618 Pseudocode Guide and the A Level syllabus statements for section 19. All pseudocode uses the official notation, including the assignment arrow ← and the comparison operators `=`, `<`, `>`.

## Example 1: Linear search with a trace

**Prompt.** Write a linear search that reports whether `TargetValue` is present in `Data[1..Upper]`. Trace it searching for `7` in `Data = [5, 3, 8, 1, 7]`.

**Solution.**

```pseudocode
DECLARE Found : BOOLEAN
DECLARE Index : INTEGER

Found ← FALSE
Index ← 1

WHILE Found = FALSE AND Index <= Upper
    IF Data[Index] = TargetValue THEN
        Found ← TRUE
    ELSE
        Index ← Index + 1
    ENDIF
ENDWHILE

IF Found = TRUE THEN
    OUTPUT "Found at position ", Index
ELSE
    OUTPUT "Not found"
ENDIF
```

Trace (`Upper = 5`, `TargetValue = 7`):

| Index | Data[Index] | Match? | Action |
|---|---|---|---|
| 1 | 5 | No | Index ← 2 |
| 2 | 3 | No | Index ← 3 |
| 3 | 8 | No | Index ← 4 |
| 4 | 1 | No | Index ← 5 |
| 5 | 7 | Yes | Found ← TRUE, exit |

Output: "Found at position 5".

**Check.** The loop guard combines two stopping conditions: found, or index past the upper bound. If the target is absent the loop exits with `Found = FALSE` and prints "Not found". Linear search works on any data, sorted or not.

## Example 2: Binary search and its conditions

**Prompt.** State the three conditions that must hold before a binary search can be used, and write pseudocode for a binary search on a sorted array `Data[1..Upper]`.

**Solution.**

The three conditions:

1. The data is **sorted** (consistently ascending or descending).
2. The data supports **direct access** by index in $O(1)$ time (an array, not a plain linked list).
3. The elements are **comparable** through a consistent ordering relation.

```pseudocode
DECLARE Found : BOOLEAN
DECLARE Lower : INTEGER
DECLARE Higher : INTEGER
DECLARE Mid : INTEGER

Found ← FALSE
Lower ← 1
Higher ← Upper

WHILE Found = FALSE AND Lower <= Higher
    Mid ← (Lower + Higher) DIV 2
    IF Data[Mid] = TargetValue THEN
        Found ← TRUE
    ELSE
        IF Data[Mid] < TargetValue THEN
            Lower ← Mid + 1
        ELSE
            Higher ← Mid - 1
        ENDIF
    ENDIF
ENDWHILE

IF Found = TRUE THEN
    OUTPUT "Found at position ", Mid
ELSE
    OUTPUT "Not found"
ENDIF
```

**Check.** Each iteration halves the search range. When `Data[Mid] < TargetValue` the target, if present, must lie in the upper half, so `Lower` jumps past `Mid`. The loop ends when the range is empty (`Lower > Higher`) with `Found` still FALSE.

## Example 3: Comparing linear and binary search

**Prompt.** Compare linear and binary search using Big O notation. Give the worst-case number of comparisons for data sizes 1 000 and 1 000 000, and state the trade-off.

**Solution.**

| Algorithm | Time (best) | Time (average) | Time (worst) | Space |
|---|---|---|---|---|
| Linear search | $O(1)$ | $O(n)$ | $O(n)$ | $O(1)$ |
| Binary search | $O(1)$ | $O(\log n)$ | $O(\log n)$ | $O(1)$ |

Worst-case comparisons:

| Data size $n$ | Linear $O(n)$ | Binary $O(\log_2 n)$ |
|---|---|---|
| 1 000 | 1 000 | 10 |
| 1 000 000 | 1 000 000 | 20 |

**Check.** Binary search wins heavily for large data, but its price is the precondition: the data must be sorted first, which itself costs time (at least $O(n \log n)$ for an efficient sort). Linear search is the right choice for small or unsorted data, or when the data changes often.

## Example 4: Bubble sort with a trace

**Prompt.** Write a bubble sort that orders `Data[1..Upper]` into ascending order. Trace the first pass on `Data = [5, 3, 8, 1]`.

**Solution.**

```pseudocode
DECLARE Temp : INTEGER
DECLARE Swapped : BOOLEAN
DECLARE Index : INTEGER

REPEAT
    Swapped ← FALSE
    FOR Index ← 1 TO Upper - 1
        IF Data[Index] > Data[Index + 1] THEN
            Temp ← Data[Index]
            Data[Index] ← Data[Index + 1]
            Data[Index + 1] ← Temp
            Swapped ← TRUE
        ENDIF
    NEXT Index
UNTIL Swapped = FALSE
```

Trace of the first pass (`Upper = 4`):

| Index | Compare | Swap? | Array after step |
|---|---|---|---|
| 1 | 5, 3 | Yes | 3, 5, 8, 1 |
| 2 | 5, 8 | No | 3, 5, 8, 1 |
| 3 | 8, 1 | Yes | 3, 5, 1, 8 |

After this pass the largest value, 8, sits at the end. A second pass would move the 1 further left, and the `Swapped` flag lets the sort stop early once a pass makes no swaps.

**Check.** The inner loop runs to `Upper - 1` because each step reads `Index` and `Index + 1`. The `Swapped` flag is what gives bubble sort its $O(n)$ best case on already-sorted data.

## Example 5: Insertion sort

**Prompt.** Write an insertion sort that orders `Data[1..Upper]` into ascending order. Explain why its best case is $O(n)$.

**Solution.**

```pseudocode
DECLARE CurrentItem : INTEGER
DECLARE CurrentPos : INTEGER
DECLARE Index : INTEGER

FOR Index ← 2 TO Upper
    CurrentItem ← Data[Index]
    CurrentPos ← Index
    WHILE CurrentPos > 1 AND Data[CurrentPos - 1] > CurrentItem
        Data[CurrentPos] ← Data[CurrentPos - 1]
        CurrentPos ← CurrentPos - 1
    ENDWHILE
    Data[CurrentPos] ← CurrentItem
NEXT Index
```

On already-sorted data the `WHILE` condition is false on the first test for every value of `Index`, so the inner loop body never runs. The outer loop still makes $n - 1$ passes, each doing one comparison and one assignment, which is $O(n)$.

**Check.** The item being inserted is held in `CurrentItem` so that shifting larger sorted elements rightwards does not overwrite it. The `WHILE` stops when the slot is found (`Data[CurrentPos - 1]` is no longer larger) or when the front of the array is reached.

## Example 6: ADT operations on a stack and a linked list

**Prompt.** Write pseudocode for `Push(NewValue)` onto a stack held in `Stack[1..MaxSize]` with a `TopPointer`, and for inserting a new node holding `NewValue` into a linked list immediately after the node pointed to by `CurrentPointer`.

**Solution.**

Push:

```pseudocode
// Push NewValue onto the stack (LIFO)
IF TopPointer = MaxSize THEN
    OUTPUT "Stack overflow"
ELSE
    TopPointer ← TopPointer + 1
    Stack[TopPointer] ← NewValue
ENDIF
```

Linked-list insert after `CurrentPointer`:

```pseudocode
NewNode.Data ← NewValue
NewNode.Next ← CurrentPointer.Next
CurrentPointer.Next ← NewNode
```

**Check.** The push checks the upper bound first to avoid overflow. The linked-list insert is the pointer-swap pattern: the new node adopts the old successor, then the predecessor is repointed at the new node. Order matters; repointing `CurrentPointer.Next` first would lose the rest of the list.

## Example 7: Implementing a stack from a linked list

**Prompt.** A stack ADT must support `Push` and `Pop`. Describe how to implement this stack using a linked list rather than an array, and write pseudocode for both operations.

**Solution.**

A linked-list stack uses the list head as the top of the stack. `Push` inserts a new node at the head; `Pop` removes the head node and moves `Head` to the next node. This honours the LIFO rule because the most recently inserted node is always at the head. No array or `TopPointer` is needed, so the stack is never full unless memory runs out.

```pseudocode
// Push: insert NewValue at the head of the list
NewNode.Data ← NewValue
NewNode.Next ← Head
Head ← NewNode

// Pop: remove and return the value at the head
IF Head = NullPointer THEN
    OUTPUT "Stack underflow"
ELSE
    PoppedValue ← Head.Data
    Head ← Head.Next
ENDIF
```

**Check.** Both operations work in $O(1)$ time because they touch only the head node. The same linked list could back a queue instead, by inserting at the tail and removing at the head; the ADT behaviour is set by which operations are exposed, not by the storage.

## Example 8: Recursion with a call-stack trace

**Prompt.** Write a recursive function `Factorial(N)` that returns $n!$. Trace `Factorial(3)` showing the call stack pushing frames and then unwinding.

**Solution.**

$$n! = n \times (n-1)!, \quad 0! = 1$$

```pseudocode
FUNCTION Factorial(N : INTEGER) RETURNS INTEGER
    IF N = 0 THEN
        RETURN 1
    ELSE
        RETURN N * Factorial(N - 1)
    ENDIF
ENDFUNCTION
```

Call-stack trace for `Factorial(3)`:

```text
Call Factorial(3)
  N = 3, not base case, needs 3 * Factorial(2)      [push frame 3]
    Call Factorial(2)
      N = 2, not base case, needs 2 * Factorial(1)  [push frame 2]
        Call Factorial(1)
          N = 1, not base case, needs 1 * Factorial(0)  [push frame 1]
            Call Factorial(0)
              N = 0, base case, RETURN 1             [frame 0 returns]
          1 * 1 = 1, RETURN 1                        [frame 1 unwinds]
      2 * 1 = 2, RETURN 2                            [frame 2 unwinds]
  3 * 2 = 6, RETURN 6                                [frame 3 unwinds]
Result: 6
```

**Check.** The base case `N = 0` is what stops the recursion; each recursive call passes `N - 1`, so the argument moves towards 0 and the chain converges. The stack grows deepest at `Factorial(0)` and then shrinks as each frame multiplies its `N` by the result from below and returns.

## Example 9: How a compiler translates recursion

**Prompt.** Explain how a compiler translates a recursive subroutine using the call stack. Define what is meant by unwinding.

**Solution.**

A compiler needs no special recursive instructions. For every subroutine call, recursive or not, it generates code to evaluate the arguments, push a **stack frame** holding the return address, the parameters, and the local variables, and then jump to the subroutine's code. For a recursive call this repeats, so each call gets its own frame with its own copy of the parameters. The variable `N` in one frame is independent of the `N` in any other frame.

When a frame reaches the base case and returns, its return value is passed back to the frame that called it, and that frame is **popped**. Control returns to the calling frame, which resumes from where it left off. This popping of frames in reverse order is called **unwinding** the stack. So the line `RETURN N * Factorial(N - 1)` means: push a frame, call `Factorial(N - 1)` and wait; when it returns, multiply its result by `N` and return that value. The stack is what lets each call remember where it was and what to do with the result.

**Check.** The depth of the call stack equals the depth of the recursion, which is why a recursion with no converging base case overflows the stack. Each frame also costs memory, so a deep recursion can fail where a simple loop with the same logic would not.
