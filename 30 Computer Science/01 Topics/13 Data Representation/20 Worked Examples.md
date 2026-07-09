---
title: Data Representation Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[Data Representation](00%20Overview.md)"
status: active
tags:
  - computerscience/data
  - worked-examples
---

# Data Representation Worked Examples

These worked examples turn the rules from the [lecture notes](10%20Lecture%20Notes.md) into routines you can imitate. Each one shows the full working and a short check, so the value is in the steps, not the final answer. Cover the solution, attempt the prompt on paper, then compare.

## Source Route

- Syllabus **9618 A Level section 13 - Data Representation**.
- 13.1 User-defined data types, 13.2 File organisation and access, 13.3 Floating-point numbers.
- Assessed in **Paper 3**.

## Example 1: Design an enumerated type

**Prompt.** A weather station records the current conditions as one of a fixed set of states: sunny, cloudy, rainy, stormy, snowy. Design a suitable user-defined data type in pseudocode and show how a variable of this type is declared and assigned.

**Solution.** The value is one of a small known set of named states with no arithmetic meaning, so an **enumerated** type fits best. The order in the declaration defines the internal mapping to $0, 1, 2, \dots$.

```pseudocode
TYPE Weather = (Sunny, Cloudy, Rainy, Stormy, Snowy)

DECLARE today : Weather
today ← Stormy
IF today = Stormy OR today = Snowy THEN
   OUTPUT "Issue weather warning"
ENDIF
```

Using an enumerated type rather than integers $0$ to $4$ lets the compiler catch illegal values such as `today ← 9` and makes the code self-documenting.

**Check.** The five names match the problem's set exactly, and every value used in the code appears on the `TYPE` line, so no undeclared value can be assigned.

## Example 2: Design a record type

**Prompt.** A library stores each book's catalogue number (integer), title, author and whether it is currently on loan (Boolean). Design a composite data type for a book and show one field access.

**Solution.** Several named fields of different types grouped under one name call for a **record**.

```pseudocode
TYPE Book
   DECLARE CatalogueNo : INTEGER
   DECLARE Title : STRING
   DECLARE Author : STRING
   DECLARE OnLoan : BOOLEAN
ENDTYPE

DECLARE b : Book
b.CatalogueNo ← 1042
b.Title ← "Things Fall Apart"
b.Author ← "Chinua Achebe"
b.OnLoan ← TRUE
OUTPUT b.Title, b.OnLoan
```

**Check.** Each declared field has a type taken from the problem (integer, string, string, Boolean), and fields are accessed with dot notation on the declared variable `b`.

## Example 3: Design a pointer type

**Prompt.** A program needs a variable that refers to the address of an `INTEGER` held elsewhere, so it can be read and updated indirectly. Declare a pointer type and show a dereference.

**Solution.** A value that stores the **address** of another value of a given base type is a **pointer**.

```pseudocode
TYPE IntPtr = ^INTEGER

DECLARE p : IntPtr
DECLARE x : INTEGER
x ← 42
p ← @x          // p holds the address of x
OUTPUT p^       // prints 42 (dereference)
p^ ← 99         // updates x to 99 through the pointer
```

Pointers are what let dynamic structures such as linked lists and trees be built and reshaped at run time.

**Check.** `p` is declared with the pointer type, `@x` takes the address of an `INTEGER`, and `p^` dereferences back to an `INTEGER` value, so the types line up at every step.

## Example 4: Choose file organisation and access

**Prompt.** For each scenario, name the most suitable file organisation and the access method it would use, with a one-line reason. (a) A nightly backup of the day's transaction logs. (b) A monthly payroll run sorted by employee number. (c) A cash machine looking up one customer's balance by account number.

**Solution.**

| Scenario | Organisation | Access | Reason |
|---|---|---|---|
| (a) Transaction log backup | Serial | Sequential | Records arrive in time order and are processed as a batch; no key is needed |
| (b) Monthly payroll | Sequential | Sequential | Sorted on the key field EmployeeID so each batch is read start to finish |
| (c) Cash machine lookup | Random | Direct | One record is needed at once; the account key hashes straight to its address |

