---
title: 13 Data Representation
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/data
---

# 13 Data Representation

## Core Idea

This A Level topic extends section 1 with the data types programmers define, the way files are organised on disk, and how real numbers are stored in binary floating-point form.

## Source Alignment

- 9618 A Level section 13 Data Representation
- 13.1 User-defined data types
- 13.2 File organisation and access
- 13.3 Floating-point numbers, representation and manipulation
- Paper 3

## What to Learn

- Why user-defined types are necessary.
- Non-composite types: enumerated, pointer.
- Composite types: set, record, class/object.
- Choosing and designing an appropriate user-defined type for a problem.
- File organisation: serial, sequential (using a key field), random (using a record key).
- File access: sequential access for serial and sequential files; direct access for sequential and random files.
- Hashing algorithms to read from and write data to random or sequential files.
- Binary floating-point format using two's complement.
- Effect of allocating bits to mantissa and exponent.
- Converting binary floating-point to denary and vice versa.
- Normalisation and the reasons for it.
- Consequences of approximation: underflow, overflow, and rounding errors.

## How to Study

- Place this topic directly after [1 Information Representation](../01%20Information%20Representation/00%20Overview.md) so the same idea (everything is bits) extends naturally.
- For floating-point, draw the mantissa and exponent fields and track sign, magnitude, and scale separately.
- Normalise by asking whether the mantissa uses its most significant bits efficiently.

## Practice Directions

- Design a user-defined type for a described problem.
- Choose a file organisation and access method for a given use.
- Convert a floating-point number between binary and denary and normalise it.

## Learning Materials

- [Lecture Notes](10%20Lecture%20Notes.md)
- [中文讲义](10%20Lecture%20Notes.zh-CN.md)
- [Worked Examples](20%20Worked%20Examples.md)
- [Key Practice Problems](30%20Key%20Practice%20Problems.md)
- [Key Practice Solutions](31%20Key%20Practice%20Solutions.md)
- [Review Checklist](80%20Review%20Checklist.md)

## Connections and Extensions

- [Information Representation](../01%20Information%20Representation/00%20Overview.md) is the foundation for the number bases, two's complement, storage sizes, and bit-level thinking used here.
- [Data Types and Structures](../10%20Data%20Types%20and%20Structures/00%20Overview.md) prepares the idea that data has type, structure, and operations; this topic formalises larger user-defined types and file organisation.
- [Further Programming](../20%20Further%20Programming/00%20Overview.md) uses records, classes, pointers, file modes, and floating-point limits in real programs.
- [Databases](../08%20Databases/00%20Overview.md) connects to records, keys, file organisation, and the need to retrieve structured data accurately.

## Common Traps

- Confusing sequential organisation with sequential access.
- Forgetting that both mantissa and exponent use two's complement.
- Treating a floating-point result as exact when rounding is unavoidable.
