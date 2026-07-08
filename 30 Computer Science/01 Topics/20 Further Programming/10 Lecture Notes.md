---
title: Further Programming Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/20 Further Programming/00 Overview|Further Programming]]"
status: active
tags:
  - computerscience/programming
  - lecture-notes
---

# Further Programming Lecture Notes

These notes cover **section 20 Further Programming** of the 9618 A Level syllabus. The topic extends AS section 11 with four programming paradigms (low-level, imperative, object-oriented, declarative) and the file-processing and exception-handling skills that Paper 4 examines in your chosen language (Java, Visual Basic .NET, or Python). Low-level and declarative programming appear only in Paper 3 theory; the rest is tested practically.

## Source Route

- Syllabus 20.1 Programming Paradigms - low-level, imperative (procedural), object-oriented, declarative.
- Syllabus 20.2 File Processing and Exception Handling - file operations on serial, sequential, random files; exceptions and `TRY/CATCH`.
- Paper 3 (theory, all paradigms) and Paper 4 (practical; excludes low-level and declarative).

## 1. Programming paradigms

A **programming paradigm** is a style or way of thinking about how a program is built - the concepts, abstractions and constructs it treats as fundamental. The same problem can be solved in several paradigms; each makes some things easy and others hard. Knowing the characteristics lets you pick the right one and read code written in any of them.

| Paradigm | Core idea | State & control | When to use |
|----------|-----------|-----------------|-------------|
| Low-level | Instructions for a specific CPU; one line → one machine instruction | Direct register/memory control | Device drivers, embedded code, exam questions on addressing modes |
| Imperative (procedural) | A sequence of statements that change program state via variables; structured into procedures/functions | Explicit, step by step | Most Paper 4 tasks; algorithms with clear control flow |
| Object-oriented | Program built from interacting **objects** that bundle data (attributes) and behaviour (methods) | Hidden inside objects | Modelling real-world entities; large, extensible systems |
| Declarative | Describe *what* is true (facts and rules); let the system reason to satisfy a goal | Not stated step by step | Logic/relationship problems: family trees, rule-based expert systems |

> A modern language may support several paradigms (Java, VB.NET and Python are imperative *and* object-oriented). For an exam answer, stay in one paradigm and name the constructs you use.

## 2. Low-level programming

Low-level code uses the CPU's own instructions. Each **addressing mode** is the rule the CPU follows to locate the operand. The table shows the load instruction that uses each mode; the same operand rules apply to `ADD`, `STO` and so on.

| Mode | How the operand is found | Mnemonic example | Effect |
|------|--------------------------|------------------|--------|
| Immediate | The operand *is* the value written in the instruction | `LDM #5` | ACC ← 5 |
| Direct | The operand is stored at the address given | `LDD [100]` | ACC ← M[100] |
| Indirect | The address given holds *another* address; the operand is there | `LDI [100]` | ACC ← M[M[100]] |
| Indexed | The operand is at (given address + Index Register) | `LDX [100]` | ACC ← M[100 + IX] |
| Relative | The address is an offset from the current PC | `JMP #3` (concept) | jump to PC + offset |

One worked instruction per mode:

```pseudocode
LDM #10         // Immediate: load the literal 10 into ACC
LDD [500]       // Direct:   load the value stored at address 500
LDI [500]       // Indirect: address 500 holds an address; load from there
LDX [500]       // Indexed:  load from address 500 + IX (array element)
JMP #3          // Relative: jump 3 instructions forward from the PC
```

Indexed addressing is the workhorse for arrays: store the base address of the array, then vary IX to step through elements. Relative addressing gives position-independent code - the same bytes run correctly wherever they are loaded.

## 3. Imperative (procedural) programming

Imperative programming describes *how* to solve a problem as a sequence of statements that read and write variables and call procedures and functions. The structured-programming backbone is assumed from AS section 11.3: sequence, selection (`IF`/`CASE`) and iteration (`FOR`/`WHILE`/`REPEAT`), with reusable logic placed in **procedures** (called as statements) and **functions** (used in expressions because they return one value).

A short worked example - a function that totals the positive values in an array:

```pseudocode
FUNCTION SumPositive(Values : ARRAY[1:10] OF INTEGER) RETURNS INTEGER
    DECLARE Total, i : INTEGER
    Total ← 0
    FOR i ← 1 TO 10
        IF Values[i] > 0 THEN
            Total ← Total + Values[i]
        ENDIF
    NEXT i
    RETURN Total
ENDFUNCTION

DECLARE Result : INTEGER
Result ← SumPositive(ExamMarks)   // function used inside an expression
OUTPUT "Total positive marks: ", Result
```

> Recap rule: choose `FOR` when the count is fixed, `WHILE` when zero iterations are possible, `REPEAT` when the body must run at least once. Use `BYREF` only when the caller's variable must change.

## 4. Object-oriented programming (OOP)

OOP models a problem as a set of cooperating **objects**. The vocabulary examiners expect:

