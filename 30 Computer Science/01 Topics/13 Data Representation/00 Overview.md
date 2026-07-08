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

- Place this topic directly after [[30 Computer Science/01 Topics/01 Information Representation/00 Overview|1 Information Representation]] so the same idea (everything is bits) extends naturally.
- For floating-point, draw the mantissa and exponent fields and track sign, magnitude, and scale separately.
- Normalise by asking whether the mantissa uses its most significant bits efficiently.

## Practice Directions

- Design a user-defined type for a described problem.
- Choose a file organisation and access method for a given use.
- Convert a floating-point number between binary and denary and normalise it.

## Learning Materials

- [[30 Computer Science/01 Topics/13 Data Representation/10 Lecture Notes|Lecture Notes]]
- [[30 Computer Science/01 Topics/13 Data Representation/10 Lecture Notes.zh-CN|中文讲义]]
- [[30 Computer Science/01 Topics/13 Data Representation/20 Worked Examples|Worked Examples]]
- [[30 Computer Science/01 Topics/13 Data Representation/30 Key Practice Problems|Key Practice Problems]]
- [[30 Computer Science/01 Topics/13 Data Representation/31 Key Practice Solutions|Key Practice Solutions]]
- [[30 Computer Science/01 Topics/13 Data Representation/80 Review Checklist|Review Checklist]]

## Connections

- [[30 Computer Science/01 Topics/01 Information Representation/00 Overview|1 Information Representation]] is the AS foundation this topic extends.
- [[30 Computer Science/01 Topics/20 Further Programming/00 Overview|20 Further Programming]] uses these types and file modes in real code.

## Common Traps

- Confusing sequential organisation with sequential access.
- Forgetting that both mantissa and exponent use two's complement.
- Treating a floating-point result as exact when rounding is unavoidable.
