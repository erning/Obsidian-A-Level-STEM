---
title: Further Programming Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/20 Further Programming/00 Overview|Further Programming]]"
status: active
tags:
  - computerscience/programming
  - solutions
---

# Further Programming Key Practice Solutions

Full solutions to the [[30 Key Practice Problems|Key Practice Problems]] for A Level section 20 Further Programming. Pseudocode follows the CAIE 9618 Pseudocode Guide, including the assignment arrow ←. OOP code is given in Java or Python; declarative code is in Prolog-style notation.

## A. Paradigms

**1.** Best paradigm for each task:

| Task | Paradigm | Justification |
|------|----------|---------------|
| (a) step through array elements | Low-level | The index register and base address are controlled directly with indexed addressing |
| (b) total a column from a sorted file | Imperative (procedural) | A running total is accumulated step by step in a loop |
| (c) simulate a library with books, members and loans | Object-oriented | The library is modelled as interacting objects that bundle data and behaviour |
| (d) reachability through flight connections | Declarative | Only connections matter; stating facts and rules and asking a goal fits naturally |

**2.** In an imperative program the programmer writes a sequence of statements that say *how* to solve the problem step by step, changing variables and calling procedures. In a declarative program the programmer states *what* is true (facts) and defines rules that relate facts, then poses a goal; the system reasons to satisfy it. Control flow is explicit in imperative code and implicit in declarative code.

**3.** Java and Python provide the variables, loops and procedures of imperative programming and also the classes, objects and inheritance of object-oriented programming, so a program can use both. An exam answer should still stay inside one paradigm because mixing styles (for example adding global variables to an OOP design) loses the clarity and the marks that naming the paradigm and its constructs earns.

**4.** Two characteristics of low-level code: each instruction corresponds to one machine instruction for a specific CPU, and the code controls registers and memory addresses directly. It is not portable to a different processor architecture.

**5.** One instruction per addressing mode:

```pseudocode
LDM #25         // Immediate: ACC ← 25
LDD [600]       // Direct:   ACC ← M[600]
LDI [600]       // Indirect: ACC ← M[M[600]]
LDX [600]       // Indexed:  ACC ← M[600 + IX]
JMP #2          // Relative: PC ← PC + 2
```

**6.** With direct addressing the operand is stored at the address given, so `LDD [600]` puts the value at address 600 into `ACC`. With indirect addressing the given address holds *another* address, and the operand is there, so `LDI [600]` reads address 600 to find an address, then reads from that address. Indirect addressing is useful when a pointer variable must be followed, for example walking a linked structure where each node stores the address of the next node.

## B. Object-oriented and declarative

**7.**

| Term | Definition |
|------|------------|
| Class | A blueprint defining the attributes and methods shared by a kind of object |
| Object | A single entity created from a class |
| Instance | One specific object of a class, with its own attribute values |
| Attribute | A named piece of data held by an object |
| Method | A procedure or function belonging to a class |
| Encapsulation | Bundling data and the code that acts on it together, and hiding internal detail from outside |

**8.** Inheritance is an "is-a" relationship: a subclass takes on the attributes and methods of a parent class, for example a `Manager` is a `Staff`. Containment (aggregation) is a "has-a" relationship: a class is built from other objects, for example a `Car` has an `Engine`. Inheritance models shared identity; containment models composition.

**9.** Java:

```java
class BankAccount {
    private double balance;            // encapsulated attribute

    public BankAccount(double openingBalance) {
        balance = openingBalance;
    }

    public double getBalance() {        // getter
        return balance;
    }

    public void setBalance(double value) {  // setter with validation
        if (value >= 0) {
            balance = value;
        }
    }
}
```

**10.** Java:

```java
class SavingsAccount extends BankAccount {     // inheritance
    private double rate;                       // 0.0 to 1.0

    public SavingsAccount(double openingBalance, double rate) {
        super(openingBalance);
        this.rate = rate;
    }

    public double getRate() {                   // getter
        return rate;
    }

    public void setRate(double value) {         // validated setter
        if (value >= 0 && value <= 1) {
            rate = value;
        }
    }

    @Override
    public void display() {                     // overridden method
        System.out.println("Balance " + getBalance() + " rate " + rate);
    }

    public static void main(String[] args) {
        SavingsAccount s = new SavingsAccount(500.0, 0.02);
        s.display();                            // Balance 500.0 rate 0.02
    }
}
```

**11.** A getter is a method that returns the value of a private attribute; a setter is a method that assigns a value to a private attribute. Making the attribute private and exposing it through a validated setter is preferred because the validation in the setter prevents invalid values (such as a negative balance) from ever being stored, while a public attribute can be set to any value directly with no protection. This is the practical form of encapsulation.

**12.**

