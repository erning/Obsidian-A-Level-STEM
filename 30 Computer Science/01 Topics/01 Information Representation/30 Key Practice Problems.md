---
title: Information Representation Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[Information Representation](00%20Overview.md)"
status: active
tags:
  - computerscience/foundations
  - practice
---

# Information Representation Key Practice Problems

These problems cover the core skills of 9618 AS Section 1. Attempt them on paper before reading [the solutions](31%20Key%20Practice%20Solutions.md). No answers are given here on purpose: the point is active recall and full written working.

## A. Number systems

1. Convert $214_{10}$ to (a) 8-bit unsigned binary and (b) hexadecimal.
2. Convert $\text{B7}_{16}$ to (a) binary and (b) denary.
3. Represent $-35$ as an 8-bit two's complement integer. Show the flip-and-add-one steps starting from $+35$.
4. Using 8-bit two's complement, compute $90 + 55$. Give the 8-bit result and state, with reasoning, whether overflow occurs.
5. Encode the denary value $839_{10}$ in Binary Coded Decimal (BCD).

## B. Prefixes and file size

6. (a) How many bytes are in $2\,\text{MiB}$? (b) Express $2\,\text{MiB}$ in decimal megabytes ($\text{MB}$).
7. A hard disk is labelled $500\,\text{GB}$ using decimal prefixes. How many $\text{GiB}$ will an operating system that uses binary prefixes report? Give your answer to one decimal place.
8. A bitmap image is $800 \times 600$ pixels with a colour depth of $24$ bits. Calculate the file size in KiB.
9. Calculate the file size, in MiB, of $2$ minutes of stereo CD-quality audio sampled at $44\,100\,\text{Hz}$ with 16-bit resolution.

## C. Text, images and sound

10. The character A has ASCII code $65_{10}$. (a) Write its 7-bit binary pattern. (b) Write the single byte that UTF-8 uses to encode it. (c) Explain why the two encodings agree for this character.
11. Give two distinct reasons why a vector graphic is preferred over a bitmap for a company logo.
12. For a bitmap image, state the effect on file size of (a) doubling the colour depth, and (b) doubling both the width and the height.
13. Define **sampling rate** and **sampling resolution**. For each, state the effect on sound quality and on file size of increasing it.
14. State why an analogue signal must be sampled at a rate greater than twice its highest frequency component.

## D. Compression

15. (a) Define lossy and lossless compression. (b) For each of a text contract and a music track for a portable player, name a suitable compression method and justify the choice.
16. Apply run-length encoding to the row of black (B) and white (W) pixels below. Give the encoded sequence and the total number of stored values.

    $\text{BBBBBWWWWWWBBBWWWWBB}$

17. Give one situation in which run-length encoding produces little or no size reduction, and explain why.
18. Explain why a photograph can usually be compressed to a much smaller file with JPEG than with PNG.

---

After finishing, check your working against [the solutions](31%20Key%20Practice%20Solutions.md) and re-attempt any question you could not complete in full.
