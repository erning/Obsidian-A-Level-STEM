---
title: Data Types and Structures Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[Data Types and Structures](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - solutions
---

# Data Types and Structures Key Practice Solutions

Full solutions to the [Key Practice Problems](30%20Key%20Practice%20Problems.md) for AS section 10. Pseudocode follows the CAIE 9618 Pseudocode Guide, including the assignment arrow ←.

## A. Data types and records

**1.** Data types for the vet surgery fields:

| Field | Data type | Justification |
|---|---|---|
| Pet name | STRING | Variable length text |
| Owner name | STRING | Variable length text |
| Age in months | INTEGER | Whole number |
| Weight in kilograms | REAL | May have a decimal part |
| Species | CHAR | Single letter |
| Date of last visit | DATE | Calendar date |
| Vaccinated | BOOLEAN | Two states only |

**2.**

```pseudocode
TYPE Employee
    DECLARE Name : STRING
    DECLARE HoursWorked : INTEGER
    DECLARE HourlyRate : REAL
ENDTYPE

DECLARE Worker : Employee
DECLARE Pay : REAL

INPUT Worker.Name
INPUT Worker.HoursWorked
INPUT Worker.HourlyRate

Pay ← Worker.HoursWorked * Worker.HourlyRate
OUTPUT Worker.Name, Pay
```

**3.** A record keeps related fields together under one name, so they can be passed to a procedure as a single unit. It also allows an array of records to store many entities cleanly, instead of several parallel arrays that must be kept in step.

**4.**

```pseudocode
TYPE Product
    DECLARE Code : INTEGER
    DECLARE Name : STRING
    DECLARE Price : REAL
    DECLARE InStock : BOOLEAN
ENDTYPE

DECLARE Item : Product

Item.Code    ← 101
Item.Name    ← "Pen"
Item.Price   ← 1.50
Item.InStock ← TRUE

IF Item.InStock = TRUE THEN
    OUTPUT Item.Code, Item.Name, Item.Price
ENDIF
```

**5.** A DATE type allows date arithmetic, such as finding the difference between two dates or checking chronological order. A STRING cannot do this reliably because string comparison depends on the text format rather than the actual date.

## B. Arrays

**6.**

```pseudocode
DECLARE Temperatures : ARRAY[1:7] OF REAL
DECLARE Day : INTEGER
DECLARE Highest : REAL

FOR Day ← 1 TO 7
    INPUT Temperatures[Day]
NEXT Day

Highest ← Temperatures[1]
FOR Day ← 2 TO 7
    IF Temperatures[Day] > Highest THEN
        Highest ← Temperatures[Day]
    ENDIF
NEXT Day

OUTPUT "Highest temperature: ", Highest
```

The accumulator `Highest` is seeded with the first element, then every later element is compared against it.

**7.**

```pseudocode
DECLARE Scores : ARRAY[1:20] OF INTEGER
DECLARE i : INTEGER
DECLARE Count : INTEGER

Count ← 0
FOR i ← 1 TO 20
    INPUT Scores[i]
    IF Scores[i] >= 50 THEN
        Count ← Count + 1
    ENDIF
NEXT i

OUTPUT "Marks at or above 50: ", Count
```

**8.**

```pseudocode
DECLARE Grid : ARRAY[1:4, 1:5] OF INTEGER
DECLARE Row : INTEGER
DECLARE Col : INTEGER

FOR Row ← 1 TO 4
    FOR Col ← 1 TO 5
        INPUT Grid[Row, Col]
    NEXT Col
NEXT Row
```

The outer loop moves down the rows and the inner loop moves across the columns of each row.

**9.**

```pseudocode
DECLARE Marks : ARRAY[1:30, 1:6] OF INTEGER
DECLARE Student : INTEGER
DECLARE Test : INTEGER
DECLARE Total : INTEGER
DECLARE Average : REAL

FOR Student ← 1 TO 30
    Total ← 0
    FOR Test ← 1 TO 6
        INPUT Marks[Student, Test]
        Total ← Total + Marks[Student, Test]
    NEXT Test
    Average ← Total / 6
    OUTPUT "Student ", Student, " average: ", Average
NEXT Student
```

**10.**

```pseudocode
DECLARE Seats : ARRAY[1:10, 1:20] OF BOOLEAN
DECLARE Row : INTEGER
DECLARE Col : INTEGER
DECLARE Booked : INTEGER

Booked ← 0
FOR Row ← 1 TO 10
    FOR Col ← 1 TO 20
        IF Seats[Row, Col] = TRUE THEN
            Booked ← Booked + 1
        ENDIF
    NEXT Col
NEXT Row

OUTPUT "Booked seats: ", Booked
```

## C. Sorting, searching and files

**11.** First pass of bubble sort on `[3, 7, 1, 9, 4]`, ascending:

| i | Compare | Swap? | Array after step |
|---|---|---|---|
| 1 | 3 and 7 | No | 3, 7, 1, 9, 4 |
| 2 | 7 and 1 | Yes | 3, 1, 7, 9, 4 |
| 3 | 7 and 9 | No | 3, 1, 7, 9, 4 |
| 4 | 9 and 4 | Yes | 3, 1, 7, 4, 9 |

After the first pass the largest value, 9, is in its final position at the end.

**12.**

```pseudocode
DECLARE A : ARRAY[1:10] OF INTEGER
DECLARE i : INTEGER
DECLARE j : INTEGER
DECLARE Temp : INTEGER
DECLARE Swapped : BOOLEAN

FOR i ← 1 TO 9
    Swapped ← FALSE
    FOR j ← 1 TO 10 - i
        IF A[j] < A[j + 1] THEN
            Temp     ← A[j]
            A[j]     ← A[j + 1]
            A[j + 1] ← Temp
            Swapped  ← TRUE
        ENDIF
    NEXT j
    IF Swapped = FALSE THEN
        // no swaps means the array is already sorted
        i ← 9
    ENDIF
NEXT i
```

The comparison uses `<` so larger values move towards the front, giving descending order. In the worst case the array is in reverse order and 9 passes are needed for 10 elements.

**13.** Linear search for `2` in `[6, 1, 4, 9, 2]`:

| Iteration | Index | B[Index] | Found |
|---|---|---|---|
| 1 | 1 | 6 | FALSE |
| 2 | 2 | 1 | FALSE |
| 3 | 3 | 4 | FALSE |
| 4 | 4 | 9 | FALSE |
| 5 | 5 | 2 | TRUE |

The value is found at index 5.

**14.**

```pseudocode
DECLARE Data : ARRAY[1:50] OF INTEGER
DECLARE Target : INTEGER
DECLARE Index : INTEGER
DECLARE Found : BOOLEAN

Found ← FALSE
Index ← 1
INPUT Target

WHILE Found = FALSE AND Index <= 50
    IF Data[Index] = Target THEN
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

The loop guard checks both that the value has not been found and that the index is still in range, so the search stops cleanly in either case.

**15.**

```pseudocode
DECLARE Figure : REAL
DECLARE Total : REAL

Total ← 0
OPENFILE "sales.txt" FOR READ

WHILE NOT EOF("sales.txt")
    READFILE "sales.txt", Figure
    Total ← Total + Figure
ENDWHILE

CLOSEFILE "sales.txt"
OUTPUT "Total sales: ", Total
```

The `EOF` function returns TRUE when the file pointer has reached the end of the file, so `WHILE NOT EOF(...)` reads every line and stops cleanly without reading past the end.

**16.**

```pseudocode
OPENFILE "days.txt" FOR WRITE
WRITEFILE "days.txt", "Monday"
WRITEFILE "days.txt", "Tuesday"
WRITEFILE "days.txt", "Wednesday"
CLOSEFILE "days.txt"
```

Each `WRITEFILE` call writes its data on a new line of the file.

## D. Abstract data types

**17.** A queue is a first-in-first-out (FIFO) structure. Items are added at one end, called the rear or tail, and removed from the other end, called the front or head. The item that has been in the queue the longest is always the next one removed.

**18.**

```pseudocode
DECLARE Stack : ARRAY[1:50] OF INTEGER
DECLARE Top : INTEGER
DECLARE Item : INTEGER

IF Top = 0 THEN
    OUTPUT "Stack is empty"
ELSE
    Item ← Stack[Top]
    Top  ← Top - 1
    OUTPUT Item
ENDIF
```

`Top = 0` means the stack is empty, so no item can be removed. Otherwise the value at `Top` is taken and `Top` is decremented, preserving the LIFO rule.

**19.** An array stores elements in contiguous memory, so inserting or deleting in the middle means shifting every later element, which is slow. A linked list stores each item in a node with a pointer to the next node, so insertion or deletion only requires updating the relevant pointers, leaving the other nodes in place. For a list that changes frequently in the middle, the linked list is therefore more efficient.

**20.** A queue can be implemented using a 1D array with two pointers, `Front` and `Rear`. On enqueue, the new item is placed at the position given by `Rear` and `Rear` is incremented by 1. On dequeue, the item at `Front` is taken and `Front` is incremented by 1. The queue is empty when `Front > Rear`. In practice the array is often treated as circular so that, when `Rear` reaches the upper bound, it wraps back to the lower bound, reusing the space freed at the front by earlier dequeues.
