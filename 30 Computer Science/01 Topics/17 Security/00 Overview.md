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

- Place this after [6 Security, Privacy and Data Integrity](../06%20Security%2C%20Privacy%20and%20Data%20Integrity/00%20Overview.md) and [14 Communication and Internet Technologies](../14%20Communication%20and%20Internet%20Technologies/00%20Overview.md).
- Separate the two questions keys answer: "Can only the recipient read it?" and "Did the stated sender write it?"
- Trace a message through encryption, transmission, and decryption for both symmetric and asymmetric cases.

## Practice Directions

- Explain how asymmetric keys send a private message and a verified message.
- Describe when SSL/TLS is appropriate.
- Explain how a digital certificate supports a digital signature.

## Learning Materials

- [Lecture Notes](10%20Lecture%20Notes.md)
- [中文讲义](10%20Lecture%20Notes.zh-CN.md)
- [Worked Examples](20%20Worked%20Examples.md)
- [Key Practice Problems](30%20Key%20Practice%20Problems.md)
- [Key Practice Solutions](31%20Key%20Practice%20Solutions.md)
- [Review Checklist](80%20Review%20Checklist.md)

## Connections and Extensions

- [Security, Privacy and Data Integrity](../06%20Security%2C%20Privacy%20and%20Data%20Integrity/00%20Overview.md) provides the threat, privacy, integrity, authentication, and encryption foundations that this topic deepens with key-based mechanisms.
- [Communication and Internet Technologies](../14%20Communication%20and%20Internet%20Technologies/00%20Overview.md) provides the protocol-stack and client-server context in which SSL/TLS, certificates, and encrypted sessions operate.
- [Ethics and Ownership](../07%20Ethics%20and%20Ownership/00%20Overview.md) connects certificates, signatures, privacy, and trust to professional responsibility when systems handle sensitive data.

## Common Traps

- Swapping the roles of the public and private key.
- Treating SSL and TLS as unrelated.
- Forgetting that a digital signature proves identity, not secrecy.
