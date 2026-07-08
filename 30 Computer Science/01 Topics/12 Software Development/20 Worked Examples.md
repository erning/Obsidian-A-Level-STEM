---
title: Software Development Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/12 Software Development/00 Overview|Software Development]]"
status: active
tags:
  - computerscience/programming
  - worked-examples
---

# Software Development Worked Examples

These worked examples show how to reason through scenario questions on life cycle choice, structure charts, state-transition diagrams, error classification, testing methods, test data, and maintenance. The recurring skill is method selection: name the category first, then justify it from the details of the scenario. Cover each solution, attempt the prompt on paper, then compare.

## Source Route

- Syllabus **9618 AS Section 12 - Software Development**.
- 12.1 Program Development Life cycle - waterfall, iterative, RAD; analysis, design, coding, testing, maintenance.
- 12.2 Program Design - structure charts, parameters, derived pseudocode, state-transition diagrams.
- 12.3 Program Testing and Maintenance - error types, testing methods, test strategy/plan, test data, maintenance types.
- Assessed in **Paper 2**.

## Example 1: Choose a life cycle model for a scenario

**Prompt.** A small team is building an app for a startup. The founders are unsure which features users will want and expect to change the requirements every few weeks. State which life cycle model is most suitable and justify it against the waterfall model.

**Solution.** The **iterative** model (or RAD) is most suitable.

1. **Requirements change.** Iterative builds the program in repeated cycles, and each iteration produces a working partial version the founders can react to. Requirements can be refined between iterations, which fits a project where the features shift weekly.
2. **Early feedback.** A working partial build appears early, so the team can show real software to users and adjust before too much is invested. This reduces the risk of building the wrong thing.
3. **Why not waterfall.** Waterfall requires each stage to be signed off before the next begins, with heavy up-front documentation. It assumes requirements are fixed and well understood, which is exactly what the scenario denies. Working code would appear only near the end, far too late to change features.

**Check.** Decide by the requirements. If the prompt says "fully known, fixed, regulated, safety-critical", choose waterfall; if it says "changing, unclear, prototype, user feedback", choose iterative or RAD.

## Example 2: Describe the life-cycle stages for a small project

**Prompt.** A club wants a program that records member attendance and prints a monthly report. Outline what happens in each of the five life-cycle stages for this project, naming one deliverable per stage.

**Solution.**
- **Analysis.** The developer interviews the club secretary to find out what data each member record holds (name, ID, dates attended), how attendance is taken, and what the monthly report must show. Deliverable: a requirements specification.
- **Design.** The developer decides the data structures (a member table), the modules (record attendance, build report), and the algorithms, captured in a structure chart and pseudocode. Deliverable: a design.
- **Coding.** The design is translated into a programming language, writing the procedures and functions from the structure chart. Deliverable: source code.
- **Testing.** Each module is run with planned test data covering normal, abnormal, and boundary cases, then the modules are combined and integration-tested. Deliverable: tested code plus a test log.
- **Maintenance.** After release the secretary reports issues or asks for changes, such as a new "absent members" list, and the program is updated. Deliverable: updated releases.

**Check.** Each stage must produce an artefact. Analysis gives the spec, design gives the chart/pseudocode, coding gives source code, testing gives a test log, maintenance gives updated releases.

## Example 3: Build a structure chart and derive pseudocode

**Prompt.** A program reads an employee's hours worked and hourly rate, calculates gross pay (with overtime at 1.5 times rate for hours over 40), and prints a payslip. Draw a structure chart showing the modules and all parameter flags, then derive pseudocode for the `CalculatePay` module.

**Solution.**

```
                    +------------------+
                    |    Payroll       |
                    +------------------+
                      /      |      \
                     /       |       \
        +-----------+   +-----------+   +------------+
        | InputData |   | Calculate |   | PrintPay   |
        +-----------+   |   Pay     |   +------------+
                        +-----------+
            Hours,Rate    |     Pay
            ------>       |     <------
                          v
                  (internal: Overtime,
                   RegularPay)
```

Parameter flags:
- `InputData` returns `Hours` and `Rate` (data flags) up to the main program.
- `CalculatePay` receives `Hours` and `Rate` from the main program and returns `Pay` (data flag).
- `PrintPay` receives `Pay`, `Hours`, and `Rate` from the main program.

Derived pseudocode for `CalculatePay`:

```pseudocode
FUNCTION CalculatePay(Hours : REAL, Rate : REAL) RETURNS REAL
    DECLARE Regular, Overtime, Pay : REAL
    IF Hours <= 40 THEN
        Regular ← Hours
        Overtime ← 0
    ELSE
        Regular ← 40
        Overtime ← Hours - 40
    ENDIF
    Pay ← Regular * Rate + Overtime * Rate * 1.5
    RETURN Pay
ENDFUNCTION
```

**Check.** Each flag on the chart maps to one parameter. `Hours` and `Rate` are only read inside `CalculatePay`, so they pass by value; the function returns `Pay` as its result, matching the `Pay` data flag on the chart.

## Example 4: Draw a state-transition diagram

**Prompt.** A metro turnstile starts locked. A passenger inserts a coin and the turnstile unlocks; one push rotates the barrier and locks it again. Draw a state-transition diagram, listing the states and the events that trigger each transition. State what happens if the passenger pushes while locked, or inserts a coin while unlocked.

**Solution.**

```
   +--------+  coin   +----------+
   | Locked | ------> | Unlocked |
   +--------+          +----------+
        ^                   |
        |                   |  push
        |   push (rotates   v
        +--- barrier) ------+
```

