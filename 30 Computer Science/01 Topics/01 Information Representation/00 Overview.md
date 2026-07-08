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

- [[30 Computer Science/01 Topics/01 Information Representation/10 Lecture Notes|Lecture Notes]]
- [[30 Computer Science/01 Topics/01 Information Representation/10 Lecture Notes.zh-CN|中文讲义]]
- [[30 Computer Science/01 Topics/01 Information Representation/20 Worked Examples|Worked Examples]]
- [[30 Computer Science/01 Topics/01 Information Representation/30 Key Practice Problems|Key Practice Problems]]
- [[30 Computer Science/01 Topics/01 Information Representation/31 Key Practice Solutions|Key Practice Solutions]]
- [[30 Computer Science/01 Topics/01 Information Representation/80 Review Checklist|Review Checklist]]

## Connections

- [[30 Computer Science/01 Topics/13 Data Representation/00 Overview|13 Data Representation]] extends this topic with user-defined types, file organisation, and floating-point numbers.
- [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]] consumes the bits that this topic defines.

## Common Traps

- Mixing binary prefixes (powers of 2) with decimal prefixes (powers of 10).
- Forgetting the sign bit when subtracting with two's complement.
- Confusing image resolution with screen resolution.
- Applying lossy compression where exact data is required.