**Check.** The two questions that decide organisation are "batch or interactive?" and "is there a usable key?". Batch without a key gives serial; batch with a sorted key gives sequential; interactive single-record access gives random. Direct access is valid for sequential and random files, but not for serial.

## Example 5: Modulus hashing with a collision

**Prompt.** Records keyed by `EmployeeID` are stored in a random file with $11$ slots, using `address = EmployeeID MOD 11`. Compute the slot for each of the keys $1754$, $1765$, $4429$, and explain how the collision is handled.

**Solution.** Apply the hash function to each key.

| EmployeeID | Calculation | Address |
|---|---|---|
| $1754$ | $1754 \bmod 11$ | $5$ |
| $1765$ | $1765 \bmod 11$ | $5$ |
| $4429$ | $4429 \bmod 11$ | $7$ |

Keys $1754$ and $1765$ both hash to slot $5$: a **collision**. To store both, the system keeps the first record at slot $5$ and places the second in an **overflow area**, chaining it to slot $5$ so a search that lands on $5$ can follow the chain. Alternatively it can **rehash**: probe the next slots ($6, 7, \dots$) and place the second record in the first free one.

To read employee $4429$, compute $4429 \bmod 11 = 7$ and go straight to slot $7$, with no scan of the file.

**Check.** The hash reduces each key to the address range $0$ to $10$, which fits $11$ slots. $1754 \bmod 11$: $1754 = 159 \times 11 + 5$, remainder $5$. $1765 \bmod 11$: $1765 = 160 \times 11 + 5$, remainder $5$. Both remainders agree, confirming the collision.

## Example 6: Floating-point to denary

**Prompt.** Convert the floating-point value $01100000\;0011$ to denary, assuming an 8-bit mantissa and a 4-bit exponent, both in two's complement.

**Solution.** Separate the two fields.

1. Exponent $0011$. Sign bit $0$, so it is $+3$.
2. Mantissa $01100000$. The binary point sits just after the sign bit, giving $0.1100000_{2}$.
3. Decode the fraction: $0.1100000_{2} = \tfrac{1}{2} + \tfrac{1}{4} = 0.75$.
4. Apply the exponent: value $= 0.75 \times 2^{3} = 0.75 \times 8 = \mathbf{6.0}$.

**Check.** A positive mantissa and a positive exponent give a positive result. $6.0$ in binary is $110.0$, which is $0.110 \times 2^{3}$, matching the mantissa and exponent read off above.

## Example 7: Denary to floating-point

**Prompt.** Convert the denary value $5.75$ to a 12-bit floating-point number with an 8-bit mantissa and a 4-bit exponent, both in two's complement. The result should be normalised.

**Solution.**

1. Convert the magnitude to binary. The integer part $5 = 101_{2}$ and the fractional part $0.75 = 0.11_{2}$, so $5.75 = 101.11_{2}$.
2. Normalise the mantissa to the form $0.1\dots$ by sliding the binary point three places left, which means multiplying the mantissa by $2^{-3}$, so the exponent becomes $+3$: $101.11_{2} = 0.10111 \times 2^{3}$.
3. Write the mantissa in 8 bits with the point after the sign bit: $0.10111 \rightarrow 01011100$ (pad the tail with two zero bits).
4. Write the exponent $+3$ in 4-bit two's complement: $0011$.
5. Result: $01011100\;0011$.

**Check.** Read it back using Example 6's routine: mantissa $0.1011100_{2} = \tfrac{1}{2} + \tfrac{1}{8} + \tfrac{1}{16} + \tfrac{1}{32} = 0.71875$, times $2^{3} = 8$ gives $5.75$. The round trip returns the original value.

## Example 8: Normalise a floating-point number

**Prompt.** The unnormalised value $00011000\;0101$ uses an 8-bit mantissa and a 4-bit exponent. Normalise it and show the shift and the exponent adjustment.

