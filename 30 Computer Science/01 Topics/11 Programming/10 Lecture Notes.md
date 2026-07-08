---
title: Programming Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/11 Programming/00 Overview|Programming]]"
status: active
tags:
  - computerscience/programming
  - lecture-notes
---

# Programming Lecture Notes

These notes cover **section 11 Programming** of the 9618 AS syllabus, examined in **Paper 2**. The aim is fluency in the official Pseudocode Guide notation: writing constants, variables, expressions, control structures, procedures and functions from a design. Every example below uses that notation exactly, including the assignment arrow `←`.

## Source Route

- Syllabus 11.1 Programming Basics - declaration, assignment, expressions, input/output, built-in functions.
- Syllabus 11.2 Constructs - `IF`, `CASE`, the three loop types, and when each is best.
- Syllabus 11.3 Structured Programming - procedures, functions, parameters and the vocabulary that examiners expect.

## 1. Constants and variables

A **constant** is a named value that never changes while the program runs; declare it once with `CONSTANT`. A **variable** is a named storage location whose value can change; declare its name and type with `DECLARE`. Both are *declarations* - they tell the reader and the compiler what exists. Use the assignment arrow `←` to give a value to a variable.

```pseudocode
CONSTANT Pi = 3.14159
CONSTANT MaxTries = 3

DECLARE Radius : REAL
DECLARE Area : REAL
DECLARE Count : INTEGER

Radius ← 5.0
Area ← Pi * Radius * Radius
Count ← 0
```

> Initialise every variable before you use it. Reading an uninitialised variable is a classic mark-losing fault.

## 2. Expressions and operators

An expression combines values and operators to produce a result. Operator **precedence** decides the order of evaluation; use parentheses to make intent obvious and to override default precedence.

| Category | Operators | Notes |
|----------|-----------|-------|
| Arithmetic | `+  -  *  /` | `/` is real division |
| Integer arithmetic | `DIV  MOD` | `DIV` integer quotient, `MOD` remainder |
| Relational | `=  <>  >  <  >=  <=` | produce `TRUE`/`FALSE` |
| Logic | `AND  OR  NOT` | combine boolean results |

Higher rows bind more tightly than lower rows; within a row the normal left-to-right rules apply. `DIV`, `MOD` and `*` outrank `+` and `-`, which in turn outrank relational and logical operators.

```pseudocode
DECLARE Total, N, Remainder : INTEGER
DECLARE Average : REAL
DECLARE Pass : BOOLEAN

Total ← 17
N ← 5
Average ← Total / N          // 3.4, real division
Remainder ← Total MOD N      // 2
Pass ← (Total >= 10) AND (Remainder = 2)   // TRUE
```

## 3. Input and output

`INPUT` reads a value from the keyboard into a variable; `OUTPUT` prints values and text to the console. Output a clear prompt *before* `INPUT` so the user knows what to type.

```pseudocode
OUTPUT "Enter your name: "
INPUT Name
OUTPUT "Hello, ", Name
```

## 4. Built-in functions and library routines

You may use built-in functions and library routines directly. Any routine **not** in the Pseudocode Guide will be defined for you in the question, and **string-manipulation functions are always supplied**, so you never invent them - call what the paper gives you and apply it exactly as specified.

```pseudocode
DECLARE Index : INTEGER
DECLARE Letter : CHAR

Index ← LENGTH(Name)         // supplied function
Letter ← UCASE(Name[0])      // supplied function
```

## 5. Constructs

### 5.1 Selection - IF with ELSE and nested IF

`IF ... THEN ... ELSE ... ENDIF` chooses between alternatives. Nest `IF` statements inside the branches to test conditions in sequence.

```pseudocode
IF Score >= 80 THEN
    OUTPUT "A"
ELSE
    IF Score >= 60 THEN
        OUTPUT "B"
    ELSE
        OUTPUT "C"
    ENDIF
ENDIF
```

### 5.2 Selection - CASE

`CASE OF <id>` dispatches on the value of one expression. Each path lists a value (or values) followed by the action; an `OTHERWISE` clause catches anything unmatched.

```pseudocode
CASE OF Day
    1    : OUTPUT "Monday"
    2    : OUTPUT "Tuesday"
    3, 4 : OUTPUT "Midweek"
    OTHERWISE OUTPUT "Other"
ENDCASE
```

### 5.3 Count-controlled loop - FOR

Use `FOR` when the number of repetitions is known in advance and driven by a counter. The counter takes each value from `v1` to `v2` inclusive.

```pseudocode
FOR i ← 1 TO 10
    OUTPUT i, " squared is ", i * i
NEXT i
```

### 5.4 Post-condition loop - REPEAT

`REPEAT ... UNTIL <cond>` runs the body **first**, then tests the condition; it repeats while the condition is `FALSE` and stops when it becomes `TRUE`. The body always executes at least once.

```pseudocode
REPEAT
    OUTPUT "Enter a positive number: "
    INPUT Value
UNTIL Value > 0
```

### 5.5 Pre-condition loop - WHILE

`WHILE <cond> ... ENDWHILE` tests the condition **before** the body and repeats while it is `TRUE`. If the condition is `FALSE` from the start, the body never runs.

