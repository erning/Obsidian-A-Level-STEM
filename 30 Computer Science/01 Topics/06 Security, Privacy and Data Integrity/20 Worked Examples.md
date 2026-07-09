---
title: Security, Privacy and Data Integrity Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[Security, Privacy and Data Integrity](00%20Overview.md)"
status: active
tags:
  - computerscience/computer-systems
  - worked-examples
---

# Security, Privacy and Data Integrity Worked Examples

Security, privacy, and integrity are three distinct ideas that are easy to blur. **Security** protects data and systems from harm such as theft, deletion, and unauthorised access. **Privacy** controls who is allowed to see data. **Integrity** keeps data correct and uncorrupted, both when it is typed in and when it is moved. The worked examples below show how to separate these ideas, choose a security measure for a named threat, pick a validation check for a field, and carry out the standard integrity computations: a modulus-11 check digit, an even-parity check that locates a single error, and a checksum. Cover each solution, attempt the prompt on paper, then compare.

## Source Route

- Syllabus **9618 AS Section 6 - Security, privacy and data integrity**.
- 6.1 Data security: user accounts, passwords, authentication (digital signatures, biometrics), firewall, anti-virus, anti-spyware, encryption, access rights; threats from malware (virus, spyware), hackers, phishing, and pharming.
- 6.2 Data integrity: data validation (range, format, length, presence, existence, limit, check digit); verification on entry (visual, double entry); verification on transfer (parity check on a byte and a block, checksum).
- Assessed in **Paper 1**.

The recurring skill is to name the category first (which idea, which measure, which check), then justify it against the alternatives. Definitions alone are not enough; the marks are in the justification tied to the scenario.

## Example 1: Separate security, privacy, and integrity in a scenario

**Prompt.** A school stores exam results and personal data for each pupil. State whether each concern is mainly a matter of security, privacy, or integrity, and justify in one line.
(a) A firewall and anti-virus software stop malware from deleting the results files.
(b) Only a pupil's own form tutor may open that pupil's full record; other staff see only a name list.
(c) Each candidate number is checked with a check digit so that a mistyped number is rejected.

**Solution.**
(a) **Security.** The measures protect the system and the files from harm (deletion or damage by malware).
(b) **Privacy.** The rule controls who is allowed to see the data, restricting access to a named group.
(c) **Integrity.** The check digit rejects an incorrect value and so keeps the stored data correct and uncorrupted.

**Check.** Ask what is being protected. Guarding against harm or unauthorised access is security; deciding who may view is privacy; ensuring the data is correct and unaltered is integrity.

## Example 2: Choose a security measure for a named threat

**Prompt.** For each threat, name one suitable security measure and justify it in one line.
(a) A virus hidden in an email attachment.
(b) A hacker trying to guess passwords over the internet.
(c) A phishing email that impersonates a bank.
(d) Spyware that records keystrokes.

**Solution.**
(a) **Anti-virus software.** It scans files and email for known virus signatures and quarantines or removes infected files, and it must be kept up to date so that newly known viruses are recognised.
(b) **A firewall together with strong passwords.** The firewall blocks unauthorised incoming connections from reaching the server, while strong passwords and a limit on login attempts make guessing impractical.
(c) **User education combined with website authentication.** Users are trained not to click links or enter credentials from a suspicious email, and the genuine site is confirmed by its digital certificate over HTTPS; a digital signature on email can also prove the real sender.
(d) **Anti-spyware software (and a biometric or on-screen login).** Anti-spyware scans for and removes key-logging programs, and an authentication method the spyware cannot capture, such as a fingerprint or an on-screen keypad, reduces what a key-logger can steal.

**Check.** Name the measure, then tie it to exactly what the threat does (damage, break-in, deception, surveillance).

## Example 3: Compare phishing and pharming

**Prompt.** Explain how phishing and pharming each direct a victim to a fake website, and state clearly how the two attacks differ.

**Solution.** Both end at a fake site that captures the victim's credentials, but the mechanism differs.
- **Phishing** relies on social engineering. The attacker sends an email or text that looks as if it comes from a legitimate organisation and tricks the user into clicking a link to the fake site and entering their login details. The user has to be fooled into acting.
- **Pharming** relies on tampering with name resolution. The attacker corrupts a DNS server or the hosts file on the victim's computer so that even typing the correct URL reaches the fake site. No misleading email is needed, and a careful user who types the address correctly can still be caught.

**Check.** Phishing means the user is tricked by a message; pharming means the network or DNS is tampered with so the correct address is redirected.

## Example 4: Choose a validation check for each field

**Prompt.** Name the single most appropriate validation check for each field.
(a) A date of birth that must not be left empty.
(b) An email address that must contain an `@` and a dot.
(c) A postcode that must be exactly 8 characters.
(d) A username that must already exist in the database before an order is accepted.
(e) An exam mark that must lie from $0$ to $100$.
(f) A bank card number.

**Solution.**
(a) **Presence check.** It rejects an empty field.
(b) **Format check.** It tests the value against a required pattern.
(c) **Length check.** It tests the number of characters.
(d) **Existence check.** It confirms the value is present in a reference table.
(e) **Range check.** It tests that the value lies between two bounds.
(f) **Check digit.** The final digit is computed from the others and rejects a mistyped number.

**Check.** Match the rule to the type. A range check sets both an upper and a lower bound; a limit check sets only one bound (for example, "age must be at least $18$" or "no more than $99$ items").

## Example 5: Compute a modulus-11 check digit

