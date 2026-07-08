---
title: Data Types and Structures Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/10 Data Types and Structures/00 Overview|Data Types and Structures]]"
status: active
tags:
  - computerscience/programming
  - lecture-notes
---

# Data Types and Structures Lecture Notes

A program acts on data, and the way that data is grouped decides what the program can do. This topic covers the eight pseudocode data types, the record structure that bundles fields of different types under one identifier, arrays that hold many values of the same type, text files that survive after the program ends, and the first abstract data types - the stack, queue and linked list. All of it is examined in Paper 2, so the pseudocode notation must be fluent and the ADT ideas must be justified, not just memorised.

## Source Route

- Syllabus **9618 AS Section 10 - Data Types and Structures**, examined in **Paper 2**.
- 10.1 Data Types and Records: select INTEGER, REAL, CHAR, STRING, BOOLEAN, DATE, ARRAY, FILE; purpose of a record; pseudocode to define, read and write a record.
- 10.2 Arrays: index, upper and lower bound; choose 1D or 2D; pseudocode to declare and process arrays; bubble sort; linear search.
- 10.3 Files: why files are needed; pseudocode to handle text files line by line.
- 10.4 Introduction to Abstract Data Types (ADT): an ADT is data plus a set of operations; stack, queue and linked list as ADTs; key features and justification; use them to add, edit and delete data (no pseudocode required); how each can be implemented using arrays.

## 1. The eight pseudocode data types

A **data type** fixes the set of values a variable can hold and the operations that make sense on it. Choose the type by asking two questions: *what values are allowed?* and *what operations are needed?* A count is an INTEGER because it can only go up in whole steps; a temperature is REAL because it has a fractional part; a yes/no flag is BOOLEAN because only two values are possible.

| Type | Holds | Example value |
| --- | --- | --- |
| **INTEGER** | A whole number (positive, negative or zero). | `42` |
| **REAL** | A number with a fractional part (floating point). | `3.14` |
| **CHAR** | A single character. | `'A'` |
| **STRING** | A sequence of zero or more characters (text). | `"Hello"` |
| **BOOLEAN** | A truth value - only `TRUE` or `FALSE`. | `TRUE` |
| **DATE** | A calendar date, held as a single logical value (not three integers). | `2026/07/07` |
| **ARRAY** | A fixed-size set of values, all of the *same* type, accessed by index. | `[5, 7, 9]` |
| **FILE** | A named store of data on backing storage that outlives the program. | `scores.txt` |

Two pairs are easily confused. **INTEGER vs REAL**: pick INTEGER when the value is inherently a whole number (a count, an index, a quantity that can never be fractional) and REAL only when a fraction is meaningful (a measurement, a money amount in a context where rounding is acceptable). **CHAR vs STRING**: CHAR holds exactly one character and is compared to `'A'`; STRING holds a run of characters and is compared to `"Apple"` - note the different quotation style in pseudocode. The DATE type matters because it lets the program reason about calendars (order, difference) without manually comparing three separate day/month/year integers.

## 2. Records

A **record** is a structure that holds a set of fields of *different* data types under one identifier. An array cannot do this: every element of an array must be the same type, so a pupil's name (STRING), age (INTEGER) and fee-paid status (BOOLEAN) cannot share one array. A record solves this by giving each field its own type but keeping them together as a single logical unit - one `Pupil` value carries the name, the age and the flag at once.

In CAIE pseudocode a record is defined with `TYPE ... ENDTYPE`, declaring each field with `DECLARE <id> : <type>`. A variable of that record type is then declared normally and its fields are reached with a dot.

```pseudocode
TYPE Pupil
    DECLARE Name : STRING
    DECLARE Age  : INTEGER
    DECLARE FeePaid : BOOLEAN
ENDTYPE

DECLARE CurrentPupil : Pupil
```

Writing to a record means assigning to each field, and reading means using each field in an expression or output. The dot selects the field from the record variable.

```pseudocode
// Save data into the record
CurrentPupil.Name    ← INPUT
CurrentPupil.Age     ← INPUT
CurrentPupil.FeePaid ← INPUT

// Read data out of the record
OUTPUT "Name: ", CurrentPupil.Name
OUTPUT "Age:  ", CurrentPupil.Age
```