```pseudocode
WHILE Total < Target
    Total ← Total + Next
    INPUT Next
ENDWHILE
```

### 5.6 Choosing a loop

| Loop | Condition tested | Body runs when | Minimum executions | Best for |
|------|------------------|----------------|--------------------|----------|
| `FOR ... NEXT` | counter bounds | count known in advance | 0 (if `v1 > v2`) | fixed, count-driven repetition |
| `REPEAT ... UNTIL` | after the body | repeat while `FALSE` | 1 | work must happen at least once |
| `WHILE ... ENDWHILE` | before the body | repeat while `TRUE` | 0 | may need zero iterations |

> Use `FOR` when the count is fixed; use `WHILE` when you may loop zero times; use `REPEAT` when the body must run at least once before a condition can be tested.

## 6. Procedures

A **procedure** is a named block of code that performs a task and is invoked with `CALL`. Use a procedure to avoid repeating a block of statements and to give a clear name to one piece of work. Parameters pass data in; they may be **by value** (a copy, the default) or **by reference** (`BYREF`, so changes inside affect the caller's variable).

```pseudocode
PROCEDURE Swap(BYREF A : INTEGER, BYREF B : INTEGER)
    DECLARE Temp : INTEGER
    Temp ← A
    A ← B
    B ← Temp
ENDPROCEDURE

CALL Swap(X, Y)   // X and Y now hold each other's values
```

`Swap` must use `BYREF`: by-value parameters would swap copies and leave the originals unchanged.

## 7. Functions

A **function** is a named block that **returns a single value** through `RETURN`. Because it yields a value, a function is **used inside an expression** - the call is replaced by its return value. Use a function (not a procedure) whenever the point of the block is to compute and give back one result.

```pseudocode
FUNCTION Larger(A : INTEGER, B : INTEGER) RETURNS INTEGER
    IF A > B THEN
        RETURN A
    ELSE
        RETURN B
    ENDIF
ENDFUNCTION

Biggest ← Larger(Larger(First, Second), Third)   // used in an expression
```

Here `Larger(...)` is evaluated and its result substituted, so `Larger(Larger(First, Second), Third)` finds the largest of three values.

## 8. Terminology

| Term | Meaning |
|------|---------|
| Header (procedure/function) | the first line: name, parameters and (for functions) return type |
| Interface | what a caller needs to know to use it: name, parameters and return type |
| Parameter | a variable named in the header that receives a value |
| Argument | the actual value passed in the `CALL` |
| Return value | the single result a function produces via `RETURN` |

## 9. Writing efficient pseudocode

- Use **meaningful identifiers** - `Total` not `T`, `IsValid` not `f`.
- Give each block **one clear purpose**; if a name needs "and", split it.
- **Avoid repetition** - move a repeated block into a procedure or function.
- Initialise before use, and keep nesting shallow where possible.
- Comment a tricky step, not the obvious ones.

## Worked-Thinking Routine

1. Read the design (flowchart or structured English) and list the inputs, outputs and the data each needs.
2. Declare constants and variables with correct types.
3. Translate straight-line steps into assignment and `INPUT`/`OUTPUT`.
4. Branch on conditions with `IF` or `CASE`; pick the loop by asking "how many times?" and "could it be zero?".
5. Wrap repeated logic in a procedure; wrap a computed result in a function.
6. Trace through with sample values to confirm each arrow and condition.

## Common Mistakes

- Writing `<-` or `=` for the assignment arrow `←`.
- Using `=` (assignment) where `=` (comparison) is meant - in pseudocode the same symbol is relational, so assignment must be `←`.
- Forgetting `ENDIF`, `ENDCASE`, `NEXT`, `ENDWHILE`, `ENDPROCEDURE`, `ENDFUNCTION`.
- Declaring a variable inside a loop when it should live outside.
- Using a function as a statement, or a procedure inside an expression.
- Using by-value parameters when the caller's value must change - remember `BYREF`.

## Quick Self-Check

- Declare a `CONSTANT`, a `REAL` variable, and assign `Pi` times the variable to it.
- Write an expression using `DIV` and `MOD` on 23 and 5.
- Rewrite a nested `IF` as a `CASE` where the value is a single integer.
- Choose the best loop for "keep asking until the password is correct".
- Write a `BYREF` procedure that doubles a number.
- Write a function that returns the average of two `REAL` values, and use it in an expression.

## Connections

- [[30 Computer Science/01 Topics/20 Further Programming/00 Overview|Further Programming]]
- [[30 Computer Science/01 Topics/09 Algorithm Design and Problem-solving/00 Overview|Algorithm Design and Problem-solving]]
- [[30 Computer Science/04 Reference/Pseudocode and Programming Reference|Pseudocode and Programming Reference]]

## Study Sequence

1. Read sections 1–4 and write each example by hand.
2. Master the three loops and justify the choice for five short scenarios.
3. Convert a straight-line script into one using a procedure and a function.
4. Do past-paper pseudocode questions under timed conditions.
5. Re-attempt any question where you dropped a structural keyword.
