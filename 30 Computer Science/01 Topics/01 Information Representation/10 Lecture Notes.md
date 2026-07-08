---
title: Information Representation Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/01 Information Representation/00 Overview|Information Representation]]"
status: active
tags:
  - computerscience/foundations
  - lecture-notes
---

# Information Representation Lecture Notes

Everything inside a computer - numbers, text, pixels, sound samples - is ultimately a pattern of bits. This topic builds the lowest layer of the CAIE 9618 model: how raw magnitudes and media are turned into binary, how to move cleanly between number bases, how to reason about file sizes, and how compression keeps those files manageable. Master this layer and the later topics on processor architecture, networks and databases become far easier to read, because they all assume you are fluent in binary and the binary/decimal size prefixes.

## Source Route

- Syllabus **9618 AS Section 1 - Information representation**.
- 1.1 Data Representation (number systems, conversions, arithmetic, overflow, BCD, hex, characters).
- 1.2 Multimedia - Graphics, Sound (bitmaps, vectors, sampling).
- 1.3 Compression (lossy, lossless, RLE).
- Assessed in **Paper 1**.

## 1. Number systems and conversions

Computers work in **binary** (base 2) because transistors are two-state devices. Humans read **denary** (base 10). Programmers and hardware designers use **hexadecimal** (base 16) as a compact, human-friendly shorthand for binary, because one hex digit maps exactly to four bits.

| Denary | Binary (4-bit) | Hexadecimal |
| --- | --- | --- |
| $0$ | $0000_2$ | $0$ |
| $5$ | $0101_2$ | $5$ |
| $10$ | $1010_2$ | $\text{A}$ |
| $15$ | $1111_2$ | $\text{F}$ |

### Binary → denary

Write the place values as powers of two and add the positions that hold a $1$.

$$1011_2 = 1{\cdot}8 + 0{\cdot}4 + 1{\cdot}2 + 1{\cdot}1 = 8 + 2 + 1 = 11_{10}$$

### Denary → binary (repeated division by 2)

Convert $45_{10}$ to binary: record remainders bottom-up.

$$45 \div 2 = 22\ \text{r}\,1,\quad 22 \div 2 = 11\ \text{r}\,0,\quad 11 \div 2 = 5\ \text{r}\,1,\quad 5 \div 2 = 2\ \text{r}\,1,\quad 2 \div 2 = 1\ \text{r}\,0,\quad 1 \div 2 = 0\ \text{r}\,1$$

Reading remainders upwards gives $101101_2$. Check: $32 + 8 + 4 + 1 = 45$. Correct.

### Hexadecimal ↔ binary

Group the binary into nibbles (4 bits) and read each as one hex digit.

$$\underbrace{1101}_{\text{D}}\ \underbrace{1010}_{\text{A}}\ \underbrace{0011}_{3}{}_2 = \text{DA3}_{16}$$

Hex is used wherever humans inspect raw bytes: colour values in **RGB** (e.g. $\text{FF8C00}$ for orange), memory addresses, machine code, MAC addresses and error codes.

### Binary Coded Decimal (BCD)

BCC stores each denary digit in its own nibble, ignoring the six values $1010$–$1111$. So $839_{10}$ becomes $1000\ 0011\ 1001_{\text{BCD}}$. BCD is not an efficient storage of the number, but it makes display arithmetic exact and avoids rounding errors, which is why it is used for currency, point-of-sale tills, digital meters and clocks.

### One's and two's complement (signed integers)

For an $n$-bit signed integer the leftmost bit is the **sign bit** ($0$ = positive, $1$ = negative). **One's complement** flips every bit. **Two's complement** - what virtually every modern CPU uses - adds $1$ to the one's complement.

Negate $+13 = 00001101_2$ in 8-bit two's complement:

1. Flip bits: $11110010_2$.
2. Add $1$: $11110010_2 + 1 = 11110011_2$.

So $-13 = 11110011_2$. Verify: the leftmost $1$ signals negative, and $-128 + 64 + 32 + 16 + 2 + 1 = -13$. An $n$-bit two's complement cell holds the range $-2^{n-1}$ to $+2^{n-1}-1$, so 8 bits cover $-128$ to $+127$.

## 2. Binary arithmetic and overflow

Binary **addition** follows the school column rule with carries, and **subtraction** is done by adding the two's complement of the subtrahend.

