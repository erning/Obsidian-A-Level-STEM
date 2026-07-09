---
title: Data Representation Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[Data Representation](00%20Overview.md)"
status: active
tags:
  - computerscience/data
  - solutions
---

# Data Representation Key Practice Solutions

This note gives worked solutions for [Data Representation Key Practice Problems](30%20Key%20Practice%20Problems.md). Each solution shows the full working so you can find the step where your reasoning diverged, not just compare final answers. All floating-point values use an 8-bit mantissa and a 4-bit exponent in two's complement unless stated otherwise.

## A. User-defined types

### Problem 1

The traffic light takes one of a fixed, ordered set of named states with no arithmetic meaning, so an **enumerated** type is the natural choice.

```pseudocode
TYPE LightState = (Red, RedAmber, Green, Amber)

DECLARE phase : LightState
phase ← Green
IF phase = Red OR phase = RedAmber THEN
   OUTPUT "Stop"
ENDIF
```

Check: the four names match the problem's states exactly, and every value assigned appears on the `TYPE` line, so the compiler can reject any illegal value.

### Problem 2

Several named fields of different types grouped under one name call for a **record**.

```pseudocode
TYPE Vehicle
   DECLARE RegNo : STRING
   DECLARE DailyRate : REAL
   DECLARE Mileage : INTEGER
   DECLARE Rented : BOOLEAN
ENDTYPE

DECLARE v : Vehicle
v.RegNo ← "AB12 CDE"
v.DailyRate ← 45.00
v.Mileage ← 24813
v.Rented ← TRUE
OUTPUT v.DailyRate
```

Check: each field has a type taken from the problem (string, real, integer, Boolean), and fields are accessed with dot notation on the declared variable `v`.

### Problem 3

A value that stores the **address** of another value is a **pointer**.

```pseudocode
TYPE RealPtr = ^REAL

DECLARE p : RealPtr
DECLARE balance : REAL
balance ← 120.50
p ← @balance       // p holds the address of balance
OUTPUT p^          // prints 120.50 (dereference)
p^ ← 75.00         // updates balance to 75.00 through the pointer
```

Check: `p` is declared with the pointer type, `@balance` takes the address of a `REAL`, and `p^` dereferences back to a `REAL`, so the types agree throughout.

### Problem 4

(a) **Enumerated** type. The responses form a small, fixed, ordered set, so naming them as constants lets the compiler catch illegal values and makes the code self-documenting.

(b) **Set**. The tags form an unordered collection with no duplicates, and the typical operations are membership ("does this photo have the tag 'beach'?") and combination, which is exactly what a set provides.

(c) **Class/object**. The data (name, address, balance) comes together with the operations that act on it (debit, credit). Encapsulating data and behaviour in one unit is the defining property of a class.

## B. File organisation and access

### Problem 5

| Scenario | Organisation | Access | Reason |
|---|---|---|---|
| (a) Monthly payroll | Sequential | Sequential | Sorted on key field EmployeeID; read start to finish once a month |
| (b) Point-of-sale log | Serial | Sequential | Sales arrive in time order, appended to the end, processed as a batch |
| (c) Hospital patient lookup | Random | Direct | One record is needed at once; patient number hashes straight to its address |

Check: batch without a key gives serial; batch with a sorted key gives sequential; interactive single-record access gives random.

### Problem 6

| Organisation | Sequential access | Direct access |
|---|---|---|
| Serial | Valid | Not valid |
| Sequential | Valid | Valid (offset from position in key order) |
| Random | Not natural | Valid (address from the hash) |

### Problem 7

Apply `address = AccountNo MOD 13`.

| AccountNo | Calculation | Address |
|---|---|---|
| $1042$ | $1042 \bmod 13$ | $2$ |
| $2071$ | $2071 \bmod 13$ | $2$ |
| $3158$ | $3158 \bmod 13$ | $8$ |
| $4203$ | $4203 \bmod 13$ | $6$ |