States: `Locked` (the resting state, barrier held) and `Unlocked` (one push permitted).

Transitions:
- `Locked --coin--> Unlocked`
- `Unlocked --push--> Locked`

Reading the diagram:
- **Push while locked** - no transition; the barrier stays locked and does not rotate. (If drawn, a self-loop on `Locked`.)
- **Coin while unlocked** - no transition; the turnstile is already unlocked, and a second coin does nothing useful. (If drawn, a self-loop on `Unlocked`.)

The behaviour is fully specified: for any current state and event, the diagram gives the next state.

**Check.** List the states first, then the events. If the question asks what an event does in a state with no outgoing arrow for it, the answer is no change (a self-loop or ignored input).

## Example 5: Classify an error type

**Prompt.** A student writes code to average three numbers. Classify each fault as syntax, logic, or run-time, and give the reason.
(a) `TOATAL ← 0` written instead of `TOTAL`.
(b) `Average ← Sum / 3` where the program should divide by the actual count entered, not always 3.
(c) `Average ← Sum / Count` when the user entered no numbers so `Count` is 0.

**Solution.**
(a) **Syntax error.** `TOATAL` is an undeclared identifier caused by a misspelling of the keyword/variable; the translator reports it and the program does not run until it is corrected. (A misspelt keyword such as `WHIEL` is also syntax.)
(b) **Logic error.** The program runs and produces output, but the result is wrong because it always divides by 3 regardless of how many numbers were entered. The system does not flag it; the programmer finds it by inspecting output or tracing.
(c) **Run-time error.** The program attempts division by zero while executing; it crashes or raises an exception when the offending statement runs.

**Check.** Decide by *when* it fails. If the translator stops it before running, syntax; if it runs and gives a wrong answer, logic; if it runs and crashes on a specific input, run-time.

## Example 6: Choose a testing method

**Prompt.** For each scenario, name the most suitable testing method and justify it.
(a) A developer has finished coding a sorting module and wants to exercise every branch and statement in it.
(b) A customer must decide whether the finished system meets the agreed requirements before signing it off.
(c) A module calls a sub-module that has not been coded yet, but the calling module must be tested now.
(d) A software house wants selected real users to try an almost-finished product in their own environment.

**Solution.**
(a) **White-box testing.** The source code and internal structure are available, so the tester can design cases that exercise every statement, branch, and path inside the module.
(b) **Acceptance testing.** The customer, not the developer, runs tests against the agreed requirements to decide whether the system can be accepted and signed off.
(c) **Stub testing.** A dummy module with the correct interface is written so the calling module can be tested before the real sub-module exists. The stub returns fixed values to exercise the caller.
(d) **Beta testing.** A selected group of real end users outside the organisation try the software in their own environment, catching issues that in-house testing misses. (Alpha, by contrast, is inside the organisation.)

**Check.** White-box needs the source; black-box needs only the specification. Alpha is internal; beta is external users; acceptance is the customer sign-off. A stub is a dummy placeholder, never the finished module.

## Example 7: Select normal, abnormal, and boundary test data

**Prompt.** An online order form lets a customer buy between 1 and 99 units of an item. Give suitable values for normal, abnormal, extreme, and boundary test data, and state the expected result for each.

**Solution.**

| Category | Test value | Expected result |
|----------|-----------|-----------------|
| Normal | `25`, `50` | Accepted and processed |
| Abnormal | `0`, `100`, `-3`, `"five"`, empty input | Rejected as invalid |
| Extreme | `1` and `99` | Accepted (the endpoints of the valid range) |
| Boundary | `0`, `1`, `99`, `100` | `0` and `100` rejected; `1` and `99` accepted |

**Check.** Extreme tests the endpoints of the valid range itself; boundary tests on and just either side to catch off-by-one errors such as `<` instead of `<=`. A boundary set therefore pairs the last accepted with the first rejected: `99`/`100` on the high edge and `0`/`1` on the low edge. Always include at least one abnormal case.

## Example 8: Classify a maintenance task

**Prompt.** Classify each post-release change as perfective, adaptive, or corrective, with a one-line reason.
(a) The program crashes when the input file is empty; a check is added to handle this.
(b) The program is moved from an old version of the database to a new one so it keeps running.
(c) A "export to PDF" button is added because users asked for it.

**Solution.**
(a) **Corrective maintenance.** It fixes a fault (a bug) that was not found before release.
(b) **Adaptive maintenance.** It changes the system so it keeps working in a new environment (the new database), without altering what the program does.
(c) **Perfective maintenance.** It improves the system beyond its original spec by adding a new feature the users requested.

**Check.** Ask one question: is it fixing a fault (corrective), adapting to a new environment (adaptive), or adding an improvement (perfective)? Calling a bug fix "adaptive" is a common error; adaptive is about the environment, not old faults.

## Study Routine

1. For life-cycle questions, decide by the requirements first: fixed and well understood points to waterfall; changing or unclear points to iterative or RAD.
2. For design questions, list inputs and outputs, break the work into one-job modules, then draw the chart and label every data and control flag.
3. Read structure charts top-down to derive pseudocode; turn each flag into a parameter, using `BYREF` only where a value must change.
4. For state diagrams, list the states, then the events, then draw an arrow for each transition.
5. For error questions, decide by when it fails: before running (syntax), wrong answer (logic), or crash (run-time).
6. For testing questions, name the method, then give normal, abnormal, extreme, and boundary data with the expected result.
7. For maintenance, ask: new feature, new environment, or fixing a fault?
