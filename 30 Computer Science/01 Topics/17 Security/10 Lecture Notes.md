---
title: Security Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/17 Security/00 Overview|Security]]"
status: active
tags:
  - computerscience/computer-systems
  - lecture-notes
---

# Security Lecture Notes

This topic extends AS section 6 (Security, Privacy and Data Integrity) into the A Level study of **cryptography**. Where AS work focused on threats and simple defences, A Level 17 explains how encryption, key pairs, secure protocols and digital certificates actually protect data in transit. The whole section is examined in Paper 3, so the emphasis is on understanding the *mechanism*, not just naming threats.

## Source Route

These notes cover the full A Level section 17, in the order that builds understanding most cleanly:

1. Encryption basics - terms, and symmetric vs asymmetric cryptography.
2. Sending a private message to an individual/organisation.
3. Sending a verified message to the public.
4. How data is encrypted and decrypted in both models, with a combined example.
5. Quantum cryptography - purpose, benefits, drawbacks.
6. SSL / TLS - purpose, client-server use, when appropriate.
7. Digital certificates - acquisition and use for digital signatures.

## 1. Encryption basics

**Plain text** is readable, unencrypted data (the original message). **Cipher text** is the scrambled output produced by an encryption algorithm. **Encryption** converts plain text to cipher text; **decryption** reverses it. The **key** is the secret value (or value pair) that controls the algorithm - without it the cipher text should be meaningless.

Two families of cryptography are examined:

| Aspect | Symmetric key cryptography | Asymmetric key cryptography |
| --- | --- | --- |
| Number of keys | One shared key | A key pair: public key + private key |
| Key relationship | Same key encrypts and decrypts | Public key encrypts; matching private key decrypts (and vice versa for signing) |
| Speed | Fast - small keys, simple maths | Slow - large keys, heavy maths |
| Key distribution | Hard - both parties must share the secret safely over a channel | Easier - public key can be published; private key never leaves the owner |
| Typical use | Bulk data encryption, file/disk encryption | Key exchange, digital signatures, small messages |
| Example algorithms | AES, DES, 3DES | RSA, ECC |

> [!note] Key distribution is the classic weakness of symmetric crypto
> If Alice and Bob must first share a secret key, how do they share it without it being intercepted? Asymmetric cryptography solves this by removing the need to share a private value.

## 2. Sending a private message to an individual / organisation

Here the goal is **secrecy**: only the intended recipient should be able to read the message. The rule is simple - **encrypt with the recipient's PUBLIC key; decrypt with the recipient's PRIVATE key**.

Worked flow (message from Aisha to Ben):

1. Aisha obtains Ben's **public key** (it can be published openly - anyone may have it).
2. Aisha encrypts her plain text with Ben's public key to produce cipher text.
3. Aisha sends the cipher text across the open network.
4. Ben receives it and decrypts it with his **private key**, which only he holds.
5. Even if an attacker intercepts the cipher text and knows Ben's public key, they cannot decrypt it - the public key does not reverse its own encryption.

> [!example] Why this works
> A public key is like an open padlock that anyone can snap shut, but only the owner has the key to open. Secrecy comes from keeping the *private* key private.

## 3. Sending a verified message to the public

Now the goal flips to **authenticity**: the public must be able to prove the message really came from the claimed sender and has not been altered. The rule is the opposite - **sign (encrypt) with the sender's PRIVATE key; verify (decrypt) with the sender's PUBLIC key**.

Worked flow (announcement from Aisha to the public):

1. Aisha encrypts her message (or more usually a hash of it) with her **private key**. This is the **digital signature**.
2. Aisha publishes the message and the signature.
3. Anyone - any member of the public - obtains Aisha's **public key** and uses it to decrypt the signature.
4. If the decrypted result matches the message (or its hash), two things are proved:
   - the sender really is Aisha (only her private key could have produced the signature);
   - the message has not been tampered with (any change would break the match).

> [!tip] The two questions keys answer
> Whenever you read a question, decide which property is being asked for:
> - **Secrecy** → encrypt with the recipient's **public** key.
> - **Authenticity** → sign with the sender's **private** key.
> Mixing these up is the single most common error in this topic.

## 4. How data is encrypted and decrypted in both models

