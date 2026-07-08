---
title: Hardware Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/03 Hardware/00 Overview|Hardware]]"
status: active
tags:
  - computerscience/computer-systems
  - practice
---

# Hardware Key Practice Problems

Work through these without looking at the solutions. Most prompts are scenario-based, so aim to justify your answer against the alternatives rather than just naming a term. For logic questions, write the Boolean expression before drawing or tabulating.

## A. Memory and storage

1. Explain why a computer needs both primary memory and secondary storage, and state which property of each makes the other necessary.

2. Contrast RAM and ROM under the headings volatility, whether it can be written to in normal use, and a typical use of each.

3. A designer must choose between SRAM and DRAM for the main memory of a desktop computer. State which is chosen and justify it against the other.

4. For each of PROM, EPROM, and EEPROM, state whether it can be erased, and describe how it is erased.

5. A games console manufacturer needs a chip that holds the final, never-updated console boot code. Choose between PROM, EPROM, and EEPROM, and justify your choice against the other two.

6. Explain why flash memory is considered a form of EEPROM, and name one device built from it.

7. A CPU sends a large document to a slow printer. Explain what a buffer does and why the system would be inefficient without one.

## B. Devices and embedded systems

8. Outline the principal operation of a laser printer from the charged drum to the finished page.

9. Describe how a 3D printer builds a solid object, naming the manufacturing method it uses.

10. Outline how a microphone converts sound into a digital signal, naming the component that performs the final conversion.

11. Compare a magnetic hard disk and a solid state drive under the headings moving parts, speed, and resistance to shock.

12. Outline how an optical disc reader uses a laser to recover the 0s and 1s stored on a disc.

13. State whether a touchscreen is an input device, an output device, or both, and justify your answer.

14. Give two benefits and two drawbacks of using an embedded system rather than a general-purpose computer in a domestic appliance.

## C. Monitoring and control

15. Distinguish a monitoring system from a control system, and state the single feature that tells them apart.

16. For a system that keeps a fish tank's temperature near a target value, name a suitable sensor, the component that converts its signal to digital data, and the actuator. Explain how feedback keeps the temperature steady.

17. A museum installs motion sensors that, on detection, switch on the lights in the room. State whether this is monitoring or control and justify your answer.

## D. Logic gates and circuits

18. A safe unlocks (output X) when a key is present (A) and either the correct code is entered (B) or a manager's card is swiped (C). Derive the Boolean expression, describe the circuit, and build the full truth table.

19. A circuit has inputs A and B. A NOT gate inverts B to give $\overline{B}$. An AND gate then takes inputs A and $\overline{B}$, and its output is X. Write the Boolean expression for X and state the input combination that makes X = 1.

20. Simplify the expression $X = A \cdot B + A \cdot \overline{B} + \overline{A} \cdot B$, showing your working, and describe the simplified circuit.

21. From the truth table below, derive a Boolean expression in sum-of-products form and describe the circuit. State which single gate has the same behaviour.

| A | B | X |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |
