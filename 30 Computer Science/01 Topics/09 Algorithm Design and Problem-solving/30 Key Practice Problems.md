---
title: Algorithm Design and Problem-solving Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[Algorithm Design and Problem-solving](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - practice
---

# Algorithm Design and Problem-solving Key Practice Problems

These problems cover the core skills of 9618 AS Section 9. Attempt them on paper before reading [the solutions](31%20Key%20Practice%20Solutions.md). The aim is full written reasoning and correct pseudocode, not just naming terms. No answers are given here on purpose: the point is active recall, decomposition, and writing the official pseudocode with the assignment arrow `←`.

## A. Abstraction and decomposition

1. A vending machine has a serial number, a manufacturer, a coin slot diameter, a button layout, a coin credit total, and the price of each selected drink. The program must decide whether the inserted coins are enough to release a drink. Build an abstract model by listing only the details that matter for this decision, and stating which real details you drop.

2. A library book has a title, author, ISBN, publisher, year, page count, cover colour, and shelf position. The system must work out whether a book is overdue. Build an abstract model by keeping only the data that affects the answer, and crossing out the rest.

3. Decompose a "student grade report" program into modules. The program must read a student's name and five marks, compute the average, decide a grade from the average, and print the report. Give a module list stating the type of each (procedure or function) and give the identifier table.

4. Decompose an "online shopping cart" program into modules. The program must add items to a cart, remove an item, compute the total price, apply a discount if the total exceeds a threshold, and print the receipt. Give a module list with types.

5. State the difference between a procedure and a function, and explain why the choice matters when you decompose a problem into modules.

## B. Pseudocode basics

6. Write an identifier table (identifier, data type, description) for a program that converts a temperature in Celsius to Fahrenheit using $F = C \times \frac{9}{5} + 32$.

7. Write pseudocode that inputs a number and outputs "Positive", "Negative", or "Zero".

8. Write pseudocode that uses a `FOR` loop to input ten numbers and output their total.

9. Write pseudocode that uses a `WHILE` loop to keep asking for a password until the user enters the value "Unlock".

10. Write pseudocode that uses a `REPEAT ... UNTIL` loop to read ages and count them, stopping when a sentinel value of -1 is entered. State why `REPEAT` rather than `WHILE` is acceptable here.

## C. Converting between notations

11. The following structured English describes an algorithm. Convert it to pseudocode.
    > Set Total to 0. Read a Number. While Number is not equal to 0, add Number to Total and read the next Number. When the loop ends, output Total.

12. The following flowchart processes a sale. Convert it to pseudocode.
    ```text
            ( Start )
                |
       / INPUT Price /         ← parallelogram
                |
       < Price > 100 ? >       ← decision (Yes left, No right)
         /            \
       Yes            No
        |              |
   Discount ←          |
   Price * 0.1         |
        |              |
        \______________/
                |
       / OUTPUT Price /        ← parallelogram
                |
            ( End )
    ```

13. Describe, symbol by symbol, the flowchart you would draw for the following pseudocode.
    ```pseudocode
    INPUT Age
    IF Age >= 18 THEN
        OUTPUT "Adult"
    ELSE
        OUTPUT "Minor"
    ENDIF
    ```

14. Express the following algorithm in all three notations: input two numbers, output the larger of the two. Give structured English, a flowchart described in words, and pseudocode.

15. A flowchart has a diamond labelled "Score >= 50 ?" with one Yes branch leading to an output box "Pass" and one No branch leading to an output box "Fail", both then joining to an End. State which construct this represents and write the equivalent pseudocode.

## D. Refinement and logic

16. Refine the following problem in levels down to implementable pseudocode. "Read the marks of a class (size not known, ended by a sentinel of -1). Output the class average and how many students scored 50 or above." Show Level 0 (major steps), Level 1 (each step refined), and Level 2 (pseudocode).

17. Refine the following problem in levels down to pseudocode. "Read 20 numbers into an array, then output the smallest value and the position where it first occurred." Show Level 0 and Level 2.

18. Write a logic statement, using explicit parentheses, that is true when a student passes: the mark is 50 or above AND the attendance is above 75.

19. Write a logic statement that is true when a shop applies an overtime rate: the hour is before 9 OR the hour is after 17.

20. The condition `Mark >= 50 AND Attendance > 75 OR HasMedical` could be read in two ways. State the two possible groupings using parentheses, and explain why writing the parentheses explicitly removes the ambiguity.

---

After finishing, check your working against [the solutions](31%20Key%20Practice%20Solutions.md) and re-attempt any question you could not complete in full.
