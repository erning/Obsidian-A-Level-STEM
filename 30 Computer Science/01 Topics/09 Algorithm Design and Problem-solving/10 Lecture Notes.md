---
title: Algorithm Design and Problem-solving Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/09 Algorithm Design and Problem-solving/00 Overview|Algorithm Design and Problem-solving]]"
status: active
tags:
  - computerscience/programming
  - lecture-notes
---

# Algorithm Design and Problem-solving Lecture Notes

A program is not typed out of thin air. Before any code is written, the problem
has to be understood, simplified, and broken into pieces, and the solution has to
be expressed as a sequence of unambiguous steps. This topic covers the thinking
skills (abstraction and decomposition) and the notation (structured English,
flowcharts, pseudocode) that turn a vague problem statement into something a
computer can execute. Paper 2 examines this material, and answers are expected in
the official pseudocode.

## Source Route

This note follows CAIE Computer Science 9618, AS section 9:

- 9.1 Computational Thinking Skills (abstraction and decomposition)
- 9.2 Algorithms (pseudocode, identifier tables, the three constructs,
  documentation notations, stepwise refinement, logic statements)

Section 9 is examined in Paper 2.

## 1. Abstraction

Abstraction is the process of reducing a real-world problem to the features that
matter for solving it, and deliberately leaving out everything that does not. The
result is an **abstract model** that contains only the essential details.

**Why it is needed.** A real problem comes with far more detail than a computer
program can or should handle. A library book has a cover colour, a page count, a
price, and a blurb, but none of those helps the system decide who borrowed it or
when it is due back. Handling irrelevant detail wastes memory, hides the real
logic, and makes the program harder to design and test.

**Purpose.** Abstraction lets you focus on the data and behaviour that the
solution actually depends on, so the problem becomes small enough to think about
and to program.

**Benefits.**

- The problem is simpler, because only relevant information remains.
- The model is easier to design, code, and test.
- The solution generalises: the same model fits any library, not just one.
- Irrelevant detail cannot introduce bugs, because it was never included.

**How to build an abstract model.** List everything known about the situation,
then cross out anything that does not affect the question being asked. What
remains is the model. Name the data items, and you have the start of an
identifier table.

### Worked example: a library loan system

Consider what is true of the real situation. A book has a title, author, ISBN,
publisher, year, page count, cover colour, shelf position, genre, and price. A
borrower has a name, address, phone, email, membership number, join date,
photograph, and any fines owed. A loan links a book and a borrower with the date
borrowed, due date, return date, and number of renewals.

The question the system must answer is narrow: who has which book, and when is it
due back? Crossing out detail that does not help:

- Book: drop publisher, year, page count, cover colour, shelf position, genre,
  price, blurb. Keep an identifier and a title.
- Borrower: drop address, phone, email, photograph, join date. Keep an identifier
  and a name.
- Loan: keep which book, which borrower, and the due date. Drop renewals and
  return date for the core model.

The abstract model is now three small sets of data, which is exactly what a
loan-tracking program needs:

| Entity | Essential data kept |
|---|---|
| Book | BookID, Title |
| Borrower | MemberID, Name |
| Loan | BookID, MemberID, DueDate |

Every item removed is a detail the program does not have to store, validate, or
display.

## 2. Decomposition

Decomposition is the process of breaking a large problem into smaller, more
manageable sub-problems, each of which can be solved on its own. The
sub-problems become the **modules** of the program. In pseudocode a module is
either a **procedure**, which performs a task and returns no value, or a
**function**, which performs a task and returns a single value.

**Why it helps.** A single large problem is hard to hold in your head; a set of
small, named tasks is not. Each module can be designed, written, and tested
separately, and a module that does one job well can be reused in other programs.

**How to decompose.** Read the problem and ask "what are the major things this
program has to do?" Write each as a short phrase. If a phrase still hides more
than one task, split it again. Each final task is one module.

### Worked example: a student grade report

**Problem.** Read a student's name and five subject marks, then output a report
showing the average mark, the overall grade, and whether the student has passed.

Splitting the major tasks:

1. Read the student's name and the five marks.
2. Calculate the average of the five marks.
3. Determine the grade from the average.
4. Output the report.

