---
title: Hardware Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/03 Hardware/00 Overview|Hardware]]"
status: active
tags:
  - computerscience/computer-systems
  - worked-examples
---

# Hardware Worked Examples

These examples model how to reason through scenario-based questions on memory types, devices, embedded systems, monitoring versus control, and logic gates. The aim is not to recite definitions but to show how to choose a component for a named situation, and how to move between a statement, a Boolean expression, a circuit, and a truth table.

## Source Route

- Syllabus: CAIE Computer Science 9618, AS Section 3 - Hardware.
- Assessed in Paper 1.
- Topics: input, output, primary memory, secondary storage; buffers; embedded systems; device operations; RAM/ROM, SRAM/DRAM, PROM/EPROM/EEPROM; monitoring versus control; logic gates and conversions between statement, expression, circuit, and truth table.

## Example 1: SRAM vs DRAM for a CPU Cache

**Prompt.** A designer must choose between SRAM and DRAM for the small, very fast memory that sits inside the CPU and holds the most frequently used instructions. State which is chosen and justify it against the other.

**Solution.** SRAM is chosen.

- SRAM holds each bit in a flip-flop, so it is faster and needs no refresh. That speed is exactly what a cache needs.
- DRAM holds each bit in a capacitor that leaks and must be refreshed thousands of times per second, so it is slower and would add delay on every CPU access.
- SRAM is more expensive and less dense than DRAM, but the cache is small, so the cost is acceptable and the high price per bit is not the deciding factor.

The cache is chosen for speed, so SRAM is used. DRAM's cheapness and density matter for the much larger main memory, not for the cache.

**Check.** If the question names a small fast store close to the CPU, the answer is SRAM; if it names the large main store, the answer is DRAM.

## Example 2: PROM vs EPROM vs EEPROM for a Controller

**Prompt.** A manufacturer is writing firmware for a washing machine's embedded controller. The firmware will be finished before shipping and will never change. Separately, a developer needs a chip whose stored data can be corrected electrically while the device runs, without removing it. For each case, choose PROM, EPROM, or EEPROM and justify it.

**Solution.**

- For the washing machine, **PROM** is suitable. It is programmed once by the user and can never be erased, which is fine because the firmware is final. PROM is also cheap in mass production. EPROM or EEPROM would also work but add cost for an erase facility that is not needed.
- For the developer who must update in place, **EEPROM** is suitable. It is erased electrically, byte by byte, while still in the circuit, so the device need not be opened and the chip need not be removed.
- **EPROM** is rejected for the second case because it is erased in bulk by strong ultraviolet light through a quartz window, which means removing the chip and wiping everything, not correcting a value in place.

**Check.** Match the erase requirement first: never = PROM, bulk by UV = EPROM, electrical in-circuit = EEPROM.

## Example 3: Sensor and Actuator Set for a Heating Control

**Prompt.** A greenhouse must keep its temperature near a target value. Name a suitable sensor, the component that turns the signal into digital data, and the actuator. Explain how feedback keeps the temperature steady.

**Solution.**

- Sensor: a **temperature sensor** (typically a thermistor), which converts air temperature into an electrical signal.
- The sensor's analogue signal is passed through an **ADC** (analogue-to-digital converter) to give digital readings the computer can compare with the target.
- Actuator: a **heater** (switched through a relay), which the computer turns on or off to change the air temperature.

Feedback is the closed loop: the heater warms the air, the temperature sensor measures the new value, and that reading is fed back to the computer, which decides whether to keep the heater on or switch it off. Because the result of the action is measured, the system can hold the temperature near the target instead of overshooting or undershooting. Without feedback the computer could not tell whether the heater had done its job.

**Check.** A control system must act, so it needs an actuator and a feedback loop; a sensor alone only monitors.

## Example 4: Monitoring vs Control for a Smoke Alarm

**Prompt.** A warehouse installs sensors that detect smoke and, on detection, sound an alarm. State whether this is a monitoring or a control system and justify your answer.

**Solution.** This is a **monitoring system**.

