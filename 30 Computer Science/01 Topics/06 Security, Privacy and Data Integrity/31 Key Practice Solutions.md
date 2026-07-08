---
title: Security, Privacy and Data Integrity Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|Security, Privacy and Data Integrity]]"
status: active
tags:
  - computerscience/computer-systems
  - solutions
---

# Security, Privacy and Data Integrity Key Practice Solutions

This note gives worked solutions for [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/30 Key Practice Problems|Security, Privacy and Data Integrity Key Practice Problems]]. Each solution shows the full reasoning, including the step-by-step computations for the check digit, the parity block, and the checksum, so you can find the step where your argument diverged rather than only comparing final answers.

## A. Security and threats

### Problem 1

- **Security** is the protection of data and systems from harm, such as theft, deletion, or unauthorised access. A supporting measure is a firewall that blocks unauthorised incoming connections.
- **Privacy** is the control of who is allowed to see data. A supporting technique is access rights that restrict a file to a named group of users.
- **Data integrity** is the correctness and freedom from corruption of data, both at entry and during transfer. A supporting technique is a check digit that rejects a mistyped code.

### Problem 2

(a) **Anti-virus software.** It scans the downloaded file for known virus signatures and quarantines or removes it, provided the definitions are kept up to date.
(b) **A firewall together with strong passwords.** The firewall blocks the attacker's unauthorised incoming connections from reaching the server, and a strong password with a limit on login attempts makes guessing impractical.
(c) **User education combined with website authentication.** Users are trained not to click links or enter credentials from a suspicious email, and the genuine site is confirmed by its digital certificate over HTTPS.
(d) **Anti-spyware software (and a non-keystroke login).** Anti-spyware scans for and removes key-logging programs; an on-screen keypad or biometric login further reduces what a key-logger can capture.

### Problem 3

**Authentication** is the process of proving that a user (or system) is who they claim to be. In a school system, a teacher logging in with a username and password, or scanning a fingerprint, is authenticating. **Access rights** are the permissions granted to an already-authenticated user, defining what they may read, write, or run. In the same system, a teacher having read access to their own class's marks but not to the finance records is an example of access rights. Authentication answers "who are you?"; access rights answer "what may you do?".

### Problem 4

Both attacks send the victim to a fake website that captures credentials, but the mechanism differs. **Phishing** relies on social engineering: a fake email or text tricks the user into clicking a link to the fake site and entering their details, so the user must be fooled into acting. **Pharming** relies on tampering with name resolution: the attacker corrupts a DNS server or the hosts file so that typing the correct URL still reaches the fake site, with no misleading message required. The key difference is that phishing depends on deceiving the user, while pharming depends on redirecting the address at the network level and can catch a careful user who types the URL correctly.

### Problem 5

Encryption converts the stored data into ciphertext that cannot be read without the decryption key, so if the laptop is lost or stolen the data remains confidential. However, encryption does not by itself guarantee integrity, because it says nothing about whether the ciphertext has been altered. An attacker who modifies the encrypted file (or who captures and replays it) could change the underlying data, and encryption alone would not detect the change. Integrity on transfer is provided instead by a parity check or a checksum, and a digital signature can prove that stored data has not been altered.

### Problem 6

Two advantages of biometric authentication over a password:
1. The user does not have to remember or carry anything, and the credential cannot be forgotten or easily shared.
2. It is hard to forge, because a fingerprint (or iris or face) is physically tied to the individual, unlike a password that can be guessed or stolen.

One limitation: biometric systems require special hardware (a scanner) and software, they can be slower and more expensive to deploy than passwords, and a false rejection or false acceptance is possible. A stolen password can also be changed, but a compromised biometric cannot.

### Problem 7

Three suitable security measures:
1. **A virtual private network (VPN) or encrypted connection.** Data travelling between the home laptop and the company network is encrypted, so an interceptor on the home network cannot read it.
2. **Anti-virus and firewall software on each laptop.** They block unauthorised connections and detect malware that could steal or damage company data.
3. **Strong authentication and access rights.** Each staff member logs in with a strong, unique password (or multi-factor authentication) and is granted access only to the files they need, limiting the damage if one laptop is compromised.

## B. Privacy and integrity

### Problem 8

(a) **Integrity.** The concern is that the data remains correct and uncorrupted when it is changed, which is an integrity requirement.
(b) **Privacy.** The concern is who is allowed to view the data, restricting it to named clinicians.
(c) **Security.** The concern is protecting the records from an attacker, which is a security requirement.

### Problem 9

