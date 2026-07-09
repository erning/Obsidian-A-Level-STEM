---
title: Hardware Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[Hardware](00%20Overview.md)"
status: active
tags:
  - computerscience/computer-systems
  - lecture-notes
---

# Hardware Lecture Notes

A processor is built from electronic switches, but switches on their own do
nothing useful. This topic is about what surrounds those switches: the devices
that bring data into the machine, the memory that holds it, the storage that
keeps it permanently, the output devices that send it back to the world, and the
logic gates that decide how the switches combine. Get these layers straight and
the rest of computer science - processors, operating systems, networks - has
something concrete to attach to.

## Source Route

This note follows CAIE Computer Science 9618, AS section 3:

- 3.1 Computers and their components
- 3.2 Logic Gates and Logic Circuits

Section 3 is examined in Paper 1.

## 1. Input, output, primary memory, and secondary storage

A computer system needs four kinds of component to do anything useful, and the
distinction between them is about role, not about speed alone.

- **Input devices** capture data from the outside world and convert it into a
  form the computer can store and process. A microphone turns sound into an
  electrical signal; a touchscreen reports where a finger lands; a sensor turns a
  physical quantity into a voltage.
- **Output devices** do the reverse: they take processed data and present it to
  the outside world. Speakers produce sound, printers produce pages, a screen
  produces an image.
- **Primary memory** (main memory) holds the data and instructions the processor
  is actively using right now. It is fast and directly addressable by the CPU,
  but it is volatile - its contents disappear when power is removed - and it is
  limited in size.
- **Secondary storage** holds data permanently, even without power, and is used
  for files, programs, and data not currently in use. It is non-volatile and
  large, but slower than primary memory because the CPU cannot address it
  directly; data must be loaded into primary memory first. **Removable storage**
  (USB flash drive, optical disc, external SSD) is secondary storage that can be
  unplugged and moved between computers.

The reason all four are needed is a direct consequence of these properties. The
CPU can only work on data that is in primary memory, but primary memory is
volatile and small. Secondary storage supplies capacity and persistence. Input
and output connect the closed box to the physical world. Removing any one role
breaks the chain.

### Buffers

A buffer is a small area of memory used to hold data temporarily while it moves
between two devices that operate at different speeds. When the CPU sends a page
to a printer, the printer is far slower than the CPU. Instead of the CPU waiting
for each line to print, it writes the whole job into a buffer (or a print
spooler) and moves on; the printer then reads from the buffer at its own pace.
Without a buffer, the fast device would stall waiting for the slow one. The same
idea smooths keyboard input, audio playback, and network data.

## 2. Memory types

### RAM versus ROM

Both are primary memory, but they differ in volatility and use.

- **RAM** (Random Access Memory) is read/write and volatile. The running program
  and its data live here, and the CPU can change any byte at any time. Contents
  are lost when power is removed.
- **ROM** (Read Only Memory) is non-volatile and cannot be written to in normal
  use. It holds permanent data such as the boot program (the BIOS/UEFI) that runs
  when the machine is first switched on.

The key contrast is: RAM is temporary working storage that the program controls;
ROM is fixed storage that survives power loss and is not changed at run time.

### SRAM versus DRAM

Both are types of RAM. The difference is how each bit is stored.

| Feature | SRAM | DRAM |
|---|---|---|
| How a bit is held | Flip-flop (several transistors) | One transistor + one capacitor |
| Refresh needed? | No | Yes - capacitor leaks, must be refreshed thousands of times per second |
| Speed | Faster | Slower |
| Cost per bit | More expensive | Cheaper |
| Density | Lower (more components per bit) | Higher |
| Typical use | CPU cache | Main memory (RAM modules) |

The distinguishing feature is refresh: DRAM must be refreshed constantly because
its capacitor leaks charge; SRAM holds its state in a flip-flop and needs no
refresh, which is why it is faster but more expensive. Because DRAM is cheap and
dense it is used for main memory; because SRAM is fast it is used for cache.

### PROM, EPROM, and EEPROM

These are all non-volatile ROM-family chips that the user can program, but they
differ in whether and how they can be erased.

