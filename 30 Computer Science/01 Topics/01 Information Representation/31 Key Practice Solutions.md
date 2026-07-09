---
title: Information Representation Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[Information Representation](00%20Overview.md)"
status: active
tags:
  - computerscience/foundations
  - solutions
---

# Information Representation Key Practice Solutions

This note gives worked solutions for [Information Representation Key Practice Problems](30%20Key%20Practice%20Problems.md). Each solution shows the full working so you can find the step where your reasoning diverged, not just compare final answers.

## A. Number systems

### Problem 1

Convert $214_{10}$ to 8-bit unsigned binary and to hexadecimal.

(a) Subtract powers of $2$:

$$214 - 128 = 86,\quad 86 - 64 = 22,\quad 22 - 16 = 6,\quad 6 - 4 = 2,\quad 2 - 2 = 0$$

Used powers: $128, 64, 16, 4, 2$.

$$214_{10} = 11010110_2$$

(b) Split into nibbles: $1101\,0110_2 = \text{D6}_{16}$.

Check: $13 \times 16 + 6 = 214$.

### Problem 2

Convert $\text{B7}_{16}$ to binary and denary.

(a) Each hex digit is one nibble: $\text{B} = 1011_2$, $7 = 0111_2$.

$$\text{B7}_{16} = 10110111_2$$

(b) $\text{B} = 11$, so $\text{B7}_{16} = 11 \times 16 + 7 = 176 + 7 = 183_{10}$.

Check: $128 + 32 + 16 + 4 + 2 + 1 = 183$.

### Problem 3

Represent $-35$ in 8-bit two's complement.

$+35 = 32 + 2 + 1 = 00100011_2$.

1. Flip every bit: $11011100_2$.
2. Add $1$: $11011100_2 + 1 = 11011101_2$.

$$-35 = 11011101_2$$

Check: $-128 + 64 + 16 + 8 + 4 + 1 = -35$.

### Problem 4

Compute $90 + 55$ in 8-bit two's complement.

$+90 = 01011010_2$ and $+55 = 00110111_2$.

$$01011010_2 + 00110111_2 = 10010001_2$$

The sign bit of the result is $1$, reading as $-128 + 16 + 1 = -111$, which is wrong for a true sum of $145$.

Overflow check: tracing the columns, the carry **into** the sign bit (bit 7) is $1$ and the carry **out of** the sign bit is $0$. They differ, so **overflow occurred**. This is expected, since the true sum $145$ exceeds the maximum 8-bit signed value $+127$.

### Problem 5

Encode $839_{10}$ in BCD.

Each denary digit becomes one nibble: $8 = 1000_2$, $3 = 0011_2$, $9 = 1001_2$.

$$839_{10} = 1000\ 0011\ 1001_{\text{BCD}}$$

Check: reading the nibbles as denary digits gives $8$, $3$, $9$.

## B. Prefixes and file size

### Problem 6

(a) $2\,\text{MiB} = 2 \times 2^{20}\,\text{bytes} = 2 \times 1\,048\,576 = 2\,097\,152\,\text{bytes}$.

(b) In decimal megabytes: $\dfrac{2\,097\,152}{10^6} = 2.097152\,\text{MB}$.

Check: $2\,\text{MiB}$ is about $4.9\%$ larger than $2\,\text{MB}$, consistent with the mebi-to-mega ratio.

### Problem 7

$500\,\text{GB} = 500 \times 10^9\,\text{bytes}$.

$$\frac{500 \times 10^9}{2^{30}} = \frac{500\,000\,000\,000}{1\,073\,741\,824} \approx 465.7\,\text{GiB}$$

The operating system reports about $465.7\,\text{GiB}$.

### Problem 8

Bitmap size: $800 \times 600$ at 24-bit colour depth.

$$800 \times 600 \times 24 = 11\,520\,000\,\text{bits}$$

$$\frac{11\,520\,000}{8} = 1\,440\,000\,\text{bytes}$$

$$\frac{1\,440\,000}{1024} \approx 1406.25\,\text{KiB}$$

The file is about $1406\,\text{KiB}$ (roughly $1.37\,\text{MiB}$).

### Problem 9

Stereo CD audio: $44\,100\,\text{Hz}$, 16-bit resolution, $2$ channels, $120$ seconds.

$$44\,100 \times 16 \times 120 \times 2 = 169\,344\,000\,\text{bits}$$

$$\frac{169\,344\,000}{8} = 21\,168\,000\,\text{bytes}$$

$$\frac{21\,168\,000}{1024 \times 1024} \approx 20.19\,\text{MiB}$$

The file is about $20.2\,\text{MiB}$.

## C. Text, images and sound

### Problem 10

(a) $65 = 64 + 1 = 1000001_2$ (7 bits).

(b) UTF-8 encodes the ASCII range as a single byte, so A is stored as $01000001_2$.

(c) UTF-8 was designed to be ASCII-compatible: code points $0$ to $127$ use one byte identical to the ASCII code. This keeps plain English text compact and lets existing ASCII tools read it unchanged.

### Problem 11

- A logo must scale from a tiny favicon to a large billboard without losing sharpness. Vector graphics resize without pixelation because the geometry is stored mathematically rather than as a fixed grid of pixels.
- Vector files stay very small because they store a list of objects and properties rather than one entry per pixel, which also makes recolouring and editing easy.

### Problem 12

(a) Doubling the colour depth doubles the file size, since size is proportional to colour depth.

(b) Doubling both width and height quadruples the file size, because the pixel count is multiplied by $2 \times 2 = 4$.

### Problem 13

- **Sampling rate**: the number of samples taken per second, in Hz. Increasing it captures higher frequencies and improves fidelity, but increases file size linearly.
- **Sampling resolution**: the number of bits used to store each sample. Increasing it gives finer amplitude steps and less quantisation noise, but also increases file size linearly.

### Problem 14

Sampling below twice the highest frequency causes **aliasing**: high-frequency components of the signal fold back into lower frequencies and distort the reconstruction. Sampling at more than twice the highest frequency (the Nyquist criterion) lets the original wave be rebuilt without that corruption.

## D. Compression

### Problem 15

(a) **Lossless** compression allows the original file to be reconstructed exactly; no information is discarded. **Lossy** compression discards information judged imperceptible, so the original cannot be recovered, but the file becomes much smaller.

(b) A text contract must be recovered byte-for-byte, so use a **lossless** method such as ZIP. A music track for a portable player only needs to sound acceptable, the ear tolerates the discarded detail, and storage is limited, so use a **lossy** method such as MP3 or AAC.

### Problem 16

The row is $\text{BBBBBWWWWWWBBBWWWWBB}$.

| Run length | Colour | Pair |
| --- | --- | --- |
| 5 | B | 5B |
| 6 | W | 6W |
| 3 | B | 3B |
| 4 | W | 4W |
| 2 | B | 2B |

Encoded: 5B 6W 3B 4W 2B, which is $5$ pairs or $10$ stored values, replacing the original $20$.

Check: $5 + 6 + 3 + 4 + 2 = 20$, matching the row length.

### Problem 17

A photograph. Adjacent pixels usually differ slightly in colour and brightness, so runs of identical values are very short, and the count-and-colour pairs add overhead instead of saving space. RLE only compresses well on images with large flat regions, such as cartoons, screenshots or icons.

### Problem 18

JPEG is lossy: it discards high-frequency colour and brightness detail that the human eye barely perceives, which yields large reductions. PNG is lossless and must preserve every pixel exactly, so it can only exploit redundancy within the data, giving much smaller savings on the continuous tones of a photograph.
