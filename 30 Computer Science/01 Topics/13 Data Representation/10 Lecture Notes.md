---
title: Data Representation Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/13 Data Representation/00 Overview|Data Representation]]"
status: active
tags:
  - computerscience/data
  - lecture-notes
---

# Data Representation Lecture Notes

This A Level topic extends AS section 1 (Information Representation). It moves from "how is a single value stored?" to "how do we model whole problems, store records on disk, and represent real numbers without losing too much accuracy?" Everything here is examined in Paper 3.

## Source Route

CAIE 9618 syllabus section 13, three sub-topics:

- **13.1** User-defined data types - enumerated, pointer, set, record, class/object
- **13.2** File organisation and access - serial, sequential, random; hashing
- **13.3** Floating-point numbers - format, conversion, normalisation, errors

## 1. User-defined data types

### 1.1 Why we need them

The built-in types (`INTEGER`, `REAL`, `BOOLEAN`, `CHAR`, `STRING`) each describe a single value. Real problems involve things with several related fields (a student has a name, a mark, a class) or a value drawn from a fixed list (the seven days, the four suits). A user-defined type lets you name such a structure once and reuse it, which makes code clearer, type-safer and easier to maintain.

Two families:

- **Non-composite** - built from a single existing type: enumerated, pointer.
- **Composite** - built from more than one component: set, record, class/object.

### 1.2 Enumerated (non-composite)

```pseudocode
TYPE Day = (Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday)
```

The values are named constants, ordered, with no arithmetic meaning. Internally they map to integers 0, 1, 2, … so comparisons and `FOR` loops work.

Worked use:

```pseudocode
DECLARE today : Day
today ← Wednesday
IF today = Friday THEN
   OUTPUT "Almost the weekend"
ENDIF
```

Use an enumerated type when a variable can only take one of a small known set of values - it catches typos and illegal values at design time.

### 1.3 Pointer (non-composite)

```pseudocode
TYPE IntPtr = ^INTEGER
```

A pointer stores the *address* of another variable, not the value itself. This is what lets you build dynamic structures (linked lists, trees) that grow and shrink at run time.

Worked use:

```pseudocode
DECLARE p : IntPtr
DECLARE x : INTEGER
x ← 42
p ← @x          // p holds the address of x
OUTPUT p^       // prints 42 (dereference)
p^ ← 99         // changes x to 99
```

### 1.4 Set (composite)

```pseudocode
TYPE CharSet = SET OF CHAR
```

A set holds a collection of values from one base type with no duplicates and no order. The classic operations are membership, union, intersection and difference.

Worked use - which vowels appear in a word:

```pseudocode
TYPE VowelSet = SET OF CHAR
DEFINE Vowels() : VowelSet
   ...
ENDDEFINE
```

Use a set when order does not matter and you mainly ask "is X in it?" or "combine these groups".

### 1.5 Record (composite)

```pseudocode
TYPE Student
   DECLARE Name : STRING
   DECLARE Mark : INTEGER
   DECLARE Grade : CHAR
ENDTYPE
```

A record groups named fields of (possibly) different types under one name - exactly what you need for a row of a file or a database tuple.

Worked use:

```pseudocode
DECLARE s : Student
s.Name ← "Ada"
s.Mark ← 87
s.Grade ← 'A'
OUTPUT s.Name, s.Mark
```

### 1.6 Class / object (composite)

A class is a record that also carries the procedures (methods) that act on its data, plus encapsulation. Objects are instances of a class. Design one when behaviour belongs with the data - see Further Programming.

### 1.7 Choosing a type for a problem

| Clue in the problem | Likely type |
|---|---|
| Fixed list of named values | Enumerated |
| Need to refer to / link another value | Pointer |
| Group of items, membership tests, no order | Set |
| Several named fields of different types | Record |
| Fields **plus** the operations on them | Class/object |

## 2. File organisation

*Organisation* = how records are physically arranged on the storage medium.

