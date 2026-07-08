---
title: Security Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/17 Security/00 Overview|Security]]"
status: active
tags:
  - computerscience/computer-systems
  - review-checklist
---

# Security Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can recall, trace, and explain the key flows without prompting.

## Ideas to Recall

- [ ] Define plain text, cipher text, encryption, decryption, and key.
- [ ] Distinguish symmetric key cryptography from asymmetric key cryptography by number of keys, speed, and key distribution.
- [ ] Recall typical uses of symmetric cryptography and asymmetric cryptography.
- [ ] Recall the secrecy rule: encrypt with the recipient's public key and decrypt with the recipient's private key.
- [ ] Recall the authenticity rule: sign with the sender's private key and verify with the sender's public key.
- [ ] Explain what a digital signature proves and what it does not prove.
- [ ] Recall the sign-then-encrypt flow for a message that needs both secrecy and authenticity.
- [ ] Explain the purpose, benefits, and drawbacks of quantum key distribution.
- [ ] Recall the purpose of SSL/TLS: encryption, server authentication, and integrity for client-server communication.
- [ ] Explain what a digital certificate is and the role of a Certificate Authority.

## Skills to Perform

- [ ] Choose symmetric or asymmetric cryptography for a scenario and justify the choice.
- [ ] Trace a private asymmetric message from sender to recipient using the correct keys.
- [ ] Trace a verified public message from signature creation to public verification.
- [ ] Trace the combined sign-then-encrypt flow and reverse it correctly on receipt.
- [ ] Name the exact key used at each step: sender or recipient, public or private.
- [ ] Explain why TLS uses asymmetric cryptography during setup and a symmetric session key for bulk data.
- [ ] Describe the SSL/TLS handshake at a high level and name where the certificate appears.
- [ ] Describe how a website owner obtains a digital certificate from a CA.
- [ ] Verify a digital signature by first checking the certificate and then using the certified public key.
- [ ] Distinguish a digital certificate from a digital signature.

## Things to Trace or Explain

- [ ] Explain why symmetric key distribution is difficult over an open channel.
- [ ] Explain why a public key can be published while a private key must never be shared.
- [ ] Trace why using Ben's public key gives secrecy for Ben but not proof that Aisha wrote the message.
- [ ] Trace why using Aisha's private key gives authenticity but not secrecy.
- [ ] Explain why the combined flow signs the original message before the package is encrypted.
- [ ] Trace quantum key distribution as key sharing, not direct data encryption.
- [ ] Explain how observing quantum states reveals eavesdropping and why the key is discarded.
- [ ] Trace a CA certificate from applicant public key, identity check, CA signature, and publication.
- [ ] Explain how a CA prevents an attacker from substituting their own public key.
- [ ] Connect this topic to [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/00 Overview|Communication and Internet Technologies]] by explaining where SSL/TLS sits in client-server communication.

## Common Errors to Avoid

- [ ] Encrypting for secrecy with the sender's public key instead of the recipient's public key.
- [ ] Signing for authenticity with the recipient's private key instead of the sender's private key.
- [ ] Saying a private key is sent, published, or shared.
- [ ] Treating a public key as if it can decrypt the cipher text it created for secrecy.
- [ ] Saying a digital signature makes a message secret.
- [ ] Treating a digital certificate as the digital signature itself.
- [ ] Forgetting that TLS switches to a symmetric session key for the data.
- [ ] Saying SSL and TLS are unrelated rather than older and newer versions of the same secure-channel idea.
- [ ] Describing quantum cryptography as direct encryption of all data rather than secure key distribution.
- [ ] Trusting a public key without explaining the certificate and CA check.

## Ready to Move On When

- [ ] I can choose the correct cryptographic model from the goal: secrecy, authenticity, or bulk encryption.
- [ ] I can write the two key rules from memory and apply them with named people in a scenario.
- [ ] I can trace sign then encrypt and the reverse receive flow without swapping key owners.
- [ ] I can explain why TLS combines asymmetric setup with symmetric session encryption.
- [ ] I can describe certificate acquisition and verification, including the CA's private-key signature and trusted public key.
- [ ] I can distinguish certificate, public key, private key, and digital signature in one coherent explanation.
- [ ] I can explain how this topic extends [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|Security, Privacy and Data Integrity]] from general protection into cryptographic mechanisms.
- [ ] I can connect TLS and certificates back to the protocol context in [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/00 Overview|Communication and Internet Technologies]].