$1042 = 80 \times 13 + 2$; $2071 = 159 \times 13 + 2$; $3158 = 242 \times 13 + 8$; $4203 = 323 \times 13 + 6$. Keys $1042$ and $2071$ both hash to slot $2$: a **collision**.

### Problem 8

Two resolution methods:

- **Overflow area.** Keep the first record (say $1042$) at slot $2$, and store the colliding record ($2071$) in a separate overflow area. Slot $2$ holds a pointer chaining to the overflow record, so a search that lands on slot $2$ can follow the chain.
- **Rehashing.** Probe the next slots in turn ($3, 4, \dots$) and place $2071$ in the first free one. A common probe is simply "next free slot".

To retrieve $2071$ later: compute $2071 \bmod 13 = 2$, go to slot $2$, find it is not the wanted record, and follow the overflow chain (or probe the next slots under rehashing) until the matching key is found.

## C. Floating-point conversion

### Problem 9

Value $01100000\;0011$.

1. Exponent $0011$, sign bit $0$, so $+3$.
2. Mantissa $01100000$, binary point after the sign bit gives $0.1100000_{2}$.
3. Fraction: $0.1100000_{2} = \tfrac{1}{2} + \tfrac{1}{4} = 0.75$.
4. Value $= 0.75 \times 2^{3} = 0.75 \times 8 = \mathbf{6.0}$.

Check: $6.0 = 110.0_{2} = 0.110 \times 2^{3}$, matching the mantissa and exponent.

### Problem 10

Value $01010000\;0010$.

1. Exponent $0010 = +2$.
2. Mantissa $01010000$, point after sign bit: $0.1010000_{2}$.
3. Fraction: $0.1010000_{2} = \tfrac{1}{2} + \tfrac{1}{8} = 0.625$.
4. Value $= 0.625 \times 2^{2} = 0.625 \times 4 = \mathbf{2.5}$.

Check: $2.5 = 10.1_{2} = 0.101 \times 2^{2}$, matching the fields.

### Problem 11

Value $10100000\;0011$. The mantissa sign bit is $1$, so it is negative.

1. Exponent $0011 = +3$.
2. Mantissa $10100000$, point after sign bit: $1.0100000_{2}$. In two's complement the leading $1$ contributes $-1$ and the remaining bits add $+0.0100000_{2} = +0.25$, so the mantissa value is $-1 + 0.25 = -0.75$.
3. Value $= -0.75 \times 2^{3} = -0.75 \times 8 = \mathbf{-6.0}$.

Check: the magnitude $6.0$ matches Problem 9, and the only difference is the negative sign bit, so the result is the negation of that value.

### Problem 12

Convert $3.25$ with 8-bit mantissa, 4-bit exponent.

1. Integer part $3 = 11_{2}$; fractional part $0.25 = 0.01_{2}$; so $3.25 = 11.01_{2}$.
2. Normalise to $0.1\dots$: slide the point two places left, exponent $+2$: $11.01_{2} = 0.1101 \times 2^{2}$.
3. Mantissa in 8 bits, point after sign bit: $0.1101 \rightarrow 01101000$ (pad with three zero bits).
4. Exponent $+2$ in 4 bits: $0010$.
5. Result: $01101000\;0010$.

Check: $0.1101000_{2} = \tfrac{1}{2} + \tfrac{1}{4} + \tfrac{1}{16} = 0.8125$, times $2^{2} = 4$ gives $3.25$. The round trip returns the original value.

### Problem 13

Convert $-2.5$ with 8-bit mantissa, 4-bit exponent.

1. Magnitude $2.5 = 10.1_{2}$. Normalise the positive form: $10.1_{2} = 0.101 \times 2^{2}$, giving a positive mantissa $01010000$ and exponent $0010$.
2. Negate the mantissa in two's complement. Flip every bit: $01010000 \rightarrow 10101111$. Add $1$: $10101111 + 1 = 10110000$.
3. Exponent is unchanged: $0010$.
4. Result: $10110000\;0010$.

