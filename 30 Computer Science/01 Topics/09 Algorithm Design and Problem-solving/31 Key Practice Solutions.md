---
title: Algorithm Design and Problem-solving Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[Algorithm Design and Problem-solving](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - solutions
---

# Algorithm Design and Problem-solving Key Practice Solutions

This note gives worked solutions for [Algorithm Design and Problem-solving Key Practice Problems](30%20Key%20Practice%20Problems.md). All pseudocode follows the CAIE Pseudocode Guide, including the assignment arrow `←`.

## A. Abstraction and decomposition

### Problem 1

The decision is whether the inserted coins cover the price of the chosen drink. Drop serial number, manufacturer, coin slot diameter, and button layout; none changes the answer.

| Item | Why it is kept |
|---|---|
| Credit (REAL) | The total value of coins inserted so far |
| Price (REAL) | The cost of the selected drink |
| Enough (BOOLEAN) | The result: is the credit at least the price? |

For each real-world detail, ask whether the decision would change if that detail changed. If not, abstraction has correctly removed it.

### Problem 2

The decision is whether the book is overdue. Drop title, author, publisher, year, page count, cover colour, and shelf position.

| Item | Why it is kept |
|---|---|
| BookID (INTEGER) | Identifies the loan |
| DueDate (DATE) | The date by which the book must be returned |
| Today (DATE) | The current date |
| Overdue (BOOLEAN) | The result: is Today later than DueDate? |

### Problem 3

The verbs read, compute, decide, print each become a module.

| Module | Type | Job |
|---|---|---|
| ReadData | Procedure | INPUT the name and five marks |
| CalculateAverage | Function | Return the mean of the five marks |
| DetermineGrade | Function | Return a grade from the average |
| PrintReport | Procedure | OUTPUT the report |

`CalculateAverage` and `DetermineGrade` return a single value, so they are functions. The other two perform actions and return nothing.

| Identifier | Data type | Description |
|---|---|---|
| `Name` | STRING | the student's name |
| `Mark` | ARRAY[1:5] OF REAL | the five subject marks |
| `Average` | REAL | the mean of the five marks |
| `Grade` | CHAR | the grade assigned |

### Problem 4

| Module | Type | Job |
|---|---|---|
| AddItem | Procedure | Add a chosen item to the cart |
| RemoveItem | Procedure | Remove a chosen item from the cart |
| CalculateTotal | Function | Return the sum of item prices in the cart |
| ApplyDiscount | Function | Return the discounted total if a threshold is met |
| PrintReceipt | Procedure | OUTPUT the receipt |

Functions return a single value (the total, the discounted total). Procedures act on the cart and return nothing.

### Problem 5

A **procedure** performs a task and returns no value; it is called as a statement with `CALL`. A **function** performs a task and returns a single value, which replaces the call in an expression. The choice matters because a module that must hand back a result (an average, a grade, a total) has to be a function, or the caller has no way to receive the value. A module that only acts on shared data is naturally a procedure.

## B. Pseudocode basics

### Problem 6

| Identifier | Data type | Description |
|---|---|---|
| `Celsius` | REAL | the input temperature in degrees Celsius |
| `Fahrenheit` | REAL | the converted temperature in degrees Fahrenheit |

### Problem 7

```pseudocode
INPUT Number
IF Number > 0 THEN
    OUTPUT "Positive"
ELSE
    IF Number < 0 THEN
        OUTPUT "Negative"
    ELSE
        OUTPUT "Zero"
    ENDIF
ENDIF
```

The nested `IF` covers the case where the number is neither positive nor negative.

### Problem 8

```pseudocode
Total ← 0
FOR Count ← 1 TO 10
    INPUT Number
    Total ← Total + Number
NEXT Count
OUTPUT "Total is ", Total
```

The count is known (ten), so `FOR` is the natural choice.

### Problem 9

```pseudocode
INPUT Password
WHILE Password <> "Unlock" DO
    OUTPUT "Try again"
    INPUT Password
ENDWHILE
OUTPUT "Unlocked"
```

`WHILE` is used because the test happens before each repetition; the input inside the loop is essential, without it the loop would run forever.

### Problem 10

```pseudocode
Count ← 0
REPEAT
    INPUT Age
    IF Age <> -1 THEN
        Count ← Count + 1
    ENDIF
UNTIL Age = -1
OUTPUT "Counted ", Count, " ages"
```

`REPEAT` is acceptable because the body must run at least once before the test on `Age` makes sense. The inner `IF` prevents the sentinel itself from being counted.

## C. Converting between notations

### Problem 11

```pseudocode
Total ← 0
INPUT Number
WHILE Number <> 0 DO
    Total ← Total + Number
    INPUT Number
ENDWHILE
OUTPUT Total
```

The "while" in the structured English maps to a `WHILE` loop, and the input inside the loop allows the loop to terminate.

### Problem 12

```pseudocode
INPUT Price
IF Price > 100 THEN
    Discount ← Price * 0.1
    Price ← Price - Discount
ENDIF
OUTPUT Price
```

The diamond becomes an `IF` with one branch (no `ELSE`, because the No branch does nothing). Both branches rejoin at the output, which sits after the `ENDIF`.

### Problem 13

1. Start terminator (rounded rectangle): "Start".
2. Input/output symbol (parallelogram): "INPUT Age".
3. Decision symbol (diamond): "Age >= 18 ?" with a Yes branch left and a No branch right.
4. On the Yes branch, an output parallelogram: "OUTPUT 'Adult'".
5. On the No branch, an output parallelogram: "OUTPUT 'Minor'".
6. The two branches rejoin at a single flow line.
7. End terminator (rounded rectangle): "End".

A two-way selection is always one diamond with exactly two outgoing arrows that rejoin after the `ENDIF`.

### Problem 14

Structured English: input two numbers A and B; if A is greater than B, the larger is A, otherwise it is B; output the larger.

Flowchart, described: Start terminator; parallelogram INPUT A, B; diamond "A > B ?" with Yes left and No right; on Yes a process rectangle Larger ← A; on No a process rectangle Larger ← B; the branches rejoin; parallelogram OUTPUT Larger; End terminator.

Pseudocode.

```pseudocode
INPUT A
INPUT B
IF A > B THEN
    Larger ← A
ELSE
    Larger ← B
ENDIF
OUTPUT "Larger is ", Larger
```

### Problem 15

The flowchart represents a **selection** (a two-way decision).

```pseudocode
INPUT Score
IF Score >= 50 THEN
    OUTPUT "Pass"
ELSE
    OUTPUT "Fail"
ENDIF
```

A diamond with one Yes and one No branch always maps to an `IF ... ELSE`.

## D. Refinement and logic

### Problem 16

Level 0 (major steps): (1) read in all the marks; (2) calculate the class average; (3) count how many scored 50 or above; (4) output the results.

Level 1 (refine each step): (1) repeatedly INPUT a mark until the sentinel -1 appears, storing each in an array and counting them; (2) sum every mark in the array, then divide by the count; (3) go through the array again, adding one to a counter for each mark of 50 or above; (4) output the average and the pass count.

Level 2 (pseudocode).

```pseudocode
DECLARE Mark : ARRAY[1:100] OF REAL
DECLARE Count, Index, PassCount : INTEGER
DECLARE Sum, Average, ThisMark : REAL

Count ← 0
INPUT ThisMark
WHILE ThisMark <> -1 DO
    Count ← Count + 1
    Mark[Count] ← ThisMark
    INPUT ThisMark
ENDWHILE

Sum ← 0
FOR Index ← 1 TO Count
    Sum ← Sum + Mark[Index]
NEXT Index
Average ← Sum / Count

PassCount ← 0
FOR Index ← 1 TO Count
    IF Mark[Index] >= 50 THEN
        PassCount ← PassCount + 1
    ENDIF
NEXT Index

OUTPUT "Average = ", Average
OUTPUT "Number passed = ", PassCount
```

### Problem 17

Level 0 (major steps): (1) read 20 numbers into an array; (2) find the smallest value and its first position; (3) output the smallest value and the position.

Level 2 (pseudocode).

```pseudocode
DECLARE Number : ARRAY[1:20] OF REAL
DECLARE Index : INTEGER
DECLARE Smallest : REAL
DECLARE Position : INTEGER

FOR Index ← 1 TO 20
    INPUT Number[Index]
NEXT Index

Smallest ← Number[1]
Position ← 1
FOR Index ← 2 TO 20
    IF Number[Index] < Smallest THEN
        Smallest ← Number[Index]
        Position ← Index
    ENDIF
NEXT Index

OUTPUT "Smallest = ", Smallest
OUTPUT "First at position ", Position
```

Using `<` (strictly less than) rather than `<=` means only the first occurrence of the smallest value is recorded, which matches "the position where it first occurred".

### Problem 18

```pseudocode
IF (Mark >= 50) AND (Attendance > 75) THEN
    OUTPUT "Pass"
ELSE
    OUTPUT "Refer"
ENDIF
```

The parentheses make the grouping explicit.

### Problem 19

```pseudocode
IF (Hour < 9) OR (Hour > 17) THEN
    OUTPUT "Overtime"
ENDIF
```

The two comparisons join with `OR`, because the overtime rate applies when either one is true.

### Problem 20

The two possible groupings are:

1. `((Mark >= 50) AND (Attendance > 75)) OR HasMedical` - passes the academic test, or holds a medical exemption, or both.
2. `(Mark >= 50) AND ((Attendance > 75) OR HasMedical)` - needs at least 50, and either high attendance or a medical exemption.

These give different answers. A student with `Mark = 40`, `Attendance = 50`, and `HasMedical = TRUE` fails under the first grouping but passes under the second. Writing the parentheses explicitly removes the ambiguity, because the default reading `A AND B OR C` is `(A AND B) OR C`, which may not be what the writer intended.
