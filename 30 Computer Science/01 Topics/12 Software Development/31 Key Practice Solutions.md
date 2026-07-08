---
title: Software Development Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/12 Software Development/00 Overview|Software Development]]"
status: active
tags:
  - computerscience/programming
  - solutions
---

# Software Development Key Practice Solutions

These solutions correspond to [[30 Computer Science/01 Topics/12 Software Development/30 Key Practice Problems|Key Practice Problems]]. Where a question asks for a diagram, draw your own first and then compare.

## A. Life cycle

### Problem 1

The **waterfall** model is most suitable. The requirements are fixed, fully documented, and regulated, which is exactly what waterfall assumes: each stage is completed and signed off before the next begins, with heavy up-front documentation, clear milestones, and full traceability for auditors. For a safety- and finance-critical payroll this control is essential.

The iterative model is less suitable here. Iterative revisits analysis and design between cycles and produces partial versions, which suits changing requirements; but for a regulated payroll that control and the signed-off documentation would be weakened. Because the requirements do not change, the early-feedback advantage of iterative is wasted on this project.

### Problem 2

The **RAD** (Rapid Application Development) model is most suitable. RAD emphasises speed and user feedback, using prototyping, reusable components, and very short cycles with heavy user involvement. The client wants to see and react to early versions, which RAD produces directly, and the four-week deadline fits RAD's short cycles.

Waterfall is unsuitable because it produces working code only near the end after every stage is signed off, and it assumes fixed requirements. The client wants to react to prototypes, so waiting for a late finished build would defeat the purpose of the prototype.

### Problem 3

- **Analysis** - study the problem and agree what the program must do. Deliverable: a requirements specification.
- **Design** - decide how to meet the requirements: data structures, modules, algorithms, interfaces. Deliverable: a design such as a structure chart and pseudocode.
- **Coding** - translate the design into a programming language. Deliverable: source code.
- **Testing** - run the code with planned data to expose and correct faults. Deliverable: tested code plus a test log.
- **Maintenance** - keep the program working and useful after release. Deliverable: updated releases.

### Problem 4

A **test strategy** is the overall approach: the scope of testing, the methods to be used, who tests what, and the order of testing (unit, then integration, then system, then acceptance). A **test plan** is the concrete schedule of individual tests derived from the strategy.

Two items each test-plan entry typically contains: the **test data** to use and the **expected result**. (A pass/fail verdict and the actual result are recorded when the test is run.)

## B. Design tools

### Problem 5

```
                  +------------------+
                  |  LibraryProgram  |
                  +------------------+
                    /      |      \
                   /       |       \
        +-----------+   +-----------+   +------------+
        | InputData |   | IssueBook |   | PrintPay   |
        +-----------+   +-----------+   +------------+
                            |  BookID
                            v
                    +---------------+
                    | CheckAvailab. |
                    +---------------+
```

Parameter and control flags:
- `InputData` returns `MemberID` and `BookID` (data flags) to the main program.
- `IssueBook` receives `MemberID` and `BookID`, calls `CheckAvailable`, and on the control flag `Available = TRUE` issues the book and returns `ReceiptData` (data flag).
- `CheckAvailable` receives `BookID` and returns the control flag `Available` (TRUE/FALSE).

### Problem 6

```pseudocode
PROCEDURE IssueBook(BYVALUE MemberID : INTEGER, BYVALUE BookID : INTEGER,
                    BYREF ReceiptData : STRING)
    DECLARE Available : BOOLEAN
    CALL CheckAvailable(BookID, Available)
    IF Available = TRUE THEN
        // mark book as issued to MemberID
        ReceiptData ← "Issued book " & BookID & " to member " & MemberID
        CALL PrintReceipt(ReceiptData)
    ELSE
        ReceiptData ← "Book not available"
    ENDIF
ENDPROCEDURE
```

`MemberID` and `BookID` are passed **by value** because they are only read inside the procedure. `ReceiptData` is passed **by reference** (`BYREF`) because the procedure must change it so the caller sees the result. `Available` is a local control flag returned from `CheckAvailable`.

### Problem 7

```
                 +-------------------+
                 |   TempAnalysis    |
                 +-------------------+
                   /      |      \
                  /       |       \
        +------------+ +-----------+ +-------------+
        | InputTemps | | Analyse   | | OutputStats |
        +------------+ +-----------+ +-------------+
                            |   |   \
                            |   |    \  Average
                  Max, Min  |   |     v
                  <---------+   +----------+
```

Parameter flags:
- `InputTemps` returns `Temps[]` and `Count` (data flags) to the main program.
- `Analyse` receives `Temps[]` and `Count`, and returns `Max`, `Min`, and `Average` (data flags).
- `OutputStats` receives `Max`, `Min`, and `Average`.

### Problem 8

```pseudocode
FUNCTION FindMax(Temps : ARRAY OF REAL, Count : INTEGER) RETURNS REAL
    DECLARE Max : REAL
    Max ← Temps[1]
    FOR i ← 2 TO Count
        IF Temps[i] > Max THEN
            Max ← Temps[i]
        ENDIF
    NEXT i
    RETURN Max
ENDFUNCTION
```

