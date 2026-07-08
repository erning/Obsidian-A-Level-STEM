---
title: Algorithm Design and Problem-solving Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/09 Algorithm Design and Problem-solving/00 Overview|Algorithm Design and Problem-solving]]"
status: active
tags:
  - computerscience/programming
  - review-checklist
---

# Algorithm Design and Problem-solving Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can recall, trace, and explain the ideas without prompting.

## Ideas to Recall

- [ ] Define abstraction and explain why an abstract model keeps only details that affect the solution.
- [ ] State the benefits of abstraction: simpler design, easier testing, less irrelevant data, and a more general solution.
- [ ] Define decomposition and explain how sub-problems become modules.
- [ ] Distinguish a procedure from a function by whether a value is returned.
- [ ] Define an algorithm as finite, unambiguous, and effective steps that solve a problem.
- [ ] Recall what an identifier table records: name, data type, and purpose.
- [ ] Name the three constructs: sequence, selection, and iteration.
- [ ] Distinguish `IF`, `CASE`, `FOR`, `WHILE`, and `REPEAT` by the control situation each one represents.
- [ ] Recall the main flowchart symbols: terminator, process, decision, input/output, and flow line.
- [ ] Explain structured English, flowcharts, and pseudocode as three representations of the same logic.
- [ ] Define stepwise refinement as expanding a high-level solution into implementable detail.
- [ ] Recall how `AND`, `OR`, and `NOT` combine comparisons in logic statements.

## Skills to Perform

- [ ] Identify the inputs, processing, and outputs before writing an algorithm.
- [ ] Build an abstract model by crossing out details that do not affect the answer.
- [ ] Decompose a scenario into one-job modules and label each as a procedure or function.
- [ ] Write an identifier table with suitable data types and meaningful names.
- [ ] Write straight-line pseudocode using assignment, input, output, and clear identifiers.
- [ ] Choose the correct loop type from the problem wording and justify the choice.
- [ ] Convert structured English into pseudocode without changing the logic.
- [ ] Convert a flowchart into pseudocode by mapping each symbol to a construct.
- [ ] Describe the flowchart that matches a short piece of pseudocode.
- [ ] Refine a problem from level 0 steps to level 1 detail and then to pseudocode.
- [ ] Write logic statements with explicit parentheses when more than one logical operator appears.
- [ ] Trace a short algorithm line by line using a small set of test data.

## Things to Trace or Explain

- [ ] Explain why input-process-output is the starting point for algorithm design.
- [ ] Trace how a selection splits into branches and rejoins after `ENDIF`.
- [ ] Trace how a `WHILE` loop can run zero times and how a `REPEAT` loop runs at least once.
- [ ] Explain how a `CASE` structure is different from several unrelated `IF` statements.
- [ ] Trace a sentinel-controlled loop and show where the next input must occur.
- [ ] Explain why a module should usually have one clear purpose.
- [ ] Trace how a logic statement changes value when parentheses are moved.
- [ ] Explain why refinement should expand all steps at one level before moving deeper.
- [ ] Connect this topic to [[30 Computer Science/01 Topics/10 Data Types and Structures/00 Overview|Data Types and Structures]] by explaining how chosen identifiers later become arrays, records, files, or ADTs.
- [ ] Connect this topic to [[30 Computer Science/01 Topics/11 Programming/00 Overview|Programming]] by explaining how designs become working pseudocode.

## Common Errors to Avoid

- [ ] Starting pseudocode before identifying inputs, processing, and outputs.
- [ ] Keeping irrelevant real-world details in an abstract model.
- [ ] Splitting a problem into modules that each do several unrelated jobs.
- [ ] Calling a routine a function when it does not return a value.
- [ ] Using a `FOR` loop when the number of repetitions is not known.
- [ ] Using `REPEAT` when the body may need to run zero times.
- [ ] Leaving a loop without changing the value that controls termination.
- [ ] Forgetting `ENDIF`, `ENDCASE`, `NEXT`, or `ENDWHILE`.
- [ ] Using assignment notation where a comparison is required, or the other way round.
- [ ] Writing `A AND B OR C` without parentheses when the intended grouping matters.

## Ready to Move On When

- [ ] I can reduce a scenario to an abstract model and justify every detail kept or removed.
- [ ] I can decompose a problem into modules and choose procedure or function for each one.
- [ ] I can write an identifier table before writing the algorithm itself.
- [ ] I can express the same simple algorithm as structured English, a flowchart description, and pseudocode.
- [ ] I can choose and write sequence, selection, and iteration constructs confidently.
- [ ] I can refine a vague high-level step until it is ready to program.
- [ ] I can trace my own pseudocode and find where a condition, loop, or update goes wrong.
- [ ] I can connect this topic to [[30 Computer Science/01 Topics/19 Computational Thinking and Problem-solving/00 Overview|Computational Thinking and Problem-solving]] and explain what is extended there.
- [ ] I can connect this topic to [[30 Computer Science/01 Topics/12 Software Development/00 Overview|Software Development]] by explaining how decomposition becomes structure charts and module testing.