| Organisation | How records are stored | Typical use |
|---|---|---|
| **Serial** | One after another, in order of arrival | Backups, transaction logs - processed as a batch |
| **Sequential** | Sorted on a **key field** | Periodic batch processing: payroll, monthly statements |
| **Random** (direct) | Each record placed at an address from its **record key** via a hash function | Interactive lookups: bank balance, stock level |

- Serial and sequential files are cheap to read start-to-finish but slow to find a single record in.
- Random files let you jump straight to a record, so they suit live systems that need fast single-record access.

## 3. File access

*Access* = the way you are allowed to read/write records.

| File organisation | Sequential access | Direct access |
|---|---|---|
| Serial | ✔ | ✘ |
| Sequential | ✔ | ✔ |
| Random | ✘ (not natural) | ✔ |

- **Sequential access** - read records one after another from the start. Used for serial and sequential files.
- **Direct access** - go straight to a record by its address/offset, without reading the ones before it. Used for sequential files (offset from position in key order) and random files (address from the hash).

## 4. Hashing algorithms

A hash function turns a record key into a file address, so a random file can place and later find a record in one calculation rather than a search.

**Modulus hashing** is the textbook example:

```
address = key MOD numberOfRecords
```

Worked example - store records keyed by `EmployeeID` in a random file with 11 slots:

| EmployeeID | 1754 | 3200 | 4429 | 5061 |
|---|---|---|---|---|
| Address = key MOD 11 | 5 | 10 | 7 | 1 |

To read employee 4429, compute $4429 \bmod 11 = 7$ and go straight to slot 7 - no scan needed.

**Collisions** occur when two keys hash to the same address. Keys 1754 and 1765 both give 5, since $1765 \bmod 11 = 5$. Collisions are resolved with an **overflow area** (chain the extra record to the slot) or by **rehashing** (probe for the next free slot).

## 5. Floating-point format

A binary floating-point number has two parts, both stored in **two's complement**:

- **Mantissa** - the significant digits, stored as a binary fraction (binary point just after the sign bit).
- **Exponent** - the power of two to multiply by.

So $\text{value} = \text{mantissa} \times 2^{\text{exponent}}$.

A common exam size is 12 bits = 8-bit mantissa + 4-bit exponent, e.g. $01011100\;0011$.

### Mantissa / exponent trade-off

For a fixed total number of bits, giving bits to one part takes them from the other.

| Change | Effect |
|---|---|
| More bits to **exponent** | Larger **range** - can represent very big and very small magnitudes |
| More bits to **mantissa** | Greater **precision** - more significant bits, smaller rounding error |

You cannot maximise both; the syllabus wants you to justify a split for a given problem.

## 6. Conversion

### 6.1 Binary floating-point → denary

Example: 8-bit mantissa, 4-bit exponent. Value $= 01100000\;0011$.

1. Exponent $0011 = +3$.
2. Mantissa $01100000$ - binary point after sign bit $\rightarrow 0.1100000$.
3. $0.1100000_{2} = \tfrac{1}{2} + \tfrac{1}{4} = 0.75$.
4. Value $= 0.75 \times 2^{3} = 0.75 \times 8 = \mathbf{6.0}$.

### 6.2 Denary → binary floating-point

Convert 5.75 with 8-bit mantissa, 4-bit exponent.

1. $5.75 = 101.11_{2}$.
2. Normalise to `0.1…` form: $101.11 = 0.10111 \times 2^{3}$.
3. Mantissa (8 bits, point after sign bit): $01011100$.
4. Exponent $+3$ (4 bits): $0011$.
5. Result: $01011100\;0011$.

For a **negative** number, the normalised mantissa begins $10$ (e.g. $10100000$); build it by writing the magnitude and taking the two's complement.

## 7. Normalisation

**What:** shift the mantissa left so that a positive number begins $01$ and a negative number begins $10$, adjusting the exponent to compensate.

**Why:** this places the binary point just after the first significant bit, so every available mantissa bit carries information $\rightarrow$ **maximum precision** for that field width, and a unique representation for each value.

