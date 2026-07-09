---
title: Security Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[Security](00%20Overview.md)"
status: active
tags:
  - computerscience/computer-systems
  - practice
---

# Security Key Practice Problems

These problems cover the core skills of 9618 A Level Section 17 Security: symmetric and asymmetric cryptography, the two key rules for private and verified messages, the combined sign-then-encrypt flow, quantum cryptography, SSL/TLS, and digital certificates. Attempt them on paper before reading [the solutions](31%20Key%20Practice%20Solutions.md). For every question that asks which key is used, name the key explicitly (sender or recipient, public or private) and state what it achieves. No answers are given here on purpose: the point is active recall and full written reasoning.

## A. Encryption

1. Define the terms **plain text**, **cipher text**, **encryption**, and **decryption**. In each case state the direction of the conversion and the item that controls it.

2. State three differences between symmetric and asymmetric key cryptography, under the headings: number of keys; speed; key distribution. For each difference explain briefly why it matters.

3. A company encrypts large backup files nightly using one shared key held by both the backup program and the recovery program.

   (a) Explain why symmetric key cryptography is a suitable choice for this workload.

   (b) Give one reason why asymmetric key cryptography would be less suitable for encrypting the backups themselves.

   (c) Suggest one situation in which the company might still use asymmetric cryptography alongside the symmetric one.

4. Name one example algorithm for symmetric cryptography and one for asymmetric cryptography. For each, state its typical use and why that use suits its strengths.

## B. Private and verified messages

5. Aisha wants to send Ben a confidential message that only Ben can read.

   (a) State the key Aisha uses to encrypt the message and the key Ben uses to decrypt it.

   (b) Explain why an attacker who intercepts the cipher text and already knows Ben's public key cannot read the message.

   (c) Explain why Aisha does not encrypt with her own public key.

6. Aisha wants to publish an announcement that anyone can read but that anyone can also prove really came from her and has not been altered.

   (a) State the key she uses to produce the signature and the key the public uses to verify it.

   (b) Explain what a successful verification proves, naming the two properties established.

   (c) Explain why the announcement itself does not need to be kept secret in this case.

7. Explain why the rule for sending a private message uses the **recipient's** keys, while the rule for sending a verified message uses the **sender's** keys. In your answer, link each rule to the property it provides.

8. Aisha must send Ben a secret contract that he can also prove came from her unaltered. Give the standard sign-then-encrypt flow, naming the key used at each step and stating what it achieves. Include the four steps Ben performs on receipt, in the correct order.

9. Explain why the signature is produced **before** the outer encryption in the combined flow, rather than after. State what would go wrong if the signature were applied to the cipher text instead of to the original contract.

## C. SSL/TLS and quantum

10. State the purpose of SSL/TLS, naming the three protections it provides. Distinguish between SSL and TLS.

11. Describe, at a high level, the SSL/TLS handshake between a client and a server, in the correct order. Explain why TLS switches from asymmetric cryptography to a symmetric session key for the bulk data.

12. Give two distinct situations in which SSL/TLS is appropriate. For each, state what data is at risk and what an attacker could do without TLS.

13. Describe the purpose of quantum cryptography (quantum key distribution), distinguishing between distributing the key and encrypting the data. Give two benefits and two drawbacks.

14. Explain how quantum cryptography detects eavesdropping, by referring to the behaviour of quantum systems. State what the legitimate parties do once an interception is detected.

## D. Digital certificates

15. Describe how a website owner acquires a digital certificate from a Certificate Authority (CA). Name what is sent to the CA, what the CA checks, what the CA returns, and what is never sent.

16. Explain how a digital certificate is used to produce and verify a digital signature. Include how the recipient checks that the certificate itself is trustworthy before relying on the public key inside it.

17. Explain the role of the Certificate Authority as a trusted third party. Describe how this prevents a man-in-the-middle attack in which an attacker publishes their own public key claiming to belong to someone else.

18. Distinguish between the **digital certificate** and the **digital signature**. For each, state what it is, who produces it, and what it is used for. Explain how the two work together.

---

After finishing, check your working against [the solutions](31%20Key%20Practice%20Solutions.md) and re-attempt any question you could not answer in full, naming the exact key at each step.