| Type | Programmed by user? | Erasable? | How it is erased |
|---|---|---|---|
| PROM | Yes, once | No | Cannot be erased (fusible links blown once) |
| EPROM | Yes | Yes, whole chip at once | Strong UV light through a quartz window |
| EEPROM | Yes | Yes, electrically, byte by byte | Electrical signal, in-circuit, no removal |

The distinguishing feature is the erase method. PROM is one-time-only; EPROM is
erased in bulk under ultraviolet light, which means removing the chip and wiping
everything; EEPROM is erased electrically and selectively while still in the
circuit, which is why it can be updated in place. Flash memory is a fast, block
form of EEPROM and is the basis of SSDs and USB sticks.

## 3. Hardware devices and their principal operations

Group the syllabus devices by role. For each, know the mechanism, not just the
name.

### Output devices

- **Laser printer.** A rotating photosensitive drum is given a uniform positive
  charge. A laser scans the page image onto the drum, discharging the spots it
  hits. Negatively charged toner powder is attracted to the discharged areas,
  forming the image on the drum. The drum rolls over paper, transferring the
  toner, and a fuser unit heats and presses the toner so it melts and bonds to
  the page. It is a dry process, fast, and good for high-volume, high-quality
  text.
- **3D printer.** Builds a solid object layer by layer (additive manufacturing).
  Software slices a 3D model into thin horizontal layers. A common method (FDM)
  extrudes melted plastic filament through a nozzle that moves over a platform;
  other methods cure liquid resin with a laser. Each layer hardens on top of the
  one below until the object is complete. Used for rapid prototyping and custom
  parts.
- **Speakers.** Convert an electrical audio signal into sound. The varying
  current from the sound card drives an electromagnet (the voice coil) attached
  to a cone, sitting inside a permanent magnet. As the current changes, the coil
  is pushed back and forth, moving the cone and pushing air to create sound
  waves.
- **Virtual reality (VR) headset.** A head-mounted unit with one or two small
  high-resolution screens viewed through lenses that give a wide, stereoscopic
  field of view. Built-in motion sensors (accelerometers and gyroscopes) track
  head movement and update the image so the user feels surrounded by the scene.
  It is usually paired with headphones and hand controllers.

### Input devices

- **Microphone.** Converts sound into an electrical signal. Sound waves (varying
  air pressure) move a thin diaphragm; in a dynamic microphone the moving
  diaphragm drives a coil in a magnetic field to generate a voltage, and in a
  condenser microphone it changes a capacitance. The resulting analogue voltage
  is then sampled by an ADC in the sound card into digital data.
- **Touchscreen.** A display combined with a touch-sensitive layer, so it is both
  an input and an output device. In a capacitive touchscreen a transparent
  conductive layer carries a small charge; when a finger touches it, the local
  capacitance changes, and the controller works out the touch coordinates. (A
  resistive touchscreen instead has two flexible layers that are pressed into
  contact.)

### Storage devices

- **Magnetic hard disk (HDD).** Stores data magnetically on rigid spinning
  platters coated with magnetic material. Read/write heads float just above the
  surface on a cushion of air and magnetise tiny regions to represent bits, then
  read the data back by sensing the magnetic fields. Platters spin fast and heads
  move radially, so any sector can be reached, but the mechanical movement makes
  it slower than solid-state storage and vulnerable to shock.
- **Solid state (flash) memory.** Stores data in arrays of floating-gate
  transistors with no moving parts (SSD, USB stick, SD card). Bits are written
  and erased electrically by trapping or removing charge on a floating gate. It
  is faster, silent, shock-resistant, and lower power than an HDD, but
  historically more expensive per gigabyte and with a limited number of
  write-erase cycles. It is electrically a form of EEPROM.
- **Optical disc reader/writer.** Uses a laser. The beam reflects off the disc
  surface; pits (tiny indentations) and lands (flat areas) reflect the beam
  differently, and the reflected light is read by a sensor to recover the 0s and
  1s. Writers use a higher-power laser to burn pits into a recordable layer
  (CD-R, DVD-R) or to change the phase of a material so data can be rewritten
  (CD-RW, DVD-RW). The medium is single-sided and removable.

## 4. Embedded systems

An embedded system is a computer system built into a larger device to perform a
specific, dedicated function. Its processor, memory, and I/O are designed for one
job rather than for general-purpose computing, and it runs fixed software called
firmware. Examples include washing machines, microwaves, car engine management
units, digital watches, traffic lights, and medical devices.

