---
title: Hardware Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/03 Hardware/00 Overview|Hardware]]"
status: active
tags:
  - computerscience/computer-systems
  - solutions
---

# Hardware Key Practice Solutions

These solutions correspond to [[30 Computer Science/01 Topics/03 Hardware/30 Key Practice Problems|Key Practice Problems]].

## A. Memory and storage

### Problem 1

The CPU can only work on data that is in primary memory, because primary memory is directly addressable by the CPU and is fast. But primary memory is volatile, so its contents are lost when power is removed, and it is limited in size. Secondary storage is non-volatile and large, so it holds files, programs, and data permanently when power is off or when they are not in use. Each property makes the other necessary: primary memory needs secondary storage because it loses everything at power off, and secondary storage needs primary memory because the CPU cannot address it directly, so data must be loaded into primary memory before it can be used.

### Problem 2

- Volatility: RAM is volatile (contents lost without power); ROM is non-volatile (contents survive without power).
- Writable in normal use: RAM is read/write and the CPU can change any byte; ROM is read-only in normal use and cannot be written to at run time.
- Typical use: RAM holds the running program and its data; ROM holds permanent data such as the boot program (BIOS/UEFI) that runs at switch-on.

### Problem 3

DRAM is chosen for main memory. DRAM stores each bit using one transistor and one capacitor, so it is cheap and dense, which is what the large main store needs. It must be refreshed thousands of times per second because the capacitor leaks, so it is slower than SRAM, but main memory is large and the speed is still acceptable. SRAM is faster and needs no refresh, but it uses several transistors per bit, so it is expensive and low density, which makes it unsuitable for the gigabytes of main memory. SRAM is used instead for the small, very fast CPU cache.

### Problem 4

- PROM: programmed once by the user; cannot be erased.
- EPROM: erasable; erased in bulk by strong ultraviolet light through a quartz window, with the chip removed from the circuit.
- EEPROM: erasable; erased electrically, byte by byte, while still in the circuit.

### Problem 5

PROM is the best choice. The boot code is final and will never change, so PROM's one-time programming is sufficient, and it is cheap in mass production. EPROM would also work but adds the cost of a quartz window and UV erase facility that will never be used. EEPROM would allow electrical updates in place, which is unnecessary and more expensive for code that never changes.

### Problem 6

Flash memory stores bits in floating-gate transistors and is written and erased electrically, which is the same mechanism as EEPROM; it is a fast, block-oriented form of EEPROM. The difference is that flash erases whole blocks at a time rather than individual bytes, which makes it fast enough for bulk storage. A solid state drive (SSD), a USB flash drive, or an SD card is built from flash memory.

### Problem 7

A buffer is a small area of memory used to hold data temporarily while it moves between two devices that operate at different speeds. The CPU is far faster than the printer, so without a buffer the CPU would have to wait after sending each line until the printer had finished it, wasting CPU time. With a buffer, the CPU writes the whole document into the buffer (or a print spooler) and moves on, and the printer reads from the buffer at its own pace. The slow device no longer stalls the fast one.

## B. Devices and embedded systems

### Problem 8

1. A rotating photosensitive drum is given a uniform positive charge.
2. A laser scans the page image onto the drum, discharging the spots it hits.
3. Negatively charged toner powder is attracted onto the discharged areas, forming the image on the drum.
4. The drum rolls over paper, transferring the toner to the page.
5. A fuser unit heats and presses the toner so it melts and bonds to the paper, producing the finished page.

### Problem 9

A 3D printer uses additive manufacturing: it builds a solid object layer by layer. Software slices a 3D model into thin horizontal layers. In a common method (FDM), a nozzle extrudes melted plastic filament over a moving platform; each layer hardens on top of the one below until the object is complete. Other methods cure liquid resin with a laser. The result is a solid, three-dimensional part built up from many thin layers.

### Problem 10

Sound waves are varying air pressure that move a thin diaphragm in the microphone. In a dynamic microphone the moving diaphragm drives a coil in a magnetic field to generate a voltage; in a condenser microphone it changes a capacitance. The resulting analogue voltage is then sampled by an ADC (analogue-to-digital converter) in the sound card, which turns each sample into a digital value the computer can store and process.

### Problem 11

- Moving parts: a magnetic hard disk has spinning platters and moving read/write heads; an SSD has no moving parts.
- Speed: an SSD is faster because it reads and writes electrically with no mechanical seeking; a magnetic hard disk is slower because the heads must move to the right track and wait for the platter to rotate.
- Resistance to shock: an SSD is shock-resistant because it has no moving parts; a magnetic hard disk is vulnerable to shock because a bump can crash the heads into the platter.