**Symmetric model.** Alice and Bob agree on one secret key *K* in advance. Alice encrypts with *K*; Bob decrypts with the same *K*. Fast and suitable for large files, but the shared key must be delivered securely first.

**Asymmetric model.** Each party owns a key pair. As above, secrecy uses the recipient's public key and authenticity uses the sender's private key. The maths is heavy, so in practice the systems are combined.

### Combined worked example - sign then encrypt

Aisha wants to send Ben a secret contract that he can also prove came from her. She needs **both** secrecy and authenticity. The standard order is *sign then encrypt*:

1. Aisha hashes the contract to get a small digest.
2. She encrypts the digest with her **private key** → this is her **digital signature**.
3. She appends the signature to the contract.
4. She encrypts the whole package (contract + signature) with Ben's **public key** → cipher text.
5. She sends the cipher text to Ben.
6. Ben decrypts the package with his **private key** → recovers contract + signature.
7. Ben decrypts the signature with Aisha's **public key** → recovers the digest.
8. Ben hashes the contract himself; if his digest matches the recovered one, the contract is authentic and unaltered.

| Step | Key used | Achieves |
| --- | --- | --- |
| Sign | Aisha's private key | Authenticity (proof of sender, integrity) |
| Encrypt | Ben's public key | Secrecy |
| Decrypt outer | Ben's private key | Recovers the secret package |
| Verify signature | Aisha's public key | Confirms authenticity and integrity |

## 5. Quantum cryptography

**Quantum cryptography** uses principles of quantum mechanics (such as the behaviour of photons and the fact that observing a quantum system changes it) to secure communication. The examined example is **quantum key distribution (QKD)**, which safely distributes a shared symmetric key rather than encrypting the data itself.

**Purpose.** To provide a key-distribution method whose security is guaranteed by the laws of physics, not by the difficulty of a mathematical problem.

**Benefits:**

- **Secure key distribution** - eavesdropping on the quantum channel disturbs the photons, which the legitimate parties can detect.
- **Eavesdropping detection** - any interception introduces errors that show up in the transmitted bits, so the parties know the key has been compromised and discard it.
- **Future-proof against quantum computing** - not broken by Shor's algorithm the way RSA would be.

**Drawbacks:**

- **High cost** - specialised hardware (single-photon sources, detectors, fibre links) is expensive.
- **Distance limitations** - signal loss over fibre limits range without trusted repeaters; free-space versions need line of sight.
- **Immaturity** - still developing; limited real-world deployment and standards compared with RSA/AES.

> [!note] Distinction worth stating
> "Quantum cryptography" in 9618 means QKD for distributing keys. The data itself is then encrypted with a normal symmetric algorithm using that distributed key.

## 6. Secure Socket Layer (SSL) / Transport Layer Security (TLS)

**SSL** is the older protocol; **TLS** is its modern successor. The two names are often used together in the syllabus. TLS provides a **secure channel** between a client and a server by combining encryption, authentication and data integrity.

**Purpose:**

- Encrypt data in transit between client and server so it cannot be read.
- Authenticate the server (via its digital certificate) so the client knows it is talking to the genuine site.
- Detect tampering through message authentication codes.

**Use in client-server communication - the handshake (high level):**

