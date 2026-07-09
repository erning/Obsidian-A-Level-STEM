---
title: 01 Information Representation
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/foundations
---

# 01 Information Representation

## Core Idea

Everything in a computer is stored as bits. This topic covers how numbers, text, images, and sound are each turned into binary, and how compression reduces the cost of storing and moving them.

## Source Alignment

- 9618 AS section 1 Information representation
- 1.1 Data Representation
- 1.2 Multimedia - Graphics, Sound
- 1.3 Compression
- Paper 1

## What to Learn

- Binary, denary, hexadecimal, and BCD representations; one's and two's complement.
- Converting integers between bases; binary addition and subtraction; overflow.
- Binary prefixes (kibi, mebi, gibi, tebi) versus decimal prefixes (kilo, mega, giga, tera).
- Character sets: ASCII, extended ASCII, and Unicode.
- Bitmap graphics: pixel, file header, image resolution, screen resolution, colour depth, and file size.
- Vector graphics: drawing object, property, and drawing list.
- Sound: sampling, sampling rate, sampling resolution, and analogue-to-digital conversion.
- Lossy and lossless compression, including run-length encoding (RLE).

## How to Study

- Convert between bases until the place-value pattern is automatic.
- Track the bit width whenever you add or subtract, and predict overflow before calculating.
- Estimate bitmap and sound file sizes from resolution and colour or sampling depth.
- Justify bitmap versus vector, and lossy versus lossless, for a named task.

## Practice Directions

- Convert numbers between binary, denary, hexadecimal, and BCD.
- Perform binary addition and subtraction with signed integers.
- Estimate image and sound file sizes and the effect of changing resolution.
- Choose a compression method for a given file type and justify it.

## Learning Materials

- [Lecture Notes](10%20Lecture%20Notes.md)
- [中文讲义](10%20Lecture%20Notes.zh-CN.md)
- [Worked Examples](20%20Worked%20Examples.md)
- [Key Practice Problems](30%20Key%20Practice%20Problems.md)
- [Key Practice Solutions](31%20Key%20Practice%20Solutions.md)
- [Review Checklist](80%20Review%20Checklist.md)

## Connections and Extensions

- [Data Representation](../13%20Data%20Representation/00%20Overview.md) extends the same bit-level ideas into floating-point numbers, user-defined data types, and file organisation.
- [Processor Fundamentals](../04%20Processor%20Fundamentals/00%20Overview.md) uses binary arithmetic, overflow, shifts, masks, and character-sized data as part of low-level execution.
- [Hardware](../03%20Hardware/00%20Overview.md) gives the physical context for storage devices, displays, speakers, microphones, and the logic circuits that make binary possible.
- [System Software](../05%20System%20Software/00%20Overview.md) uses compression, files, and translators that all depend on accurate representation of data.

## Common Traps

- Mixing binary prefixes (powers of 2) with decimal prefixes (powers of 10).
- Forgetting the sign bit when subtracting with two's complement.
- Confusing image resolution with screen resolution.
- Applying lossy compression where exact data is required.