Each task becomes a module. "Calculate the average" and "determine the grade"
take input and produce a result, so they are functions. "Read the data" and
"output the report" do work but need not return a value, so they are procedures
(the data they read can be stored in variables shared by the main program).

| Module | Type | Job |
|---|---|---|
| ReadData | Procedure | INPUT the name and five marks |
| CalculateAverage | Function | Return the mean of five marks |
| DetermineGrade | Function | Return a grade from the average |
| PrintReport | Procedure | OUTPUT the report |

The main program then reads as four calls in sequence, which is exactly how it
will look as pseudocode later.

## 3. Algorithms and identifier tables

An **algorithm** is a sequence of defined steps that solves a problem or performs
a task. To qualify as an algorithm the steps must be finite (they come to an
end), unambiguous (each step has one meaning), and effective (each step can
actually be carried out).

Every algorithm manipulates data, and that data lives in **identifiers** (the
names given to variables and constants). Good identifier names are meaningful and
describe what the value represents, so `TotalMark` is clear and `x` is not. The
full set of identifiers used by an algorithm is recorded in an **identifier
table**, which lists each name, its data type, and a description of what it is
for. The table is written before or alongside the pseudocode so the reader knows
exactly what each variable holds.

### Worked example: identifier table for "largest of three numbers"

The problem: input three numbers and output the largest. The data needed is
three inputs and one value to hold the result so far.

| Identifier | Data type | Description |
|---|---|---|
| `Num1` | REAL | the first number input |
| `Num2` | REAL | the second number input |
| `Num3` | REAL | the third number input |
| `Largest` | REAL | the largest value found so far |

With the table written, the pseudocode that follows it can use these names
without further explanation, because the table already says what each one means.

## 4. The three constructs

Every algorithm is built from just three constructs. Any logic, however complex,
is some combination of them.

**Sequence** - steps carried out one after another, in order.

```pseudocode
Num1 ← 6
Num2 ← 9
Sum ← Num1 + Num2
OUTPUT "Sum is ", Sum
```

**Selection** - choosing between alternative paths based on a condition. The
`IF` statement handles one or two branches; `CASE OF` selects one branch from
many based on the value of a single variable.

```pseudocode
// Two-way selection
IF Sum >= 10 THEN
    OUTPUT "Large"
ELSE
    OUTPUT "Small"
ENDIF

// Many-way selection
CASE OF Grade
    "A" : OUTPUT "Excellent"
    "B" : OUTPUT "Good"
    "C" : OUTPUT "Satisfactory"
    OTHERWISE OUTPUT "Refer"
ENDCASE
```

**Iteration** - repeating a block of steps. Three forms exist for three
situations. `FOR` repeats a known number of times; `WHILE` tests before each
repetition and may run zero times; `REPEAT` runs the body first and tests after,
so it always runs at least once.

```pseudocode
// Fixed count
FOR Count ← 1 TO 5
    OUTPUT Count
NEXT

// Pre-condition loop: may not run at all
INPUT Answer
WHILE Answer <> "stop" DO
    OUTPUT "You said ", Answer
    INPUT Answer
ENDWHILE

// Post-condition loop: runs at least once
REPEAT
    INPUT Guess
UNTIL Guess = SecretNumber
```

The choice between `WHILE` and `REPEAT` is about when the condition is tested:
`WHILE` checks before the body, `REPEAT` checks after. Use `WHILE` when the loop
might not need to run at all, and `REPEAT` when the body must execute at least
once before the test makes sense.

## 5. Three notations for the same algorithm

An algorithm can be written down in three ways, and you must be able to convert
between them. They differ only in how formal they are, not in the logic.

- **Structured English** is plain English arranged under the three constructs,
  with indentation to show structure. It is quick to write and easy for a
  non-programmer to read, but it can be ambiguous.
- **A flowchart** is a diagram. Each kind of step has its own symbol, and arrows
  show the order of execution. It shows the flow of control at a glance, but it
  is slow to draw and hard to change for a large algorithm.
- **Pseudocode** is a compact, language-like notation that looks close to a real
  programming language without being any one of them. It is the form used in
  Paper 2, and it follows the CAIE Pseudocode Guide exactly.

### Flowchart symbols

