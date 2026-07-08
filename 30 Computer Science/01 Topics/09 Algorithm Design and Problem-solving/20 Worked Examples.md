---
title: Algorithm Design and Problem-solving Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/09 Algorithm Design and Problem-solving/00 Overview|Algorithm Design and Problem-solving]]"
status: active
tags:
  - computerscience/programming
  - worked-examples
---

# Algorithm Design and Problem-solving Worked Examples

These worked examples show how to move from a problem statement to an algorithm in the official pseudocode. The method is: identify the inputs, process, and outputs first, then choose the right construct and notation, and only then write code. Cover each solution, attempt the prompt on paper, then compare.

## Source Route

- Syllabus **9618 AS Section 9 - Algorithm Design and Problem-solving**.
- 9.1 Computational Thinking Skills: abstraction and decomposition into modules.
- 9.2 Algorithms: pseudocode, identifier tables, the three constructs (sequence, selection, iteration), three notations (structured English, flowchart, pseudocode), stepwise refinement, logic statements.
- Assessed in **Paper 2**. Pseudocode follows the CAIE Pseudocode Guide, including the assignment arrow `←`.

## Example 1: Build an abstract model of a taxi fare system

**Prompt.** A city taxi has a vehicle registration, an engine size, a paint colour, a driver name, a driver licence number, a start mileage, and a meter that charges a flat flag fall followed by a rate per kilometre. The fare system must work out the cost of each trip from the kilometres travelled. Build an abstract model by stating only the details that matter for computing the fare.

**Solution.** The question is narrow: compute the fare from the kilometres of a trip. Drop registration, engine size, paint colour (they describe the car but not the fare); drop driver name and licence (the driver does not change the charge); drop start mileage (the trip distance, not the odometer, drives the fare).

| Item | Why it is kept |
|---|---|
| FlagFall (REAL) | Flat charge added to every trip |
| RatePerKm (REAL) | Charge per kilometre travelled |
| Kilometres (REAL) | The distance of this trip |
| Fare (REAL) | The result to output |

**Check.** For each candidate data item ask: "If this value changed, would the fare change?" If not, it is irrelevant. Abstraction has succeeded when only items that affect the answer remain.

## Example 2: Decompose a parking-garage program into modules

**Prompt.** A parking garage program must: read a ticket number on entry and record the entry time; on exit read the ticket again, look up the entry time, compute the duration, apply the tariff, print the fee, and mark the bay free again. Decompose this into modules, give a module list with types, and give the identifier table.

**Solution.** Each verb in the description is a candidate module.

| Module | Type | Job |
|---|---|---|
| RecordEntry | Procedure | Read ticket number, store entry time, mark a bay occupied |
| LookupEntryTime | Function | Return the entry time stored for a given ticket |
| CalculateDuration | Function | Return the duration from entry time to exit time |
| CalculateFee | Function | Return the fee by applying the tariff to the duration |
| PrintFee | Procedure | OUTPUT the fee for the driver |
| FreeBay | Procedure | Mark the bay free for the ticket |

Functions return a single value (entry time, duration, fee). Procedures perform an action and return nothing, called as statements by `CALL`.

| Identifier | Data type | Description |
|---|---|---|
| `TicketNumber` | INTEGER | the ticket read on entry and exit |
| `EntryTime` | REAL | the time a vehicle entered |
| `ExitTime` | REAL | the time a vehicle leaves |
| `Duration` | REAL | length of stay in hours |
| `Fee` | REAL | the amount to charge |
| `BayOccupied` | ARRAY[1:100] OF BOOLEAN | whether each bay is in use |

**Check.** Every module does exactly one job; if you can split a module into two clear tasks, do so.

## Example 3: Write pseudocode from structured English

**Prompt.** Convert this structured-English description into pseudocode.

> Input a password from the user. If the password is equal to "Open123", output "Access granted"; otherwise output "Access denied". Then, regardless of the branch taken, output "Session ended".

**Solution.** One selection with two branches, followed by one step that always runs. That final step is outside the `IF`, because "regardless of the branch" places it in sequence after the selection.

```pseudocode
INPUT Password
IF Password = "Open123" THEN
    OUTPUT "Access granted"
ELSE
    OUTPUT "Access denied"
ENDIF
OUTPUT "Session ended"
```

**Check.** Indentation shows the structure: `OUTPUT "Session ended"` sits at the same level as the `INPUT`, so it runs after the `IF` finishes. If the wording had said "after granting access", that line would move inside the `THEN` branch.

## Example 4: Write pseudocode from a flowchart

**Prompt.** The following flowchart processes exam marks. Convert it to pseudocode.

```text
        ( Start )
            |
   / INPUT Mark /          ← parallelogram
            |
   < Mark >= 50 ? >        ← decision (Yes left, No right)
     /            \
   Yes            No
    |              |
 PassCount ←      |
 PassCount + 1    |
    |              |
    \______________/
            |
   Total ← Total + 1       ← process
            |
   < More marks ? >        ← decision (Yes loops back to INPUT; No goes down)
     /            \
   Yes            No
    |              |
 (loops up)        |
            ( End )
```

**Solution.** The flowchart reads marks, checks each for a pass, counts passes, counts all marks, and asks whether there are more. The pre-condition test "More marks?" before the body could repeat suggests a `WHILE`; a `REPEAT` would force at least one mark even if there were none.

```pseudocode
PassCount ← 0
Total ← 0
INPUT "Any more marks? ", More
WHILE More = "Y" DO
    INPUT Mark
    IF Mark >= 50 THEN
        PassCount ← PassCount + 1
    ENDIF
    Total ← Total + 1
    INPUT "Any more marks? ", More
ENDWHILE
OUTPUT "Passes: ", PassCount
OUTPUT "Total: ", Total
```