- The sensors measure a physical quantity (smoke) and the system reports it by sounding an alarm.
- The system does **not** drive an actuator that changes the thing being measured. It does not put out the fire or alter the air; it only observes and warns.

It would become a control system if the reading were used to act on the environment, for example to trigger a sprinkler that reduces the fire. As described, it only watches and alerts, so it is monitoring.

**Check.** Ask whether the system acts on the environment. If it only measures, reports, or alarms, it is monitoring; if it drives an actuator to change the quantity, it is control.

## Example 5: Truth Table from a Burglar Alarm Statement

**Prompt.** A burglar alarm output X sounds when the system is armed (A) and either a window is open (B) or a door is open (C). Derive the Boolean expression, describe the circuit, and build the truth table.

**Solution.**

Expression: "Armed" is A; "window open or door open" is $B + C$; the AND joins them, so

$$
X = A \cdot (B + C)
$$

Circuit: an OR gate takes inputs B and C; its output feeds one input of an AND gate, whose other input is A. The AND gate output is X.

Truth table, with an intermediate column $B + C$:

| A | B | C | $B + C$ | $X = A \cdot (B + C)$ |
|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 1 | 0 |
| 1 | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 | 1 |
| 1 | 1 | 0 | 1 | 1 |
| 1 | 1 | 1 | 1 | 1 |

The alarm sounds only when armed and at least one entry point is open.

**Check.** The parentheses matter: $A \cdot B + C$ would sound the alarm whenever the door is open, armed or not, which is wrong.

## Example 6: Boolean Expression from a Circuit

**Prompt.** A circuit has inputs A and B. A NOT gate inverts A to give $\overline{A}$. A NAND gate then takes inputs $\overline{A}$ and B, and its output is X. Write the Boolean expression for X.

**Solution.** A NAND gate outputs the NOT of (its inputs ANDed). The inputs to the NAND gate are $\overline{A}$ and B, so their AND is $\overline{A} \cdot B$, and NAND complements it:

$$
X = \overline{\overline{A} \cdot B}
$$

To read this back: invert A, AND it with B, then invert the result.

**Check.** NAND is AND-then-NOT, so the expression must show the AND inside the overbar. If you had written $A \cdot \overline{B}$ you would have inverted the wrong input.

## Example 7: Simplify a Boolean Expression

**Prompt.** Simplify the expression

$$
X = A \cdot B + A \cdot \overline{B}
$$

**Solution.** Factor out the common term A:

$$
X = A \cdot (B + \overline{B})
$$

For any variable, $B + \overline{B} = 1$ (it is either B or not B, so always true). Therefore

$$
X = A \cdot 1 = A
$$

So the simplified expression is simply $X = A$. A whole two-gate circuit reduces to a wire carrying A, because whenever A is 1 the output is 1 regardless of B, and whenever A is 0 the output is 0.

**Check.** Confirm with a truth table: the original expression is 1 only when $A = 1$ (in both the $B = 0$ and $B = 1$ rows), and 0 whenever $A = 0$, which matches $X = A$.

## Example 8: Truth Table to Circuit Description

**Prompt.** The truth table below defines an output X of inputs A and B. Derive a Boolean expression in sum-of-products form and describe the circuit.

| A | B | X |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 0 |

**Solution.** Write one AND term for each row where X = 1, using the uncomplemented variable for each 1 and the complemented variable for each 0 in that row, then OR the terms together.

The only row with X = 1 is $A = 0, B = 0$, which gives the term $\overline{A} \cdot \overline{B}$. So

$$
X = \overline{A} \cdot \overline{B}
$$

Circuit description: a NOT gate inverts A, a second NOT gate inverts B. The two inverted signals feed an AND gate, whose output is X. Reading the table, X is 1 only when both inputs are 0, which is exactly the NOR function. So the same behaviour could be built with a single NOR gate, which is the simplified form.

**Check.** The sum-of-products expression and the NOR gate agree: both give X = 1 only for the row $A = 0, B = 0$.