| Symbol (shape) | Meaning |
|---|---|
| Terminator (rounded rectangle) | Start or End |
| Process (rectangle) | an action: assign, calculate |
| Decision (diamond) | a condition with Yes / No branches |
| Input / Output (parallelogram) | reading data in or writing data out |
| Flow line (arrow) | the direction of execution |

### Worked example: largest of three numbers in all three notations

The problem: input three numbers and output the largest.

**Structured English.**

1. Input three numbers: Num1, Num2, Num3.
2. Set Largest to Num1.
3. If Num2 is greater than Largest, then set Largest to Num2.
4. If Num3 is greater than Largest, then set Largest to Num3.
5. Output Largest.

**Flowchart** (read the boxes top to bottom; the shaped words note the symbol):

```text
          ( Start )                         ← terminator
              |
  / INPUT Num1, Num2, Num3 /                ← parallelogram
              |
         Largest ← Num1                    ← process
              |
      < Num2 > Largest ? >                  ← decision
        / Yes        \ No
         |             |
    Largest ← Num2    |
         |_____________|
              |
      < Num3 > Largest ? >                  ← decision
        / Yes        \ No
         |             |
    Largest ← Num3    |
         |_____________|
              |
       / OUTPUT Largest /                   ← parallelogram
              |
          ( End )                           ← terminator
```

**Pseudocode.**

```pseudocode
INPUT Num1
INPUT Num2
INPUT Num3
Largest ← Num1
IF Num2 > Largest THEN
    Largest ← Num2
ENDIF
IF Num3 > Largest THEN
    Largest ← Num3
ENDIF
OUTPUT "Largest is ", Largest
```

All three describe the same steps in the same order. Converting between them is a
matter of swapping the surface notation, not the logic: each box in the
flowchart maps to a line or block in the pseudocode, and each line of structured
English maps to the same.

## 6. Stepwise refinement

Stepwise refinement is a top-down design method. You write the solution as a few
high-level steps first, in plain terms, and then take each step in turn and
expand it into more detail. You keep expanding until every step is specific
enough to translate directly into pseudocode. The result is the same algorithm,
just written at increasing levels of detail.

The rule is one level at a time: do not jump straight to pseudocode for one part
while leaving another part as a vague phrase. Refine every step at a level
before going deeper anywhere.

### Worked example: class mark statistics

**Problem.** Read the marks of a whole class (size not known in advance, ended by
a sentinel of -1), then output the class average and how many students passed
(mark of 50 or above).

**Level 0 - the major steps.**

1. Read in all the marks.
2. Calculate the class average.
3. Count how many passed.
4. Output the results.

**Level 1 - refine each step.**

1. Read in all marks: repeatedly INPUT a mark until the sentinel -1 appears,
   storing each in an array and counting them.
2. Calculate the average: sum every mark in the array, then divide by the count.
3. Count passes: go through the array once more, adding one to a counter for each
   mark of 50 or above.
4. Output the average and the pass count.

**Level 2 - pseudocode.**

```pseudocode
DECLARE Mark : ARRAY[1:100] OF REAL
DECLARE Count : INTEGER
DECLARE Index : INTEGER
DECLARE Sum : REAL
DECLARE Average : REAL
DECLARE PassCount : INTEGER
DECLARE ThisMark : REAL

// 1. Read in all the marks
Count ← 0
INPUT ThisMark
WHILE ThisMark <> -1 DO
    Count ← Count + 1
    Mark[Count] ← ThisMark
    INPUT ThisMark
ENDWHILE

// 2. Calculate the average
Sum ← 0
FOR Index ← 1 TO Count
    Sum ← Sum + Mark[Index]
NEXT
Average ← Sum / Count

// 3. Count how many passed
PassCount ← 0
FOR Index ← 1 TO Count
    IF Mark[Index] >= 50 THEN
        PassCount ← PassCount + 1
    ENDIF
NEXT

// 4. Output the results
OUTPUT "Average = ", Average
OUTPUT "Number passed = ", PassCount
```

Each comment in the final code lines up with a Level 1 step, which is the point
of the method: the high-level structure survives into the finished program.

## 7. Logic statements