A record is the right choice whenever a real-world item has several properties of different types that should travel together. If the properties are all the same type and you need many of them, use an array instead.

## 3. Arrays

An **array** is a data structure that holds a fixed number of values, all of the same type, accessed through an **index**. The **lower bound** and **upper bound** define the range of valid indexes; in CAIE pseudocode the lower bound is usually `1`, so an array declared `ARRAY[1:5]` has indexes `1, 2, 3, 4, 5` and a length of five. Getting the bounds wrong - starting at `0` when the array starts at `1`, or reading one past the end - is the most common array error.

A **one-dimensional (1D) array** is a single list, suitable for a set of values along one axis (a week of temperatures, a class of marks). A **two-dimensional (2D) array** is a grid of rows and columns, suitable for data laid out along two axes (a class of pupils each with several marks, a board of cells). Choose 1D when the data has one logical dimension and 2D when it naturally forms a table.

```pseudocode
// 1D array: five exam marks, indexes 1 to 5
DECLARE Marks : ARRAY[1:5] OF INTEGER

// 2D array: 3 classes (rows), each with 5 marks (columns)
DECLARE Grid : ARRAY[1:3, 1:5] OF INTEGER
```

Processing an array means looping across every valid index. A 1D loop runs one counter from lower to upper bound; a 2D loop nests an inner loop (columns) inside an outer loop (rows), or vice versa.

```pseudocode
// Worked example 1 - sum all marks in a 1D array
DECLARE Total : INTEGER
Total ← 0
FOR Index ← 1 TO 5
    Total ← Total + Marks[Index]
NEXT Index
OUTPUT "Total = ", Total
```

```pseudocode
// Worked example 2 - find the largest mark in a 1D array
DECLARE MaxMark : INTEGER
MaxMark ← Marks[1]
FOR Index ← 2 TO 5
    IF Marks[Index] > MaxMark THEN
        MaxMark ← Marks[Index]
    ENDIF
NEXT Index
OUTPUT "Highest = ", MaxMark
```

```pseudocode
// Worked example 3 - sum column 2 of a 2D array (across all 3 rows)
DECLARE ColTotal : INTEGER
ColTotal ← 0
FOR Row ← 1 TO 3
    ColTotal ← ColTotal + Grid[Row, 2]
NEXT Row
OUTPUT "Column 2 total = ", ColTotal
```

The pattern is always the same: declare the array with explicit bounds, initialise an accumulator or best-so-far before the loop, then loop across every valid index updating it. Always read the first element before the loop when hunting for a maximum, so the search has a value to beat.

## 4. Bubble sort

A **bubble sort** repeatedly compares adjacent pairs of elements and swaps them if they are in the wrong order, so the largest unsorted value "bubbles" to its correct position on each pass. After each pass the sorted region grows by one at the end, and the algorithm stops a pass early when no swaps were made. It is simple but slow - roughly $O(n^2)$ comparisons on $n$ items.

```pseudocode
// Bubble sort: put Marks[1..5] into ascending order
DECLARE Temp : INTEGER
DECLARE Swapped : BOOLEAN

REPEAT
    Swapped ← FALSE
    FOR Index ← 1 TO 4          // compare adjacent pairs 1-2 ... 4-5
        IF Marks[Index] > Marks[Index + 1] THEN
            Temp ← Marks[Index]
            Marks[Index] ← Marks[Index + 1]
            Marks[Index + 1] ← Temp
            Swapped ← TRUE
        ENDIF
    NEXT Index
UNTIL Swapped = FALSE
```

Trace one pass on `[5, 3, 8, 1]`. Compare indexes 1-2: `5 > 3`, swap → `[3, 5, 8, 1]`, swapped = TRUE. Compare 2-3: `5 > 8`? no. Compare 3-4: `8 > 1`, swap → `[3, 5, 1, 8]`, swapped = TRUE. The pass ends with the largest value, `8`, fixed in its final place at the end. Because a swap happened, another pass runs: `3 > 5`? no; `5 > 1`, swap → `[3, 1, 5, 8]`; `5 > 8`? no. Another swap happened, so a third pass runs: `3 > 1`, swap → `[1, 3, 5, 8]`; the rest compare in order. A final pass makes no swaps, so `Swapped` stays FALSE and the sort stops. The inner loop runs to `upper - 1` because each comparison looks at index *and* index + 1; running to the upper bound would read past the end.

