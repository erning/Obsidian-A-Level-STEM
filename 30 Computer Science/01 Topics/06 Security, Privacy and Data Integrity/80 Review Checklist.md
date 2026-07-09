---
title: Security, Privacy and Data Integrity Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[Security, Privacy and Data Integrity](00%20Overview.md)"
status: active
tags:
  - computerscience/computer-systems
  - review-checklist
---

# Security, Privacy and Data Integrity Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can recall, trace, and explain the ideas without prompting.

## Ideas to Recall

- [ ] Define data security, data privacy, and data integrity as three separate properties.
- [ ] Distinguish security of a computer system from security of the data stored in or transferred by it.
- [ ] Recall the purpose of user accounts, passwords, authentication, digital signatures, biometrics, firewalls, anti-virus, anti-spyware, encryption, and access rights.
- [ ] Recall how viruses, spyware, hackers, phishing, and pharming work.
- [ ] Distinguish phishing from pharming by whether the user is tricked or the address resolution is redirected.
- [ ] Recall the seven validation methods: range, limit, length, format, presence, existence, and check digit.
- [ ] Distinguish validation from verification.
- [ ] Recall data-entry verification methods: visual check and double entry.
- [ ] Recall data-transfer verification methods: byte parity, block parity, and checksum.
- [ ] Explain what a modulus-11 check digit, parity bit, parity block, and checksum can detect.

## Skills to Perform

- [ ] Classify a scenario as mainly security, privacy, or integrity and justify the choice.
- [ ] Match a named threat to an appropriate countermeasure and explain why it works.
- [ ] Choose the best validation check for a field by identifying the error it should catch.
- [ ] Distinguish range check from limit check, and presence check from existence check.
- [ ] Compute a modulus-11 check digit by laying out weights, products, sum, remainder, and final digit.
- [ ] Use even parity to decide whether a received byte contains a detected error.
- [ ] Use a parity block to locate and correct a single flipped bit by intersecting the failing row and column.
- [ ] Compute a checksum and decide whether the receiver detects a transmission error.
- [ ] Explain why validation can accept a value that is still wrong.
- [ ] Choose between visual checking and double entry for a data-entry situation.

## Things to Trace or Explain

- [ ] Trace a threat from method of attack to the specific measure that limits its risk.
- [ ] Explain why access rights protect privacy while anti-virus software protects the system from malware.
- [ ] Trace a phishing attempt and a pharming attack to show the difference in mechanism.
- [ ] Explain why encryption protects confidentiality but does not, by itself, guarantee integrity.
- [ ] Trace a check-digit calculation from original digits to the receiver's recomputation.
- [ ] Trace a byte parity check and state why it detects but does not locate an error.
- [ ] Trace a parity block and show how one failing row and one failing column identify a bit.
- [ ] Explain a checksum failure case where two changes cancel each other out.
- [ ] Connect this topic to [Communication](../02%20Communication/00%20Overview.md) by explaining why networked systems introduce threats and transfer errors.
- [ ] Connect this topic to [Databases](../08%20Databases/00%20Overview.md) by explaining how validation, access rights, backup, and integrity appear inside a DBMS.

## Common Errors to Avoid

- [ ] Treating security, privacy, and integrity as interchangeable words.
- [ ] Answering a privacy question with a measure that only protects the system from malware.
- [ ] Confusing authentication with access rights.
- [ ] Saying phishing and pharming are the same because both end at a fake website.
- [ ] Claiming validation proves the value is correct.
- [ ] Using a range check when only one boundary is needed, or a limit check when two boundaries are needed.
- [ ] Confusing presence, existence, and format checks.
- [ ] Saying a single parity bit can correct an error.
- [ ] Forgetting that parity and checksums can miss some multiple errors.
- [ ] Treating encryption as the answer to every threat without naming what it protects.

## Ready to Move On When

- [ ] I can separate a problem into security, privacy, and integrity before choosing a measure.
- [ ] I can explain each named threat by mechanism, effect, and countermeasure.
- [ ] I can choose validation methods from the field and error type rather than from memorised wording.
- [ ] I can calculate and verify a check digit without skipping the weighted-sum step.
- [ ] I can work byte parity, block parity, and checksum examples and state what each can and cannot do.
- [ ] I can explain validation versus verification using the questions "acceptable?" and "correct?".
- [ ] I can connect network threats back to [Communication](../02%20Communication/00%20Overview.md).
- [ ] I can see how this topic prepares for cryptographic security in [Security](../17%20Security/00%20Overview.md) and database integrity in [Databases](../08%20Databases/00%20Overview.md).
