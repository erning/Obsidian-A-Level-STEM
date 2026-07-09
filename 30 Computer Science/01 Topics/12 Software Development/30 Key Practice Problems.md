---
title: Software Development Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[Software Development](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - practice
---

# Software Development Key Practice Problems

Work through these without looking at the solutions. Most prompts are scenario-based, so aim to justify your answer against the alternatives rather than just naming a term. For design questions, draw the chart and label every flag before writing any pseudocode.

Worked solutions are in [Key Practice Solutions](31%20Key%20Practice%20Solutions.md).

## A. Life cycle

1. A bank is commissioning a new payroll system for a stable business with fixed, fully documented requirements and strict regulation. State which life cycle model is most suitable and justify it against the iterative model.

2. A two-developer team has four weeks to build a GUI prototype for a client who wants to see and react to early versions. Name the most suitable life cycle model and justify it against the waterfall model.

3. Name the five stages of the development life cycle and state one deliverable produced at each stage.

4. Distinguish a test strategy from a test plan. For the test plan, state two items that each individual test entry typically contains.

## B. Design tools

5. A library program reads a member ID and a book ID, checks whether the book is available, and if so issues the book to the member and prints a receipt. Draw a structure chart showing the modules and all parameter flags. Include a control flag for availability.

6. Using your structure chart from question 5, derive pseudocode for the module that issues the book. List the parameters and state whether each is passed by value or by reference, giving a reason.

7. A program inputs a list of temperatures and outputs the maximum, minimum, and average. Draw a structure chart showing the modules and label every data flag.

8. From your chart in question 7, derive pseudocode for the module that finds the maximum temperature.

9. A vending machine starts in the `Idle` state. Inserting a coin moves it to the `CoinInserted` state; selecting a product dispenses the product and returns it to `Idle`; pressing cancel in `CoinInserted` refunds the coin and returns to `Idle`. Draw a state-transition diagram and list the states and the events that trigger each transition.

10. A document editor has states `Closed`, `Open`, `Editing`, and `Saved`. Open takes `Closed` to `Open`; begin edit takes `Open` to `Editing`; save takes `Editing` to `Saved`; close takes `Open` or `Saved` back to `Closed`. Draw the state-transition diagram. State what happens if save is attempted from `Closed`.

## C. Errors and testing

11. For each fault, classify it as syntax, logic, or run-time and give a one-line reason.

    (a) `IF x > 0 OUTPUT "positive"` written with a missing `THEN`.
    (b) `Total ← Total - Score` where the program should add the score.
    (c) `Result ← Data(Index)` when `Index` is larger than the array size.
    (d) The keyword `OUTPUT` is misspelt as `OUTPIT`.

12. A developer has the source code of a single module and wants to exercise every statement and branch in it. Name the testing method and justify it against black-box testing.

13. A module calls a sub-module that has not yet been coded. State the testing method used to test the calling module, and explain how the placeholder works.

14. Distinguish alpha testing from beta testing. State which organisation performs each, and name one situation where each is used.

15. A registration form accepts a discount percentage in the range 5 to 50 inclusive. Give one value for each of normal, abnormal, extreme, and boundary test data, and state the expected result for each.

16. A field stores a year of birth as an integer between 1900 and 2010 inclusive. Give two boundary test values that should be rejected and two that should be accepted, with reasons.

17. State what a walkthrough is and contrast it with a dry run. Name who is involved in each and when each is used.

## D. Maintenance

18. Classify each post-release change as perfective, adaptive, or corrective, with a one-line reason.

    (a) A formula that computed tax using the wrong rate is corrected.
    (b) A search screen is redesigned so results load noticeably faster.
    (c) The program is updated to run under a new version of the operating system.
    (d) A graph feature is added to an existing report.

19. A school's student records program, already in use, must be changed because the government has introduced a new attendance code set. Classify the maintenance type and justify it.

20. Explain why correcting a previously unnoticed crash is classified as corrective rather than adaptive, even though the change is made after release.
