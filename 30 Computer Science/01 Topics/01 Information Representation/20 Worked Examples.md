---
title: Information Representation Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[Information Representation](00%20Overview.md)"
status: active
tags:
  - computerscience/foundations
  - worked-examples
---

# Information Representation Worked Examples

These worked examples turn the rules from the [lecture notes](10%20Lecture%20Notes.md) into routines you can imitate. Each one shows the full working and a short check, so the value is in the steps, not the final answer. Cover the solution, attempt the prompt on paper, then compare.

## Source Route

- Syllabus **9618 AS Section 1 - Information representation**.
- 1.1 Data Representation, 1.2 Multimedia, 1.3 Compression.
- Assessed in **Paper 1**.

## Example 1: Denary to binary and hexadecimal

**Prompt.** Convert the denary value $173_{10}$ to (a) 8-bit unsigned binary and (b) hexadecimal.

**Solution.**

(a) Subtract powers of $2$, largest first.

$$173 - 128 = 45,\quad 45 - 32 = 13,\quad 13 - 8 = 5,\quad 5 - 4 = 1,\quad 1 - 1 = 0$$

The used powers are $128, 32, 8, 4, 1$, so bits $7,5,3,2,0$ are $1$ and the rest are $0$.

$$173_{10} = 10101101_2$$

(b) Group the bits into nibbles from the right and read each as one hex digit.

$$\underbrace{1010}_{\text{A}}\ \underbrace{1101}_{\text{D}}{}_2 = \text{AD}_{16}$$

**Check.** $\text{AD}_{16} = 10 \times 16 + 13 = 173$, and $10101101_2 = 128 + 32 + 8 + 4 + 1 = 173$. Both match.

## Example 2: Two's complement addition with overflow

**Prompt.** Compute $-50 + (-90)$ using 8-bit two's complement. Give the 8-bit result and state whether overflow occurred.

**Solution.**

Form each operand by negating the positive value. $+50 = 00110010_2$, so flip and add $1$:

$$-50 = 11001101_2 + 1 = 11001110_2$$

$+90 = 01011010_2$, so flip and add $1$:

$$-90 = 10100101_2 + 1 = 10100110_2$$

Add the two values. Working column by column, a ninth bit appears at the left:

$$11001110_2 + 10100110_2 = 1\,01110100_2$$

The leading $1$ (the carry out of the sign bit) is discarded, leaving $01110100_2 = +116_{10}$.

To detect overflow, compare the carry **into** the sign bit (bit 7) with the carry **out of** it. Tracing the columns, the carry into bit 7 is $0$ and the carry out of bit 7 is $1$. They differ, so **overflow occurred**.

**Check.** The true sum is $-140$, which lies outside the 8-bit signed range $[-128, +127]$. Overflow is therefore expected, and the nonsense result $+116$ confirms it.

## Example 3: Binary prefixes versus decimal prefixes

**Prompt.** A pen drive is labelled $16\,\text{GB}$ using decimal prefixes. (a) How many bytes is that? (b) How many $\text{GiB}$ will an operating system that uses binary prefixes report? (c) Explain the gap.

**Solution.**

(a) Decimal giga means $10^9$.

$$16\,\text{GB} = 16 \times 10^9\,\text{bytes} = 16\,000\,000\,000\,\text{bytes}$$

(b) Binary gibi means $2^{30}$.

$$\frac{16 \times 10^9}{2^{30}} = \frac{16\,000\,000\,000}{1\,073\,741\,824} \approx 14.90\,\text{GiB}$$

(c) The vendor counts in steps of $10^9$, the operating system in steps of $2^{30} \approx 1.074 \times 10^9$. Because each binary step is about $7.4\%$ larger, the same number of bytes needs fewer of them.

**Check.** The reported value is smaller than $16$, which is the correct direction, and $14.90\,\text{GiB} \times 2^{30} \approx 16 \times 10^9\,\text{bytes}$, recovering the labelled capacity.

## Example 4: ASCII and Unicode

**Prompt.** The uppercase letter Z has ASCII code $90_{10}$. Give its (a) 7-bit ASCII pattern, (b) 8-bit extended ASCII byte, (c) UTF-8 byte. Why does the UTF-8 byte equal the ASCII byte?

**Solution.**

(a) $90 = 64 + 16 + 8 + 2 = 1011010_2$.

