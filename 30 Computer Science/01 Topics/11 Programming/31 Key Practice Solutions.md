---
title: Programming Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[Programming](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - solutions
---

# Programming Key Practice Solutions

Full solutions to the [Key Practice Problems](30%20Key%20Practice%20Problems.md) for AS section 11 Programming. Pseudocode follows the CAIE 9618 Pseudocode Guide, including the assignment arrow ←.

## A. Variables and expressions

**1.**

```pseudocode
CONSTANT VatRate = 0.20

DECLARE Price : REAL
DECLARE Total : REAL

OUTPUT "Enter the price: "
INPUT Price
Total ← Price + Price * VatRate
OUTPUT "Total is ", Total
```

The constant is declared once and never reassigned. Multiplication binds more tightly than addition, so `Price * VatRate` is computed first, then added to `Price`.

**2.**

```pseudocode
DECLARE A, B, Quotient, Remainder : INTEGER

A ← 17
B ← 5
Quotient  ← A DIV B   // 3
Remainder ← A MOD B   // 2
OUTPUT "Quotient ", Quotient, " Remainder ", Remainder
```

`DIV` gives the integer quotient and `MOD` gives the remainder after integer division.

**3.**

```pseudocode
DECLARE Age : INTEGER
DECLARE IsMember : BOOLEAN
DECLARE CanEnter : BOOLEAN

INPUT Age
INPUT IsMember
CanEnter ← (Age >= 18) AND (IsMember = TRUE)
OUTPUT CanEnter
```

The parentheses make the two comparisons explicit before `AND` combines them. The result is a single BOOLEAN value stored in `CanEnter`.

**4.**

```pseudocode
DECLARE Name : STRING

OUTPUT "Enter your name: "
INPUT Name
OUTPUT "Hello, ", Name, " Your name has ", LENGTH(Name), " characters"
```

`LENGTH` is a string function supplied by the question, so it is called directly rather than implemented.

**5.** Declaring a variable fixes its name and data type so the compiler or interpreter can allocate storage and type-check later use. Initialising it gives it a defined starting value; reading a variable before it is initialised is undefined behaviour and a common source of faults. In pseudocode the assignment arrow ← stores a value into a variable, whereas `=` is the relational equals operator used inside a comparison, for example `IF Count = 0 THEN`. The two must not be confused.

## B. Selection

**6.**

```pseudocode
DECLARE Age : INTEGER

OUTPUT "Enter age: "
INPUT Age

IF Age < 5 THEN
    OUTPUT "Free"
ELSE
    IF Age >= 65 THEN
        OUTPUT "Free"
    ELSE
        IF Age <= 17 THEN
            OUTPUT "Half price"
        ELSE
            OUTPUT "Full price"
        ENDIF
    ENDIF
ENDIF
```

The two free cases share a category but are tested separately, each with its own simple comparison. The branches are checked in an order that prevents one condition from capturing a value meant for a later branch.

**7.**

```pseudocode
DECLARE Code : INTEGER

OUTPUT "Enter code 1-3: "
INPUT Code

CASE OF Code
    1 : OUTPUT "Water"
    2 : OUTPUT "Juice"
    3 : OUTPUT "Cola"
    OTHERWISE OUTPUT "Invalid code"
ENDCASE
```

`CASE OF` dispatches on the single value `Code`, and `OTHERWISE` catches every value that does not match a listed case.

**8.**

```pseudocode
DECLARE Username, Password : STRING

OUTPUT "Enter username: "
INPUT Username
OUTPUT "Enter password: "
INPUT Password

IF Username = "admin" AND Password = "letmein" THEN
    OUTPUT "Access granted"
ELSE
    OUTPUT "Access denied"
ENDIF

OUTPUT "Session ended"
```

The final `OUTPUT` sits after `ENDIF` at the same level as the `INPUT` statements, so it runs regardless of which branch the `IF` took.

**9.**

```pseudocode
DECLARE Code : INTEGER

CASE OF Code
    1 : OUTPUT "Add"
    2 : OUTPUT "Edit"
    3 : OUTPUT "Delete"
    OTHERWISE OUTPUT "Unknown"
ENDCASE
```

A nested `IF` that tests one variable for equality against a list of values collapses naturally into a `CASE`, with `OTHERWISE` replacing the innermost `ELSE`.

## C. Loops

**10.** Best loop for each task:

| Task | Loop | Reason |
|---|---|---|
| (a) 7 times 1 to 7 times 12 | `FOR` | The count, 12, is fixed and known in advance |
| (b) repeat until 1 to 100 | `REPEAT` | The prompt must appear at least once, so the body runs at least once |
| (c) process a possibly empty file | `WHILE` | The file may be empty, so the body may need to run zero times |

**11.**

```pseudocode
DECLARE i : INTEGER

FOR i ← 1 TO 10
    OUTPUT i, " squared is ", i * i
NEXT i
```

The counter `i` takes each integer from 1 to 10 inclusive, and the body uses it both as the operand and as part of the output.

**12.**

```pseudocode
DECLARE Password : STRING

REPEAT
    OUTPUT "Enter the password: "
    INPUT Password
UNTIL Password = "Open123"
```

`REPEAT` runs the body first, then tests. The loop repeats while the condition is FALSE and stops when it becomes TRUE, so the user is always prompted at least once.

**13.**

```pseudocode
DECLARE Value, Total : INTEGER

Total ← 0
OUTPUT "Enter a value: "
INPUT Value

WHILE Total < 100
    Total ← Total + Value
    OUTPUT "Enter a value: "
    INPUT Value
ENDWHILE

OUTPUT "Total is ", Total
```

The guard `Total < 100` is tested before the body, so if `Total` already meets or exceeds 100 the body does not run at all.

**14.** A `FOR` loop fits best because exactly 25 marks are entered, a fixed count known in advance.

```pseudocode
DECLARE Mark, PassCount, i : INTEGER

PassCount ← 0
FOR i ← 1 TO 25
    OUTPUT "Enter mark: "
    INPUT Mark
    IF Mark >= 50 THEN
        PassCount ← PassCount + 1
    ENDIF
NEXT i

OUTPUT "Passes: ", PassCount
```

The accumulator `PassCount` is initialised to 0 before the loop and is incremented inside a selection that tests each mark.

## D. Procedures and functions

**15.**

```pseudocode
PROCEDURE Swap(BYREF A : INTEGER, BYREF B : INTEGER)
    DECLARE Temp : INTEGER
    Temp ← A
    A ← B
    B ← Temp
ENDPROCEDURE

DECLARE X : INTEGER
DECLARE Y : INTEGER

X ← 5
Y ← 9
CALL Swap(X, Y)
OUTPUT "X is ", X, " Y is ", Y   // X is 9 Y is 5
```

The parameters must be `BYREF` because the procedure must change the caller's variables `X` and `Y`. By-value parameters would receive copies, the swap would affect only the copies, and `X` and `Y` in the caller would stay as 5 and 9. The temporary variable `Temp` holds one value while the other is overwritten; without it the first value would be lost.

**16.**

```pseudocode
FUNCTION Average(A : REAL, B : REAL) RETURNS REAL
    RETURN (A + B) / 2
ENDFUNCTION

DECLARE P, Q, R, Mean : REAL

P ← 6.0
Q ← 8.0
R ← 10.0

Mean ← Average(Average(P, Q), R)
OUTPUT "Average is ", Mean   // Average is 8.0
```

The inner call `Average(P, Q)` is evaluated first and returns 7.0, which is then passed as the first argument to the outer call `Average(7.0, R)`. A function call is replaced by its return value, so it can appear inside a larger expression.

**17.**

| Term | Identification |
|---|---|
| Header | `FUNCTION Discount(Price : REAL, Percent : REAL) RETURNS REAL` |
| Interface | Name `Discount`, two REAL parameters, returns REAL |
| Parameter | `Price` and `Percent` |
| Argument | `200.0` and `10.0` |
| Return value | the result of `Price * Percent / 100`, here 20.0 |

The return value replaces the whole call, so `Saved ← Discount(200.0, 10.0)` becomes `Saved ← 20.0`.

**18.** Two reasons to move a repeated block into a procedure or function: it removes duplication, so a fix or change is made in one place only and cannot drift between copies; and it gives the block a name that expresses its purpose, which makes the calling code shorter and easier to read.

**19.**

```pseudocode
CONSTANT TipPercent = 15

FUNCTION Tip(Price : REAL) RETURNS REAL
    RETURN Price * TipPercent / 100
ENDFUNCTION

DECLARE BillA, BillB, BillC, Amount : REAL

INPUT BillA
INPUT BillB
INPUT BillC

Amount ← Tip(BillA)
OUTPUT Amount
Amount ← Tip(BillB)
OUTPUT Amount
Amount ← Tip(BillC)
OUTPUT Amount
```

The percentage is now a single constant, so changing the rate needs only one edit. The function has one clear purpose and is used inside an expression, which is the correct way to call a function.

**20.**

```pseudocode
PROCEDURE Greet(Name : STRING)
    OUTPUT "Hello, ", Name
ENDPROCEDURE

CALL Greet("Sam")
```

The parameter `Name` is passed by value, which is the default, because the procedure only reads it and does not need to change anything in the caller. The argument `"Sam"` is supplied in the `CALL`.