A **logic statement** is a condition built from comparisons joined by the logical
operators `AND`, `OR`, and `NOT`. Logic statements appear wherever a decision is
made: in `IF` conditions, in `CASE OF` selectors, and in the condition tested by
`WHILE` and `REPEAT`.

The comparisons are the familiar relational operators: `=`, `<`, `>`, `<=`,
`>=`, and `<>` (not equal). Logical operators combine them:

- `AND` is true only when both sides are true.
- `OR` is true when at least one side is true.
- `NOT` reverses a single condition.

```pseudocode
// Pass requires mark of at least 50 AND attendance above 75%
IF Mark >= 50 AND Attendance > 75 THEN
    OUTPUT "Pass"
ELSE
    OUTPUT "Refer"
ENDIF

// Overtime applies outside 9 to 17
IF Hour < 9 OR Hour > 17 THEN
    OUTPUT "Overtime"
ENDIF

// Keep asking until the input is valid (NOT invalid)
REPEAT
    INPUT Age
UNTIL NOT (Age < 0 OR Age > 120)
```

Parentheses matter just as they do in arithmetic. `A AND B OR C` is read as
`(A AND B) OR C`, which is not the same as `A AND (B OR C)`. When a condition is
even slightly complex, write the parentheses explicitly so the meaning cannot be
mistaken.

## Worked-Thinking Routine

Use this routine for any algorithm question.

1. Read the problem and identify the inputs, the process, and the outputs. Write
   them down before anything else.
2. Decide what data the program needs and write the identifier table.
3. Decompose the problem into modules; note which are procedures and which are
   functions.
4. Sketch the logic in structured English or a flowchart first, so the flow of
   control is clear before you commit to pseudocode.
5. Translate into the official pseudocode, using the three constructs and the
   assignment arrow `←`.
6. Trace the algorithm with a small set of test data, line by line, to confirm
   it produces the expected output.

## Common Mistakes

- Starting to write pseudocode before identifying the inputs and outputs.
- Including irrelevant detail in an abstract model (abstraction means leaving it
  out).
- Decomposing into steps that are not modules, or making one function do several
  jobs.
- Choosing the wrong loop: `REPEAT` when the body might need to run zero times,
  or `FOR` when the count is not known.
- Forgetting `ENDIF`, `ENDCASE`, `NEXT`, or `ENDWHILE`, or using `=` for
  assignment instead of `←`.
- Writing logic statements without parentheses, so `AND` / `OR` grouping is
  ambiguous.
- Using notation that is not in the Pseudocode Guide.

## Quick Self-Check

You are ready to move on when you can answer these without notes.

1. State what abstraction is and give one benefit it provides.
2. List the essential data you would keep in an abstract model of a car park that
   records which bays are occupied.
3. What is the difference between a procedure and a function?
4. Decompose a "vending machine" program into four modules.
5. Write an identifier table for a program that converts Celsius to Fahrenheit.
6. Name the three constructs and give one pseudocode example of each.
7. Draw the flowchart symbols for terminator, process, decision, and input /
   output.
8. Express "find the smaller of two numbers" in structured English and in
   pseudocode.
9. Take the level-0 step "process a list of names" and refine it two levels.
10. Why does `A AND B OR C` need parentheses, and what are its two possible
    meanings?

## Connections

- [[30 Computer Science/01 Topics/19 Computational Thinking and Problem-solving/00 Overview|Computational Thinking and Problem-solving]]
  extends these skills with searching and sorting algorithms, recursion, ADTs,
  and complexity analysis.
- [[30 Computer Science/01 Topics/11 Programming/00 Overview|Programming]]
  turns these designs into real code in a high-level language.
- [[30 Computer Science/04 Reference/Pseudocode and Programming Reference|Pseudocode and Programming Reference]]
  is the notation reference for every pseudocode answer.

## Study Sequence

1. Read sections 1 and 2 to fix what abstraction and decomposition are for, and
   work through each worked example until you can produce the model or the module
   split yourself.
2. Learn the identifier table format in section 3 and write one for a simple
   problem of your own.
3. Memorise the three constructs and their pseudocode forms in section 4.
4. Practise expressing one small algorithm in all three notations, as in section
   5, until converting between them is automatic.
5. Work the stepwise-refinement example in section 6 on paper, level by level.
6. Self-check against the questions above before connecting to Programming.