**Solution.**

1. Read the fields. Mantissa $00011000$, exponent $0101 = +5$. The mantissa is positive (sign bit $0$), so a normalised positive value must begin with the bits $01$.
2. Shift the mantissa left until the leading bits are $01$. Currently it begins $0001$, so shift left by $3$ places: $00011000 \rightarrow 01100000$.
3. Each left shift of the mantissa multiplies it by $2$, so to keep the value unchanged subtract $1$ from the exponent per shift: $5 - 3 = 2$.
4. Exponent $+2$ in 4-bit two's complement is $0010$.
5. Result: $01100000\;0010$.

**Check.** Decode both forms to confirm they are equal. Unnormalised: $0.0001100_{2} = \tfrac{3}{32}$, times $2^{5} = 32$ gives $3.0$. Normalised: $0.1100000_{2} = 0.75$, times $2^{2} = 4$ also gives $\mathbf{3.0}$. The values match, so the normalisation is correct.

## Example 9: Mantissa and exponent trade-off

**Prompt.** Two 16-bit floating-point formats are proposed. Format A uses a 10-bit mantissa and a 6-bit exponent; format B uses a 12-bit mantissa and a 4-bit exponent. For each, state which property is larger, range or precision, and explain why.

**Solution.**

- **Format A (10 + 6):** the larger exponent field gives a wider **range**. With 6 exponent bits it can encode powers of two from $-32$ to $+31$, so it can represent very large and very small magnitudes. The cost is a smaller mantissa, so fewer significant bits and lower **precision**.
- **Format B (12 + 4):** the larger mantissa field gives higher **precision**, because more bits are available for significant digits and the rounding error is smaller. The cost is a smaller exponent, so the storable magnitudes cover a narrower **range**.

The trade-off is fundamental: for a fixed total number of bits, bits given to the exponent widen the range, while bits given to the mantissa sharpen the precision. You cannot maximise both at once, so the split is chosen to suit the problem.

**Check.** The bit counts add to $16$ in both cases ($10 + 6$ and $12 + 4$), and each format is stronger exactly where the other is weaker, which is the defining property of the trade-off.

## Example 10: Underflow, overflow and rounding

**Prompt.** For each situation, name the floating-point error that occurs and explain it in one sentence. (a) Adding $10^{-40}$ to $0$ in a system whose smallest normalised magnitude is about $10^{-38}$. (b) Squaring a number whose result needs an exponent of $+130$ when the field only holds exponents up to $+127$. (c) Storing $0.1_{10}$ in a binary mantissa.

**Solution.**

(a) **Underflow.** The result is too close to zero for the field to represent, because its magnitude is smaller than the smallest normalised number, so it is stored as $0$.

(b) **Overflow.** The magnitude is too large for the exponent field; the required power of two cannot be stored, so the result is undefined or stored as infinity.

(c) **Rounding error.** $0.1_{10} = 0.000\overline{1100}_{2}$ has no exact finite binary form, so the stored mantissa is the nearest representable value and a small error is introduced. This is also the reason `0.1 + 0.2` does not equal `0.3` in most programming languages.

**Check.** Each case matches the boundary it crosses: underflow sits below the smallest magnitude, overflow above the largest, and rounding error arises whenever a denary fraction has no exact binary expansion that fits the mantissa width.

## Study Routine

1. For type questions, read the noun in the problem: a *list of names* suggests a record, a *fixed set of states* an enumerated type, an *address link* a pointer.
2. For file questions, ask two things: batch or interactive, and is there a usable key? Then match to serial, sequential or random.
3. For hashing, always reduce the key modulo the number of slots, and plan for collisions with an overflow area or rehashing.
4. For floating-point conversion, separate mantissa and exponent first, decode each in two's complement, then combine.
5. For normalisation, identify the sign bit, shift the mantissa until the leading bits are $01$ or $10$, and move the exponent the opposite way to preserve the value.
