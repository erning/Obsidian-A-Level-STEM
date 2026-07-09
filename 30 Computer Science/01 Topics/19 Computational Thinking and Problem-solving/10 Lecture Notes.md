---
title: Computational Thinking and Problem-solving Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[Computational Thinking and Problem-solving](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - lecture-notes
---

# Computational Thinking and Problem-solving Lecture Notes

This A Level topic extends AS section 9 with the standard searching and sorting algorithms, the operations on abstract data types, recursion, and the Big O notation used to compare algorithms. Where the AS note stopped at "describe how a stack works", here you must write the actual pseudocode for searching, sorting, and the ADT operations, and be able to argue about how fast an algorithm runs and how much memory it uses. Paper 3 and Paper 4 examine this material (Paper 4 except low-level and declarative programming).

## Source Route

- Syllabus **9618 A Level section 19 - Computational Thinking and Problem-solving**.
- 19.1 Algorithms: linear and binary search; insertion and bubble sort; ADTs (find, insert, delete); the graph as an ADT; implementing one ADT from another; algorithm comparison and Big O notation.
- 19.2 Recursion: essential features, expression in a language, writing and tracing; how a compiler translates recursion using stacks and unwinding.
- Examined in **Paper 3 and Paper 4** (Paper 4 except low-level and declarative programming).

## 1. Linear search

A **linear search** examines each element of an array in turn, from the lower bound upwards, until it finds the target or runs out of elements. It needs no precondition: the data may be sorted or unsorted, and it works on any array type. Its cost is $O(n)$ in the worst case, because if the target is last (or absent) every element is inspected.

The discipline is to stop the moment the target is found, and to report "not found" honestly if the loop ends without a match.

```pseudocode
// Linear search: is TargetValue present in Data[1..Upper]?
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

Trace a search for `7` in `Data = [5, 3, 8, 1, 7]` (so `Upper = 5`). `Index = 1`: `5 = 7`? no → `Index = 2`. `Index = 2`: `3 = 7`? no → `Index = 3`. `Index = 3`: `8 = 7`? no → `Index = 4`. `Index = 4`: `1 = 7`? no → `Index = 5`. `Index = 5`: `7 = 7`? yes → `Found = TRUE`, loop exits. Output "Found at position 5". If the target were `9`, the loop would exit when `Index` became `6` (past the upper bound) with `Found` still FALSE, producing "Not found".

## 2. Binary search

A **binary search** exploits the order in sorted data. At each step it compares the target with the **middle** element and discards the half that cannot contain the target, repeating on the remaining half until found or the range is empty.

**Conditions for a binary search.** All three must hold:

1. The data is **sorted** (ascending or descending, consistently).
2. The data supports **direct access** by index in $O(1)$ (an array, not a plain linked list).
3. The elements are **comparable** with a consistent ordering relation.

If the data is unsorted, a binary search may return the wrong answer or miss a present item.

```pseudocode
// Binary search: is TargetValue present in sorted Data[1..Upper]?
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
            Lower ← Mid + 1      // target is in the upper half
        ELSE
            Higher ← Mid - 1     // target is in the lower half
        ENDIF
    ENDIF
ENDWHILE

IF Found = TRUE THEN
    OUTPUT "Found at position ", Mid
ELSE
    OUTPUT "Not found"
ENDIF
```

Trace a search for `7` in the sorted array `Data = [1, 3, 5, 7, 9]` (`Upper = 5`). `Lower = 1, Higher = 5`. `Mid = 3`: `Data[3] = 5`, `5 < 7` → search upper half, `Lower = 4`. `Mid = 4`: `Data[4] = 7`, match → `Found = TRUE`. Output "Found at position 4". Only two comparisons; the linear search needed five.

**How performance varies with data size.** Each comparison halves the search range, so the number of comparisons grows with the logarithm of $n$. Doubling the data adds only one more comparison in the worst case. The table shows the worst-case comparisons for several sizes.

| Data size $n$ | Linear search $O(n)$ | Binary search $O(\log_2 n)$ |
|---|---|---|
| 8 | 8 | 3 |
| 1 000 | 1 000 | 10 |
| 1 000 000 | 1 000 000 | 20 |

For small $n$ the difference is negligible; for large sorted data sets binary search is dramatically faster. The price is the precondition - the data must be sorted first, which itself costs time.

## 3. Bubble sort and insertion sort

Both are simple $O(n^2)$ sorts whose actual running time depends on the **initial order** of the data, not just its size.

### Bubble sort

A **bubble sort** repeatedly compares adjacent pairs and swaps them if they are in the wrong order, so the largest unsorted value "bubbles" to its correct position on each pass. It stops a pass early when no swaps were made, which lets it detect an already-sorted array.

```pseudocode
// Bubble sort: put Data[1..Upper] into ascending order
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

Trace one pass on `[5, 3, 8, 1]` (`Upper = 4`). Pair 1–2: `5 > 3`, swap → `[3, 5, 8, 1]`, `Swapped = TRUE`. Pair 2–3: `5 > 8`? no. Pair 3–4: `8 > 1`, swap → `[3, 5, 1, 8]`, `Swapped = TRUE`. The pass ends with the largest value, `8`, fixed at the end. The inner loop runs to `Upper - 1` because each comparison reads index *and* index + 1.

### Insertion sort

An **insertion sort** builds the sorted array one element at a time. It takes the next unsorted element and shifts it leftwards past any larger sorted elements, inserting it into its correct place. Sorted elements are moved right by one to make room.

```pseudocode
// Insertion sort: put Data[1..Upper] into ascending order
DECLARE CurrentItem : INTEGER
DECLARE CurrentPos : INTEGER
DECLARE Index : INTEGER

FOR Index ← 2 TO Upper
    CurrentItem ← Data[Index]
    CurrentPos ← Index
    WHILE CurrentPos > 1 AND Data[CurrentPos - 1] > CurrentItem
        Data[CurrentPos] ← Data[CurrentPos - 1]   // shift larger item right
        CurrentPos ← CurrentPos - 1
    ENDWHILE
    Data[CurrentPos] ← CurrentItem
NEXT Index
```

Trace one step on `[3, 5, 8, 1]`, taking `Index = 4` (the `1`). `CurrentItem = 1`, `CurrentPos = 4`. `Data[3] = 8 > 1` → shift `8` right → `[3, 5, 8, 8]`, `CurrentPos = 3`. `Data[2] = 5 > 1` → shift `5` right → `[3, 5, 5, 8]`, `CurrentPos = 2`. `Data[1] = 3 > 1` → shift `3` right → `[3, 3, 5, 8]`, `CurrentPos = 1`. Loop stops (`CurrentPos = 1`). Insert `1` at position 1 → `[1, 3, 5, 8]`.

### How performance depends on initial order

| Sort | Best case | Worst case | Average |
|---|---|---|---|
| Bubble | Already sorted: $O(n)$ (one pass, no swaps) | Reverse sorted: $O(n^2)$ | $O(n^2)$ |
| Insertion | Already sorted: $O(n)$ (no shifts) | Reverse sorted: $O(n^2)$ | $O(n^2)$ |

Both degrade to $O(n^2)$ on reversed data and run in near-linear time on nearly-sorted data, because each pass does almost no work. Insertion sort is usually slightly faster than bubble sort in practice because it shifts elements directly rather than swapping through many passes.

## 4. Big O notation

**Big O notation** describes how an algorithm's use of a resource (time or memory) grows as the input size $n$ grows, ignoring constant factors and lower-order terms. It gives the **order of growth** - the shape of the curve - rather than an exact count. An $O(n^2)$ algorithm always loses to an $O(n \log n)$ one for large enough $n$, even if the constant on the $O(n^2)$ side is small.

- **Time complexity** is how the number of operations grows with $n$.
- **Space complexity** is how the amount of extra memory grows with $n$.

When you state complexity, give the worst case unless told otherwise, and justify it from the loops: a single pass over $n$ items is $O(n)$; a nested pair of passes is $O(n^2)$; halving the range each step is $O(\log n)$.

### Complexity comparison

| Algorithm | Time (best) | Time (average) | Time (worst) | Space |
|---|---|---|---|---|
| Linear search | $O(1)$ | $O(n)$ | $O(n)$ | $O(1)$ |
| Binary search | $O(1)$ | $O(\log n)$ | $O(\log n)$ | $O(1)$ |
| Bubble sort | $O(n)$ | $O(n^2)$ | $O(n^2)$ | $O(1)$ |
| Insertion sort | $O(n)$ | $O(n^2)$ | $O(n^2)$ | $O(1)$ |

All four use only a fixed amount of extra memory ($O(1)$ space) because they work in place on the array. The searches are $O(1)$ in the best case because the target might sit in the first position inspected.

## 5. ADT operations

An **abstract data type (ADT)** is a collection of data together with a defined set of operations; the user thinks in terms of the operations and their behaviour, not the storage. At A Level you must write pseudocode for the operations below.

| Structure | Find | Insert | Delete |
|---|---|---|---|
| Linked list | traverse from head following pointers | link a new node in | repoint pointers to bypass a node |
| Binary tree | compare and go left or right | attach at a free child position | (not required) |
| Stack | (n/a) | push onto top | pop from top |
| Queue | (n/a) | enqueue at rear | dequeue from front |

A node is drawn as a record holding a data value plus a pointer (in a linked list) or two child pointers (in a binary tree). A **head pointer** records where a linked list starts, and a **null pointer** marks the end or an empty child.

### Find in a linked list

```pseudocode
// Find the node holding TargetValue; return its position or 0
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

### Insert into a stack (push)

```pseudocode
// Push NewValue onto the stack (LIFO: add at the top)
IF TopPointer = MaxSize THEN
    OUTPUT "Stack overflow"
ELSE
    TopPointer ← TopPointer + 1
    Stack[TopPointer] ← NewValue
ENDIF
```

### Insert into a queue (enqueue)

```pseudocode
// Enqueue NewValue into the queue (FIFO: add at the rear)
IF NumberOfItems = MaxSize THEN
    OUTPUT "Queue full"
ELSE
    RearPointer ← (RearPointer MOD MaxSize) + 1   // wrap round (circular)
    Queue[RearPointer] ← NewValue
    NumberOfItems ← NumberOfItems + 1
ENDIF
```

### Insert into a linked list (after a given node)

```pseudocode
// Insert a new node holding NewValue after CurrentPointer
NewNode.Data ← NewValue
NewNode.Next ← CurrentPointer.Next
CurrentPointer.Next ← NewNode
```

The new node's `Next` is set to the node that used to follow `CurrentPointer`, then `CurrentPointer.Next` is repointed at the new node. To insert at the head, set `NewNode.Next ← Head` then `Head ← NewNode`.

### Insert into a binary tree

```pseudocode
// Insert NewValue into a binary search tree
DECLARE CurrentPointer : POINTER
DECLARE Inserted : BOOLEAN

IF Root = NullPointer THEN
    Root.Data ← NewValue
    Root.Left ← NullPointer
    Root.Right ← NullPointer
ELSE
    CurrentPointer ← Root
    Inserted ← FALSE
    WHILE Inserted = FALSE
        IF NewValue < CurrentPointer.Data THEN
            IF CurrentPointer.Left = NullPointer THEN
                CurrentPointer.Left ← NewNode
                NewNode.Data ← NewValue
                NewNode.Left ← NullPointer
                NewNode.Right ← NullPointer
                Inserted ← TRUE
            ELSE
                CurrentPointer ← CurrentPointer.Left
            ENDIF
        ELSE
            IF CurrentPointer.Right = NullPointer THEN
                CurrentPointer.Right ← NewNode
                NewNode.Data ← NewValue
                NewNode.Left ← NullPointer
                NewNode.Right ← NullPointer
                Inserted ← TRUE
            ELSE
                CurrentPointer ← CurrentPointer.Right
            ENDIF
        ENDIF
    ENDWHILE
ENDIF
```

### Delete from a stack (pop)

```pseudocode
// Pop the top value from the stack (LIFO: remove from the top)
IF TopPointer = 0 THEN
    OUTPUT "Stack underflow"
ELSE
    PoppedValue ← Stack[TopPointer]
    TopPointer ← TopPointer - 1
ENDIF
```

### Delete from a queue (dequeue)

```pseudocode
// Dequeue the next value from the queue (FIFO: remove from the front)
IF NumberOfItems = 0 THEN
    OUTPUT "Queue empty"
ELSE
    DequeuedValue ← Queue[FrontPointer]
    FrontPointer ← (FrontPointer MOD MaxSize) + 1   // wrap round (circular)
    NumberOfItems ← NumberOfItems - 1
ENDIF
```

### Delete from a linked list

```pseudocode
// Delete the node holding TargetValue (with a PreviousPointer trailing behind)
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
        Head ← CurrentPointer.Next          // deleting the head node
    ELSE
        PreviousPointer.Next ← CurrentPointer.Next   // bypass the node
    ENDIF
ENDIF
```

The node to delete is bypassed: the previous node's `Next` is repointed straight at the node *after* the deleted one. Deleting the head node is a special case, handled by moving `Head` along.

## 6. The graph as an ADT

A **graph** is an abstract data type consisting of a set of **vertices** (nodes) and a set of **edges** that connect pairs of vertices. Its key features are:

- **Vertices** hold values; **edges** model a relationship between two vertices.
- An edge may be **directed** (one-way) or **undirected** (two-way).
- An edge may carry a **weight** (a cost, distance, or capacity), giving a **weighted graph**.
- A graph has **no fixed entry point** and **no fixed traversal order**; unlike a tree, it may contain cycles and any vertex may connect to any other.

**Justifying a graph for a given situation.** Use a graph wherever the problem is fundamentally about *connections* or *routes* between things, rather than about a sequence or a hierarchy. A road or rail network is a graph: towns are vertices, roads are weighted edges, and the task (shortest route) is meaningless without the connection structure. A social network is a graph: people are vertices and friendships are undirected edges. A web of web pages with hyperlinks is a directed graph. A binary search tree or an array would not model these, because there is no single root and no fixed parent-child order - the data is a network. You are not required to write code for a graph structure, only to describe it and justify its use.

## 7. Implementing ADTs from built-in types or other ADTs

An ADT defines behaviour; the storage that backs it is a separate choice. Because an ADT only exposes its operations, one ADT can be **implemented on top of another ADT**, or directly on top of a built-in type such as an array or record. The implementing structure simply has to honour the operations and the ordering rule.

| ADT | Can be implemented from | Why it works |
|---|---|---|
| **Stack** | a 1D array, or a linked list | Both can add and remove at one end (LIFO). |
| **Queue** | a 1D array (circular), or a linked list | Both can add at one end and remove at the other (FIFO). |
| **Linked list** | two parallel arrays (data + next-pointer), or a dynamic array of records | The `Next` values recreate the pointer chain. |
| **Dictionary** | a hash table, or an array of (key, value) records, or a binary search tree | Maps keys to values by hashing, search, or comparison. |
| **Binary tree** | a 1D array (`Data[i]`, children at `2i` and `2i+1`), or a linked structure of records with two child pointers | Either stores nodes positionally or chains them with pointers. |

The point is flexibility: if you already have a working linked list, you can build a stack by always inserting and removing at the head, with no new storage code. If you only have arrays, you can still build any of the five ADTs above by choosing the right pointer scheme.

## 8. Recursion

**Recursion** is when a subroutine (a function or procedure) calls itself to solve a smaller instance of the same problem. The essential features are three:

1. **A base case** - a condition that stops the recursion and returns a value directly, without another recursive call. Without it the routine never ends.
2. **A recursive case** - the routine calls itself with a smaller or simpler argument.
3. **Convergence** - every recursive call must move towards the base case, so the chain of calls is guaranteed to terminate.

If a routine calls itself but never gets closer to a base case, it recurses forever and the call stack overflows.

**How recursion is expressed in a language.** A recursive function is written exactly like any other function; the recursion is just an `IF` that either returns the base value or returns `f(smaller argument)`. The language supplies the machinery - each call gets its own set of local variables and parameters on a call stack, and results pass back as the calls unwind.

### Worked example: factorial

$$n! = n \times (n-1)!, \quad 0! = 1$$

```pseudocode
FUNCTION Factorial(N : INTEGER) RETURNS INTEGER
    IF N = 0 THEN
        RETURN 1                    // base case
    ELSE
        RETURN N * Factorial(N - 1) // recursive case
    ENDIF
ENDFUNCTION
```

Call-stack trace for `Factorial(3)`. Each call pushes a frame and waits for the call it made to return; the frames then unwind in reverse order.

```text
Call Factorial(3)
  N = 3, not base case, needs 3 * Factorial(2)      [push frame 3]
    Call Factorial(2)
      N = 2, not base case, needs 2 * Factorial(1)  [push frame 2]
        Call Factorial(1)
          N = 1, not base case, needs 1 * Factorial(0)  [push frame 1]
            Call Factorial(0)
              N = 0, base case, RETURN 1            [frame 0 returns]
          1 * 1 = 1, RETURN 1                       [frame 1 unwinds]
      2 * 1 = 2, RETURN 2                           [frame 2 unwinds]
  3 * 2 = 6, RETURN 6                               [frame 3 unwinds]
Result: 6
```

Notice the stack grows to its deepest at `Factorial(0)` and shrinks as each frame multiplies and returns.

### When recursion is beneficial

Recursion suits problems whose definition is naturally self-similar: tree and graph traversal (a subtree is itself a tree), divide-and-conquer sorts and searches (work on each half), and mathematical definitions like factorial, Fibonacci, or greatest common divisor. It is beneficial when the recursive version is clearly shorter and closer to the problem's definition than an iterative loop with an explicit stack would be. It is a poor choice when the recursion depth could be large (stack overflow) or when a simple loop does the same job, because each recursive call costs a frame of memory.

## 9. How a compiler translates recursion

A compiler does not need special "recursive" instructions; it uses the ordinary **call stack** that every subroutine call already uses. When a function is called, the compiler generates code to:

1. Evaluate the arguments.
2. **Push a stack frame** holding the return address, the parameters, and the function's local variables.
3. Jump to the function's code.

For a recursive call this happens again and again: each call gets its *own* frame with its *own* copy of `N`, so the variable `N` in one frame is not disturbed by the recursive call that uses a different `N`. The frames accumulate while the recursion goes deeper.

When a frame eventually hits the base case and returns, the return value is passed back to the frame that called it, and that frame is **popped**. Control returns to the calling frame, which continues from where it left off. This popping of frames, in reverse order, is called **unwinding** the stack. So the line `RETURN N * Factorial(N - 1)` means: call `Factorial(N - 1)`, push a frame and wait; when it returns, multiply its result by `N`, then return *that*. The stack is what lets each call remember where it was and what to do with the result.

## Worked-Thinking Routine

1. For a search question, first check whether the data is sorted: if yes and direct access exists, binary search is available; otherwise use linear search.
2. For a sort question, choose insertion or bubble, then trace one full pass on paper listing the array after each comparison before committing to pseudocode.
3. For a Big O question, count the nested loops: $k$ nested passes over $n$ give $O(n^k)$; a halving pattern gives $O(\log n)$.
4. For an ADT operation, name the ordering rule (LIFO, FIFO, pointer chain, BST comparison), draw the before-and-after pointer state, then write the pseudocode from the drawing.
5. For a recursion question, write the base case first, then the recursive case, then trace the call stack pushing frames down and unwinding results back up.

## Common Mistakes

- Applying binary search to unsorted data, or to a structure without direct access (a plain linked list).
- Running a bubble sort inner loop to the upper bound instead of `Upper - 1`, which reads past the end.
- Forgetting the `Swapped` flag in bubble sort, so it always does all passes even when already sorted.
- Confusing which end a stack or queue uses: a stack pushes and pops at the top only; a queue enqueues at the rear and dequeues from the front.
- Writing a recursive routine with no base case, or with a recursive case that does not converge to the base case.
- Tracing recursion only downwards: you must also unwind the stack, multiplying results back up.
- Treating an ADT as identical to one implementation. The ADT is the behaviour; the array or linked list is just one way to store it.
- Stating Big O as an exact count of operations rather than the order of growth.

## Quick Self-Check

You are ready to move on when you can answer these without notes.

1. State the three conditions that must hold before a binary search can be used.
2. Write a linear search and trace it looking for `4` in `[2, 7, 4, 9]`.
3. Write a binary search and trace it looking for `7` in sorted `[1, 3, 5, 7, 9]`.
4. How many worst-case comparisons does binary search make on 1 000 items? On 1 000 000?
5. Write a bubble sort and an insertion sort, and state each one's best and worst case.
6. Trace one bubble-sort pass on `[5, 3, 8, 1]`.
7. Give the time and space complexity of all four algorithms in a comparison table.
8. Write pseudocode to find a value in a linked list and to insert a node after a given node.
9. Write pseudocode for push, pop, enqueue, and dequeue, including overflow / underflow checks.
10. Describe the key features of a graph and justify its use for a road network.
11. For each of stack, queue, linked list, dictionary, and binary tree, name a structure it can be built from.
12. State the three essential features of recursion and trace `Factorial(3)` on the call stack.
13. Explain what a compiler pushes onto the stack for each recursive call and what "unwinding" means.

## Connections

- [Algorithm Design and Problem-solving](../09%20Algorithm%20Design%20and%20Problem-solving/00%20Overview.md) is the AS foundation this topic extends - abstraction, decomposition, the three constructs, and the pseudocode notation all come from there.
- [Data Types and Structures](../10%20Data%20Types%20and%20Structures/00%20Overview.md) defines the ADTs (stack, queue, linked list) and their array implementations; this topic turns their operations into full algorithms.

## Study Sequence

1. Read sections 1 and 2, then hand-trace a linear and a binary search on a six-element array until the difference in comparisons is obvious.
2. Memorise the binary-search conditions before writing its pseudocode.
3. Work through section 3, tracing one full pass of each sort on the same array.
4. Learn the Big O table in section 4 and practise justifying each entry from the loop structure.
5. For section 5, write each ADT operation from a pointer drawing rather than from memory.
6. Skim sections 6 and 7 for the descriptive content; be ready to justify a graph and to name what each ADT can be built from.
7. For section 8, trace `Factorial(4)` on the call stack on paper, pushing and then unwinding every frame.
8. Self-check against the questions above before moving on to further programming.