```prolog
% Facts (given)
parent(tom, bob).
parent(tom, kay).
parent(bob, ann).
parent(kay, lee).

% Rule: X and Y are siblings if they share a parent and are different people
sibling(X, Y) :- parent(P, X), parent(P, Y), X \= Y.

% Rule: X and Y are cousins if a parent of X and a parent of Y are siblings
cousin(X, Y) :- parent(A, X), parent(B, Y), sibling(A, B), X \= Y.
```

The guard `X \= Y` stops a person being their own sibling. `cousin` reuses `sibling`, so the two parents being siblings is enough.

**13.**

```prolog
?- sibling(bob, kay).   % yes - both have parent tom
?- cousin(ann, lee).    % yes - ann's parent bob and lee's parent kay are siblings
?- sibling(bob, bob).   % no - the X \= Y guard fails
```

**14.** A **fact** is a simple statement that a relationship holds, for example `parent(tom, bob).`. A **rule** is a conditional relationship `head :- body.` whose head is true when every part of the body can be satisfied. A **goal** is a query such as `?- sibling(bob, kay).`. To satisfy a goal, the system tries to match it against a fact, or against the head of a rule and then satisfy each part of that rule's body, binding variables as it goes.

## C. File processing

**15.** The mode is `READ` because the program only reads the file.

```pseudocode
DECLARE ProductName : STRING

OPENFILE "Stock.dat" FOR READ
WHILE NOT EOF("Stock.dat")
    READFILE "Stock.dat", ProductName
    OUTPUT ProductName
ENDWHILE
CLOSEFILE "Stock.dat"
```

**16.** The mode is `APPEND` because new data must be added without destroying what is already there.

```pseudocode
OPENFILE "Events.dat" FOR APPEND
WRITEFILE "Events.dat", NewEntry
CLOSEFILE "Events.dat"
```

`WRITE` would be wrong because opening for `WRITE` creates a new file and the existing log entries would be lost.

**17.**

```pseudocode
DECLARE Rec : AccountRecord

OPENFILE "Accounts.dat" FOR RANDOM
SEEK "Accounts.dat", Idx              // move pointer to this record address
GETRECORD "Accounts.dat", Rec         // read the fixed-length record
Rec.Balance ← 0
PUTRECORD "Accounts.dat", Rec         // write the updated record back
CLOSEFILE "Accounts.dat"
```

**18.** A serial file stores records in the order they arrive, with no key field, so the only way to find one record is to read from the start until it is found; it is used for log files and sensor data. A sequential file stores records sorted by a key field, so records can be read in key order and a record can be found by reading until its key is reached; it is used for payroll and batch processing on sorted data.

**19.** The three modes are `READ`, `WRITE` and `APPEND`. Opening for `WRITE` creates a new file: if the file already exists its contents are lost. Opening for `APPEND` keeps the existing data and adds new records at the end.

**20.** A random file is preferred when a single record must be found quickly without reading the whole file, for example looking up a customer by account number in a real-time system. `SEEK` moves the file pointer straight to the record's address, so the access time does not grow with the number of records, unlike a sequential search.

## D. Exception handling

**21.** An exception is an error condition raised while a program runs, for example division by zero or trying to open a file that does not exist. If an exception is not handled, the program crashes.

**22.** Handling is appropriate when a failure is possible but not normal and there is a real recovery action, for example prompting again when a user types a non-numeric value. Catching an exception broadly would be a mistake when it hides a real bug, for example wrapping a calculation that should never fail in a bare `catch (Exception)`: the fault is masked, the data looks correct, and the cause is hard to find. The rule is to catch the most specific exception first.

**23.**

```pseudocode
DECLARE Divisor, Result : REAL

TRY
    OUTPUT "Enter a divisor: "
    INPUT Divisor
    Result ← 100 / Divisor
    OUTPUT "Result is ", Result
CATCH DivByZero
    OUTPUT "Cannot divide by zero."
ENDTRY
```

**24.** Java:

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
        } catch (ArithmeticException e) {    // most specific, handled first
            System.out.println("Cannot divide by zero.");
        } catch (Exception e) {              // general safety net
            System.out.println("Invalid input.");
        }
    }
}
```

Python:

```python
try:
    d = int(input("Enter a divisor: "))
    result = 100 / d
    print("100 /", d, "=", result)
except ZeroDivisionError:        # most specific, handled first
    print("Cannot divide by zero.")
except Exception:                # general safety net
    print("Invalid input.")
```

**25.** Reading a file whose name the user types is a good candidate for exception handling because the file may not exist or may be unreadable, which is outside the program's control; this is possible but not normal, and the program can recover. The kind of exception is a file-not-found (or `IOException`). A sensible recovery action is to report that the file could not be opened and let the user type the name again or cancel, rather than crash.
