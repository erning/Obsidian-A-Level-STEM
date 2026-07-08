---
title: Information Representation Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/01 Information Representation/00 Overview|Information Representation]]"
status: active
tags:
  - computerscience/foundations
  - review-checklist
---

# Information Representation Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can recall, convert, calculate, and justify the ideas without prompting.

## Ideas to Recall

- [ ] Define bit, byte, nibble, binary, denary, hexadecimal, and Binary Coded Decimal (BCD).
- [ ] Recall why hexadecimal is a compact way to inspect binary data.
- [ ] Distinguish unsigned binary, one's complement, and two's complement representations.
- [ ] State the signed range of an $n$-bit two's complement integer.
- [ ] Explain overflow as a result that falls outside the representable range.
- [ ] Distinguish decimal prefixes such as kB, MB, GB from binary prefixes such as KiB, MiB, GiB.
- [ ] Recall the roles of ASCII, extended ASCII, Unicode, UTF-8, and UTF-16.
- [ ] Define pixel, image resolution, screen resolution, colour depth, drawing object, property, and drawing list.
- [ ] Define sampling rate, sampling resolution, analogue-to-digital conversion, and audio channels.
- [ ] Distinguish lossy compression from lossless compression, and recall when RLE is effective.

## Skills to Perform

- [ ] Convert integers between denary, binary, and hexadecimal, including padding to a fixed bit width.
- [ ] Convert each hexadecimal digit to a nibble and group binary bits into nibbles from the right.
- [ ] Encode a denary value in BCD by writing one nibble per denary digit.
- [ ] Form the two's complement of a positive integer by flipping bits and adding 1.
- [ ] Add and subtract signed 8-bit two's complement values and discard the final carry-out correctly.
- [ ] Detect overflow by comparing the carry into the sign bit with the carry out of the sign bit.
- [ ] Calculate bitmap file size using width, height, and colour depth, then convert bits to bytes and KiB.
- [ ] Calculate sound file size using sampling rate, sampling resolution, duration, and channels.
- [ ] Apply run-length encoding to a row of repeated symbols and count the stored values.
- [ ] Choose lossy or lossless compression for a named file and justify the choice from the need for exact recovery.

## Things to Trace or Explain

- [ ] Explain why all stored data can be treated as bit patterns but still needs an interpretation.
- [ ] Trace a denary-to-binary conversion using place values or repeated division, and check the result.
- [ ] Trace a two's complement subtraction as addition of a negative operand.
- [ ] Explain why $+127 + 1$ overflows in 8-bit two's complement even though the binary addition produces a bit pattern.
- [ ] Explain why a storage device labelled in GB may appear smaller when reported in GiB.
- [ ] Trace how an ASCII character becomes a 7-bit pattern, an 8-bit byte, and a UTF-8 byte when it is in the ASCII range.
- [ ] Explain why increasing both bitmap width and height changes file size by a factor of four.
- [ ] Explain how increasing sampling rate and sampling resolution affects sound quality and file size.
- [ ] Explain why RLE works on large flat regions but usually not on photographs.
- [ ] Connect bit patterns and overflow to [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]].

## Common Errors to Avoid

- [ ] Treating hexadecimal as a different value rather than a shorter notation for the same bit pattern.
- [ ] Forgetting to pad binary values before grouping them into hex nibbles.
- [ ] Reading a two's complement negative value as if it were unsigned.
- [ ] Detecting overflow from the final carry-out alone.
- [ ] Forgetting that an $n$-bit two's complement range ends at $+2^{n-1}-1$, not $+2^{n-1}$.
- [ ] Writing $1\,\text{kB}=1024$ bytes instead of using KiB for the binary prefix.
- [ ] Mixing up image resolution with screen resolution.
- [ ] Confusing colour depth with the number of pixels.
- [ ] Forgetting to include stereo channels in sound file size.
- [ ] Choosing lossy compression for data that must be reconstructed exactly.

## Ready to Move On When

- [ ] I can convert between denary, binary, and hexadecimal without losing leading zeros that matter.
- [ ] I can represent positive and negative integers in two's complement and explain the sign bit.
- [ ] I can perform binary addition and subtraction and state whether overflow has occurred.
- [ ] I can explain the difference between decimal and binary size prefixes using a numerical example.
- [ ] I can calculate bitmap and sound file sizes with correct units at every step.
- [ ] I can choose between bitmap and vector graphics for a named use and justify the choice.
- [ ] I can choose between lossy, lossless, and RLE compression from the type of data and the need for exact recovery.
- [ ] I can explain how this topic prepares for [[30 Computer Science/01 Topics/13 Data Representation/00 Overview|Data Representation]].
- [ ] I can connect binary arithmetic and masks to [[30 Computer Science/01 Topics/04 Processor Fundamentals/00 Overview|Processor Fundamentals]].
- [ ] I can connect stored media and physical devices to [[30 Computer Science/01 Topics/03 Hardware/00 Overview|Hardware]].