| Term | Meaning |
|------|---------|
| Class | A blueprint that defines the attributes and methods shared by a kind of object |
| Object | A single entity created from a class; an **instance** |
| Instance | One specific object of a class (each has its own attribute values) |
| Property / attribute | A named piece of data held by an object |
| Method | A procedure or function belonging to a class; the object's behaviour |
| Encapsulation | Bundling data and the code that acts on it together, and hiding internal detail from outside |
| Getter | A method that returns the value of a private attribute |
| Setter | A method that assigns a value to a private attribute, usually with validation |
| Inheritance | A subclass takes on the attributes and methods of a parent class, and may extend or override them |
| Polymorphism | Different objects can respond to the same method call in their own way (often via overriding) |
| Containment / aggregation | A class is built from other objects (a "has-a" relationship) |

**Designing classes.** List the nouns in the problem - each candidate is a class. Each class gets the attributes it must remember and the methods it must perform. Mark attributes private and expose them through getters/setters so the outside world cannot break the data. Use inheritance only when one class truly *is a* kind of another; use containment when one class *has* others as parts.

Worked example - a `Vehicle` class with a `Car` subclass, showing encapsulation (private attributes), a getter and a validated setter, inheritance, and polymorphism (overridden `describe`):

```python
class Vehicle:
    def __init__(self, make, top_speed):
        self.__make = make            # encapsulated attribute
        self.__top_speed = top_speed

    def get_make(self):               # getter
        return self.__make

    def get_top_speed(self):          # getter
        return self.__top_speed

    def set_top_speed(self, value):   # setter with validation
        if value >= 0:
            self.__top_speed = value

    def describe(self):               # method, overridden below
        return "Vehicle: " + self.__make


class Car(Vehicle):                   # inheritance: Car is a Vehicle
    def __init__(self, make, top_speed, doors):
        super().__init__(make, top_speed)
        self.__doors = doors

    def describe(self):               # polymorphism: overrides Vehicle.describe
        return "Car: " + self.get_make() + " (" + str(self.__doors) + " doors)"


v = Vehicle("Honda", 180)            # two instances
c = Car("Tesla", 250, 4)
c.set_top_speed(260)                 # setter used to change a private value
print(v.describe())                  # Vehicle: Honda
print(c.describe())                  # Car: Tesla (4 doors)
```

A fleet object holding many `Vehicle` instances would illustrate **containment/aggregation** - the fleet *has* vehicles.

## 5. Declarative programming

Declarative programming (logic programming) does not say *how* to compute step by step. You state what is true as **facts**, define **rules** that combine facts, then pose a **goal** (query) that the system tries to satisfy by matching facts and rules. Prolog-style notation is standard for this topic.

- **Fact** - a simple statement that a relationship holds, e.g. `parent(tom, bob).`
- **Rule** - a conditional relationship, written `head :- body.`; the head is true if every part of the body is true.
- **Goal** - a query such as `?- grandparent(tom, ann).`, which the system answers `yes`/`no` (and may bind variables).

Worked example - family relationships from a set of facts, a grandparent rule built from two parent facts, and two goals:

```prolog
% Facts: who is a parent of whom
parent(tom, bob).
parent(mary, bob).
parent(bob, ann).
parent(bob, sue).

% Rule: X is a grandparent of Z if X is a parent of Y
%       and Y is a parent of Z
grandparent(X, Z) :- parent(X, Y), parent(Y, Z).

% Goals
?- grandparent(tom, ann).   % yes - tom -> bob -> ann
?- grandparent(mary, sue).  % yes - mary -> bob -> sue
?- grandparent(ann, tom).   % no
```

The system satisfies `grandparent(tom, ann)` by finding a `Y` (bob) such that both `parent(tom, bob)` and `parent(bob, ann)` are facts. Adding a rule needs no new facts - the same facts are reused.

## 6. File processing

A file holds data on backing store so it survives after the program ends. The three file **organisations** in the syllabus differ in how records are stored and therefore which operations suit them.

| Organisation | How records are stored | Access pattern | Add a record | Find one record | Typical use |
|--------------|------------------------|----------------|--------------|-----------------|-------------|
| Serial | In order of arrival, no key | Read from start to end; cannot skip | Append to the end | Search the whole file | Log files, sensor/event data |
| Sequential | Sorted by a key field | Read in key order, start to end | Insert at the correct key position | Read until the key is reached (or passed) | Payroll, batch processing on sorted data |
| Random (direct) | Fixed-length records at computed addresses | Direct to any record via its address | Write to a free slot | `SEEK` then `GETRECORD` - no scanning | Real-time lookups, indexes |

The pseudocode operations are the same whatever the language: open in a **mode**, read or write records, then close. A file is open in only one mode at a time, and `EOF()` returns `TRUE` when there are no more records.

Sequential file - read every record and print a name:

```pseudocode
DECLARE MemberRecord : STRING

OPENFILE "Members.dat" FOR READ
WHILE NOT EOF("Members.dat")
    READFILE "Members.dat", MemberRecord
    OUTPUT MemberRecord
ENDWHILE
CLOSEFILE "Members.dat"
```

