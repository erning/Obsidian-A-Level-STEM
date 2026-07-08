---
title: Security, Privacy and Data Integrity Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|Security, Privacy and Data Integrity]]"
status: active
tags:
  - computerscience/computer-systems
  - lecture-notes
---

# Security, Privacy and Data Integrity Lecture Notes

This topic is built on three ideas that students habitually confuse. **Security** is protection from harm - keeping data and systems safe from loss, damage or unauthorised access. **Privacy** is control over *who is allowed to see* personal or confidential data. **Integrity** is the *correctness and completeness* of data - that it has not been altered, corrupted or lost. A breach of security can lead to a breach of privacy, and corrupt data has lost its integrity, but the three are not the same thing: naming them precisely is the first step to a correct exam answer, because a question that asks "how is *privacy* protected" is not answered by "install a firewall".

## Source Route

- Syllabus **9618 AS Section 6 - Security, Privacy and Data Integrity**.
- 6.1 Data Security: the security/privacy/integrity distinction; security of systems and of data; security measures (user accounts, passwords, authentication via digital signatures and biometrics, firewall, anti-virus, anti-spyware, encryption); threats from networks and the internet (malware - virus, spyware; hackers; phishing; pharming); restricting the risks; data security methods (encryption, access rights).
- 6.2 Data Integrity: validation vs verification; validation methods (range, format, length, presence, existence, limit, check digit); verification on entry (visual check, double entry) and on transfer (parity check - byte and block; checksum).
- Assessed in **Paper 1**.

## 1. Security, privacy and integrity

The syllabus asks you to explain the difference between three terms. Learn them as three separate questions.

- **Data security** - keeping data *safe* from accidental or deliberate loss, damage, theft or unauthorised access. Security is about preventing harm. A locked server room, a firewall and an encrypted hard disk are all security measures.
- **Data privacy** - keeping personal or confidential data *visible only to those authorised* to see it. Privacy is about confidentiality and the right to control one's own information. Restricting access rights so only a doctor can read a patient record is a privacy measure.
- **Data integrity** - the *correctness, completeness and currency* of data: that it is accurate, has not been corrupted in storage or transfer, and still reflects reality. Validation and verification are the tools that protect integrity.

Why precision matters: a question "Describe a measure to protect the **privacy** of patient data" wants access rights or encryption (controlling who can read it); answering "install anti-virus software" loses marks because anti-virus protects the *system* from malware, it does not control *who* may see the data. Match the measure to the concept named in the question.

The syllabus also stresses that you need **both** the security of the *data* and the security of the *computer system*. Protecting the data alone (for example, encrypting files) is not enough if the system running on it is wide open; protecting the system alone (firewall, anti-virus) is not enough if the data inside can be read by anyone. The two layers work together.

## 2. Security measures for computer systems

These measures defend the *system* - from a stand-alone PC to a whole network. Read the table as "what does each measure actually protect?"

| Measure | What it protects / how |
| --- | --- |
| **User accounts** | Each user has a named identity on the system, so access and actions can be *identified, controlled and audited*. Limits who can log in and what they can do once in. |
| **Passwords** | A secret known only to the user; the first check that the person at the keyboard really is the account owner. Strong passwords (long, mixed characters, not reused) resist guessing. |
| **Authentication techniques** | Proving a user is who they claim to be - the "who are you?" check. Goes beyond passwords. |
| **Digital signatures** | An authentication technique using public-key cryptography: a sender signs data with their private key so the receiver can verify, with the sender's public key, that the data really came from them and was not altered. Authenticates the *source*. |
| **Biometrics** | Authentication by a body characteristic (fingerprint, iris, face, voice). Hard to forge or share, but needs special hardware and raises privacy concerns about stored biological data. |
| **Firewall** | A gatekeeper between a private network and the internet (or between network zones) that inspects packets and blocks traffic that does not match its rules. Protects against *unauthorised access* from outside. |
| **Anti-virus software** | Scans files and memory, compares them against a database of known virus *signatures*, and quarantines or removes anything that matches. Must be kept up to date with new signatures. |
| **Anti-spyware** | Detects and removes *spyware* - software that secretly monitors activity and reports it back. Complements anti-virus, which targets self-replicating malware. |
| **Encryption** | Scrambles data into ciphertext that is meaningless without the decryption key. Protects data *even if* an attacker obtains it - on disk, in transit, or in a stolen laptop. |

Note that **authentication** (digital signatures, biometrics) is about *verifying identity*, which is distinct from a password (something you know): biometrics is "something you are" and a digital signature proves "the holder of this private key". These three factors - know, have, are - are the basis of *multi-factor authentication*, where combining factors is far stronger than any one alone.

