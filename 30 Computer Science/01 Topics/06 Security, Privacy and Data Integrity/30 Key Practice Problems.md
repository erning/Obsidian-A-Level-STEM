---
title: Security, Privacy and Data Integrity Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|Security, Privacy and Data Integrity]]"
status: active
tags:
  - computerscience/computer-systems
  - practice
---

# Security, Privacy and Data Integrity Key Practice Problems

These problems cover the core skills of 9618 AS Section 6. Attempt them on paper before reading [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/31 Key Practice Solutions|the solutions]]. Most prompts are scenario-based, so aim to justify your answer against the alternatives rather than just naming a term. No answers are given here on purpose: the point is active recall and full written reasoning.

## A. Security and threats

1. Define each of security, privacy, and data integrity in one sentence, and give one measure or technique that supports each.

2. For each threat, name one suitable security measure and justify your choice in one line.
   (a) A virus contained in a file downloaded from the internet.
   (b) A hacker attempting to guess a user's password over the internet.
   (c) A phishing email that impersonates an online shop.
   (d) Spyware that records a user's keystrokes.

3. Distinguish **authentication** from **access rights**, and give one example of each in a school information system.

4. Explain how phishing and pharming each cause a victim to visit a fake website, and state the key difference between the two attacks.

5. Explain how encryption protects the confidentiality of data stored on a laptop, and explain why encryption alone does not guarantee the integrity of that data.

6. Give two advantages of biometric authentication (such as a fingerprint) over a password, and one practical limitation of biometrics.

7. A company permits staff to work from home using personal laptops that connect to the company network. Suggest three distinct security measures that reduce the risk of data being lost or stolen, and justify each briefly.

## B. Privacy and integrity

8. A hospital stores electronic patient records. For each concern, state whether it is mainly a matter of security, privacy, or integrity, and justify in one line.
   (a) Records must not be corrupted when the database is updated.
   (b) Only the patient's own doctor and nurse may view a record.
   (c) Records must not be copied by an attacker breaking into the server.

9. Explain why a value can pass a range check and still be incorrect, and name one verification method that would catch such an error at the point of entry.

10. State two differences between data validation and data verification.

## C. Validation

11. Name the single most appropriate validation check for each field.
    (a) A mobile phone number that must be exactly 11 digits.
    (b) A customer number that must already exist in the customer table.
    (c) A percentage score that must be between $0$ and $100$.
    (d) A surname field that must not be left empty.
    (e) A membership number whose final digit is computed from the others.
    (f) An order quantity that must not exceed $99$ items.

12. Distinguish a **range check** from a **limit check**, and give one example of each.

13. A product code uses the five digits $3\ 1\ 7\ 4\ 2$ with the weights $5, 4, 3, 2, 1$ applied from left to right. The check digit is found by a modulus-11 method: compute the weighted sum, divide by $11$, and subtract the remainder from $11$. Calculate the check digit and state the full code.

14. Explain why a check digit reliably detects a single mistyped digit, but is not a guarantee that the whole code has been entered correctly.

## D. Verification

15. State two methods of data verification on entry, and explain a situation where each is appropriate.

16. A byte $11010110$ is received using even parity, where the eighth bit is the parity bit. State whether an error is detected and explain why. State one thing that this single parity bit cannot do.

17. A 4-row data block is transmitted using even parity, with a parity bit for each row and a parity byte for the columns. The received block is shown below; exactly one data bit has been flipped.

```
        d1 d2 d3 d4 | parity
Row 1:   1  1  0  0 | 0
Row 2:   0  0  0  1 | 0
Row 3:   1  0  1  0 | 0
Row 4:   1  1  0  1 | 1
-------------------------------
parity:  1  0  0  0
```

    Locate the bit that is in error (give the row and column), state what its correct value should be, and explain how you used the row and column parities.

18. Four data values $58$, $97$, $143$, and $210$ are transmitted, followed by a checksum equal to their sum.
    (a) Calculate the checksum that is sent.
    (b) The receiver receives $58$, $97$, $144$, $210$ and checksum $508$. Determine whether an error is detected, and show your working.
    (c) Give one example of a change that a checksum would fail to detect.

19. Distinguish a **parity check** from a **checksum** as methods of verifying data during transfer, and state one limitation that they share.

20. A student writes: "Verification on transfer always corrects the error." Explain why this statement is not true in general for a single parity bit, and state what extra information a parity block provides compared with a single parity bit.

---

After finishing, check your working against [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/31 Key Practice Solutions|the solutions]] and re-attempt any question you could not complete in full.