**Check.** Every flowchart symbol maps to one pseudocode feature: parallelograms to `INPUT`/`OUTPUT`, rectangles to assignment, diamonds to `IF` or loop conditions, arrows to order.

## Example 5: Convert pseudocode to a flowchart description

**Prompt.** Describe, symbol by symbol, the flowchart you would draw for the following pseudocode.

```pseudocode
INPUT Number
IF Number > 0 THEN
    OUTPUT "Positive"
ELSE
    OUTPUT "Not positive"
ENDIF
```

**Solution.**

1. Start terminator (rounded rectangle): "Start".
2. Parallelogram: "INPUT Number".
3. Diamond: "Number > 0 ?" with a Yes branch left and a No branch right.
4. On Yes, an output parallelogram: "OUTPUT 'Positive'".
5. On No, an output parallelogram: "OUTPUT 'Not positive'".
6. Both branches join at a single flow line.
7. End terminator: "End".

The two output boxes converge before the End, because both branches of an `IF ... ELSE` reach the same point after `ENDIF`.

**Check.** A two-way selection is always one diamond with exactly two outgoing arrows that rejoin after the branches.

## Example 6: Use all three constructs in one algorithm

**Prompt.** Write a pseudocode algorithm that reads ten integers, counts how many are positive, and prints the count followed by a message saying whether the majority were positive. The algorithm must clearly use sequence, selection, and iteration.

**Solution.** The iteration is the fixed ten repetitions, so `FOR` fits. Inside the loop, a selection checks the sign of each number. Around the loop, assignments and outputs form the sequence.

```pseudocode
PositiveCount ← 0                                    // sequence
FOR Count ← 1 TO 10                                  // iteration
    INPUT Number
    IF Number > 0 THEN                               // selection
        PositiveCount ← PositiveCount + 1
    ENDIF
NEXT Count

OUTPUT "Positive count: ", PositiveCount
IF PositiveCount > 5 THEN                            // selection
    OUTPUT "Majority were positive"
ELSE
    OUTPUT "Majority were not positive"
ENDIF
```

**Check.** Each construct must be visible: `FOR ... NEXT` is iteration, both `IF` blocks are selection, the straight runs of assignment and `OUTPUT` are sequence.

## Example 7: Stepwise refinement of a rainfall problem

**Prompt.** Refine the following problem in levels down to implementable pseudocode. "Read the daily rainfall for a month (30 days). Output the wettest day's rainfall and the number of dry days (rainfall of 0)."

**Solution.**

Level 0: (1) read in the rainfall figures; (2) find the wettest day; (3) count the dry days; (4) output the results.

Level 1: (1) loop 30 times, reading one value into an array each time; (2) set a variable to the first value, then scan the array, replacing it whenever a larger value appears; (3) scan the array again, adding one to a counter whenever the value is 0; (4) output the wettest value and the dry-day count.

Level 2 (pseudocode).

```pseudocode
DECLARE Rain : ARRAY[1:30] OF REAL
DECLARE Index : INTEGER
DECLARE Wettest : REAL
DECLARE DryDays : INTEGER

// 1. Read in the rainfall figures
FOR Index ← 1 TO 30
    INPUT Rain[Index]
NEXT Index

// 2. Find the wettest day
Wettest ← Rain[1]
FOR Index ← 2 TO 30
    IF Rain[Index] > Wettest THEN
        Wettest ← Rain[Index]
    ENDIF
NEXT Index

// 3. Count the dry days
DryDays ← 0
FOR Index ← 1 TO 30
    IF Rain[Index] = 0 THEN
        DryDays ← DryDays + 1
    ENDIF
NEXT Index

// 4. Output the results
OUTPUT "Wettest day: ", Wettest
OUTPUT "Dry days: ", DryDays
```

**Check.** Each comment in the final code lines up with a Level 1 step: the high-level structure survives into the finished program. Refine every step at one level before going deeper anywhere.

## Example 8: Use logic statements to define a condition

**Prompt.** A password is valid only when it is at least 8 characters long AND it is not equal to the user's username OR the word "password". Write a single logic statement in pseudocode that is true exactly when the password is valid, using explicit parentheses. Then write the `IF` that prints "Valid" or "Invalid".

**Solution.** Two conditions must combine: length at least 8, and not matching either banned value. The "not matching either banned value" part needs `OR` inside a `NOT`.

```pseudocode
INPUT Username
INPUT Password
LengthOk ← LENGTH(Password) >= 8
NotBanned ← NOT (Password = Username OR Password = "password")
IF LengthOk AND NotBanned THEN
    OUTPUT "Valid"
ELSE
    OUTPUT "Invalid"
ENDIF
```

Without the parentheses around `Password = Username OR Password = "password"`, the `NOT` would apply only to the first comparison. Storing the two parts in Boolean variables keeps the final `IF` readable.

**Check.** For any logic statement with more than one operator, write the parentheses explicitly. `A AND B OR C` is read as `(A AND B) OR C`, not the same as `A AND (B OR C)`; the two can give different answers on the same inputs.

## Study Routine

1. Identify the inputs, the process, and the outputs before anything else.
2. For abstraction, ask of every detail: "Would the answer change if this changed?" If not, drop it.
3. For decomposition, list the verbs; each becomes a module, a function if it returns a value, otherwise a procedure.
4. Choose the construct by the situation: `FOR` for a known count, `WHILE` when the body may run zero times, `REPEAT` when it must run at least once.
5. Convert between notations by mapping symbols: parallelogram to `INPUT`/`OUTPUT`, rectangle to assignment, diamond to `IF` or loop condition.
6. Refine in levels, one level at a time, and keep the comments in the final pseudocode aligned to the high-level steps.
7. Write logic statements with explicit parentheses whenever more than one operator is present.
