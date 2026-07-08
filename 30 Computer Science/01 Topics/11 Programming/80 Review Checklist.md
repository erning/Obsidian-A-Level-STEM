---
title: Programming Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/11 Programming/00 Overview|Programming]]"
status: active
tags:
  - computerscience/programming
  - review-checklist
---

# Programming Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can recall, trace, and explain the ideas without prompting.

## Ideas to Recall

- [ ] Distinguish a constant from a variable.
- [ ] Explain why variables must be declared and initialised before use.
- [ ] Recall the arithmetic, integer arithmetic, relational, and logical operators used in pseudocode.
- [ ] Explain operator precedence and why parentheses make expressions clearer.
- [ ] Recall how `INPUT` and `OUTPUT` interact with the user.
- [ ] Explain why supplied built-in functions should be called as specified, not invented.
- [ ] Distinguish `IF`, nested `IF`, and `CASE` selection.
- [ ] Distinguish `FOR`, `REPEAT`, and `WHILE` loops by when the condition is checked and how often the body may run.
- [ ] Define a procedure as a named block called as a statement.
- [ ] Define a function as a named block that returns one value and can be used in an expression.
- [ ] Distinguish pass by value from pass by reference.
- [ ] Recall header, interface, parameter, argument, and return value.

## Skills to Perform

- [ ] Declare constants and variables using suitable data types.
- [ ] Assign values using the assignment arrow and use `=` only for equality comparison.
- [ ] Build arithmetic and Boolean expressions using parentheses where needed.
- [ ] Use `DIV` and `MOD` correctly for integer quotient and remainder.
- [ ] Write input and output statements with clear prompts.
- [ ] Translate a straight-line design into declarations, assignments, input, and output.
- [ ] Write nested `IF` statements for ordered conditions.
- [ ] Replace suitable equality-based nested `IF` statements with `CASE`.
- [ ] Choose the correct loop type and write the loop so its control value changes.
- [ ] Write a procedure with parameters and call it using `CALL`.
- [ ] Write a function with a return type and use the returned value inside an expression.
- [ ] Use `BYREF` only when the caller's variable must be changed.
- [ ] Refactor repeated logic into a procedure or function with one clear purpose.

## Things to Trace or Explain

- [ ] Trace an expression containing `DIV`, `MOD`, comparisons, and logical operators.
- [ ] Trace a nested `IF` and show which branch is reached.
- [ ] Explain why a `CASE` statement must dispatch on one expression.
- [ ] Trace a `FOR` loop and state the first and last counter values used.
- [ ] Trace a `REPEAT` loop and show why the body runs before the test.
- [ ] Trace a `WHILE` loop where the body runs zero times.
- [ ] Explain how a function call is replaced by its return value in a larger expression.
- [ ] Trace a `BYREF` procedure and show how the caller's variables change.
- [ ] Explain how an interface lets a caller use a routine without knowing its body.
- [ ] Connect this topic to [[30 Computer Science/01 Topics/09 Algorithm Design and Problem-solving/00 Overview|Algorithm Design and Problem-solving]] by explaining how algorithm designs become code.

## Common Errors to Avoid

- [ ] Writing assignment with `=` instead of the assignment arrow.
- [ ] Using a variable before it has been initialised.
- [ ] Forgetting a required closing keyword such as `ENDIF`, `ENDCASE`, `NEXT`, `ENDWHILE`, `ENDPROCEDURE`, or `ENDFUNCTION`.
- [ ] Choosing `CASE` when the branches test unrelated conditions.
- [ ] Writing a loop whose termination condition can never become false.
- [ ] Using `REPEAT` when the loop may need to run zero times.
- [ ] Using a procedure inside an expression.
- [ ] Calling a function as if it were a standalone statement and ignoring the return value.
- [ ] Passing by value when the routine must update the caller's variable.
- [ ] Making one routine do several unrelated jobs.

## Ready to Move On When

- [ ] I can write clean pseudocode from a small design without guessing syntax.
- [ ] I can select the correct construct before writing the code.
- [ ] I can trace variables, conditions, and loop counters through a routine.
- [ ] I can decide whether a reusable block should be a procedure or a function.
- [ ] I can explain a routine's header, interface, parameters, arguments, and return value.
- [ ] I can use pass by reference deliberately and explain why it is needed.
- [ ] I can connect this topic to [[30 Computer Science/01 Topics/10 Data Types and Structures/00 Overview|Data Types and Structures]] through declarations, arrays, records, and files.
- [ ] I can connect this topic to [[30 Computer Science/01 Topics/12 Software Development/00 Overview|Software Development]] by explaining how code is designed, tested, and maintained.
- [ ] I can see how this foundation prepares for [[30 Computer Science/01 Topics/20 Further Programming/00 Overview|Further Programming]].