## 3. Threats from networks and the internet

Connecting a computer to a network or the internet is what introduces most threats. Read the table as **threat → how it works → countermeasure**; that is how the syllabus frames the question.

| Threat | How it works | Countermeasure |
| --- | --- | --- |
| **Virus** (malware) | A malicious program that attaches itself to a host file and *self-replicates*; when the host runs, the virus runs too and spreads to other files, often damaging data or slowing the system. | Anti-virus software with updated signatures; do not run untrusted files; user access rights to limit damage. |
| **Spyware** (malware) | Malware that secretly *monitors* the user's activity (keystrokes, sites visited) and sends the information back, often for theft of passwords or personal data. | Anti-spyware; firewall to block unauthorised outbound traffic; avoid untrusted downloads. |
| **Hacker** | A person who gains *unauthorised access* to a system, exploiting weak passwords, open ports or software flaws, to steal, alter or destroy data. | Strong passwords and user accounts; firewall; keep software patched; authentication; access rights; encryption of the data so stolen data is unusable. |
| **Phishing** | Fraudulent emails or websites that *impersonate* a trusted organisation (a bank, a service) to trick the user into typing in passwords, card numbers or other credentials. | User education and suspicion; never follow links or type credentials from an email; check the real URL; anti-phishing filters. |
| **Pharming** | Malicious redirection: the user types a *correct* web address but is silently sent to a fake site, through a corrupted DNS entry or modified host file, so even a careful user is fooled. | Use trusted, secure DNS; digital certificates / HTTPS so the browser can verify the genuine site; keep the system free of malware that alters host files. |

The distinction between **phishing** and **pharming** is commonly tested: phishing tricks the *user* into visiting a fake address (the attack is in the message); pharming redirects the *request* so the correct address leads to a fake site (the attack is in the routing/DNS). A user who checks the URL carefully can defeat phishing but may still fall to pharming.

To **restrict the risks** in general: combine technical measures (firewall, anti-virus, encryption, access rights), procedural measures (strong password policy, user education, regular updates and patches, backups), and physical measures (locked rooms, secure disposal of media). Defence in depth - layering several measures - is more effective than relying on any single one.

## 4. Data security methods

The syllabus singles out two measures specifically for the security of the *data* itself (as opposed to the system around it).

**Encryption** transforms readable *plaintext* into unreadable *ciphertext* using a key. Without the correct decryption key, the ciphertext is meaningless, so encryption protects data even when an attacker gets hold of it - whether it sits on a stolen laptop or travels across the internet. The strength depends on the algorithm and key length, and on keeping the key secret.

**Access rights** (also called access permissions or privileges) control *which users may read, write, execute or delete* which files, records or fields. Access is granted per user role (a hospital clerk may *view* an appointment but not *edit* a diagnosis), so that even authenticated users can only reach the data their job requires. This is the principle of *least privilege*, and it directly protects **privacy** because it decides who can see what.

Access rights answer privacy; encryption answers confidentiality in transit and at rest. Both are needed: access rights stop an insider browsing data they should not see, while encryption protects the same data if the storage medium is stolen.

## 5. Data validation

**Data validation** is an *automatic* check, performed by the computer, that a data item is *reasonable and acceptable* before it is accepted. Validation asks "could this value be correct?" - it catches typing errors and impossible values, but it **cannot** guarantee the value is actually correct (a valid-looking but wrong postcode still passes). That gap is what *verification* fills.

The syllabus lists seven validation methods. For each, learn the kind of error it catches.

| Method | What it checks | Example field | Error it catches |
| --- | --- | --- | --- |
| **Range check** | Value lies *between two bounds* (a lower and an upper) | Exam score must be 0-100 | A score of 150 or -5 |
| **Limit check** | Value is on the correct side of a *single* boundary (an upper *or* a lower limit, not both) | A temperature must not exceed 100 °C; a salary must not exceed a cap | A temperature of 250 °C |
| **Length check** | The number of characters is acceptable (often an exact or maximum length) | Phone number must be 8 to 11 digits | A 3-digit "phone number" |
| **Format check** | The value matches a required *pattern* of character types and positions | Product code `ABC-1234` (3 letters, hyphen, 4 digits); date `DD/MM/YYYY` | `AB12-XYZ` or `31/13/2020` where the pattern itself is wrong |
| **Presence check** | The field is *not left empty* - some data has been entered | Surname on a registration form | A blank surname |
| **Existence check** | The value *already exists* in a reference file or lookup table | A customer ID must exist in the customer file | An order referring to customer ID `9999` that is not on file |
| **Check digit** | An extra digit, computed from the others, that detects transcription errors | The final digit of a barcode, ISBN or bank account number | A single mistyped digit, or an adjacent transposition |