Benefits:

- Small, low power, and cheap to mass-produce.
- Reliable and dedicated: it does one task with no general-purpose operating
  system overhead, and often responds in real time.
- Predictable and fast for its purpose.

Drawbacks:

- Limited hardware: little memory and processing power compared with a general
  computer.
- Hard to upgrade or repair; firmware updates may be difficult or impossible.
- Purpose-built, so it cannot easily be reused for a different task.
- A bug in the embedded firmware can require the whole device to be recalled, and
  developing and testing the software is specialised work.

## 5. Monitoring and control systems

These systems use sensors to read the physical world. The crucial distinction is
whether the system only observes, or also acts.

- A **monitoring system** measures a physical quantity through a sensor and
  reports or displays it, and may sound an alarm if a reading goes outside a set
  range. It does **not** change the thing being measured; it only watches. For
  example, a greenhouse that displays its temperature and texts you when it drops
  below 5 degrees is monitoring.
- A **control system** measures a physical quantity and uses that reading to
  control the process by driving actuators, in order to keep the quantity at or
  near a target value. The greenhouse that switches its heater on when the
  temperature drops below 5 degrees and off again when it rises is a control
  system. The difference is action.

The components of either system are:

- **Sensors** convert a physical quantity into an electrical signal. The syllabus
  names four: temperature (typically a thermistor), pressure, infra-red (detects
  heat, motion, or reflected IR), and sound (microphone-based).
- An **ADC** (analogue-to-digital converter) turns the sensor's continuous
  signal into digital data the computer can use.
- The **computer** compares each reading with preset limits or a target value and
  decides what to do.
- **Actuators** are the doing parts of a control system: a motor, valve, relay,
  heater, or pump that turns an electrical signal into physical action. A
  monitoring system has sensors but usually no actuators.
- **Feedback** is the closed loop in a control system. The actuator's action
  changes the physical quantity (the heater warms the air), the sensor measures
  the new value, and the result is fed back to the computer to decide the next
  action. Without feedback the system could not tell whether its action worked,
  so it could not hold the quantity steady. Feedback is what keeps a control
  system stable around its target.

## 6. Logic gates and logic circuits

A logic gate is an electronic component whose output (0 or 1) is a fixed function
of its inputs (0 or 1). Treat 0 as off / false / low voltage and 1 as on / true /
high voltage. At AS Level, every gate except NOT has exactly two inputs.

**Boolean notation.** AND is written as a dot or by juxtaposition ($A \cdot B$ or
$AB$), OR as a plus ($A + B$), and NOT as an overbar ($\overline{A}$). Parentheses
set the order of operations, exactly as in algebra.

### The six gates and their truth tables

**NOT** - the output is the inverse of the input.

| A | NOT A |
|---|---|
| 0 | 1 |
| 1 | 0 |

**AND** - the output is 1 only when both inputs are 1.

| A | B | A AND B |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

**OR** - the output is 1 when at least one input is 1.

| A | B | A OR B |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

**NAND** - AND followed by NOT; the output is 0 only when both inputs are 1.

| A | B | A NAND B |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

**NOR** - OR followed by NOT; the output is 1 only when both inputs are 0.

| A | B | A NOR B |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 0 |

**XOR** (exclusive OR) - the output is 1 when exactly one input is 1, that is,
when the inputs differ.

| A | B | A XOR B |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

Two memory aids: NAND and NOR are the complements of AND and OR, so their truth
tables are AND and OR with the output column flipped. XOR is "one or the other,
but not both".

### Converting between statement, expression, circuit, and truth table

The syllabus asks you to convert in every direction. The route is always through
the expression:

- **Statement to expression.** Identify each condition and give it a variable.
  Join conditions with AND when both are required, OR when either is enough, and
  NOT for "the opposite of". Use parentheses to show grouping.
- **Expression to circuit.** Each AND, OR, NOT in the expression becomes one gate.
  Wire the gates so that outputs feed the inputs required by the structure of the
  expression; parentheses tell you which gates feed which.
- **Circuit (or expression) to truth table.** List every combination of inputs.
  For each row, work through the gates left to right, filling in any intermediate
  columns you need, until you reach the final output.