### Problem 12

A laser beam reflects off the surface of the spinning disc. The surface holds pits (tiny indentations) and lands (flat areas), which reflect the beam differently. A sensor measures the reflected light and converts the changes between pits and lands into the 0s and 1s of the stored data. A writer uses a higher-power laser to burn pits into a recordable layer, or to change the phase of a material so the data can be rewritten.

### Problem 13

A touchscreen is both an input device and an output device. It is an output device because it displays an image like any screen, and it is an input device because its touch-sensitive layer detects where a finger lands and reports the touch coordinates to the computer. In a capacitive touchscreen, a transparent conductive layer carries a small charge; touching it changes the local capacitance, and the controller calculates the coordinates.

### Problem 14

Benefits:

- Small, low power, and cheap to mass-produce for one dedicated task.
- Reliable and predictable, with no general-purpose operating system overhead, and often real-time response.

Drawbacks:

- Limited hardware, with little memory and processing power compared with a general-purpose computer.
- Hard to upgrade or repair; a firmware bug may require the whole device to be recalled, and development and testing are specialised work.

## C. Monitoring and control

### Problem 15

A monitoring system measures a physical quantity through a sensor and reports or displays it, and may sound an alarm if a reading goes outside a set range; it does not change the thing being measured. A control system measures a physical quantity and uses that reading to drive actuators that change the process, in order to hold the quantity at or near a target value. The single feature that tells them apart is action: a control system acts on the environment through an actuator, while a monitoring system only observes.

### Problem 16

- Sensor: a temperature sensor, typically a thermistor, which converts water temperature into an electrical signal.
- The sensor's analogue signal is passed through an ADC (analogue-to-digital converter) to give digital readings.
- Actuator: a heater (switched through a relay) that warms the water.

Feedback is the closed loop: the heater warms the water, the temperature sensor measures the new value, and that reading is fed back to the computer, which compares it with the target and decides whether to keep the heater on or switch it off. Because the result of the action is measured, the system can hold the temperature near the target instead of overshooting or undershooting. Without feedback the computer could not tell whether the heater had done its job.

### Problem 17

This is a control system. The motion sensors measure a physical quantity, and the system uses that reading to drive an actuator, the lights, which act on the environment by changing its state. Because the reading causes an action that changes the room, this is control rather than monitoring. If the sensors only logged motion or displayed a message without switching the lights, it would be monitoring.

## D. Logic gates and circuits

### Problem 18

Expression: "Key present" is A; "correct code or manager's card" is $B + C$; the AND joins them, so

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

The safe unlocks only when the key is present and at least one of the code or card condition holds.

### Problem 19

An AND gate outputs the AND of its inputs. The inputs to the AND gate are A and $\overline{B}$, so

$$
X = A \cdot \overline{B}
$$

Reading it back: invert B, AND it with A. X = 1 only when $A = 1$ and $B = 0$.

### Problem 20

$$
X = A \cdot B + A \cdot \overline{B} + \overline{A} \cdot B
$$

Combine the first two terms by factoring out A:

$$
A \cdot B + A \cdot \overline{B} = A \cdot (B + \overline{B}) = A \cdot 1 = A
$$

So the expression reduces to

$$
X = A + \overline{A} \cdot B
$$

Now use the absorption identity: $A + \overline{A} \cdot B = A + B$. (When A is 1 the output is 1 regardless of B; when A is 0 the output is B.) Therefore

$$
X = A + B
$$

Simplified circuit: a single OR gate taking inputs A and B. The output is 1 whenever at least one input is 1.

### Problem 21

Write one AND term for each row where X = 1, using the uncomplemented variable for each 1 and the complemented variable for each 0, then OR the terms.

The rows with X = 1 are:

- $A = 0, B = 1$, giving $\overline{A} \cdot B$
- $A = 1, B = 0$, giving $A \cdot \overline{B}$

So

$$
X = \overline{A} \cdot B + A \cdot \overline{B}
$$

Circuit: a NOT gate inverts A and a second NOT gate inverts B. One AND gate takes inputs $\overline{A}$ and B; a second AND gate takes inputs A and $\overline{B}$. The two AND outputs feed an OR gate, whose output is X.

Reading the table, X is 1 exactly when the two inputs differ, which is the XOR function. So the same behaviour is given by a single XOR gate, the simplified form.