## 5. Linear search

A **linear search** examines each element of an array in turn, from the lower bound upwards, until it finds the target or runs out of elements. It works on unsorted data and on any array type; its cost is $O(n)$ in the worst case. The key discipline is to stop the moment the target is found and to report "not found" honestly if the loop ends without a match.

```pseudocode
// Linear search: is TargetValue present in Marks[1..5]?
DECLARE Found : BOOLEAN
DECLARE Index  : INTEGER
DECLARE TargetValue : INTEGER

Found ← FALSE
Index ← 1
TargetValue ← INPUT

WHILE Found = FALSE AND Index <= 5
    IF Marks[Index] = TargetValue THEN
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

Trace a search for `7` in `[5, 3, 8, 1, 7]`. Index 1: `5 = 7`? no → Index 2. Index 2: `3 = 7`? no → Index 3. Index 3: `8 = 7`? no → Index 4. Index 4: `1 = 7`? no → Index 5. Index 5: `7 = 7`? yes → Found = TRUE, stop. Output "Found at position 5". If the target were `9`, the loop would exit when Index became `6` (past the upper bound) with Found still FALSE, producing "Not found". The loop condition guards both conditions: keep going only while you have neither found the item nor run off the end.

## 6. Text files

Programs hold their data in main memory (RAM), which is volatile: when the program ends, or the power is lost, the data disappears. A **file** is needed whenever data must survive - saved between runs, shared with another program, or moved to another machine. Files are stored on backing storage (a disk), which is non-volatile, so a saved score, a configuration setting or a log of results is still there next time.

CAIE pseudocode handles **text files** - files made of one or more lines of characters - with a small, fixed set of commands. A file must be **opened** before use, naming the mode (read, write or append); it is **closed** when finished so the data is flushed and the handle released. While open, `READFILE` pulls in one line at a time, `WRITEFILE` sends out a line, and `EOF` (end-of-file) tests whether there is any more input to read.

| Command | Purpose |
| --- | --- |
| `OPENFILE <filename> FOR READ` | Open an existing file to read from the start. |
| `OPENFILE <filename> FOR WRITE` | Open a file to write from the start (overwrites existing contents). |
| `OPENFILE <filename> FOR APPEND` | Open a file to add lines at the end (keeps existing contents). |
| `READFILE <filename>, <variable>` | Read the next line into the variable. |
| `WRITEFILE <filename>, <data>` | Write a line of data to the file. |
| `EOF(<filename>)` | Returns TRUE when there are no more lines to read. |
| `CLOSEFILE <filename>` | Close the file, flushing and releasing it. |

The standard pattern for reading a whole file is a `WHILE NOT EOF(...)` loop: open for read, then keep reading one line at a time and processing it until there is nothing left, then close.

```pseudocode
// Worked example - read and print every line of pupils.txt until the end
DECLARE ThisLine : STRING

OPENFILE "pupils.txt" FOR READ
WHILE NOT EOF("pupils.txt")
    READFILE "pupils.txt", ThisLine
    OUTPUT ThisLine