- **Truth table to expression.** Write down one AND term for every row in which
  the output is 1, using the uncomplemented variable for each 1 and the
  complemented variable for each 0 in that row; then OR these terms together.
  This is a sum-of-products form and can then be simplified.

### Worked example: build a circuit and truth table from a statement

**Statement.** A burglar alarm sounds when the system is armed (A) and (a window
is open (B) or a door is open (C)). Let X be the alarm output.

**Step 1 - expression.** "Armed" is A. "Window open or door open" is $B + C$.
"And" joins them, so

$$
X = A \cdot (B + C)
$$

**Step 2 - circuit.** An OR gate takes inputs B and C. The output of that OR gate
feeds one input of an AND gate; the other input of the AND gate is A. The output
of the AND gate is X.

**Step 3 - truth table.** Include the intermediate column $B + C$ so nothing is
done in your head.

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

The alarm sounds only when the system is armed and at least one entry point is
open. Notice that the parentheses matter: the expression $A \cdot B + C$ would
mean the alarm sounds whenever the door is open, armed or not, which is wrong.

## Worked-Thinking Routine

Use this routine for any logic or hardware question.

1. Decide the role of each thing in the question: input, output, memory,
   storage, sensor, or actuator.
2. For memory questions, separate volatile from non-volatile first, then place
   the device inside the right family (RAM/ROM, SRAM/DRAM, PROM/EPROM/EEPROM).
3. For monitoring versus control, ask: does the system act, or only observe? If
   it acts, it needs an actuator and feedback.
4. For logic, always go through the expression. Write it down before drawing or
   tabulating.
5. Build truth tables with all $2^n$ input rows, and add an intermediate column
   for each gate output so the working is checkable.
6. After building a circuit or table, re-read the statement and confirm it means
   the same thing.

## Common Mistakes

- Treating the RAM/ROM difference as just "volatile vs non-volatile". The full
  distinction is volatile and read/write (RAM) versus non-volatile and read-only
  in normal use (ROM).
- Saying SRAM is used for main memory because it is faster. DRAM is main memory
  because it is cheaper and denser; SRAM is cache.
- Confusing EPROM (UV light, whole chip, chip must be removed) with EEPROM
  (electrical, byte by byte, in-circuit).
- Forgetting that at AS Level every gate except NOT has exactly two inputs.
- Mixing up NAND, NOR, and XOR output columns. NAND and NOR are AND/OR flipped;
  XOR is "different inputs".
- Ignoring operator precedence and parentheses: $A \cdot B + C$ is not
  $A \cdot (B + C)$.
- Describing a control system without an actuator, or forgetting that control
  needs feedback to stay stable.

## Quick Self-Check

You are ready to move on when you can answer these without notes.

1. Why does a computer need both primary memory and secondary storage?
2. What does a buffer do, and why is it needed when a CPU drives a printer?
3. State the single feature that distinguishes SRAM from DRAM.
4. How does an EPROM differ from an EEPROM in the way it is erased?
5. Outline the principal operation of a laser printer from charged drum to
   finished page.
6. Why is flash memory considered a form of EEPROM?
7. Give one benefit and one drawback of an embedded system.
8. What is the difference between a monitoring system and a control system?
9. Which component turns an electrical signal into physical action in a control
   system, and why does feedback matter?
10. Draw the truth table for NAND and for XOR from memory.

## Connections

- [Processor Fundamentals](../04%20Processor%20Fundamentals/00%20Overview.md)
  puts these same logic gates and memory types inside the CPU, and uses registers
  and buses built from them.
- [Hardware and Virtual Machines](../15%20Hardware%20and%20Virtual%20Machines/00%20Overview.md)
  extends logic circuits into Boolean algebra and into adders and other
  combinational circuits at A Level.

## Study Sequence

1. Read sections 1 and 2 to fix the roles of input, output, memory, and storage
   and the memory-type families.
2. Learn the device operations in section 3 by the mechanism, grouped by role.
3. Make the monitoring-versus-control and feedback ideas in section 5 concrete
   with one worked scenario each.
4. Memorise the six truth tables, then practise all four conversions with the
   worked example as a model.
5. Self-check against the questions above before connecting to Processor
   Fundamentals.
