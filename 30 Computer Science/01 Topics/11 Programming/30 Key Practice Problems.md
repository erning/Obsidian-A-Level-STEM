---
title: Programming Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[Programming](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - practice
---

# Programming Key Practice Problems

These problems cover AS section 11 Programming: variables and expressions, selection with `IF` and `CASE`, the three loop types, and procedures and functions with parameter passing. Attempt every problem on paper before checking the [solutions file](31%20Key%20Practice%20Solutions.md). No answers appear in this file so it can be used for active recall.

## A. Variables and expressions

1. Declare a constant `VatRate` set to 0.20. Declare variables `Price` of type REAL and `Total` of type REAL. Input a price from the user, compute the total as the price plus VAT, and output the total.

2. Given two integer variables `A` set to 17 and `B` set to 5, write statements that assign the integer quotient to `Quotient` using `DIV`, assign the remainder to `Remainder` using `MOD`, and output both.

3. A program stores a user's age as an INTEGER and a membership flag as a BOOLEAN. Write an expression using `AND` that is TRUE only when the age is at least 18 AND the member flag is TRUE. Assign it to a BOOLEAN variable `CanEnter` and output the result.

4. Write pseudocode that inputs a student's name and outputs a greeting using the built-in function `LENGTH` to report how many characters the name contains. The `LENGTH` function is supplied by the question.

5. Explain why each variable must be declared and initialised before it is used in an expression, and state the difference between the assignment arrow ← and the equals sign `=` as it appears in a comparison.

## B. Selection

6. A bus fare is free for passengers aged under 5 or 65 and over, half price for ages 5 to 17, and full price otherwise. Write nested `IF` statements that input an age and output the fare category.

7. A vending machine code of 1 dispenses "Water", 2 dispenses "Juice", 3 dispenses "Cola", and any other code triggers an "Invalid code" message. Write pseudocode using a `CASE` statement.

8. A login system reads a username and a password. Access is granted only when the username equals "admin" AND the password equals "letmein". Otherwise access is denied. Write the `IF` statement and a final `OUTPUT "Session ended"` that must run regardless of the result.

9. Rewrite the following nested `IF` as an equivalent `CASE` statement on the value of `Code`.

```pseudocode
IF Code = 1 THEN
    OUTPUT "Add"
ELSE
    IF Code = 2 THEN
        OUTPUT "Edit"
    ELSE
        IF Code = 3 THEN
            OUTPUT "Delete"
        ELSE
            OUTPUT "Unknown"
        ENDIF
    ENDIF
ENDIF
```

## C. Loops

10. For each task below, state which loop type (`FOR`, `REPEAT` or `WHILE`) is the best fit and justify your choice. No code is required.
    (a) Print the multiplication table for 7 from 7 times 1 up to 7 times 12.
    (b) Keep prompting the user for a number until they enter a value between 1 and 100 inclusive.
    (c) Read and process records from a file that may be empty when opened.

11. Write a `FOR` loop that outputs the squares of the integers from 1 to 10 inclusive.

12. Write a `REPEAT ... UNTIL` loop that asks the user to enter a password and repeats until the password equals "Open123".

13. Write a `WHILE ... ENDWHILE` loop that reads integers and adds them to a running total, stopping as soon as the total reaches or exceeds 100. The loop must not run at all if the total already starts at or above 100.

14. A teacher wants to enter exactly 25 marks and count how many are passes at 50 or above. Choose the most appropriate loop type, justify it, and write the pseudocode.

## D. Procedures and functions

15. Write a procedure `Swap` that exchanges the values of two integer variables held by the caller, so that the caller's variables change. Explain why the parameters must be passed by reference using `BYREF`. Show a `CALL` that uses variables `X` and `Y`.

16. Write a function `Average` that takes two REAL values and returns their average as a REAL. Then use it in an expression to compute and output the average of three values `A`, `B` and `C`.

17. For the function and call below, identify the header, the interface, each parameter, each argument, and the return value.

```pseudocode
FUNCTION Discount(Price : REAL, Percent : REAL) RETURNS REAL
    RETURN Price * Percent / 100
ENDFUNCTION

DECLARE Saved : REAL
Saved ← Discount(200.0, 10.0)
```

18. State two reasons why a programmer would move a repeated block of statements into a procedure or function rather than copy and paste the block each time.

19. The following pseudocode computes a 15 percent tip three times by repeating the formula. Refactor it to use a function that takes the price and returns the tip. Declare the percentage as a constant.

```pseudocode
INPUT BillA
INPUT BillB
INPUT BillC
Tip ← BillA * 15 / 100
OUTPUT Tip
Tip ← BillB * 15 / 100
OUTPUT Tip
Tip ← BillC * 15 / 100
OUTPUT Tip
```

20. Write a procedure `Greet` that takes a single STRING parameter by value called `Name` and outputs "Hello, " followed by the name. Then write the `CALL` statement that invokes it with the argument "Sam".