### Worked subtraction with two's complement

Compute $7 - 3$ using 8 bits.

1. $+7 = 00000111_2$, $+3 = 00000011_2$.
2. Negate $3$: flip $\to 11111100_2$, add $1 \to 11111101_2$.
3. Add: $00000111_2 + 11111101_2 = 00000100_2$ (carry out of $1$ is discarded).
4. Read result: $00000100_2 = +4$. Correct.

### Overflow

**Overflow** occurs when the result of an addition/subtraction falls outside the representable range of the cell. Detect it by checking the carry **into** the sign bit against the carry **out of** the sign bit: if they differ, overflow has occurred.

Example, still 8 bits: $+127 + 1$.

$$01111111_2 + 00000001_2 = 10000000_2$$

The result looks like $-128$, which is wrong for "$+128$" - that value cannot fit in 8-bit two's complement. The carry into the sign bit is $1$, the carry out is $0$, so they differ: overflow flagged.

## 3. Binary prefixes vs decimal prefixes

Storage vendors and networks use **decimal prefixes** (powers of $10$); operating systems and memory use **binary prefixes** (powers of $2$). Mixing them is a classic source of "where did my gigabytes go?" confusion.

| Decimal (SI) | Value | Binary | Value | Ratio |
| --- | --- | --- | --- | --- |
| kilo (kB) | $10^3$ | kibi (KiB) | $2^{10} = 1024$ | $\sim 2.4\%$ |
| mega (MB) | $10^6$ | mebi (MiB) | $2^{20} = 1\,048\,576$ | $\sim 4.9\%$ |
| giga (GB) | $10^9$ | gibi (GiB) | $2^{30} \approx 1.07\times 10^9$ | $\sim 7.4\%$ |
| tera (TB) | $10^{12}$ | tebi (TiB) | $2^{40}$ | $\sim 10\%$ |

So $1\,\text{KiB} = 1024\,\text{bytes}$ but $1\,\text{kB} = 1000\,\text{bytes}$. A "500 GB" disk sold in decimal units holds $500 \times 10^9\,\text{bytes} = 500\,000\,000\,000$ bytes, which an OS using binary prefixes reports as $\dfrac{500\times 10^9}{2^{30}} \approx 465.7\,\text{GiB}$.

## 4. Text, images and sound

### Text - ASCII, extended ASCII, Unicode

Each character is given a numeric **code** that is stored in binary. **ASCII** uses 7 bits ($128$ codes, English letters, digits and control characters). **Extended ASCII** adds an 8th bit for $256$ codes (accented letters, box-drawing). **Unicode** is a universal scheme covering scripts and emoji; its common encodings are **UTF-8** (1–4 bytes per character, ASCII-compatible) and **UTF-16**. Text file size is roughly $\text{characters} \times \text{bytes per character}$, then compressed by the OS.

### Graphics - bitmaps and vectors

A **bitmapped (raster)** image is a grid of **pixels**. A file header stores metadata (dimensions, colour depth); each pixel stores its colour using a fixed number of bits called the **colour depth** (or bit depth).

- **Image resolution** = number of pixels across $\times$ number of pixels down.
- **Screen resolution** = pixels the display hardware can show.
- **Colour depth** $d$ bits allows $2^d$ colours; RGB commonly uses $24$ bits ($8$ each for red, green, blue).

#### Bitmap file size

$$\text{size (bits)} = \text{width} \times \text{height} \times \text{colour depth}$$

Example: a $1920 \times 1080$ image at 24-bit colour.

$$\text{bits} = 1920 \times 1080 \times 24 = 49\,766\,400\ \text{bits}$$

$$\text{bytes} = \frac{49\,766\,400}{8} = 6\,220\,800\ \text{bytes}$$

$$\text{KiB} = \frac{6\,220\,800}{1024} \approx 6075\ \text{KiB} \approx 5.93\ \text{MiB}$$

Doubling colour depth doubles file size; doubling the width and height quadruples it (because both dimensions grow). Increasing resolution improves detail but inflates the file.

**Vector graphics** store the image as a **drawing list** of objects (line, rectangle, curve) plus their **properties** (coordinates, stroke, fill). They scale without quality loss and stay tiny, so they suit logos, fonts and CAD. Bitmaps suit photographs with continuous tone; vectors suit flat graphics that must be resized.