1. Client contacts the server and lists the encryption methods it supports.
2. Server responds with its chosen methods and sends its **digital certificate** (containing its public key).
3. Client verifies the certificate (see section 7) and trusts the server's public key.
4. Both sides agree on a **session key** (the client often encrypts a random value with the server's public key and sends it; this value seeds the session key).
5. The session key is a **symmetric** key used to encrypt the rest of the exchange - symmetric because it is fast for bulk data.

So TLS uses **asymmetric** cryptography for authentication and key exchange, then switches to **symmetric** cryptography for the actual data. This is the combined pattern from section 4 in action.

**When SSL/TLS is appropriate:** any situation involving sensitive data crossing an open network - online banking, e-commerce checkout, logging into webmail, submitting personal or payment details, transferring medical records, API calls carrying credentials. The `https://` scheme and the padlock icon in a browser indicate a TLS-protected connection.

## 7. Digital certificates

A **digital certificate** is an electronic document that **binds a public key to an identity** (a person, server or organisation). It lets a stranger trust that a given public key really belongs to the claimed owner, rather than to an attacker. The system that issues and manages these certificates is called a **Public Key Infrastructure (PKI)**.

### How a digital certificate is acquired

1. The applicant (e.g. a website owner) generates a key pair: a public key and a private key.
2. The applicant sends the **public key** and proof of identity to a trusted **Certificate Authority (CA)**.
3. The CA verifies the identity (business registration, domain control, etc.).
4. The CA creates a certificate containing the applicant's identity, their public key, the validity period and the CA's own details.
5. The CA **signs the certificate with the CA's private key** and returns it to the applicant.
6. The applicant publishes the certificate; the **private key is never shared** - only they hold it.

### How a digital certificate is used to produce digital signatures

A certificate confirms ownership of a public key, which makes digital signatures meaningful:

1. The sender signs a message (or its hash) with their **private key**, producing the digital signature - exactly as in section 3.
2. The sender attaches their **digital certificate** so the recipient has the matching public key.
3. The recipient checks the certificate: it must be valid, not expired, and **signed by a trusted CA**. The recipient verifies the CA's signature using the CA's public key (which is built into browsers/operating systems).
4. Once the certificate is trusted, the recipient uses the public key inside it to verify the sender's signature on the message.

> [!important] Role of the CA
> The Certificate Authority is the trusted third party that vouches for the binding between identity and public key. Without it, an attacker could publish their own public key claiming to be someone else (a man-in-the-middle attack). The CA's own signature is what makes a certificate trustworthy.

## Worked-Thinking Routine

When you meet a section 17 question:

1. **Identify the property** - secrecy, authenticity, or both? This decides which key does what.
2. **Name the parties** clearly - sender vs recipient, public vs private, encrypt vs sign. Use the labels from the question.
3. **Pick the model** - symmetric (one shared key, fast) or asymmetric (key pair, secure distribution).
4. **Follow the key rule** - public key for secrecy on the recipient's side; private key for authenticity on the sender's side.
5. **Add a certificate if identity is in question** - verification needs a trusted CA to bind the key.
6. **State the protocol** if the question is about web traffic - TLS does the handshake, then symmetric bulk encryption.

## Common Mistakes

- **Confusing which key encrypts for secrecy.** Secrecy uses the *recipient's public* key, not the sender's.
- **Confusing which key signs for authenticity.** Signing uses the *sender's private* key, not the recipient's.
- **Saying the private key is shared.** It never is. Only the public key is published.
- **Forgetting that TLS switches to symmetric.** Asymmetric is used for setup; the bulk data uses a symmetric session key.
- **Treating a digital certificate as the signature itself.** The certificate binds a key to an identity; the signature is produced separately using the private key that matches the certified public key.
- **Mixing up quantum cryptography with quantum computing attacks.** QKD distributes keys securely; it is not the same as a quantum computer breaking RSA.
- **Writing "SSL is secure" with no detail.** State the three protections: encryption, server authentication, integrity.

## Quick Self-Check

1. State two differences between symmetric and asymmetric key cryptography.
2. Aisha wants only Ben to read her message. Whose public key does she use, and whose private key does Ben use?
3. Aisha wants everyone to prove her announcement really came from her. Which key produces the signature, and which key verifies it?
4. Why does TLS use a symmetric session key after the handshake?
5. List three benefits and two drawbacks of quantum cryptography.
6. Describe how a website obtains a digital certificate from a CA.
7. Explain the role of the CA in preventing a man-in-the-middle attack.

## Connections

- [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|Security, Privacy and Data Integrity]] - AS foundation: threats, simple defences, data integrity.
- [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/00 Overview|Communication and Internet Technologies]] - the network context where TLS and certificates actually run.

## Study Sequence

1. Read sections 1-4 and rehearse the **two key rules** until automatic.
2. Practise stating symmetric vs asymmetric differences from memory.
3. Work through the combined *sign then encrypt* flow on paper for both parties.
4. Add quantum cryptography as a focused case study on key distribution.
5. Tie TLS back to the combined model - asymmetric for handshake, symmetric for data.
6. Finish with digital certificates and the CA's role; connect to how browsers verify `https://` sites.