Worked example - normalise $00011000\;0101$ (8-bit mantissa, 4-bit exponent):

1. Unnormalised value: mantissa $0.0001100 = \tfrac{3}{32}$, exponent $+5$ $\rightarrow \tfrac{3}{32} \times 32 = 3.0$.
2. Shift mantissa left 3 places until it begins $01$: $00011000 \rightarrow 01100000$.
3. Reduce exponent by 3 to keep the value: $5 - 3 = 2$.
4. Result: $01100000\;0010$.
5. Check: $0.1100000 \times 2^{2} = 0.75 \times 4 = \mathbf{3.0}$. ✓

Rule of thumb: each left shift of the mantissa = subtract 1 from the exponent.

## 8. Approximation, underflow, overflow, rounding errors

A finite binary field cannot represent every real number. Four consequences:

- **Approximation.** Many denary fractions have no exact binary form. $0.1_{10} = 0.000\overline{1100}_{2}$, so storing 0.1 is always slightly off - which is why `0.1 + 0.2 != 0.3` in most languages.
- **Rounding error.** When the true value needs more bits than the mantissa has, the stored value is rounded to the nearest representable number; the lost bits cause a small error that can accumulate over many operations.
- **Underflow.** A result too close to zero to represent (magnitude smaller than the smallest normalised number) underflows to zero. Adding $10^{-40}$ to 0 in a system whose smallest number is about $10^{-38}$ gives 0.
- **Overflow.** A result too large in magnitude for the exponent field overflows - the exponent bits cannot hold the required power of two, so the number is stored as "infinity" or is undefined.

## Worked-Thinking Routine

1. **Type question** - read the noun in the problem: a *list of names*? Record. A *fixed set of states*? Enumerated. *Links*? Pointer. *Fields plus behaviour*? Class.
2. **File question** - ask two things: (a) batch or interactive? (b) is there a usable key? Batch + key → sequential; interactive + key → random.
3. **Floating-point conversion** - separate mantissa and exponent first, decode each in two's complement, then combine.
4. **Normalisation** - identify the sign bit, shift the mantissa until the leading bits match the sign ($01$ or $10$), move the exponent the opposite way.

## Common Mistakes

- Using an enumerated value that was not declared on the `TYPE` line.
- Confusing *organisation* (serial/sequential/random) with *access* (sequential/direct).
- Forgetting the exponent is **signed** - $1011$ is $-5$, not $11$.
- Not compensating the exponent when normalising - shifting the mantissa changes the value unless you fix the exponent.
- Assuming 0.1 is exactly representable in binary.
- Putting the binary point in the wrong place - in the syllabus it sits just after the sign bit.

## Quick Self-Check

1. Give one reason to define an enumerated type instead of using integers 1–7.
2. Which file organisation suits a cash machine looking up one account?
3. What access methods are valid for a sequential file?
4. Why modulus-hash a key before storing in a random file?
5. A 16-bit float uses 10 mantissa / 6 exponent bits; another uses 12 / 4. Which has the bigger range, which the better precision?
6. Convert $01010000\;0010$ to denary (8-bit mantissa, 4-bit exponent).
7. Why normalise before storing?
8. Give an example each of underflow and overflow.

## Connections

- [[30 Computer Science/01 Topics/01 Information Representation/00 Overview|Information Representation]] - the AS foundation: number bases, two's complement integers, text/image/sound encoding that this topic builds on.
- [[30 Computer Science/01 Topics/20 Further Programming/00 Overview|Further Programming]] - uses the user-defined types here (records, classes, pointers) and the file modes for real programs.

## Study Sequence

1. Read section 1 and write the four pseudocode type definitions from memory.
2. Memorise the organisation/access table; do three file-choice questions.
3. Practise one modulus-hashing table including a collision.
4. Drill floating-point conversion both ways until automatic.
5. Do five normalisation questions including negatives.
6. Write one sentence each for approximation / underflow / overflow / rounding.