### Sound

Sound is a continuous (analogue) pressure wave. To store it digitally we **sample** the wave at regular intervals and quantise each sample to an integer of $r$ bits (the **sampling resolution**). The **sampling rate** is the number of samples per second (Hz).

$$\text{size (bits)} = \text{sampling rate} \times \text{resolution} \times \text{duration} \times \text{channels}$$

Example: 30 seconds of CD-quality stereo audio at $44\,100\ \text{Hz}$, 16-bit resolution, 2 channels.

$$\text{bits} = 44\,100 \times 16 \times 30 \times 2 = 42\,336\,000\ \text{bits}$$

$$\text{bytes} = \frac{42\,336\,000}{8} = 5\,292\,000\ \text{bytes} \approx 5.05\ \text{MiB}$$

Higher sampling rate and resolution improve fidelity (capturing higher frequencies and finer amplitude steps) but increase file size linearly.

## 5. Compression

Files are compressed to save storage and transmission bandwidth. Two families:

- **Lossless** - the original can be reconstructed exactly (text, spreadsheets, program files). Examples: ZIP, PNG, FLAC.
- **Lossy** - some information judged imperceptible is discarded (photos, music, video). Examples: JPEG, MP3, MPEG. Much higher ratios; the original cannot be recovered.

| File type | Typical method | Reason |
| --- | --- | --- |
| Text | Lossless (Huffman, LZW) | Must recover exact bytes |
| Bitmap | Lossy (JPEG) or lossless (PNG) | Eye tolerates loss; photos compress well |
| Vector | Lossless | Objects are already compact; lossy would corrupt geometry |
| Sound | Lossy (MP3) or lossless (FLAC) | Ear tolerates loss; speech/music compress well |

### Run-length encoding (RLE)

RLE replaces a run of identical values with a single value plus a count. For an image row of 12 black/white pixels:

$$\text{BBBBBWWWWBB} \;\to\; 5\text{B}\,4\text{W}\,2\text{B}$$

The 12 symbols become 3 pairs. RLE is lossless and very effective on images with large flat regions (cartoons, screenshots, icons) but useless on photographs, where adjacent pixels rarely match.

## Worked-Thinking Routine

1. Identify the target base or representation; choose the smallest set of steps to get there.
2. For size questions, work in **bits first**, then divide by $8$ for bytes, by $1024$ for KiB, by $1024$ again for MiB.
3. For signed arithmetic, convert to two's complement, add, then check the carry into vs out of the sign bit for overflow.
4. For compression, classify the data first (text vs photo vs flat graphic) before picking lossy or lossless.
5. Carry units at every step - bits vs bytes is the most common exam slip.

## Common Mistakes

- Writing $1\,\text{kB} = 1024\,\text{bytes}$; that is the **kibi** value. Decimal kilo is $1000$.
- Forgetting to discard the carry-out when adding two's complement numbers.
- Detecting overflow by the carry-out alone rather than comparing carry-in and carry-out of the sign bit.
- Computing image size in bytes before multiplying by colour depth (wrong order).
- Ignoring stereo channels (factor of $2$) in a sound file size.
- Assuming RLE helps photographs - it rarely does.

## Quick Self-Check

- Convert $11001010_2$ to denary and to hex. (Hint: sign bit tells you nothing about magnitude here - treat as unsigned.)
- Negate $+22$ in 8-bit two's complement.
- Add $-50 + -80$ in 8 bits. Did overflow occur? How do you know?
- A $800 \times 600$ bitmap with 16-bit colour depth - how many KiB?
- 1 minute of mono speech at $8000\ \text{Hz}$, 8-bit - how many KiB?
- Give one reason a vector graphic is preferable to a bitmap for a company logo.

## Connections

- [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]] - overflow flags feed directly into the CPU's status register.
- [[30 Computer Science/01 Topics/13 Data Representation/00 Overview|Data Representation]] (A Level extension) - integers, floating point, parity and error detection build on this topic.

## Study Sequence

1. Read this note top to bottom; redo every worked example on paper.
2. Drill base conversions until the denary/hex/binary table is automatic.
3. Practise two's complement addition and overflow detection until the carry rule is reflexive.
4. Memorise the two file-size formulae and rehearse unit conversions.
5. Finish with the syllabus checklist: tick each "show understanding" point against what you can now explain.