ENDWHILE
CLOSEFILE "pupils.txt"
```

To create or replace a file, open it `FOR WRITE` and use `WRITEFILE` for each line; to add to an existing file without losing what is there, open it `FOR APPEND`. The golden rule is that every `OPENFILE` must be matched by a `CLOSEFILE`, and that `READFILE` must be called only while `NOT EOF` is true - reading past the end is undefined.

## 7. Abstract data types (ADTs)

An **abstract data type (ADT)** is a collection of data together with a set of operations that may be performed on that data. The word *abstract* means the user thinks in terms of the operations and their behaviour, not the physical layout: a stack is "last in, first out" regardless of whether it is stored in an array or a linked structure. The stack, the queue and the linked list are the three ADTs named in the syllabus.

| ADT | Ordering rule | Key operations | Typical use |
| --- | --- | --- | --- |
| **Stack** | **LIFO** - last in, first out. Add and remove at the same end (the top). | **push** (add to top), **pop** (remove from top) | Undo/redo, back-button history, call stack, reversing. |
| **Queue** | **FIFO** - first in, first out. Add at one end (rear), remove at the other (front). | **enqueue** (add to rear), **dequeue** (remove from front) | Print spooler, task scheduler, keyboard buffer, ticket line. |
| **Linked list** | No fixed order; each **node** holds data plus a **pointer** to the next node. | **insert**, **delete**, **find** following the pointers | Dynamic lists of unknown size, playlist, undo log, adjacency lists. |

**Justifying a choice** comes down to the ordering rule the task needs. A program's undo feature should use a **stack** because the most recent action must be the first undone - LIFO. A printer queue should use a **queue** because jobs should come out in the order they arrived - FIFO. A list of pupils where items are frequently inserted and deleted in the middle, and whose size is not known in advance, should use a **linked list** because a node can be linked in or unlinked by adjusting pointers, without shifting every later element as an array would.

At AS level you are **not** required to write pseudocode for these structures, but you must be able to describe adding, editing and deleting data in them. For a stack: push adds a new top item, pop removes the current top; you can only ever touch the top. For a queue: enqueue adds at the rear, dequeue removes from the front; the front is the next to leave. For a linked list: to insert a node, set its pointer to the node that previously followed the current node, then repoint the current node at the new one; to delete, repoint the previous node's pointer straight at the node *after* the one being removed, bypassing it. A **head pointer** records where the list starts, and a null pointer marks the end.

### Implementing the ADTs with arrays

Each ADT can be built on top of an ordinary array, using one or more extra variables as pointers into it. This is what "implemented using arrays" means: the array provides the storage, and a pointer variable implements the ADT's discipline.

- **Stack using an array** - declare an array for the data plus an integer **TopOfStack pointer**. Push writes data at `TopOfStack` then increments the pointer; pop decrements the pointer then reads `Data[TopOfStack]`. Both operations happen at one end of the array, which is exactly the LIFO rule. Check the pointer against the bounds before push (stack full) and pop (stack empty).
- **Queue using an array** - declare an array plus two integers, a **front pointer** and a **rear pointer**. Enqueue writes at the rear pointer and advances it; dequeue reads at the front pointer and advances it. Data leaves in the same order it entered, giving FIFO. A real implementation wraps the pointers round to the start when they reach the end (a circular queue) so the array space is reused.
- **Linked list using two arrays** - because a node needs both a data value *and* a pointer to the next node, use **two parallel arrays**: one holds the data (`Data[i]`) and the other holds the corresponding next-pointer (`Next[i]`). Following the list means reading `Data[i]`, then moving to `i = Next[i]`, until the pointer is null. A separate **head pointer** holds the index of the first node; inserting or deleting is just a matter of rewriting values in the `Next` array, leaving the `Data` array untouched.

The point to remember is that an ADT is *not* the same thing as its array implementation. The ADT defines the behaviour (LIFO, FIFO, pointer-chaining); the array is merely one convenient way to provide the storage behind that behaviour.

## Worked-Thinking Routine

1. For a "choose the data type" question, ask what values are allowed and what operations are needed: counting or indexing → INTEGER; measurement with fractions → REAL; single symbol → CHAR; text → STRING; two-state flag → BOOLEAN; calendar value → DATE; many same-type values → ARRAY; persistent storage → FILE.
2. For a record question, list the fields with their types inside `TYPE ... ENDTYPE`, declare a variable of that type, then use the dot to read and write each field.
3. For an array question, write the bounds explicitly (`ARRAY[1:n]` or `ARRAY[1:r, 1:c]`), initialise any accumulator or best-so-far before the loop, and loop across every valid index - never past the upper bound.
4. For a bubble sort question, write the `REPEAT ... UNTIL Swapped = FALSE` outer loop and the `FOR` inner loop to `upper - 1`, swapping adjacent out-of-order pairs; trace one pass by listing the array after each comparison.
5. For a linear search question, set `Found ← FALSE` and `Index` to the lower bound, loop while not found and within bounds, and on exit distinguish the found and not-found cases explicitly.
6. For a file question, match every `OPENFILE` with a `CLOSEFILE`, pick READ/WRITE/APPEND for the job, and guard `READFILE` with `WHILE NOT EOF`.
7. For an ADT question, name the ordering rule (LIFO/FIFO/pointer chain) and the operations, justify the choice by that rule, and describe the array implementation by saying which pointers are kept.

## Common Mistakes

- Using REAL where INTEGER is correct (a count or index can never be fractional) or INTEGER where REAL is needed (a measurement with a fractional part).
- Confusing CHAR (one character, `'A'`) with STRING (text, `"Apple"`).
- Declaring an array but forgetting the bounds, or looping from `0` when the lower bound is `1`, or reading one past the upper bound.
- Running the bubble sort inner loop to the upper bound instead of `upper - 1`, which reads past the end on the last comparison.
- In linear search, forgetting to stop when the item is found, or forgetting to report "not found" when the loop ends.
- Opening a file and never closing it, or calling `READFILE` without guarding it with `EOF`.
- Using `FOR WRITE` when you meant to add to a file - it overwrites. Adding to an existing file needs `FOR APPEND`.
- Treating an ADT as identical to its array implementation. The ADT is the *behaviour*; the array is one way to *store* it.
- Forgetting which end a stack or queue operates on: a stack pushes and pops at the *top* only; a queue enqueues at the *rear* and dequeues from the *front*.
- Describing a linked-list delete without repointing the previous node - the deleted node must be bypassed by rewriting the `Next` value.

## Quick Self-Check

- Name the eight pseudocode data types and give one example value for each.
- Give one reason to choose INTEGER over REAL, and one to choose REAL over INTEGER.
- Distinguish CHAR and STRING with an example of each.
- Write `TYPE ... ENDTYPE` for a record with three fields of different types, and pseudocode to read one field in and write another out.
- Declare a 1D array of five integers and a 2D array of 3 rows by 5 columns, then sum the second column of the 2D array.
- Write a bubble sort for an array of five items and trace one pass on `[4, 1, 3, 2, 5]`.
- Write a linear search and trace it searching for `3` in `[4, 1, 3, 2, 5]`.
- Explain why files are needed and name the three open modes, saying which overwrites and which adds.
- Write pseudocode to read and print every line of a text file until end of file.
- Define an ADT in one sentence, and state the ordering rule and operations of a stack, a queue and a linked list.
- Justify, in one sentence each, why an undo feature uses a stack, a print queue uses a queue, and a dynamic pupil list uses a linked list.
- Describe how to implement a stack, a queue and a linked list using arrays, naming the pointer variable(s) each needs.

## Connections

- [[30 Computer Science/01 Topics/19 Computational Thinking and Problem-solving/00 Overview|Computational Thinking and Problem-solving]] takes the ADTs defined here and turns their operations into full algorithms (push, pop, enqueue, dequeue, traverse).
- [[30 Computer Science/01 Topics/09 Algorithm Design and Problem-solving/00 Overview|Algorithm Design and Problem-solving]] supplies the pseudocode notation and the tracing habits used throughout this note.

## Study Sequence

1. Read this note top to bottom, then close it and write the eight data types and one example of each from memory.
2. Drill record definition: write `TYPE ... ENDTYPE` for a record with three fields of different types and pseudocode to read and write each field.
3. Practise declaring 1D and 2D arrays and processing them - sum a column, find a maximum - until the loop bounds are automatic.
4. Hand-trace a bubble sort and a linear search on a five-element array until each swap and comparison is fluent.
5. Memorise the file command set, then write the read-until-EOF pattern from memory, matching each `OPENFILE` with a `CLOSEFILE`.
6. Learn the three ADTs as ordering-rule-plus-operations, justify each for a named task, and describe its array implementation naming the pointer(s).
7. Finish against the syllabus checklist: tick each "select", "write pseudocode" and "describe" point only when you can do it without notes.
