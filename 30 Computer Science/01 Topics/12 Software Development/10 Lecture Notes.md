---
title: Software Development Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[Software Development](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - lecture-notes
---

# Software Development Lecture Notes

These notes cover **section 12 Software Development** of the 9618 AS syllabus, examined in **Paper 2**. The focus is the journey from a problem to a maintainable program: which life cycle to follow, how to design with structure charts and state-transition diagrams, how to find and classify errors, and how to choose test data and maintenance actions that examiners reward.

## Source Route

- Syllabus 12.1 Program Development Life cycle - analysis, design, coding, testing, maintenance; waterfall, iterative, RAD.
- Syllabus 12.2 Program Design - structure charts, parameters, derived pseudocode, state-transition diagrams.
- Syllabus 12.3 Program Testing and Maintenance - error types, testing methods, test strategy/plan, test data, maintenance types.

## 1. The development life cycle

A **development life cycle** is a structured sequence of stages that turns a problem into a working, maintained program. The point is control: each stage has a purpose and a deliverable, so progress can be checked and faults caught early rather than after release.

- **Analysis** - study the problem, gather requirements, and agree what the program must do. Output: a requirements specification.
- **Design** - decide how to meet the requirements: data structures, modules, algorithms, interfaces, file formats. Output: a design (structure charts, pseudocode, diagrams).
- **Coding** - translate the design into a programming language. Output: source code.
- **Testing** - run the code with planned data to expose faults; locate and correct them. Output: tested code plus a test log.
- **Maintenance** - keep the program working and useful after release: fix bugs, adapt to change, improve performance. Output: updated releases.

> Stages are not always strictly sequential. In iterative and RAD models a team revisits analysis and design as understanding grows, but every stage still happens.

## 2. Life cycle models compared

Different projects suit different cycles. A payroll for a stable business is not built the same way as a prototype for a startup whose requirements shift weekly.

| Model | Principles | Benefits | Drawbacks | When to use |
|-------|-----------|----------|-----------|-------------|
| **Waterfall** | Linear, top-down: finish each stage and sign it off before the next begins; heavy up-front documentation | Easy to manage; milestones clear; full documentation; works well when requirements are fixed and well understood | Late feedback - working code appears only near the end; hard to go back; poor fit for changing or unclear requirements | Stable, well-understood problems; safety-critical systems; large teams needing formal contracts |
| **Iterative** | Build in repeated cycles (iterations); each iteration runs through analysis–design–code–test and produces a working but partial version that grows | Early working software; faults found sooner; requirements can be refined between iterations; risk reduced step by step | More complex to manage; documentation and integration effort repeat; scope can creep if iterations are not controlled | Large projects, evolving requirements, where early partial results reduce risk |
| **RAD** (Rapid Application Development) | Emphasise speed and user feedback; use prototyping, reusable components and CASE tools; very short cycles with heavy user involvement | Fast usable results; users see and react to prototypes; good for reusable, modular systems | Needs highly skilled developers and committed users; quality may suffer under time pressure; hard to plan for very large or critical systems | Small/medium projects, tight deadlines, uncertain requirements, GUI/database apps built from components |

> Exam tip: if the question says "requirements not fully known" think iterative or RAD; if it says "well understood, fixed, regulated" think waterfall.

## 3. Structure charts

A **structure chart** decomposes a problem into modules (sub-tasks) and shows how they call one another and what data passes between them. It expresses the *design* of a program - its hierarchy and interfaces - without writing the code. The purpose is to make the structure readable, support stepwise refinement, and let each module be coded and tested separately.

### 3.1 Symbols

- **Module box** - a named sub-task (a procedure or function). The top box is the main program; boxes beneath are modules it calls.
- **Sequential / call connectors** - the line from a parent down to a child module shows that the parent calls the child.
- **Data flag** - an arrow with an open head, labelled with the data name, showing a value flowing into or out of a module.
- **Control flag** - an arrow with a filled head, labelled with the flag name, showing a control signal such as `EOF` or `Error`.

By convention a flag drawn on the left of a connector carries data down into the child, and a flag on the right carries data back up.

### 3.2 Worked example - a simple statistics program

Problem: read a list of exam scores, then output the average and the count of scores that beat the average.

```
                     +-------------------+
                     |   StatsProgram    |
                     +-------------------+
                       /              \
                      /                \
          +----------------+      +------------------+
          |   InputScores  |      |   ProcessScores  |
          +----------------+      +------------------+
                                         |    \
                                  Count  |     \  Average
                                         v      v
                                 +-----------------+
                                 |   CountAbove    |
                                 +-----------------+
```

Parameter flags:

- `InputScores` returns `Scores[]` and `Count` (data flags) to the main program.
- `ProcessScores` receives `Scores[]` and `Count` from the main program, and computes `Average` (data flag).
- `CountAbove` receives `Scores[]`, `Count` and `Average`, returns `AboveCount` (data flag).

### 3.3 Deriving pseudocode from the chart

Read the chart top-down, left to right; each module becomes a `PROCEDURE` or `FUNCTION`, and the flags become its parameters.

```pseudocode
PROCEDURE InputScores(BYREF Scores : ARRAY OF REAL, BYREF Count : INTEGER)
    OUTPUT "Enter number of scores: "
    INPUT Count
    FOR i ← 1 TO Count
        OUTPUT "Enter score: "
        INPUT Scores[i]
    NEXT i
ENDPROCEDURE

FUNCTION CalcAverage(Scores : ARRAY OF REAL, Count : INTEGER) RETURNS REAL
    DECLARE Total : REAL
    Total ← 0
    FOR i ← 1 TO Count
        Total ← Total + Scores[i]
    NEXT i
    RETURN Total / Count
ENDFUNCTION

FUNCTION CountAbove(Scores : ARRAY OF REAL, Count : INTEGER, Average : REAL) RETURNS INTEGER
    DECLARE Above : INTEGER
    Above ← 0
    FOR i ← 1 TO Count
        IF Scores[i] > Average THEN
            Above ← Above + 1
        ENDIF
    NEXT i
    RETURN Above
ENDPROCEDURE

// Main program
DECLARE Scores : ARRAY[1..100] OF REAL
DECLARE Count, Above : INTEGER
DECLARE Average : REAL

CALL InputScores(Scores, Count)
Average ← CalcAverage(Scores, Count)
Above ← CountAbove(Scores, Count, Average)
OUTPUT "Average = ", Average
OUTPUT "Scores above average = ", Above
```

> Each flag on the chart maps to one parameter in the header. If the chart shows a value being changed and returned, use `BYREF`; if it is only read, pass by value.

## 4. State-transition diagrams

A **state-transition diagram** documents an algorithm (or a component) by showing its possible **states**, the **transitions** between them, and the **events** that trigger each transition. It is ideal for anything that reacts to a sequence of inputs: a process controller, a menu, an object whose behaviour depends on history.

### 4.1 Worked example - an online order

States an order passes through: `New`, `Paid`, `Shipped`, `Delivered`.

```
   +-----+  pay     +-----+  ship    +--------+  deliver  +-----------+
   | New | -------> | Paid| ------> | Shipped | ---------> | Delivered |
   +-----+          +-----+          +--------+             +-----------+
                        |                                           ^
                        | cancel                                    |
                        v                                           |
                   +---------+   refund                             |
                   | Cancelled|  ------ (returns funds, ends) ------+
                   +---------+
```

Transitions: `New --pay--> Paid`, `Paid --ship--> Shipped`, `Shipped --deliver--> Delivered`, `Paid --cancel--> Cancelled`, `Cancelled --refund--> Delivered` (terminal accounting). Reading the diagram, you can state for any current state and event what the next state is - exactly what a state-based algorithm needs.

## 5. Error types

| Type | Definition | Example | When detected |
|------|-----------|---------|---------------|
| **Syntax error** | Code that breaks the grammar rules of the language | `IF x > 5 OUTPUT "hi"` (missing `THEN`); misspelt keyword `WHIEL` | At **compile/translate time**, before the program runs |
| **Logic error** | The program runs and produces output, but the wrong result | `Average ← Total / (Count + 1)` instead of `Total / Count`; wrong comparison `>` instead of `<` | At **run time**, usually by inspecting output or tracing; the system may not flag it |
| **Run-time error** | The program attempts an illegal operation while executing | Division by zero; accessing an index out of range; opening a missing file | At **run time**, when the offending statement executes - the program crashes or raises an exception |

> To correct: fix syntax errors first (the translator reports them); reproduce logic and run-time errors with trace data, then amend the offending line and re-test.

## 6. Testing methods

| Method | What it does | When used |
|--------|-------------|-----------|
| **Dry run** | The programmer traces through the code **by hand** on paper, following each line and tracking variables in a trace table, without running it | Early checking of logic; verifying a small routine; exam questions |
| **Walkthrough** | The programmer or team steps through the code or design **together**, explaining what each part does and questioning it | Reviewing a design or module before coding/committing |
| **White-box** | Tests based on the **internal structure** of the code - exercising every statement, branch and path | When the source code and full structure are available; unit testing of a known module |
| **Black-box** | Tests based only on the **specification/inputs and expected outputs**, with no knowledge of the code inside | Functional testing against requirements; acceptance-style checks |
| **Integration** | Tests modules **combined together** to check that interfaces and data passed between them work | After individual modules pass, before system testing |
| **Alpha** | Testing **inside the developing organisation**, often by the developers themselves or an in-house test team, on real or near-real data | Early in-house shakedown before release to users |
| **Beta** | Testing by a **selected group of real end users** outside the organisation, using the software in their own environment | Just before general release, to catch issues real usage exposes |
| **Acceptance** | Testing by the **customer/end user** to decide whether the system meets the agreed requirements and can be accepted (signed off) | At the end of development, before the system goes live |
| **Stub** | A **dummy module** with a fixed simple interface is written so a module that calls it can be tested before the real sub-module exists | Top-down development and testing, when a called module is not yet coded |

> White-box looks *inside* the box (structure); black-box treats the box as opaque (specification). Alpha is *internal*; beta is *external users*; acceptance is *the customer signing off*.

## 7. Test strategy, test plan and test data

A **test strategy** is the overall approach: the scope of testing, the methods to be used, who tests what, and the order of testing (unit → integration → system → acceptance). It answers "how will we make sure this is fit for release?".

A **test plan** is the concrete schedule of individual tests derived from the strategy. Each entry typically contains:

- a test identifier and description;
- the method (dry run, white-box, etc.);
- the **test data** to use;
- the **expected result**;
- space to record the **actual result** and a pass/fail verdict.

### 7.1 Choosing test data

| Category | Meaning | For an age field `0–120` |
|----------|---------|--------------------------|
| **Normal** | Typical, valid values the program should handle | `25`, `40`, `67` |
| **Abnormal** (erroneous) | Values of the wrong type or clearly invalid that the program should reject | `"twenty"`, `-5`, `200`, empty input |
| **Extreme** | Valid values at the very edges of the allowed range | `0` and `120` |
| **Boundary** | Values on and just either side of a boundary, to check the comparison operator | `0`, `1`, `119`, `120`, and the just-outside `-1`, `121` |

> Extreme tests the endpoints of the valid range; boundary tests around the edge to catch off-by-one errors (`<` vs `<=`). Always include both, plus at least one abnormal case.

## 8. Maintenance types

After release the program is **maintained**. The syllabus distinguishes three reasons for changing it.

| Type | Definition | Example |
|------|-----------|---------|
| **Perfective** | Improve the system beyond its original spec - new features, better performance, better usability | Adding a "print to PDF" option; making a report run faster |
| **Adaptive** | Change the system so it keeps working in a **new environment** | Porting to a new OS, a new database version, or new tax rules from a government update |
| **Corrective** | **Fix a fault** that was not found before release | Correcting a formula that miscalculates VAT; fixing a crash on empty input |

> Perfective = "make it nicer"; adaptive = "keep it working as the world changes"; corrective = "fix what was always wrong".

## Worked-Thinking Routine

1. Read the scenario and decide whether requirements are fixed or changing - this picks the life cycle.
2. For a design question, list inputs and outputs first, then break the work into modules with one job each.
3. Draw the structure chart: parent at top, child modules below, and label every data and control flag.
4. Read the chart top-down to write pseudocode; turn each flag into a parameter, using `BYREF` only where a value must change.
5. For testing questions, name the method, then give data in each category (normal, abnormal, extreme/boundary) with the expected result.
6. For maintenance questions, ask: new feature, new environment, or fixing a fault - then label perfective, adaptive or corrective.

## Common Mistakes

- Choosing waterfall for a project whose requirements keep changing.
- Forgetting data/control flags on a structure chart, or drawing arrows without labels.
- Confusing extreme (the endpoint itself) with boundary (just inside and just outside).
- Mixing up alpha (internal) and beta (external users), or beta and acceptance (customer sign-off).
- Calling a bug fix "adaptive" - adaptive is about a *new environment*, not correcting old faults.
- Listing only normal test data and ignoring abnormal and boundary cases.
- Stating a stub is the finished module - a stub is a *dummy* placeholder for testing.

## Quick Self-Check

- Name the five life-cycle stages and one deliverable from each.
- For "a startup building an app whose features change weekly", justify iterative or RAD over waterfall.
- Draw a structure chart for a payroll that inputs hours, calculates pay, and prints a payslip, with parameter flags.
- From that chart, write the pseudocode for the `CalculatePay` module.
- Give normal, abnormal, extreme and boundary data for a password that must be 8–20 characters.
- Classify: adding dark mode; moving to a new database; fixing a divide-by-zero crash.

## Connections

- [Programming](../11%20Programming/00%20Overview.md) produces the code that these life-cycle stages manage.
- [Further Programming](../20%20Further%20Programming/00%20Overview.md) extends testing and maintenance into larger paradigms.

## Study Sequence

1. Learn the five stages and the three models; match each model to a project type.
2. Practise reading and drawing structure charts, then derive pseudocode from each.
3. Draw one state-transition diagram for a real process you use.
4. Memorise the error-types and testing-methods tables and give an example of each.
5. Build a test plan for a small routine covering all four data categories.
6. Drill maintenance classification until perfective/adaptive/corrective are automatic.