A range check only tests whether the value lies between two bounds, not whether it is the true value. An age of $30$ passes a range check of $0$ to $120$ even if the person is really $25$. **Double entry** would catch such an error: the value is typed twice and the two entries are compared, and a mismatch is flagged for the operator to resolve against the source.

### Problem 10

1. Validation is an automatic check that a value is reasonable and acceptable according to a rule; verification is a check that the data entered or received matches what was intended.
2. Validation is performed by the computer at input; verification on entry is performed by an operator (visual or double entry) and verification on transfer uses parity checks or checksums.

## C. Validation

### Problem 11

(a) **Length check.** (b) **Existence check.** (c) **Range check.** (d) **Presence check.** (e) **Check digit.** (f) **Limit check.**

### Problem 12

A **range check** sets both an upper and a lower bound, for example "an exam mark must be between $0$ and $100$". A **limit check** sets a single bound, for example "an order quantity must not exceed $99$ items" or "an applicant's age must be at least $18$".

### Problem 13

Multiply each digit by its weight and sum:

- $3 \times 5 = 15$
- $1 \times 4 = 4$
- $7 \times 3 = 21$
- $4 \times 2 = 8$
- $2 \times 1 = 2$

Weighted sum $= 15 + 4 + 21 + 8 + 2 = 50$.

Remainder on division by $11$: $50 \bmod 11 = 6$.

Check digit $= 11 - 6 = 5$.

Full code: $317425$.

### Problem 14

A check digit is computed from the other digits by a known rule, so a single mistyped digit almost always changes the weighted sum and therefore the remainder, producing a check digit that no longer matches and causing the code to be rejected. However, it is not a full guarantee of correctness: two digits can be transposed or several digits changed in a way that happens to preserve the remainder (depending on the weights used), and the check digit says nothing about whether the correct code for the right person or product was chosen in the first place.

## D. Verification

### Problem 15

- **Visual check.** The operator looks at the entered data on the screen (or a printout) and compares it by eye against the source document. It is quick and cheap and suits small amounts of non-critical data.
- **Double entry.** The data is typed in twice, by two operators or in two passes, and the two entries are compared; any mismatch is flagged. It is used for critical data such as bank account numbers, where the cost of a typing error is high and the extra effort is justified.

### Problem 16

Count the 1s in $11010110$. There are five 1s (an odd number), so even parity is violated and an error is detected. A single parity bit cannot locate which bit is wrong, and it cannot detect an even number of bit errors in the same byte (because the total would still be even).

### Problem 17

Check each row and column using even parity.

- Row 1 has two 1s and parity $0$: even. OK.
- Row 2 has one 1 and parity $0$: odd. **Error in Row 2.**
- Row 3 has two 1s and parity $0$: even. OK.
- Row 4 has three 1s and parity $1$: even. OK.
- Column 1 has three 1s and parity $1$: even. OK.
- Column 2 has two 1s and parity $0$: even. OK.
- Column 3 has one 1 and parity $0$: odd. **Error in Column 3.**
- Column 4 has two 1s and parity $0$: even. OK.

The failing row (Row 2) and the failing column (Column 3) intersect at the bit in **Row 2, Column 3**. The received value is $0$; its correct value should be $1$.

### Problem 18

(a) Sum $= 58 + 97 + 143 + 210 = 508$. The checksum $508$ is sent.

(b) The receiver adds the values received: $58 + 97 + 144 + 210 = 509$. This does not equal the received checksum $508$, so an error is detected.

(c) A checksum fails to detect changes that leave the total unchanged. For example, if $143$ became $142$ and $210$ became $211$, the sum would still be $508$ and the corruption would not be detected.

### Problem 19

A **parity check** adds a single bit to each byte (or block) so that the total number of 1s follows a fixed rule (even or odd); it detects that an error has occurred in a byte but cannot say which bit. A **checksum** adds together all the data values and sends the total alongside the data; the receiver recomputes the total and compares it. The shared limitation is that neither method is foolproof: an even number of bit changes can keep parity correct, and changes that cancel out can keep a checksum correct. Both detect most single errors but can miss some multiple errors.

### Problem 20

A single parity bit can only signal that an error has occurred; it cannot identify which bit is wrong, so the receiver cannot correct it and must request a retransmission. The statement is therefore not true in general for a single parity bit. A **parity block** adds a parity bit to each row and a parity byte to the columns, so that a single-bit error produces one failing row and one failing column; their intersection locates the bit, and because it is located the receiver can flip it back and correct it. Even a parity block, however, cannot guarantee correction of multiple errors in the same row or column.
