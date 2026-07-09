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

- [Lecture Notes](10%20Lecture%20Notes.md)
- [中文讲义](10%20Lecture%20Notes.zh-CN.md)
- [Worked Examples](20%20Worked%20Examples.md)
- [Key Practice Problems](30%20Key%20Practice%20Problems.md)
- [Key Practice Solutions](31%20Key%20Practice%20Solutions.md)
- [Review Checklist](80%20Review%20Checklist.md)

## Connections and Extensions

- [Communication](../02%20Communication/00%20Overview.md) supplies the network and internet setting where malware, hackers, phishing, pharming, parity checks, and checksums become necessary.
- [Security](../17%20Security/00%20Overview.md) extends these foundations into key-based encryption, SSL/TLS, digital certificates, and trusted public keys.
- [Databases](../08%20Databases/00%20Overview.md) reuses validation, verification, access rights, backup, and data-integrity ideas inside a DBMS.
- [Ethics and Ownership](../07%20Ethics%20and%20Ownership/00%20Overview.md) connects the privacy and access-control ideas here to professional responsibility when handling other people's data.

## Common Traps

- Treating validation and verification as the same thing.
- Choosing a range check where a format check is needed.
- Forgetting that a parity check detects but cannot correct an error.