Two pairs are often confused, so keep them apart. **Range vs limit**: a range check uses *two* boundaries (upper and lower), a limit check uses *one*. **Presence vs existence**: presence checks the field is *not empty*; existence checks the value is *already on file*. **Format vs existence**: format checks the *shape* of the value; existence checks it *exists in a table*.

### Worked check-digit calculation (modulus 11)

A **check digit** is one extra digit appended to a number and computed from the other digits, so that if any digit is mistyped the recomputed check digit will not match. Here is a modulus-11 scheme.

Rules:
1. Assign each digit a *weight* by position, counting down. For a 4-digit base code the weights are 5, 4, 3, 2.
2. Multiply each digit by its weight and sum the products.
3. Divide the sum by 11 and take the remainder.
4. Subtract the remainder from 11. That is the check digit. (If the result is 11, the check digit is 0; if it is 10, the check digit is written as X.)

Compute the check digit for the base code `3 1 2 8`:

| Digit | Weight | Product |
| --- | --- | --- |
| 3 | 5 | 15 |
| 1 | 4 | 4 |
| 2 | 3 | 6 |
| 8 | 2 | 16 |
| | **Sum** | **41** |

- $41 \div 11 = 3$ remainder $8$.
- Check digit $= 11 - 8 = 3$.
- Full code transmitted: **31283**.

**Verification at the receiver**: recompute the weighted sum of the first four digits ($41$), take $41 \bmod 11 = 8$, and $11 - 8 = 3$. The recomputed check digit equals the received check digit, so the code is accepted. If the code had been mistyped as `31293`, the recomputed check digit from `3 1 2 9` would be $3{\times}5 + 1{\times}4 + 2{\times}3 + 9{\times}2 = 43$, $43 \bmod 11 = 10$, $11 - 10 = 1 \neq 3$, and the error is detected. Note that the check digit *detects* the error; it does not correct it - the code is rejected and must be re-entered.

## 6. Data verification

**Data verification** checks that the data is *correct* - that what was entered or transferred matches the intended source. Where validation asks "is this value acceptable?", verification asks "is this data right?". The syllabus splits verification by *when* it happens: during **data entry** (a human is keying data in) and during **data transfer** (data is moving across a medium and may be corrupted).

### Verification on data entry

| Method | How it works |
| --- | --- |
| **Visual check (proof-reading)** | The person entering the data *looks* at the screen and compares it against the source document by eye, correcting any mismatch before confirming. Simple, but depends on human attention and misses errors that "look right". |
| **Double entry** | The same data is keyed in *twice*, usually by two different people. The system compares the two; if they differ, it rejects the entry and asks for it again. Catches most keying errors because two people making the identical mistake is unlikely. |

Double entry is stronger than a visual check because it does not rely on a single human's care; it is used for high-value data such as new bank account numbers or exam marks.

### Verification on data transfer

When data travels across a network or storage medium, electrical noise or interference can flip a bit. Two checks are used.

**Parity check (byte)**. Each byte is sent with one extra **parity bit** so that the total number of 1s in the byte matches an agreed parity - usually **even** parity (an even number of 1s).

*Worked example (even parity, parity bit sent as the most significant bit).*
- Data bits: `0 1 0 0 1 1 0`. Count the 1s: three (odd). For even parity the parity bit must be `1` to make the total even.
- Byte transmitted: `1 0 1 0 0 1 1 0`.
- Suppose it arrives as `1 0 1 0 0 0 1 0` (one bit has flipped). The receiver counts the 1s: three (odd), but even parity expects an even count - so an error is detected.

Two limits of a single-byte parity check must be stated: it **detects** an error but **cannot correct** it (any of the eight bits could be the wrong one), and if an *even number* of bits flip the parity is even again and the error goes undetected.

**Parity check (block)**. To get around the "cannot correct" limit, data is sent as a **block** of bytes arranged in a grid. A parity bit is added to each row (byte) *and* a parity byte (or parity bit per column) is added at the bottom. If a single bit flips, exactly one row *and* one column will show a parity error, and their intersection **locates** the faulty bit - which can then be *corrected* by flipping it back. Block parity therefore allows single-bit error *correction*; a single parity bit only allows *detection*.

**Checksum**. A summary value computed from the data and sent alongside it. The receiver recomputes the checksum from the received data and compares it with the one sent; if they differ, the data was corrupted in transit and a retransmission is requested.

