---
title: Programming Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[Programming](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - worked-examples
---

# Programming Worked Examples

These worked examples show how to turn a design into correct pseudocode for AS section 11. Each example follows the same pattern: a CAIE-style prompt, a full solution in official notation, and a short check of the points examiners look for. Attempt each prompt on paper before reading the solution. All pseudocode uses the CAIE Pseudocode Guide notation, including the assignment arrow ←.

## Source Route

- Syllabus 9618 AS section 11 Programming.
- 11.1 Programming Basics - constants, variables, assignment, expressions, input/output, built-in functions.
- 11.2 Constructs - `IF` with `ELSE` and nesting, `CASE`, and the three loop types with justification.
- 11.3 Structured Programming - procedures, functions, parameter passing and terminology.
- Assessed in Paper 2.

## Example 1: Constants, variables and an expression

**Prompt.** A program computes the area of a circle. Declare a constant `Pi` set to 3.14159, declare a variable `Radius` of type REAL, input the radius from the user, compute the area, and output it.

**Solution.**

```pseudocode
CONSTANT Pi = 3.14159

DECLARE Radius : REAL
DECLARE Area : REAL

OUTPUT "Enter the radius: "
INPUT Radius
Area ← Pi * Radius * Radius
OUTPUT "Area is ", Area
```

**Check.** The constant is declared once with `CONSTANT` and is never reassigned. Both variables are declared with their types before use, and `Radius` is given a value by `INPUT` before it appears in the expression. The assignment uses the ← arrow, not `=` and not the two characters `<-`.

## Example 2: Nested IF for a grading rule

**Prompt.** A mark is graded A for 80 or above, B for 60 to 79, C for 40 to 59, and Fail below 40. Write pseudocode that inputs the mark and outputs the grade, using nested `IF` statements.

**Solution.**

```pseudocode
DECLARE Mark : INTEGER

OUTPUT "Enter the mark: "
INPUT Mark

IF Mark >= 80 THEN
    OUTPUT "Grade A"
ELSE
    IF Mark >= 60 THEN
        OUTPUT "Grade B"
    ELSE
        IF Mark >= 40 THEN
            OUTPUT "Grade C"
        ELSE
            OUTPUT "Fail"
        ENDIF
    ENDIF
ENDIF
```

**Check.** The boundaries are tested in descending order, so each `IF` only needs one comparison. An ascending test would match `Mark >= 40` first and never reach grade A. Every `IF` has a matching `ENDIF`.

## Example 3: CASE for a menu

**Prompt.** A menu offers options 1 to 4: 1 prints "New game", 2 prints "Load game", 3 prints "Settings", 4 prints "Quit". Any other value prints "Invalid choice". Write pseudocode using a `CASE` statement.

**Solution.**

```pseudocode
DECLARE Choice : INTEGER

OUTPUT "Enter choice 1-4: "
INPUT Choice

CASE OF Choice
    1 : OUTPUT "New game"
    2 : OUTPUT "Load game"
    3 : OUTPUT "Settings"
    4 : OUTPUT "Quit"
    OTHERWISE OUTPUT "Invalid choice"
ENDCASE
```

**Check.** `CASE OF` dispatches on one value and each path lists a value with its action. `OTHERWISE` catches every value that does not match a listed case, so no separate `IF` check is needed afterwards. `ENDCASE` closes the structure.

## Example 4: Choose and write the right loop

**Prompt.** For each task below, choose the loop type (`FOR`, `REPEAT` or `WHILE`) that fits best, justify the choice, and write the pseudocode.

(a) Print the word "Hello" exactly 5 times.
(b) Keep asking the user for a password until they enter a non-empty string.
(c) Read and count positive rainfall readings until the sentinel value 0 is entered. The sentinel 0 is not counted, and 0 could be the very first value entered.

**Solution.**

| Task | Loop | Reason |
|---|---|---|
| (a) | `FOR` | The count is fixed and known in advance |
| (b) | `REPEAT` | The prompt must be shown at least once, so the body must run at least once |
| (c) | `WHILE` | The sentinel may appear first, so the body may need to run zero times |

```pseudocode
// (a) Count known in advance
DECLARE i : INTEGER
FOR i ← 1 TO 5
    OUTPUT "Hello"
NEXT i

// (b) Body must run at least once
DECLARE Password : STRING
REPEAT
    OUTPUT "Enter a password: "
    INPUT Password
UNTIL LENGTH(Password) > 0

// (c) Body may run zero times
DECLARE Reading, Count : INTEGER
Count ← 0
OUTPUT "Enter a reading, 0 to stop: "
INPUT Reading
WHILE Reading > 0
    Count ← Count + 1
    OUTPUT "Enter a reading, 0 to stop: "
    INPUT Reading
ENDWHILE
OUTPUT "Count is ", Count
```

**Check.** Use `FOR` when the count is fixed, `REPEAT` when the body must run at least once before the condition can be tested, and `WHILE` when the body may need to run zero times. A `WHILE` test is checked before the body; a `REPEAT` test is checked after. `LENGTH` is a string function that the question supplies, so it is called directly.

## Example 5: Procedure with a BYREF parameter

**Prompt.** Write a procedure `Swap` that exchanges the values of two integer variables held by the caller. The caller's variables must change. Call the procedure with two variables `X` and `Y`, then output both.

**Solution.** `Swap` must change the caller's variables, so both parameters are passed by reference using `BYREF`. A by-value parameter would swap only copies and leave the originals unchanged.

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

**Check.** The temporary variable `Temp` holds one value while the other is overwritten; without it the first value would be lost. `BYREF` is essential: had `A` and `B` been by value, `X` and `Y` in the caller would still be 5 and 9.

## Example 6: Function used in an expression

**Prompt.** Write a function `Larger` that takes two integers and returns the larger. Then use it in an expression to find the largest of three values `First`, `Second` and `Third`, assigning the result to `Biggest`.

**Solution.** A function returns a single value through `RETURN`, so its call is replaced by that value and can sit inside an expression.

```pseudocode
FUNCTION Larger(A : INTEGER, B : INTEGER) RETURNS INTEGER
    IF A > B THEN
        RETURN A
    ELSE
        RETURN B
    ENDIF
ENDFUNCTION

DECLARE First, Second, Third, Biggest : INTEGER

First  ← 14
Second ← 27
Third  ← 9

Biggest ← Larger(Larger(First, Second), Third)
OUTPUT "Largest is ", Biggest   // Largest is 27
```

**Check.** The inner call `Larger(First, Second)` is evaluated first and returns 27; that value is then passed as the first argument to the outer call `Larger(27, Third)`, which returns 27. A function must always reach a `RETURN` on every path.

## Example 7: Identify the terminology

**Prompt.** Consider this function definition and its call:

```pseudocode
FUNCTION Area(Length : REAL, Width : REAL) RETURNS REAL
    RETURN Length * Width
ENDFUNCTION

DECLARE Result : REAL
Result ← Area(3.0, 4.5)
```

Identify the function header, the interface, each parameter, each argument, and the return value.

**Solution.**

| Term | Identification |
|---|---|
| Header | `FUNCTION Area(Length : REAL, Width : REAL) RETURNS REAL` - the first line, giving name, parameters and return type |
| Interface | Name `Area`, two REAL parameters, returns REAL - all a caller needs to use it |
| Parameter | `Length` and `Width` - the variables named in the header |
| Argument | `3.0` and `4.5` - the actual values passed in the call |
| Return value | the result of `Length * Width`, here 13.5, which replaces the call |

**Check.** Parameters live in the definition; arguments live in the call. The interface is the contract a caller relies on, and it does not include the body. The return value replaces the whole call expression, so `Result ← Area(3.0, 4.5)` becomes `Result ← 13.5`.

## Example 8: Refactor inefficient pseudocode

**Prompt.** The following pseudocode repeats the same markup calculation three times. Refactor it to remove the repetition using a function.

```pseudocode
DECLARE PriceA, PriceB, PriceC, Total : REAL
INPUT PriceA
INPUT PriceB
INPUT PriceC
Total ← PriceA + PriceA * 20 / 100
OUTPUT "With markup ", Total
Total ← PriceB + PriceB * 20 / 100
OUTPUT "With markup ", Total
Total ← PriceC + PriceC * 20 / 100
OUTPUT "With markup ", Total
```

**Solution.** The markup calculation and its output appear three times with only the price differing, so move the calculation into a function that takes the price and returns the marked-up total. The percentage is a fixed value, best declared once as a constant.

```pseudocode
CONSTANT MarkupPercent = 20

FUNCTION WithMarkup(Price : REAL) RETURNS REAL
    RETURN Price + Price * MarkupPercent / 100
ENDFUNCTION

DECLARE PriceA, PriceB, PriceC, Total : REAL

INPUT PriceA
INPUT PriceB
INPUT PriceC

Total ← WithMarkup(PriceA)
OUTPUT "With markup ", Total
Total ← WithMarkup(PriceB)
OUTPUT "With markup ", Total
Total ← WithMarkup(PriceC)
OUTPUT "With markup ", Total
```

**Check.** The percentage now lives in one constant, so changing the markup rate needs only one edit. The function has a single clear purpose and is called inside an expression, which is the correct use of a function. Each call site is shorter and the intent is named.

## Study Routine

1. Read the prompt and list the constants, variables and types you need before writing any code.
2. Pick the construct by the situation: `IF` for a choice, `CASE` for dispatch on one value, `FOR` for a known count, `REPEAT` when the body must run at least once, `WHILE` when it may run zero times.
3. Use `BYREF` only when the caller's variable must change; otherwise pass by value.
4. Use a function when the point is to compute and return one value; use a procedure for an action.
5. After writing, trace with sample values to confirm every arrow, condition and keyword.
