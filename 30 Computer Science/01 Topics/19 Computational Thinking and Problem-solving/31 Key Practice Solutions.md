---
title: Computational Thinking and Problem-solving Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[Computational Thinking and Problem-solving](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - solutions
---

# Computational Thinking and Problem-solving Key Practice Solutions

Full solutions to the [Key Practice Problems](30%20Key%20Practice%20Problems.md) for 9618 A Level section 19. Pseudocode follows the CAIE 9618 Pseudocode Guide, including the assignment arrow ←. Complexity is given in Big O notation with justification from the loop structure.

## A. Searching

**1.**

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

Worst-case time complexity is $O(n)$. If the target is last or absent, the loop runs through all $n$ elements, so the number of iterations grows linearly with the data size. Space complexity is $O(1)$ because only two extra variables are used.

**2.** The three conditions are: the data is sorted (consistently ascending or descending); the data supports direct access by index in $O(1)$ time (an array, not a plain linked list); and the elements are comparable through a consistent ordering relation.

**3.**

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

**4.** Trace for `TargetValue = 9` in `Data = [2, 5, 7, 9, 12, 15, 18]` (`Upper = 7`):

| Step | Lower | Higher | Mid | Data[Mid] | Action |
|---|---|---|---|---|---|
| 1 | 1 | 7 | 4 | 9 | Match, Found ← TRUE |

The target sits at the middle of the first probe, so the search ends in one comparison. Output "Found at position 4".

**5.** Linear search makes up to 1 000 000 comparisons in the worst case ($O(n)$). Binary search makes about 20 comparisons in the worst case ($O(\log_2 n)$, since $2^{20} \approx 1\,000\,000$). Binary search is faster for large data because each comparison halves the remaining search range, so the comparison count grows with the logarithm of $n$ rather than with $n$ itself. The trade-off is that the data must be sorted first.

## B. Sorting

**6.**

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

The `Swapped` flag records whether any swap occurred during a pass. If a complete pass makes no swaps the array is already sorted and the outer loop stops early, giving the $O(n)$ best case. Without it the sort would always perform all $n - 1$ passes.

**7.** First pass on `Data = [4, 2, 7, 1, 3]` (`Upper = 5`):

| Index | Compare | Swap? | Array after step |
|---|---|---|---|
| 1 | 4, 2 | Yes | 2, 4, 7, 1, 3 |
| 2 | 4, 7 | No | 2, 4, 7, 1, 3 |
| 3 | 7, 1 | Yes | 2, 4, 1, 7, 3 |
| 4 | 7, 3 | Yes | 2, 4, 1, 3, 7 |

After the first pass the largest value, 7, is in its final position at the end.

**8.**

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

**9.** Step with `Index = 4` on `Data = [2, 5, 7, 1]`. `CurrentItem = 1`, `CurrentPos = 4`.

| CurrentPos | Compare | Action | Array after step |
|---|---|---|---|
| 4 | Data[3] = 7 > 1 | Shift 7 right | 2, 5, 7, 7 |
| 3 | Data[2] = 5 > 1 | Shift 5 right | 2, 5, 5, 7 |
| 2 | Data[1] = 2 > 1 | Shift 2 right | 2, 2, 5, 7 |
| 1 | Front reached | Insert 1 at position 1 | 1, 2, 5, 7 |

**10.**

| Sort | Best | Average | Worst | Space |
|---|---|---|---|---|
| Bubble | $O(n)$ | $O(n^2)$ | $O(n^2)$ | $O(1)$ |
| Insertion | $O(n)$ | $O(n^2)$ | $O(n^2)$ | $O(1)$ |

Both are $O(1)$ in space because they reorder the array in place using only a fixed number of extra variables (`Temp`, `Swapped`, `CurrentItem`, `CurrentPos`). No second array proportional to $n$ is allocated.

## C. Abstract data types

**11.**

```pseudocode
DECLARE CurrentPointer : POINTER
DECLARE Found : BOOLEAN

Found ← FALSE
CurrentPointer ← Head

WHILE Found = FALSE AND CurrentPointer <> NullPointer
    IF CurrentPointer.Data = TargetValue THEN
        Found ← TRUE
    ELSE
        CurrentPointer ← CurrentPointer.Next
    ENDIF
ENDWHILE

IF Found = TRUE THEN
    OUTPUT "Found"
ELSE
    OUTPUT "Not found"
ENDIF
```

**12.**

```pseudocode
NewNode.Data ← NewValue
NewNode.Next ← CurrentPointer.Next
CurrentPointer.Next ← NewNode
```

The new node adopts the old successor before the predecessor is repointed; reversing the order would lose the rest of the list.

**13.**

```pseudocode
DECLARE CurrentPointer : POINTER
DECLARE PreviousPointer : POINTER
DECLARE Found : BOOLEAN

Found ← FALSE
CurrentPointer ← Head
PreviousPointer ← NullPointer

WHILE Found = FALSE AND CurrentPointer <> NullPointer
    IF CurrentPointer.Data = TargetValue THEN
        Found ← TRUE
    ELSE
        PreviousPointer ← CurrentPointer
        CurrentPointer ← CurrentPointer.Next
    ENDIF
ENDWHILE

IF Found = TRUE THEN
    IF PreviousPointer = NullPointer THEN
        Head ← CurrentPointer.Next
    ELSE
        PreviousPointer.Next ← CurrentPointer.Next
    ENDIF
ENDIF
```

When the target is the head node, `PreviousPointer` is still `NullPointer`, so `Head` is moved directly to the second node. Otherwise the previous node's `Next` is repointed past the deleted node, bypassing it.

**14.** Push:

```pseudocode
IF TopPointer = MaxSize THEN
    OUTPUT "Stack overflow"
ELSE
    TopPointer ← TopPointer + 1
    Stack[TopPointer] ← NewValue
ENDIF
```

Pop:

```pseudocode
IF TopPointer = 0 THEN
    OUTPUT "Stack underflow"
ELSE
    PoppedValue ← Stack[TopPointer]
    TopPointer ← TopPointer - 1
ENDIF
```

**15.** Enqueue:

```pseudocode
IF NumberOfItems = MaxSize THEN
    OUTPUT "Queue full"
ELSE
    RearPointer ← (RearPointer MOD MaxSize) + 1
    Queue[RearPointer] ← NewValue
    NumberOfItems ← NumberOfItems + 1
ENDIF
```

Dequeue:

```pseudocode
IF NumberOfItems = 0 THEN
    OUTPUT "Queue empty"
ELSE
    DequeuedValue ← Queue[FrontPointer]
    FrontPointer ← (FrontPointer MOD MaxSize) + 1
    NumberOfItems ← NumberOfItems - 1
ENDIF
```

The `MOD MaxSize` wrap lets the rear and front pointers reuse the space freed at the front by earlier dequeues, turning the array into a circular buffer.

**16.** A graph is an abstract data type consisting of a set of vertices (nodes) and a set of edges that connect pairs of vertices. Key features: vertices hold values; edges model a relationship between two vertices; an edge may be directed (one-way) or undirected (two-way); an edge may carry a weight giving a weighted graph; a graph has no fixed entry point and no fixed traversal order, and may contain cycles.

Two suitable situations:

- A road or rail network: towns are vertices, roads are weighted edges (distance or time), and the task, such as finding a shortest route, only makes sense in terms of the connections. An array or tree cannot model the many-to-many connections.
- A social network: people are vertices and friendships are undirected edges. Any person may connect to any other with no single root, so a tree is unsuitable.

**17.**

| ADT | Can be implemented from | Why it works |
|---|---|---|
| Stack | A 1D array, or a linked list | Both can add and remove at one end (LIFO) |
| Queue | A 1D array (circular), or a linked list | Both can add at one end and remove at the other (FIFO) |
| Linked list | Two parallel arrays (data and next-pointer), or a dynamic array of records | The `Next` values recreate the pointer chain |
| Dictionary | A hash table, an array of (key, value) records, or a binary search tree | Maps keys to values by hashing, search, or comparison |
| Binary tree | A 1D array (children at `2i` and `2i + 1`), or a linked structure of records with two child pointers | Either stores nodes positionally or chains them with pointers |

## D. Recursion and complexity

**18.** The three essential features are: a base case that stops the recursion and returns a value directly; a recursive case in which the subroutine calls itself with a smaller or simpler argument; and convergence, meaning every recursive call moves towards the base case. If the recursive case does not converge, the calls never stop, the call stack grows without bound, and the program terminates with a stack overflow.

**19.**

```pseudocode
FUNCTION Factorial(N : INTEGER) RETURNS INTEGER
    IF N = 0 THEN
        RETURN 1
    ELSE
        RETURN N * Factorial(N - 1)
    ENDIF
ENDFUNCTION
```

**20.** Call-stack trace for `Factorial(4)`:

```text
Call Factorial(4)
  N = 4, not base case, needs 4 * Factorial(3)      [push frame 4]
    Call Factorial(3)
      N = 3, not base case, needs 3 * Factorial(2)  [push frame 3]
        Call Factorial(2)
          N = 2, not base case, needs 2 * Factorial(1)  [push frame 2]
            Call Factorial(1)
              N = 1, not base case, needs 1 * Factorial(0)  [push frame 1]
                Call Factorial(0)
                  N = 0, base case, RETURN 1         [frame 0 returns]
              1 * 1 = 1, RETURN 1                    [frame 1 unwinds]
          2 * 1 = 2, RETURN 2                        [frame 2 unwinds]
        3 * 2 = 6, RETURN 6                          [frame 3 unwinds]
    4 * 6 = 24, RETURN 24                            [frame 4 unwinds]
Result: 24
```

**21.** A compiler translates a recursive subroutine using the ordinary call stack that every subroutine call already uses. For each call it generates code to evaluate the arguments, push a stack frame holding the return address, the parameters, and the local variables, and then jump to the subroutine's code. For a recursive call this repeats, so each call gets its own frame with its own copy of the parameters; the `N` in one frame is independent of the `N` in any other frame.

When a frame reaches the base case and returns, its return value is passed back to the frame that called it, and that frame is popped. Control returns to the calling frame, which resumes from where it left off. This popping of frames in reverse order is called unwinding the stack. So the line `RETURN N * Factorial(N - 1)` means: push a frame, call `Factorial(N - 1)` and wait; when it returns, multiply its result by `N` and return that value.

**22.** Recursion is beneficial when the problem definition is naturally self-similar. Tree and graph traversal suit recursion because a subtree is itself a tree; divide-and-conquer sorts and searches suit it because each half is a smaller instance of the same problem. In both cases the recursive code is shorter and closer to the definition than an iterative version with an explicit stack.

Recursion is a poor choice when the recursion depth could be large, risking stack overflow, or when a simple loop does the same job. Each recursive call costs a frame of memory, so a factorial computed by recursion on a very large `N` would use more memory and run no faster than a loop with an accumulator.
