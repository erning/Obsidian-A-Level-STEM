---
title: Data Types and Structures Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[Data Types and Structures](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - worked-examples
---

# Data Types and Structures Worked Examples

This page steps through eight worked examples that cover the AS section 10 data types and structures. Each example follows the same pattern: a prompt in CAIE style, a full pseudocode solution, and a short check of the key points to remember in an exam.

## Source Route

Worked from the CAIE 9618 Pseudocode Guide and the AS Level syllabus statements for section 10. All pseudocode uses the official notation, including the assignment arrow ←.

## Example 1: Choosing data types

**Prompt.** A college stores the following data for each student: full name, age in years, average grade as a percentage, gender recorded as a single letter, date of birth, and whether fees have been paid. Choose an appropriate data type for each field and justify each choice.

**Solution.**

| Field | Data type | Justification |
|---|---|---|
| Full name | STRING | Text of variable length |
| Age in years | INTEGER | Whole number, no decimal needed |
| Average grade | REAL | Percentage may have a decimal part |
| Gender | CHAR | Single character, M or F |
| Date of birth | DATE | Calendar date, handled as a date type |
| Fees paid | BOOLEAN | Only two states, paid or not paid |

**Check.** INTEGER is used where values are whole numbers and REAL where a decimal part is possible. BOOLEAN is reserved for true or false fields, never for 0 or 1 stored as numbers.

## Example 2: Defining and using a record

**Prompt.** Define a record type `Book` with fields `Title`, `Author`, `Year` and `Price`. Declare a variable of this type, assign values to all fields, and output the values.

**Solution.**

```pseudocode
TYPE Book
    DECLARE Title : STRING
    DECLARE Author : STRING
    DECLARE Year : INTEGER
    DECLARE Price : REAL
ENDTYPE

DECLARE MyBook : Book

MyBook.Title  ← "Computer Science"
MyBook.Author ← "Smith"
MyBook.Year   ← 2020
MyBook.Price  ← 39.99

OUTPUT MyBook.Title, MyBook.Author, MyBook.Year, MyBook.Price
```

**Check.** The record is declared with `TYPE...ENDTYPE`. Each field has its own data type and is accessed using dot notation, `RecordName.FieldName`. Reading a field back uses the same syntax: `INPUT MyBook.Title` would work just as well as assignment.

## Example 3: Processing a 1D array

**Prompt.** Declare an array `Numbers` that can hold 10 integers. Populate it from input and compute the total of all values stored.

**Solution.**

```pseudocode
DECLARE Numbers : ARRAY[1:10] OF INTEGER
DECLARE Total : INTEGER
DECLARE Index : INTEGER

Total ← 0
FOR Index ← 1 TO 10
    INPUT Numbers[Index]
    Total ← Total + Numbers[Index]
NEXT Index

OUTPUT "Total is ", Total
```

**Check.** The bounds `1:10` give valid indices 1 to 10 inclusive. The loop variable is used as the index, so each element is visited exactly once. The accumulator `Total` is initialised to 0 before the loop.

## Example 4: Processing a 2D array

**Prompt.** A 2D array `Sales[1:5, 1:4]` stores the sales, in dollars, for 5 shops across 4 weeks. Write pseudocode to compute and output the total sales for shop 3.

**Solution.**

```pseudocode
DECLARE Sales : ARRAY[1:5, 1:4] OF REAL
DECLARE Shop3Total : REAL
DECLARE Week : INTEGER

Shop3Total ← 0
FOR Week ← 1 TO 4
    Shop3Total ← Shop3Total + Sales[3, Week]
NEXT Week

OUTPUT "Shop 3 total is ", Shop3Total
```

**Check.** The first index fixes the shop at 3 while the second index varies across the weeks. 2D arrays use `Array[Row, Column]` notation, and the chosen data type REAL suits money values.

## Example 5: Bubble sort with a trace

**Prompt.** The array `A` holds the values `[5, 2, 8, 1]` in indices 1 to 4. Trace the first pass of a bubble sort that arranges the values into ascending order, showing the array after each comparison.

**Solution.**

```pseudocode
DECLARE A : ARRAY[1:4] OF INTEGER
DECLARE Temp : INTEGER
DECLARE i : INTEGER

// First pass only, for n = 4 elements, compares indices 1 to 3
FOR i ← 1 TO 3
    IF A[i] > A[i + 1] THEN
        Temp   ← A[i]
        A[i]   ← A[i + 1]
        A[i+1] ← Temp
    ENDIF
NEXT i
```

Trace of the first pass:

| Step | i | Compare | Swap? | Array after step |
|---|---|---|---|---|
| 1 | 1 | 5 and 2 | Yes | 2, 5, 8, 1 |
| 2 | 2 | 5 and 8 | No | 2, 5, 8, 1 |
| 3 | 3 | 8 and 1 | Yes | 2, 5, 1, 8 |

After the first pass the largest value, 8, has bubbled to the last position. The full sort would repeat this pass, reducing the range each time, until no swaps occur in a pass.

**Check.** A bubble sort compares adjacent pairs and swaps them if they are in the wrong order. After pass `k`, the last `k` elements are in their final positions, so the inner loop range can shrink each pass.

## Example 6: Linear search with a trace

**Prompt.** Using a linear search, find the value `8` in the array `[5, 2, 8, 1]`. Trace each comparison and state the index returned.

**Solution.**

```pseudocode
DECLARE A : ARRAY[1:4] OF INTEGER
DECLARE Found : BOOLEAN
DECLARE Index : INTEGER
DECLARE Target : INTEGER

Target ← 8
Found ← FALSE
Index ← 1

WHILE Found = FALSE AND Index <= 4
    IF A[Index] = Target THEN
        Found ← TRUE
    ELSE
        Index ← Index + 1
    ENDIF
ENDWHILE

IF Found = TRUE THEN
    OUTPUT "Found at index ", Index
ELSE
    OUTPUT "Not found"
ENDIF
```

Trace:

| Iteration | Index | A[Index] | Target | Found |
|---|---|---|---|---|
| 1 | 1 | 5 | 8 | FALSE |
| 2 | 2 | 2 | 8 | FALSE |
| 3 | 3 | 8 | 8 | TRUE |

The search stops at index 3 and outputs `Found at index 3`.

**Check.** A linear search checks each element in turn from the first index. It works on unsorted data and stops as soon as the target is found. If the loop ends with `Found = FALSE`, the value is not present.

## Example 7: Reading a text file until EOF

**Prompt.** A text file `data.txt` contains an unknown number of lines. Write pseudocode to read every line, count them, and output the count.

**Solution.**

```pseudocode
DECLARE Line : STRING
DECLARE LineCount : INTEGER

LineCount ← 0
OPENFILE "data.txt" FOR READ

WHILE NOT EOF("data.txt")
    READFILE "data.txt", Line
    LineCount ← LineCount + 1
ENDWHILE

CLOSEFILE "data.txt"
OUTPUT "Number of lines: ", LineCount
```

**Check.** The file is opened for `READ` before any reading and closed after. The `EOF` function returns TRUE when the end of the file is reached, so `WHILE NOT EOF(...)` processes every line. `READFILE` reads one line at a time into the variable `Line`.

## Example 8: Array implementation of a stack

**Prompt.** Describe how a stack can be implemented using a 1D array, and write pseudocode for a `Push` operation that adds a value provided by the user.

**Solution.**

A stack is a last-in-first-out (LIFO) structure. Using an array, a pointer variable `Top` records the index of the most recently added item. `Push` increments `Top` and stores the new item at that position. `Pop` returns the item at `Top` and then decrements `Top`. The stack is empty when `Top = 0` and full when `Top` equals the upper bound of the array.

```pseudocode
DECLARE Stack : ARRAY[1:100] OF INTEGER
DECLARE Top : INTEGER
DECLARE NewItem : INTEGER

Top ← 0
INPUT NewItem

IF Top = 100 THEN
    OUTPUT "Stack is full"
ELSE
    Top ← Top + 1
    Stack[Top] ← NewItem
ENDIF
```

**Check.** The pointer `Top` must be checked against the array bounds before any push or pop. The LIFO rule is enforced because `Push` always adds at `Top + 1` and `Pop` always removes from `Top`, so the most recent item is always the first one taken off.