Appending a new record (serial or sequential - both add at the end or in key order):

```pseudocode
OPENFILE "Log.dat" FOR APPEND
WRITEFILE "Log.dat", NewEntry
CLOSEFILE "Log.dat"
```

Random file - seek to a record by address, read it, change a field, write it back:

```pseudocode
DECLARE Rec : MemberRecord

OPENFILE "Data.dat" FOR RANDOM
SEEK "Data.dat", RecordIndex      // move pointer to this record address
GETRECORD "Data.dat", Rec          // read the fixed-length record
Rec.Status ← "Paid"
PUTRECORD "Data.dat", Rec          // write the updated record back
CLOSEFILE "Data.dat"
```

> Modes: `READ`, `WRITE` (creates a new file - existing data is lost), `APPEND` (adds to the end). Random files use `RANDOM` with `SEEK`, `GETRECORD` and `PUTRECORD`. Always `CLOSEFILE` when finished; a forgotten close can lose buffered data.

## 7. Exceptions and exception handling

An **exception** is an error condition raised while a program runs - for example division by zero, a missing file, an out-of-range array index, or invalid input. If it is not handled the program crashes. **Exception handling** catches the condition at a point where the program can respond sensibly (show a message, use a default, retry), so execution continues or stops cleanly instead of aborting.

Use exception handling when a failure is **possible but not normal** and you have a genuine recovery path: reading a file the user named, parsing input, dividing by a value that might be zero. Do not wrap every statement - catching too broadly hides real bugs. Handle the most specific error first, then a general one as a safety net.

Worked example in Java - dividing 100 by a user-supplied value, with a specific catch for division by zero:

```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("Enter a divisor: ");
        try {
            int d = in.nextInt();
            int result = 100 / d;            // may raise ArithmeticException
            System.out.println("100 / " + d + " = " + result);
        } catch (ArithmeticException e) {    // division by zero
            System.out.println("Cannot divide by zero.");
        } catch (Exception e) {              // any other failure, e.g. bad input
            System.out.println("Invalid input.");
        }
    }
}
```

The pseudocode form is `TRY / CATCH / ENDTRY`:

```pseudocode
TRY
    OUTPUT "Enter a divisor: "
    INPUT Divisor
    Result ← 100 / Divisor
    OUTPUT "Result is ", Result
CATCH DivByZero
    OUTPUT "Cannot divide by zero."
ENDTRY
```

The matching construct in each Paper 4 language is Java `try / catch`, VB.NET `Try / Catch`, Python `try / except`.

## Worked-Thinking Routine

1. Identify the paradigm the question asks for and stay inside it; name the constructs you use.
2. For low-level, decide the addressing mode each instruction needs before writing the mnemonic.
3. For OOP, list the classes (nouns), their attributes and methods; mark private data and plan getters/setters; apply inheritance only for "is-a".
4. For declarative, write all facts first, then rules that combine them, then phrase the goal precisely.
5. For files, choose the mode before opening; loop with `EOF()` for sequential, `SEEK` for random; close every file.
6. For exceptions, list what can fail, catch the most specific first, and provide a real recovery action.

## Common Mistakes

- Mixing paradigms inside one answer (e.g. adding global variables to an OOP design).
- Confusing direct (`LDD`, one address) with indirect (`LDI`, address of an address).
- Making attributes public and skipping getters/setters, which loses encapsulation marks.
- Using inheritance where containment ("has-a") is meant.
- Forgetting `CLOSEFILE`, or opening a file for `WRITE` when `APPEND` was required.
- Catching a bare `Exception` and hiding the real fault, or handling exceptions that can never occur.

## Quick Self-Check

- Name the four paradigms and one situation where each fits best.
- Write one load instruction for each of the five addressing modes and state its effect.
- Design a `BankAccount` class with a private balance, a getter and a validated setter.
- Write a declarative rule for `sibling(X, Y)` using a `parent/2` fact.
- Write pseudocode to append a record to a sequential file and to update a random record.
- Write a `TRY/CATCH` block that handles a missing-file error, and state its Java form.

## Connections

- [[30 Computer Science/01 Topics/11 Programming/00 Overview|Programming]] - the AS foundation this topic extends.
- [[30 Computer Science/01 Topics/13 Data Representation/00 Overview|Data Representation]] - file organisations and record types used here.
- [[30 Computer Science/04 Reference/Pseudocode and Programming Reference|Pseudocode and Programming Reference]] - file handling, exception and Paper 4 language equivalents.

## Study Sequence

1. Read sections 1–2 and write one instruction for each addressing mode from memory.
2. Recap section 11.3; confirm you can write a function used in an expression.
3. Build a small class hierarchy on paper before coding the OOP example.
4. Write a declarative facts/rules set for a new relationship (e.g. `ancestor`).
5. Practise file code in your Paper 4 language for all three organisations.
6. Add exception handling to a file-reading program and run it with a missing file.