(b) Extended ASCII pads to 8 bits: $01011010_2$.

(c) UTF-8 encodes the ASCII range $0$ to $127$ as a single byte identical to the ASCII code, so Z is stored as $01011010_2$, the same byte.

The match is deliberate: UTF-8 was designed to be **ASCII-compatible**, so plain English text needs no extra space and existing ASCII tools still read it. Characters outside the ASCII range, such as the Chinese character 中 or emoji, need two to four bytes in UTF-8.

**Check.** $01011010_2 = 64 + 16 + 8 + 2 = 90$, and $01011010_2 = 5\text{A}_{16}$, the documented ASCII code for Z.

## Example 5: Bitmap file size

**Prompt.** A bitmap image is $1024 \times 768$ pixels with a colour depth of $16$ bits. Calculate the file size in (a) bits, (b) bytes, (c) KiB.

**Solution.**

$$\text{size (bits)} = \text{width} \times \text{height} \times \text{colour depth}$$

(a) $1024 \times 768 \times 16 = 12\,582\,912\,\text{bits}$.

(b) $\dfrac{12\,582\,912}{8} = 1\,572\,864\,\text{bytes}$.

(c) $\dfrac{1\,572\,864}{1024} = 1536\,\text{KiB}$.

**Check.** $1536\,\text{KiB} = 1.5\,\text{MiB}$, a clean number that fits the inputs: the factor of $1024$ in the width cancels one division by $1024$, leaving $768 \times 2 = 1536$.

## Example 6: Sound file size

**Prompt.** A mono voice recording lasts $45$ seconds, sampled at $22\,050\,\text{Hz}$ with a sampling resolution of $8$ bits. Calculate the file size in KiB.

**Solution.**

$$\text{size (bits)} = \text{sampling rate} \times \text{resolution} \times \text{duration} \times \text{channels}$$

With one channel:

$$22\,050 \times 8 \times 45 \times 1 = 7\,938\,000\,\text{bits}$$

$$\frac{7\,938\,000}{8} = 992\,250\,\text{bytes}$$

$$\frac{992\,250}{1024} \approx 969\,\text{KiB}$$

**Check.** Each of halving the CD sampling rate, using 8-bit instead of 16-bit, and mono instead of stereo cuts the size relative to CD audio, so a sub-megabyte answer for $45$ seconds of mono speech is plausible.

## Example 7: Run-length encoding

**Prompt.** A row of 20 black (B) and white (W) pixels reads $\text{BBBBBWWWWWWBBBWWWWBB}$. Apply run-length encoding and state the number of stored values.

**Solution.** Replace each run of identical pixels by a count and a colour.

| Run length | Colour | Encoded pair |
| --- | --- | --- |
| 5 | B | 5B |
| 6 | W | 6W |
| 3 | B | 3B |
| 4 | W | 4W |
| 2 | B | 2B |

Encoded: 5B 6W 3B 4W 2B. That is $5$ pairs, or $10$ stored values, replacing the original $20$.

**Check.** The counts sum to $5 + 6 + 3 + 4 + 2 = 20$, matching the row length, and the colours alternate correctly, so the row can be rebuilt exactly. The encoding is therefore lossless.

## Example 8: Lossy versus lossless justification

**Prompt.** A wedding photographer must (a) archive the master images for later re-editing and (b) email small preview copies to the client. Choose a compression method for each and justify it.

**Solution.**

(a) **Lossless** for the masters, for example RAW or TIFF (or PNG for screen work). Re-editing demands the exact original pixel values; any discarded detail is gone permanently, which is unacceptable for a master.

(b) **Lossy** for the previews, for example JPEG. Previews only need to look acceptable on a screen, the human eye tolerates the small artefacts JPEG introduces, and lossy compression gives far smaller files that email quickly. The masters are retained separately, so the lost detail does not matter.

**Check.** The decision rests on a single question: must the original be recoverable exactly? Yes - lossless; no - lossy. That matches the rule from the lecture notes.

## Study Routine

1. For conversions, write the place-value table or the subtraction chain. Do not do it in your head.
2. For two's complement, always form the negative operand explicitly, then compare carry into and out of the sign bit.
3. For file sizes, compute in bits first, then divide by $8$, then by $1024$ repeatedly, carrying units at every line.
4. For compression, first classify the data (text, photograph, flat graphic, audio) and then ask whether exact recovery matters.
