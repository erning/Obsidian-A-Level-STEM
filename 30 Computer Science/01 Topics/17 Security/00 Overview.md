---
title: 17 Security
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/computer-systems
---

# 17 Security

## Core Idea

This A Level topic extends section 6 with the cryptography that protects data in transit: symmetric and asymmetric encryption, SSL/TLS, quantum cryptography, and digital certificates.

## Source Alignment

- 9618 A Level section 17 Security
- 17.1 Encryption, Encryption Protocols and Digital Certificates
- Paper 3

## What to Learn

- How encryption works: public key, private key, plain text, cipher text, symmetric and asymmetric key cryptography.
- Using keys to send a private message to an individual or organisation.
- Using keys to send a verified message to the public.
- How data is encrypted and decrypted with symmetric and asymmetric cryptography.
- Quantum cryptography: purpose, benefits, and drawbacks.
- Secure Socket Layer (SSL) / Transport Layer Security (TLS): purpose, use in client-server communication, and appropriate situations.
- Digital certification: how a certificate is acquired and how it is used to produce digital signatures.

## How to Study

- Place this after [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|6 Security, Privacy and Data Integrity]] and [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/00 Overview|14 Communication and Internet Technologies]].
- Separate the two questions keys answer: "Can only the recipient read it?" and "Did the stated sender write it?"
- Trace a message through encryption, transmission, and decryption for both symmetric and asymmetric cases.

## Practice Directions

- Explain how asymmetric keys send a private message and a verified message.
- Describe when SSL/TLS is appropriate.
- Explain how a digital certificate supports a digital signature.

## Learning Materials

- [[30 Computer Science/01 Topics/17 Security/10 Lecture Notes|Lecture Notes]]
- [[30 Computer Science/01 Topics/17 Security/10 Lecture Notes.zh-CN|中文讲义]]
- [[30 Computer Science/01 Topics/17 Security/20 Worked Examples|Worked Examples]]
- [[30 Computer Science/01 Topics/17 Security/30 Key Practice Problems|Key Practice Problems]]
- [[30 Computer Science/01 Topics/17 Security/31 Key Practice Solutions|Key Practice Solutions]]
- [[30 Computer Science/01 Topics/17 Security/80 Review Checklist|Review Checklist]]

## Connections

- [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|6 Security, Privacy and Data Integrity]] is the AS foundation this topic extends.
- [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/00 Overview|14 Communication and Internet Technologies]] provides the protocols SSL/TLS runs over.

## Common Traps

- Swapping the roles of the public and private key.
- Treating SSL and TLS as unrelated.
- Forgetting that a digital signature proves identity, not secrecy.