`Temps` and `Count` are passed by value because the function only reads them. The function returns `Max`, which corresponds to the `Max` data flag on the chart.

### Problem 9

```
   +------+  coin   +-------------+
   | Idle | ------> | CoinInserted|
   +------+          +-------------+
      ^              /          |
      |   refund    /           |  select
      +----------- (cancel)     v
      +------- dispense -------+
```

States: `Idle` and `CoinInserted`.

Events and transitions:
- `Idle --coin--> CoinInserted`
- `CoinInserted --select--> Idle` (product dispensed)
- `CoinInserted --cancel--> Idle` (coin refunded)

### Problem 10

```
   +--------+ open    +------+ begin edit  +---------+  save   +--------+
   | Closed | ------> | Open | ----------> | Editing | ------> | Saved  |
   +--------+          +------+             +---------+         +--------+
        ^                 |                                       |
        |       close     |        close                          |
        +-----------------+ <-------------------------------------+
```

States: `Closed`, `Open`, `Editing`, `Saved`.

Transitions:
- `Closed --open--> Open`
- `Open --begin edit--> Editing`
- `Editing --save--> Saved`
- `Open --close--> Closed`
- `Saved --close--> Closed`

**Save from `Closed`:** there is no `save` transition leaving `Closed`, so save is ignored (no state change). To save, a document must first be opened.

## C. Errors and testing

### Problem 11

(a) **Syntax error.** The `IF` statement is missing its `THEN`; the translator reports it and the program does not run until it is corrected.
(b) **Logic error.** The program runs and produces output, but the wrong result because `-` was written instead of `+`. The system does not flag it; the programmer finds it by tracing or inspecting output.
(c) **Run-time error.** The program attempts to read an array index that is out of range while executing; it crashes or raises an exception when that statement runs.
(d) **Syntax error.** `OUTPIT` is a misspelt keyword; the translator cannot recognise it and reports the error before the program runs.

### Problem 12

**White-box testing.** The source code and full internal structure are available, so the tester can design cases that exercise every statement, branch, and path inside the module.

Black-box testing is less suitable here because it tests only against the specification using inputs and expected outputs, with no knowledge of the code inside. It cannot guarantee that every branch has been exercised, which is the developer's goal for this module.

### Problem 13

**Stub testing.** A **stub** is a dummy module with the same interface as the not-yet-coded sub-module. The calling module is tested against the stub, which returns fixed, simple values so the caller's logic can be checked before the real sub-module exists.

The stub is a placeholder only. Once the real sub-module is coded, the stub is removed and the two modules are integration-tested together.

### Problem 14

- **Alpha testing** is performed **inside the developing organisation**, often by the developers themselves or an in-house test team, on real or near-real data, as an early shakedown before release.
- **Beta testing** is performed by a **selected group of real end users outside the organisation**, using the software in their own environment, just before general release, to catch issues that real usage exposes.

### Problem 15

| Category | Test value | Expected result |
|----------|-----------|-----------------|
| Normal | `20` | Accepted and applied |
| Abnormal | `"ten"`, `0`, `75`, empty input | Rejected as invalid |
| Extreme | `5` and `50` | Accepted (the endpoints of the valid range) |
| Boundary | `4`, `5`, `50`, `51` | `4` and `51` rejected; `5` and `50` accepted |

### Problem 16

Boundary values:
- Rejected: `1899` (just below the lower bound) and `2011` (just above the upper bound).
- Accepted: `1900` (the lower endpoint) and `2010` (the upper endpoint).

Reason: the valid range is 1900 to 2010 inclusive, so `1900` and `2010` are the last accepted values on each edge, while `1899` and `2011` are the first rejected. This pairing catches an off-by-one error such as `<` instead of `<=` in the comparison.

### Problem 17

A **walkthrough** is a review in which the programmer or team steps through the code or design **together**, explaining what each part does and questioning it; several people are involved. A **dry run** is performed by a single programmer who traces through the code **by hand** on paper, following each line and tracking variables in a trace table, without running it and without a group.

The walkthrough is collaborative review; the dry run is a solo paper trace.

## D. Maintenance

### Problem 18

(a) **Corrective.** It fixes a fault (the wrong tax rate) that was not found before release.
(b) **Perfective.** It improves performance beyond the original spec by making the screen faster.
(c) **Adaptive.** It changes the system so it keeps working in a new environment (the new operating system), without altering what the program does.
(d) **Perfective.** It adds a new feature (the graph) beyond the original spec.

### Problem 19

**Adaptive maintenance.** The program already works; the change is needed because the *external environment* (the government's code set) has changed, and the program must be adapted to keep working correctly under the new rules. It is not fixing an old fault (so not corrective), and it is not adding an optional improvement (so not perfective).

### Problem 20

Corrective maintenance fixes a **fault** that was present but undiscovered before release; the bug was always in the code, and the change removes it. Adaptive maintenance is about a **new environment** (new OS, new database, new external rules); the program was working correctly before the environment changed. A crash fix addresses an internal fault, not an environmental change, so it is corrective.
