---
title: Pseudocode and Programming Reference
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/9618
  - reference
---

# Pseudocode and Programming Reference

This reference summarises the pseudocode notation used in CAIE Computer Science 9618 Paper 2, and gives equivalent Paper 4 programming patterns in Java, Visual Basic .NET, and Python. The authoritative source for pseudocode is the [Pseudocode Guide for Teachers 2027-2029](../../assets/syllabus/9618%20-%20Computer%20Science/CAIE%20Computer%20Science%209618%20Pseudocode%20Guide%202027-2029.pdf); this note is a quick lookup.

## Pseudocode Conventions

- Keywords are upper-case (`IF`, `REPEAT`, `PROCEDURE`).
- Identifiers are mixed case (camelCase or PascalCase), for example `NumberOfPlayers`.
- Indentation shows nesting (usually three spaces).
- Comments start with `//` and run to the end of the line.
- Meta-variables are written in angle brackets `<...>` and should be substituted.

## Data Types and Declarations

| Type | Meaning |
|---|---|
| `INTEGER` | whole number |
| `REAL` | number with a fractional part |
| `CHAR` | single character, written `'x'` |
| `STRING` | sequence of characters, written `"text"` |
| `BOOLEAN` | `TRUE` or `FALSE` |
| `DATE` | calendar date, usually `dd/mm/yyyy` |

```pseudocode
DECLARE Counter : INTEGER
DECLARE TotalToPay : REAL
DECLARE GameOver : BOOLEAN

CONSTANT HourlyRate = 6.50
CONSTANT DefaultText = "N/A"
```

Constants take a literal only, never a variable or expression.

## Assignment

The assignment operator is `←`.

```pseudocode
Counter ← 0
Counter ← Counter + 1
TotalToPay ← NumberOfHours * HourlyRate
```

## Operators

| Category | Operators |
|---|---|
| Arithmetic | `+`, `-`, `*`, `/`, `DIV` (integer quotient), `MOD` (remainder) |
| Relational | `>`, `<`, `>=`, `<=`, `=` (equal), `<>` (not equal) |
| Logic | `AND`, `OR`, `NOT` |

`/` always returns a `REAL`, even for integer operands. Use parentheses to make the order explicit in complex expressions.

## Input and Output

```pseudocode
INPUT Answer
OUTPUT Score
OUTPUT "You have ", Lives, " lives left"
```

## Arrays

Lower bound is usually 1; state it explicitly because it defaults to 0 or 1 in different systems.

```pseudocode
DECLARE StudentNames : ARRAY[1:30] OF STRING
DECLARE NoughtsAndCrosses : ARRAY[1:3,1:3] OF CHAR

StudentNames[1] ← "Ali"
NoughtsAndCrosses[2,3] ← 'X'

FOR Index ← 1 TO 30
   StudentNames[Index] ← ""
NEXT Index
```

Whole-array assignment is allowed between arrays of the same size and type (`SavedGame ← NoughtsAndCrosses`). Do not refer to a group of elements with a range like `[1 TO 30]`; use a loop.

## User-Defined Types

```pseudocode
// Enumerated (non-composite)
TYPE Season = (Spring, Summer, Autumn, Winter)

// Pointer (non-composite)
TYPE TIntPointer = ^INTEGER

// Record (composite)
TYPE StudentRecord
   DECLARE LastName : STRING
   DECLARE FirstName : STRING
   DECLARE DateOfBirth : DATE
   DECLARE YearGroup : INTEGER
   DECLARE FormGroup : CHAR
ENDTYPE

// Set (composite)
TYPE LetterSet = SET OF CHAR
DEFINE Vowels ('A','E','I','O','U') : LetterSet
```

## Selection

```pseudocode
// IF
IF <condition> THEN
   <statement(s)>
ELSE
   <statement(s)>
ENDIF

// CASE
CASE OF Move
   'W' : Position ← Position - 10
   'S' : Position ← Position + 10
   OTHERWISE : CALL Beep
ENDCASE
```

`CASE` clauses are tested in sequence and the first match runs; `OTHERWISE` must be last. A value may be a range: `1 TO 10 : <statement>`.

## Iteration

```pseudocode
// Count-controlled
FOR Index ← 1 TO 10
   <statement(s)>
NEXT Index

// With a step (may be negative)
FOR Index ← 10 TO 1 STEP -1
   <statement(s)>
NEXT Index

// Post-condition: runs at least once
REPEAT
   <statement(s)>
UNTIL <condition>

// Pre-condition: may never run
WHILE <condition>
   <statement(s)>
ENDWHILE
```

## Procedures and Functions

