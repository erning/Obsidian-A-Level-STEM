---
title: Data Representation Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/13 Data Representation/00 Overview|Data Representation]]"
status: active
tags:
  - computerscience/data
  - practice
---

# Data Representation Key Practice Problems

These problems cover the core skills of 9618 A Level section 13. Attempt them on paper before reading [[30 Computer Science/01 Topics/13 Data Representation/31 Key Practice Solutions|the solutions]]. No answers are given here on purpose: the point is active recall and full written working. Assume an 8-bit mantissa and a 4-bit exponent, both in two's complement, unless a question says otherwise.

## A. User-defined types

1. A traffic light controller has exactly four states: red, red-amber, green, amber. Design a suitable user-defined data type in pseudocode and show how a variable of this type is declared and assigned.
2. A car rental firm stores, for each vehicle, its registration number, daily hire rate, mileage, and whether it is currently rented. Design a composite data type for a vehicle and show one field access.
3. A program needs to track the memory address of a previously declared `REAL` variable and update that variable indirectly. Declare a suitable pointer type and show one dereference.
4. For each scenario below, name the most appropriate user-defined data type (enumerated, pointer, set, record, or class/object) and give one reason.
    - (a) The seven valid responses to a multiple-choice question, A to G.
    - (b) The unordered collection of tags a user has applied to a photo.
    - (c) A customer's name, address, and balance, together with the procedures that debit and credit the account.

## B. File organisation and access

5. For each scenario, name the most suitable file organisation and the access method it would use, with a one-line reason.
    - (a) A payroll file sorted on the key field EmployeeID, processed once a month.
    - (b) A point-of-sale terminal appending each sale to the end of the day's log.
    - (c) A hospital system looking up one patient's record by patient number.
6. State which access methods (sequential, direct, both, or neither) are valid for each file organisation: serial, sequential, random.
7. A random file uses `address = AccountNo MOD 13` with 13 slots. Compute the slot for each of the keys $1042$, $2071$, $3158$, $4203$, and identify any collision.
8. Using the file from question 7, describe two methods for resolving the collision you found, and state how the system later retrieves one of the colliding records.

## C. Floating-point conversion

9. Convert the floating-point value $01100000\;0011$ to denary (8-bit mantissa, 4-bit exponent).
10. Convert the floating-point value $01010000\;0010$ to denary.
11. Convert the floating-point value $10100000\;0011$ to denary. Note that the mantissa is negative.
12. Convert the denary value $3.25$ to a 12-bit floating-point number (8-bit mantissa, 4-bit exponent), giving the normalised result.
13. Convert the denary value $-2.5$ to a 12-bit floating-point number (8-bit mantissa, 4-bit exponent).
14. A 16-bit format uses a 10-bit mantissa and a 6-bit exponent. Another uses a 12-bit mantissa and a 4-bit exponent. For each format, state whether range or precision is favoured, and explain why.

## D. Normalisation and errors

15. Normalise the value $00011000\;0101$ (8-bit mantissa, 4-bit exponent). Show the mantissa shift and the exponent adjustment.
16. Normalise the value $11011000\;0101$ (8-bit mantissa, 4-bit exponent). Note that this is a negative number.
17. Explain two reasons why floating-point numbers are normalised before storage.
18. For each situation, name the floating-point error that occurs and explain it in one sentence.
    - (a) Adding $10^{-45}$ to $0$ in a system whose smallest normalised magnitude is about $10^{-38}$.
    - (b) Multiplying two large numbers so the result needs an exponent of $+130$ in a field that only holds up to $+127$.
    - (c) Storing $0.2_{10}$ in a binary mantissa.
19. Give one example of how rounding errors can accumulate across many arithmetic operations, and state one practical consequence for programmers.
20. A classmate claims that "a wider exponent field always gives more accurate answers". Explain why this claim is wrong, using the mantissa and exponent trade-off.

---

After finishing, check your working against [[30 Computer Science/01 Topics/13 Data Representation/31 Key Practice Solutions|the solutions]] and re-attempt any question you could not complete in full.
