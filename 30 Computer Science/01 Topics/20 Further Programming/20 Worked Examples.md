---
title: Further Programming Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[Further Programming](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - worked-examples
---

# Further Programming Worked Examples

These worked examples cover 9618 A Level section 20 Further Programming: the four paradigms, class design in an object-oriented language, a declarative facts-and-rules solution, file processing for sequential and random files, and exception handling. Each example follows the same pattern: a CAIE-style prompt, a full solution, and a short check of the points examiners look for. Attempt each prompt on paper before reading the solution. All pseudocode uses the CAIE Pseudocode Guide notation, including the assignment arrow ←.

## Source Route

- Syllabus 9618 A Level section 20 Further Programming.
- 20.1 Programming Paradigms - low-level (addressing modes), imperative/procedural, object-oriented, declarative.
- 20.2 File Processing and Exception Handling - open/close, read/write records, serial/sequential/random files, and exception handling in Java, Visual Basic .NET, or Python program code.
- Assessed in Paper 3 (all paradigms) and Paper 4 (practical, excluding low-level and declarative).

## Example 1: Classify a task by paradigm

**Prompt.** For each task below, name the most appropriate paradigm (low-level, imperative/procedural, object-oriented, or declarative) and justify the choice in one sentence.

(a) Reading the value held in a specific memory address on a particular CPU.
(b) Computing the total of a list of marks using a loop.
(c) Simulating a bank with customers, accounts and transactions.
(d) Reasoning about who is whose grandchild in a family tree.

**Solution.**

| Task | Paradigm | Justification |
|------|----------|---------------|
| (a) | Low-level | It controls a specific CPU's memory and registers directly, one machine instruction per line |
| (b) | Imperative (procedural) | The total is a step-by-step accumulation in a loop over an array |
| (c) | Object-oriented | The bank is modelled as interacting objects (Customer, Account, Transaction) that bundle data and behaviour |
| (d) | Declarative | Only relationships matter; stating facts and rules and asking a goal is the natural fit |

**Check.** The decision hinges on what is fundamental to the task. If it is the hardware, go low-level; if it is a clear sequence of state changes, go imperative; if it is cooperating entities with their own data, go object-oriented; if it is relationships and logical inference, go declarative. Avoid mixing paradigms inside one answer.

## Example 2: Low-level code for each addressing mode

**Prompt.** Using the Topic 4 instruction-set notation, assume an accumulator `ACC`, an index register `IX`, and a program counter `PC`. Write one load or jump instruction that uses each of the five addressing modes (immediate, direct, indirect, indexed, relative) and state the effect of each.

**Solution.**

```pseudocode
LDM #10         // Immediate: ACC ← 10 (the operand is the literal value)
LDD 500         // Direct:   ACC ← M[500] (operand is at the given address)
LDI 500         // Indirect: ACC ← M[M[500]] (address 500 holds another address)
LDX 500         // Indexed:  ACC ← M[500 + IX] (base address plus the index register)
JMP +3          // Relative: PC ← PC + 3 (jump an offset from the current PC)
```

**Check.** `LDM` loads the literal shown after `#`. `LDD` dereferences the address once. `LDI` dereferences twice, so it is the value at the address held at the named address. `LDX` adds the index register to the base address, which is how arrays are stepped through. Relative addressing makes the code position-independent because every jump is measured from where execution currently is.

## Example 3: Design classes and write OOP code

**Prompt.** Model a simple staff system. A `Staff` class has a private name and a private salary, with a getter for the name and a validated setter for the salary (it must not be negative). A `Manager` is a kind of `Staff` that also has a bonus. Write the classes in Python, instantiate a `Manager`, use the setter to change the salary, and demonstrate method overriding via a `details` method.

**Solution.**

```python
class Staff:
    def __init__(self, name, salary):
        self.__name = name              # encapsulated attributes
        self.__salary = salary

    def get_name(self):                 # getter
        return self.__name

    def get_salary(self):               # getter
        return self.__salary

    def set_salary(self, value):        # setter with validation
        if value >= 0:
            self.__salary = value

    def details(self):                  # method, overridden below
        return self.__name + ", salary " + str(self.__salary)


class Manager(Staff):                   # inheritance: Manager is a Staff
    def __init__(self, name, salary, bonus):
        super().__init__(name, salary)
        self.__bonus = bonus

    def details(self):                  # polymorphism: overrides Staff.details
        return self.get_name() + ", salary " + str(self.get_salary()) + ", bonus " + str(self.__bonus)


m = Manager("Alice", 40000, 5000)
m.set_salary(45000)                     # validated setter used to change a private value
print(m.details())                      # Alice, salary 45000, bonus 5000
```

**Check.** Both attributes are private (the `__` prefix), so the outside world must use the getter and the validated setter, which is encapsulation. `Manager(Staff)` expresses an "is-a" relationship, so inheritance is the right choice. `super().__init__` initialises the parent part of the object before the bonus is stored. The overridden `details` runs when the call is made on a `Manager` instance, demonstrating polymorphism.

## Example 4: Declarative facts, rules and a goal

**Prompt.** Given the family relationships below, write a set of Prolog-style facts, a rule that defines `grandparent(X, Z)`, and two goals: one that should succeed and one that should fail.

- Tom is a parent of Bob.
- Mary is a parent of Bob.
- Bob is a parent of Ann.
- Bob is a parent of Sue.

**Solution.**

```prolog
% Facts: who is a parent of whom
parent(tom, bob).
parent(mary, bob).
parent(bob, ann).
parent(bob, sue).

% Rule: X is a grandparent of Z if there is some Y
%       such that X is a parent of Y and Y is a parent of Z
grandparent(X, Z) :- parent(X, Y), parent(Y, Z).

% Goals
?- grandparent(tom, ann).   % yes - tom -> bob -> ann
?- grandparent(ann, tom).   % no
```

**Check.** Every fact is a simple term ending with a full stop. The rule's head is true when every part of its body can be satisfied. To answer `grandparent(tom, ann)` the system finds a `Y` (here `bob`) such that both `parent(tom, bob)` and `parent(bob, ann)` are facts. The second goal fails because no chain matches `ann -> ... -> tom`. No new facts are needed when the rule is added.

## Example 5: Sequential file read

**Prompt.** A sequential file `Members.dat` stores one member name per record, sorted by surname. Write pseudocode that opens the file for reading, reads and outputs every record until the end of the file is reached, and closes the file. State the mode used and why.

**Solution.** The mode is `READ` because the program only reads; it does not change the file.

```pseudocode
DECLARE MemberRecord : STRING

OPENFILE "Members.dat" FOR READ
WHILE NOT EOF("Members.dat")
    READFILE "Members.dat", MemberRecord
    OUTPUT MemberRecord
ENDWHILE
CLOSEFILE "Members.dat"
```

**Check.** `OPENFILE ... FOR READ` opens the file in read mode. The `WHILE NOT EOF(...)` guard is tested before each read, so the loop stops as soon as the end of the file is reached and never reads past it. `CLOSEFILE` frees the file and flushes any buffers. Sequential files are read from start to end because records are stored in key order.

## Example 6: Random file update with SEEK

**Prompt.** A random-access file `Data.dat` holds fixed-length records. Write pseudocode that opens the file for random access, moves the file pointer to the record at index `RecordIndex`, reads the record into `Rec`, changes its `Status` field to "Paid", writes the record back, and closes the file.

**Solution.**

```pseudocode
DECLARE Rec : MemberRecord

OPENFILE "Data.dat" FOR RANDOM
SEEK "Data.dat", RecordIndex        // move pointer to this record address
GETRECORD "Data.dat", Rec           // read the fixed-length record
Rec.Status ← "Paid"
PUTRECORD "Data.dat", Rec           // write the updated record back
CLOSEFILE "Data.dat"
```

**Check.** Random files use mode `RANDOM`. `SEEK` moves the file pointer directly to the chosen record address without scanning, which is what makes random access fast. `GETRECORD` reads the fixed-length record at the pointer, the field is updated using the assignment arrow, and `PUTRECORD` writes it back at the same position. `CLOSEFILE` is still required.

## Example 7: When exception handling is appropriate

**Prompt.** State what an exception is, give two examples of conditions that can raise one, and explain when it is appropriate to handle an exception rather than let the program stop. Give one situation where handling would be a mistake.

**Solution.** An exception is an error condition raised while a program runs, for example division by zero, a missing file, an out-of-range array index, or invalid input. If it is not handled, the program crashes.

Handling is appropriate when a failure is possible but not normal and there is a genuine recovery path: reading a file the user named, parsing input, dividing by a value that might be zero. In those cases a language exception handler can report the problem, use a default, or retry, so execution continues or stops cleanly.

Handling is a mistake when it catches a bare `Exception` around code that cannot realistically fail, or around a bug such as a logic error. Catching too broadly hides the real fault, making the program harder to debug and giving the appearance of correctness while the data is wrong.

**Check.** The test is "possible but not normal, plus a real recovery action". Handle the most specific exception first, and only add a general catch as a safety net.

## Example 8: Exception-handling code

**Prompt.** Write a program that inputs a divisor and prints 100 divided by it. Handle division by zero with a clear message, and any other failure with a different message. Give the solution in Java, Visual Basic .NET, and Python program code.

**Solution.**

Java:

```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("Enter a divisor: ");
        try {
            int d = in.nextInt();
            int result = 100 / d;             // may raise ArithmeticException
            System.out.println("100 / " + d + " = " + result);
        } catch (ArithmeticException e) {     // division by zero, handled first
            System.out.println("Cannot divide by zero.");
        } catch (Exception e) {               // any other failure, e.g. bad input
            System.out.println("Invalid input.");
        }
    }
}
```

Visual Basic .NET:

```vbnet
Module MainModule
    Sub Main()
        Console.Write("Enter a divisor: ")
        Try
            Dim d As Integer = Integer.Parse(Console.ReadLine())
            Dim result As Integer = 100 \ d
            Console.WriteLine("100 / " & d & " = " & result)
        Catch ex As DivideByZeroException   ' division by zero, handled first
            Console.WriteLine("Cannot divide by zero.")
        Catch ex As Exception               ' any other failure, e.g. bad input
            Console.WriteLine("Invalid input.")
        End Try
    End Sub
End Module
```

Python:

```python
try:
    d = int(input("Enter a divisor: "))
    result = 100 / d
    print("100 /", d, "=", result)
except ZeroDivisionError:        # division by zero, handled first
    print("Cannot divide by zero.")
except Exception:                # any other failure, e.g. non-numeric input
    print("Invalid input.")
```

**Check.** Each solution wraps the risky statement inside the language's exception construct, and the most specific exception (`ArithmeticException` / `DivideByZeroException` / `ZeroDivisionError`) is caught first. The general catch sits last as a safety net so that an unexpected failure still produces a message instead of a crash. The CAIE Pseudocode Guide does not provide a separate exception-handling pseudocode syntax, so exam practice should use a Paper 4 language.

## Study Routine

1. Read the prompt and identify the paradigm before writing anything; name the constructs you use.
2. For low-level, decide the addressing mode each instruction needs, then write the mnemonic.
3. For OOP, list the classes, mark private attributes, plan getters/setters, and apply inheritance only for a true "is-a" relationship.
4. For declarative work, write all facts first, then rules that combine them, then phrase the goal precisely.
5. For files, choose the mode before opening; loop with `EOF()` for sequential, `SEEK` for random; close every file.
6. For exceptions, list what can fail, catch the most specific first, and provide a real recovery action.
