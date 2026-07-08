---
title: Data Representation Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/13 Data Representation/00 Overview|Data Representation]]"
status: active
tags:
  - computerscience/data
  - review-checklist
---

# Data Representation Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can design types, choose file organisations, and convert floating-point values without prompting.

## Ideas to Recall

- [ ] Explain why user-defined data types make programs clearer, safer, and easier to maintain.
- [ ] Distinguish non-composite types from composite types.
- [ ] Recall the purpose of enumerated, pointer, set, record, and class/object types.
- [ ] Distinguish file organisation from file access.
- [ ] Define serial, sequential, and random file organisation.
- [ ] Define sequential access and direct access.
- [ ] Explain how a key field or record key supports searching and placement.
- [ ] Recall how modulus hashing turns a record key into a file address.
- [ ] Define collision, overflow area, and rehashing.
- [ ] Recall that binary floating-point values store both mantissa and exponent in two's complement.
- [ ] Distinguish range from precision in the mantissa/exponent bit split.
- [ ] Define normalisation, approximation, underflow, overflow, and rounding error.

## Skills to Perform

- [ ] Choose an enumerated type for a fixed list of named values and write the pseudocode declaration.
- [ ] Declare and use a pointer type, including address-of and dereference notation.
- [ ] Design a record type with fields and access one field using dot notation.
- [ ] Choose between set, record, class/object, pointer, and enumerated type for a described problem.
- [ ] Choose serial, sequential, or random file organisation for a scenario and name the access method.
- [ ] Complete the organisation/access table for serial, sequential, and random files.
- [ ] Apply `address = key MOD numberOfRecords` and identify collisions.
- [ ] Describe how overflow areas or rehashing allow colliding records to be stored and later retrieved.
- [ ] Convert a binary floating-point value to denary by decoding mantissa and exponent separately.
- [ ] Convert a denary value to normalised binary floating point with fixed mantissa and exponent widths.
- [ ] Normalise positive and negative floating-point values and adjust the exponent in the opposite direction.
- [ ] Explain the effect of allocating more bits to the mantissa or exponent.

## Things to Trace or Explain

- [ ] Trace how an enumerated value is limited to names declared on the `TYPE` line.
- [ ] Explain how a pointer stores an address rather than the value itself.
- [ ] Trace how a record groups fields that would otherwise travel as separate variables.
- [ ] Explain why a class/object is a record-like structure plus behaviour and encapsulation.
- [ ] Trace a batch file scenario to serial or sequential organisation by asking whether it has a useful key.
- [ ] Trace an interactive lookup to random organisation and direct access through hashing.
- [ ] Explain how retrieval follows the same hash calculation used for storage.
- [ ] Trace a floating-point value from mantissa and exponent to $\text{mantissa}\times2^{\text{exponent}}$.
- [ ] Explain why a normalised positive mantissa begins $01$ and a normalised negative mantissa begins $10$.
- [ ] Explain why storing $0.1_{10}$ or $0.2_{10}$ in binary floating point introduces rounding error.
- [ ] Connect this topic back to [[30 Computer Science/01 Topics/01 Information Representation/00 Overview|Information Representation]].

## Common Errors to Avoid

- [ ] Using an enumerated value that was not declared.
- [ ] Treating a pointer as if it stored the value rather than the address.
- [ ] Using a set when order or duplicates matter.
- [ ] Confusing file organisation with file access.
- [ ] Saying a serial file supports direct access.
- [ ] Forgetting that collisions are expected and must be resolved.
- [ ] Treating the exponent as unsigned when it is stored in two's complement.
- [ ] Placing the binary point somewhere other than just after the mantissa sign bit.
- [ ] Shifting the mantissa during normalisation without compensating the exponent.
- [ ] Claiming that a wider exponent field automatically gives a more accurate value.

## Ready to Move On When

- [ ] I can choose and write a suitable user-defined type from the wording of a problem.
- [ ] I can explain the difference between a value, an address, a record field, and an object method.
- [ ] I can choose file organisation and access method from batch/interactive use and the presence of a key.
- [ ] I can apply a hash function, detect a collision, and describe a retrieval route after collision resolution.
- [ ] I can decode and encode fixed-width binary floating-point values using two's complement mantissa and exponent fields.
- [ ] I can normalise positive and negative values and explain why normalisation improves precision and gives a unique form.
- [ ] I can distinguish range, precision, approximation, rounding error, underflow, and overflow.
- [ ] I can explain how this topic extends [[30 Computer Science/01 Topics/01 Information Representation/00 Overview|Information Representation]].
- [ ] I can connect user-defined types and file handling to [[30 Computer Science/01 Topics/20 Further Programming/00 Overview|Further Programming]].
- [ ] I can connect records, keys, and retrieval to [[30 Computer Science/01 Topics/08 Databases/00 Overview|Databases]].
