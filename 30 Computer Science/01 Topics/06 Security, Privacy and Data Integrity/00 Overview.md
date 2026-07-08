---
title: 06 Security, Privacy and Data Integrity
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/computer-systems
---

# 06 Security, Privacy and Data Integrity

## Core Idea

Security protects data and systems from harm; privacy protects who can see data; integrity protects data from corruption. This topic covers the threats, the defences, and the checks that keep data correct.

## Source Alignment

- 9618 AS section 6 Security, privacy and data integrity
- 6.1 Data Security
- 6.2 Data Integrity
- Paper 1

## What to Learn

- The difference between security, privacy, and integrity.
- Security measures: user accounts, passwords, authentication (digital signatures, biometrics), firewall, anti-virus, anti-spyware, encryption, access rights.
- Network and internet threats: malware (virus, spyware), hackers, phishing, pharming.
- Methods to restrict the risks posed by threats.
- Data validation: range check, format check, length check, presence check, existence check, limit check, check digit.
- Data verification on entry: visual check, double entry.
- Data verification on transfer: parity check (byte and block), checksum.

## How to Study

- Separate the three ideas (security, privacy, integrity) before learning any list of measures.
- Match each validation type to the kind of error it catches.
- Distinguish validation (is the value acceptable?) from verification (is the data correct?).

## Practice Directions

- Choose a security measure for a given threat.
- Select appropriate validation methods for a set of fields.
- Explain how a parity check or checksum detects an error during transfer.

## Learning Materials

- [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/10 Lecture Notes|Lecture Notes]]
- [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/10 Lecture Notes.zh-CN|中文讲义]]
- [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/20 Worked Examples|Worked Examples]]
- [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/30 Key Practice Problems|Key Practice Problems]]
- [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/31 Key Practice Solutions|Key Practice Solutions]]
- [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/80 Review Checklist|Review Checklist]]

## Connections and Extensions

- [[30 Computer Science/01 Topics/02 Communication/00 Overview|Communication]] supplies the network and internet setting where malware, hackers, phishing, pharming, parity checks, and checksums become necessary.
- [[30 Computer Science/01 Topics/17 Security/00 Overview|Security]] extends these foundations into key-based encryption, SSL/TLS, digital certificates, and trusted public keys.
- [[30 Computer Science/01 Topics/08 Databases/00 Overview|Databases]] reuses validation, verification, access rights, backup, and data-integrity ideas inside a DBMS.
- [[30 Computer Science/01 Topics/07 Ethics and Ownership/00 Overview|Ethics and Ownership]] connects the privacy and access-control ideas here to professional responsibility when handling other people's data.

## Common Traps

- Treating validation and verification as the same thing.
- Choosing a range check where a format check is needed.
- Forgetting that a parity check detects but cannot correct an error.