*Worked example.* Three data bytes are sent as 8-bit values:

| Byte | Binary | Decimal |
| --- | --- | --- |
| 1 | `0110 0101` | 101 |
| 2 | `0011 0010` | 50 |
| 3 | `0001 1010` | 26 |

- Sum $= 101 + 50 + 26 = 177$, which is `1011 0001` in binary.
- The sender transmits the three bytes followed by the checksum byte `1011 0001`.
- The receiver adds the three received bytes. If the sum is still `1011 0001`, matching the received checksum, the data is accepted. If noise flipped a bit and the recomputed sum were, say, `1011 0000`, it would not match the received checksum, the error would be detected, and the receiver would request retransmission.

Like parity, a checksum **detects** corruption but does **not correct** it; the response to a failed checksum is to ask the sender to send the data again.

## Worked-Thinking Routine

1. For any question, first name the concept precisely: is it about **security** (harm), **privacy** (who sees) or **integrity** (correctness)? Your whole answer follows from this.
2. For a "describe a security measure" question, state the measure, what it protects, and *how* - one concrete sentence each.
3. For a threats question, structure the answer as threat → how it works → countermeasure, and use that order for each threat named.
4. For a validation question, identify the *type of error* being caught (empty, out of range, wrong shape, not on file, mistyped digit) and name the matching validation method.
5. For a check-digit question, lay out the weighted sum as a table, then remainder, then subtraction - show every step.
6. For a transfer-integrity question, decide whether it is *detection only* (parity byte, checksum) or *detection and correction* (parity block), and say so explicitly.

## Common Mistakes

- Treating security, privacy and integrity as interchangeable. They are three different properties; a measure for one is not automatically a measure for the others.
- Answering a "protect privacy" question with "install anti-virus". Anti-virus protects the system; privacy needs access rights / encryption.
- Confusing a **range check** (two bounds) with a **limit check** (one bound).
- Confusing **presence** (not empty) with **existence** (already on file), and both with **format** (correct shape).
- Claiming validation guarantees correct data. Validation only checks acceptability; a plausible wrong value still passes.
- Saying a single-byte parity check can *correct* an error. It can only detect; correction needs block parity.
- Forgetting that parity (and checksums) fail to detect an *even number* of bit errors.
- Mixing up **phishing** (the user is tricked into a wrong address) with **pharming** (the correct address is redirected).
- Listing encryption as the answer to every threat; encryption protects the *data*, it does not stop malware running or a hacker logging in.
- Writing the check digit without showing the weighted-sum table, so partial credit is lost if the final digit is wrong.

## Quick Self-Check

- In one sentence each, define data security, data privacy and data integrity.
- A hospital wants only a patient's own doctor to read their record. Which concept is this, and which measure implements it?
- Name the security measure that best protects data on a *stolen* laptop, and explain why.
- For each of virus, spyware, hacker, phishing and pharming, give one countermeasure and say why it works.
- State the difference between phishing and pharming in one sentence.
- Give a field example for each of the seven validation methods and the error each catches.
- Distinguish range check from limit check with one example each.
- Compute a modulus-11 check digit for a 4-digit code of your choice and show the full working.
- Explain why double entry is stronger than a visual check.
- Work an even-parity example showing detection of a single-bit error, and state the two limits of byte parity.
- Explain how block parity can *locate and correct* a single-bit error where byte parity cannot.
- Work a checksum example with three bytes and show what the receiver does on a mismatch.

## Connections

- [[30 Computer Science/01 Topics/17 Security/00 Overview|Security]] (A Level) extends this with encryption protocols, SSL/TLS, digital certificates and the public-key infrastructure that underpins digital signatures.
- [[30 Computer Science/01 Topics/02 Communication/00 Overview|Communication]] covers the networks and the internet whose connectivity introduces the threats described here, and whose data transfer is checked by parity and checksum.

## Study Sequence

1. Read this note top to bottom; then close it and write your own one-sentence definitions of security, privacy and integrity from memory.
2. Memorise the security-measures and threats tables until each "what it protects" and each "how it works / countermeasure" is automatic.
3. Drill the three confusable pairs: range vs limit, presence vs existence, phishing vs pharming.
4. Practise a modulus-11 check-digit calculation from a blank page until the table-and-remainder method is fluent.
5. Re-do the parity and checksum worked examples, stating aloud each time whether the method detects only, or detects and corrects.
6. Finish with the syllabus checklist: tick each "describe" and "show understanding" point against what you can now explain without notes.