```pseudocode
// Procedure with no parameters
PROCEDURE Reset()
   <statement(s)>
ENDPROCEDURE

// Procedure with parameters (by value unless stated)
PROCEDURE Swap(BYREF X : INTEGER, Y : INTEGER)
   Temp ← X
   X ← Y
   Y ← Temp
ENDPROCEDURE

CALL Reset()
CALL Swap(A, B)

// Function: the return value replaces the call
FUNCTION Cube(N : INTEGER) RETURNS INTEGER
   RETURN N * N * N
ENDFUNCTION
```

Parameters are passed by value unless marked `BYREF`. A function is used in an expression; a procedure is called as a statement.

## File Handling

### Text files

```pseudocode
DECLARE LineOfText : STRING
OPENFILE "FileA.txt" FOR READ
OPENFILE "FileB.txt" FOR WRITE
WHILE NOT EOF("FileA.txt")
   READFILE "FileA.txt", LineOfText
   IF LineOfText = "" THEN
      WRITEFILE "FileB.txt", "-----------------------------"
   ELSE
      WRITEFILE "FileB.txt", LineOfText
   ENDIF
ENDWHILE
CLOSEFILE "FileA.txt"
CLOSEFILE "FileB.txt"
```

- Modes: `READ`, `WRITE` (creates a new file, existing data is lost), `APPEND`.
- `EOF(<file identifier>)` returns `TRUE` when there are no more lines.
- A file is open in only one mode at a time.

### Random files

```pseudocode
OPENFILE "Data.dat" FOR RANDOM
SEEK "Data.dat", Address
GETRECORD "Data.dat", RecordVar
PUTRECORD "Data.dat", RecordVar
CLOSEFILE "Data.dat"
```

Random files hold fixed-length records; `SEEK` moves the file pointer to a record address before `GETRECORD` or `PUTRECORD`.

## Trace Tables

A trace table tracks the value of each variable after each statement executes. Use one column per variable, one row per executed statement, and include loop counters and conditions. The trace is the main way to verify pseudocode and assembly programs by hand.

| Statement | `Counter` | `Total` |
|---|---|---|
| `Counter ← 0` | 0 | - |
| `Total ← 0` | 0 | 0 |
| `Counter ← Counter + 1` | 1 | 0 |

## Paper 4 Language Equivalents

Paper 4 is completed in Java (console mode), Visual Basic .NET (console mode), or Python (console mode). The table gives the equivalent of common pseudocode operations in each language.

| Operation | Pseudocode | Java | Visual Basic .NET | Python |
|---|---|---|---|---|
| Declare / assign | `Counter ← 0` | `int counter = 0;` | `Dim counter As Integer = 0` | `counter = 0` |
| Integer division | `a DIV b` | `a / b` (cast) | `a \ b` | `a // b` |
| Modulus | `a MOD b` | `a % b` | `a Mod b` | `a % b` |
| Input (string) | `INPUT Name` | `name = in.nextLine();` | `name = Console.ReadLine()` | `name = input()` |
| Output | `OUTPUT X` | `System.out.println(x);` | `Console.WriteLine(x)` | `print(x)` |
| For loop | `FOR I ← 1 TO 10 ... NEXT I` | `for (int i=1; i<=10; i++) {...}` | `For i = 1 To 10 ... Next` | `for i in range(1, 11): ...` |
| While loop | `WHILE C ... ENDWHILE` | `while (c) {...}` | `While c ... End While` | `while c: ...` |
| Procedure | `PROCEDURE P() ... ENDPROCEDURE` | `static void P() {...}` | `Sub P() ... End Sub` | `def P(): ...` |
| Function | `FUNCTION F() RETURNS ...` | `static int f() { return ...; }` | `Function F() As Integer ... End Function` | `def f(): return ...` |
| Array | `ARRAY[1:10] OF INTEGER` | `int[] a = new int[10];` | `Dim a(9) As Integer` | `a = [0] * 10` |

## Exception Handling (A Level, section 20.2)

Exceptions are raised when a program cannot continue normally, for example on division by zero, a missing file, or invalid input. Handling prevents a crash and lets the program respond cleanly.

The official CAIE Pseudocode Guide does not define an exception-handling pseudocode construct. Section 20.2 asks candidates to write program code, so use the construct from the chosen Paper 4 language:

| Language | Form |
|---|---|
| Java | `try { ... } catch (SpecificException e) { ... } catch (Exception e) { ... }` |
| Visual Basic .NET | `Try ... Catch ex As SpecificException ... Catch ex As Exception ... End Try` |
| Python | `try: ... except SpecificError: ... except Exception: ...` |

Catch the most specific exception first and use a broad catch only as a final safety net with a clear recovery action.

## How to Use This Reference

- Cross-check every Paper 2 answer against the official Pseudocode Guide before submission; examiners mark on this notation.
- For Paper 4, pick one language and keep its patterns automatic.
- When stuck on a trace, fill the trace table column by column rather than reading the code linearly.