Check: mantissa $1.0110000_{2} = -1 + 0.0110000_{2} = -1 + 0.375 = -0.625$, times $2^{2} = 4$ gives $-2.5$. Correct, and the leading bits $10$ confirm a normalised negative.

### Problem 14

- **Format A (10-bit mantissa, 6-bit exponent):** favours **range**. The 6-bit exponent encodes a wider spread of powers of two, so it can represent very large and very small magnitudes, at the cost of fewer significant bits and lower precision.
- **Format B (12-bit mantissa, 4-bit exponent):** favours **precision**. The larger mantissa holds more significant bits, reducing the rounding error, at the cost of a narrower range.

Both total 16 bits; the trade-off is that bits given to the exponent widen the range while bits given to the mantissa sharpen the precision.

## D. Normalisation and errors

### Problem 15

Value $00011000\;0101$.

1. Exponent $0101 = +5$. Mantissa sign bit $0$ (positive), so the normalised form must begin $01$.
2. Currently the mantissa begins $0001$, so shift left until it begins $01$: $00011000 \rightarrow 01100000$, which is $3$ left shifts.
3. Subtract $1$ from the exponent per shift: $5 - 3 = 2$. Exponent $0010$.
4. Result: $01100000\;0010$.

Check: unnormalised, $0.0001100_{2} = \tfrac{3}{32}$, times $2^{5} = 32$ gives $3.0$. Normalised, $0.1100000_{2} = 0.75$, times $2^{2} = 4$ also gives $3.0$. The values match.

### Problem 16

Value $11011000\;0101$. The mantissa sign bit is $1$ (negative), so the normalised form must begin $10$.

1. Exponent $0101 = +5$. Mantissa currently begins $11$, so shift left until it begins $10$: $11011000 \rightarrow 10110000$, which is $1$ left shift.
2. Subtract $1$ from the exponent: $5 - 1 = 4$. Exponent $0100$.
3. Result: $10110000\;0100$.

Check: unnormalised, $1.1011000_{2} = -1 + 0.1011000_{2} = -1 + 0.6875 = -0.3125$, times $2^{5} = 32$ gives $-10.0$. Normalised, $1.0110000_{2} = -1 + 0.0110000_{2} = -1 + 0.375 = -0.625$, times $2^{4} = 16$ also gives $-10.0$. The values match.

### Problem 17

1. **Maximum precision.** Normalisation places the binary point just after the first significant bit, so every available mantissa bit carries information rather than repeating leading zeros or ones. For a given field width this gives the smallest possible rounding error.
2. **Unique representation.** Without normalisation the same value could be stored in several ways (for example $0.1000 \times 2^{2}$ and $0.0100 \times 2^{3}$). Normalisation gives each value a single canonical form, which makes equality tests and arithmetic consistent.

### Problem 18

(a) **Underflow.** The result is too close to zero to represent, because its magnitude is smaller than the smallest normalised number, so it is stored as $0$.

(b) **Overflow.** The magnitude is too large for the exponent field; the required power of two cannot be stored, so the result is undefined or stored as infinity.

(c) **Rounding error.** $0.2_{10} = 0.0\overline{0011}_{2}$ has no exact finite binary form, so the stored mantissa is the nearest representable value and a small error is introduced.

### Problem 19

Summing many small values, such as adding $0.1$ ten thousand times, lets each rounding error accumulate, because $0.1_{10}$ has no exact binary form. A bank iterating such additions daily could drift noticeably from the true total. A practical consequence is that programmers compare floating-point results with a tolerance (an "epsilon") rather than testing for exact equality, and may use a decimal or integer representation for money.

### Problem 20

The claim confuses **range** with **accuracy**. A wider exponent field does widen the range, but for a fixed total number of bits those extra bits are taken from the mantissa, leaving fewer significant bits and therefore a larger rounding error, that is, lower precision. Accuracy in the sense of "how close is the stored value to the true value" depends on the mantissa, not the exponent. So a wider exponent field lets you represent bigger and smaller magnitudes, but it does not make any individual value more accurate.
