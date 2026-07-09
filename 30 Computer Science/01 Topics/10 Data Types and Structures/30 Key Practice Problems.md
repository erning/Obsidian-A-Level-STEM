---
title: Data Types and Structures Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[Data Types and Structures](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - practice
---

# Data Types and Structures Key Practice Problems

These problems cover the AS section 10 syllabus: data types, records, arrays, sorting and searching, text files, and the abstract data types stack, queue and linked list. Attempt every problem on paper before checking the [solutions file](31%20Key%20Practice%20Solutions.md).

## A. Data types and records

1. A vet surgery records, for each pet: pet name, owner name, age in months, weight in kilograms, species as a single letter, date of last visit, and whether the pet is vaccinated. Choose a suitable data type for each field and justify each choice.

2. Define a record type `Employee` with fields `Name` of type STRING, `HoursWorked` of type INTEGER, and `HourlyRate` of type REAL. Declare a variable of this type and write pseudocode to input all fields from the user and output the total pay.

3. State two reasons why a programmer would use a record instead of separate variables for the related fields of one entity.

4. Define a record type `Product` with fields `Code` (INTEGER), `Name` (STRING), `Price` (REAL) and `InStock` (BOOLEAN). Write pseudocode that declares a `Product`, assigns values, and then outputs the product only if its `InStock` value is TRUE.

5. A date of birth is stored as a DATE. Give one advantage of using the DATE data type instead of storing the date as a STRING.

## B. Arrays

6. Declare a 1D array `Temperatures` that can hold 7 real values, one per day of the week. Write pseudocode to input the 7 values and then output the highest temperature.

7. A 1D array `Scores` holds 20 integer marks. Write pseudocode to count how many marks are greater than or equal to 50.

8. A 2D array `Grid` has 4 rows and 5 columns of integers. Write pseudocode to input every element, row by row.

9. A 2D array `Marks[1:30, 1:6]` stores the marks of 30 students, each of whom sat 6 tests. Write pseudocode to compute and output the average mark for each student.

10. A 2D array `Seats[1:10, 1:20]` represents a theatre. Each element is TRUE if the seat is booked and FALSE otherwise. Write pseudocode to count the total number of booked seats.

## C. Sorting, searching and files

11. The array `A` holds `[3, 7, 1, 9, 4]`. Trace the first pass of a bubble sort into ascending order, showing the array after each comparison.

12. Write a complete bubble sort that sorts an array of 10 integers into descending order. State how many passes the algorithm will need in the worst case.

13. The array `B` holds `[6, 1, 4, 9, 2]`. Trace a linear search for the value `2`, showing each comparison and the final result.

14. Write pseudocode to search a 1D array of 50 integers for a target value, outputting the index of the first occurrence or a "not found" message.

15. A text file `sales.txt` stores one sales figure per line. Write pseudocode to read every figure, compute the total, and output it. State the purpose of the `EOF` function.

16. Write pseudocode that opens a text file for writing, writes the strings "Monday", "Tuesday" and "Wednesday" each on a new line, and then closes the file.

## D. Abstract data types

17. Describe the key features of a queue and state the order in which items are removed.

18. A stack is implemented using an array `Stack[1:50]` and a pointer `Top`. Write pseudocode for a `Pop` operation that removes and returns the top item, including a check for an empty stack.

19. Justify why a linked list, rather than an array, is a more suitable structure for a list of items that will frequently have items inserted and deleted from the middle.

20. Describe how a queue can be implemented using a 1D array with two pointers. Name the two pointers and explain how each is updated on enqueue and dequeue.