**Prompt.** A product code uses the five digits $1\ 8\ 6\ 4\ 7$ with the weights $5, 4, 3, 2, 1$ applied from left to right. The check digit is computed by a modulus-11 method: find the weighted sum, divide by $11$, and subtract the remainder from $11$. Calculate the check digit and state the full code.

**Solution.** Multiply each digit by its weight and sum:

- $1 \times 5 = 5$
- $8 \times 4 = 32$
- $6 \times 3 = 18$
- $4 \times 2 = 8$
- $7 \times 1 = 7$

Weighted sum $= 5 + 32 + 18 + 8 + 7 = 70$.

Remainder on division by $11$: $70 \bmod 11 = 4$.

Check digit $= 11 - 4 = 7$.

Full code: $186477$.

**Check.** Re-run the check on the full code $186477$ using the first five digits; the weighted sum of the data digits is still $70$, remainder $4$, check digit $7$, which matches the appended digit. (In schemes where the remainder is $0$ or $1$, special handling is needed because $11 - 0 = 11$ is not a single digit; some systems use an `X`, others reject that code.)

## Example 6: Even-parity check, and locating the error with a parity block

**Prompt.** A byte $11001101$ is received using even parity (the eighth bit is the parity bit). State whether an error is detected. Then, using the parity block below, locate the single bit that has been flipped, assuming even parity throughout.

```
        d1 d2 d3 d4 | parity
Row 1:   1  0  1  1 | 1
Row 2:   0  1  1  0 | 0
Row 3:   1  0  0  0 | 0
Row 4:   0  0  1  1 | 0
-------------------------------
parity:  0  0  1  0
```

**Solution.**
- Single byte: count the 1s in $11001101$. There are five 1s, an odd number, so even parity is violated and an error is detected. A single parity bit detects the error but cannot say which bit is wrong.
- Block: check each row and each column using even parity.
  - Row 1 has three 1s and parity bit $1$: total four, even. OK.
  - Row 2 has two 1s and parity bit $0$: total two, even. OK.
  - Row 3 has one 1 and parity bit $0$: total one, odd. **Error in Row 3.**
  - Row 4 has two 1s and parity bit $0$: total two, even. OK.
  - Column 1 has two 1s and parity $0$: even. OK.
  - Column 2 has one 1 and parity $0$: odd. **Error in Column 2.**
  - Column 3 has three 1s and parity $1$: even. OK.
  - Column 4 has two 1s and parity $0$: even. OK.

The failing row and failing column intersect at **Row 3, Column 2**. That bit should be $1$, not $0$, so the receiver flips it back to correct the block.

**Check.** A single parity bit only detects; a parity block (two-dimensional parity) locates a single-bit error at the intersection of the odd row and the odd column, which lets the receiver correct it. Two errors in the same row or column can still escape.

## Example 7: Compute and check a checksum

**Prompt.** Three data blocks $120$, $85$, and $233$ are transmitted, followed by a checksum equal to their sum. (a) State the checksum sent. (b) The receiver receives $120$, $86$, $233$ and checksum $438$. Determine whether an error is detected, and give one case where a checksum would fail to detect an error.

**Solution.**
(a) Sum $= 120 + 85 + 233 = 438$. The checksum $438$ is sent as a fourth value.
(b) The receiver adds the values it received: $120 + 86 + 233 = 439$. This does not equal the received checksum $438$, so an error is detected.

A checksum fails when two or more values change but their total stays the same. For example, if $85$ became $84$ and $233$ became $234$, the sum is still $438$ and the corruption would not be detected.

**Check.** A checksum detects any change that alters the total, which catches most single-value corruptions, but it is not foolproof against changes that cancel out.

## Example 8: Validation versus verification

**Prompt.** Distinguish data validation from data verification, and explain why a value can pass validation yet still be wrong.

**Solution.**
- **Validation** is an automatic check, performed by the computer at the point of input, that the value is reasonable and acceptable according to a rule (range, format, length, presence, existence, limit, or check digit). It asks: is this value sensible?
- **Verification** is a check that the data entered or received matches what was intended. It asks: is this data correct? On entry this is done by a visual check or by double entry; on transfer it is done by a parity check or a checksum.

A value can pass validation and still be wrong because validation only tests the value against a rule, not against the truth. An age of $30$ passes a range check of $0$ to $120$ even if the person is really $25$. Entry verification such as double entry (typing the value twice and comparing) catches this kind of mistake because the second entry is compared against the first and a mismatch is flagged for the operator.

**Check.** Validation = "is it acceptable?" (rule-based, automatic). Verification = "is it correct?" (comparison against the source or a duplicate). Most systems use both: validation at input, plus verification on entry and on transfer.

## Study Routine

1. Separate the three ideas first. Harm or unauthorised access is security; who may see data is privacy; correctness and freedom from corruption is integrity.
2. For threats, name the measure, then justify it against what the threat actually does.
3. For phishing versus pharming, decide whether the user is tricked by a message or whether the address itself is redirected.
4. For validation, match the rule to the type: presence, format, length, existence, range, limit, check digit.
5. For a check digit, lay out the weights, multiply, sum, take the modulus, and subtract from the modulus.
6. For parity, remember the single bit only detects; the block locates the error at the intersection of the odd row and odd column.
7. For a checksum, sum the values and compare; remember that cancelling changes can escape.
8. For validation versus verification, ask whether the test is "acceptable?" (rule) or "correct?" (comparison).
