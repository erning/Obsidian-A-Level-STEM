---
title: Security Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/17 Security/00 Overview|Security]]"
status: active
tags:
  - computerscience/computer-systems
  - worked-examples
---

# Security Worked Examples

These worked examples cover the core skills of 9618 A Level Section 17 Security: choosing between symmetric and asymmetric cryptography, the two key rules for secrecy and authenticity, the combined sign-then-encrypt flow, quantum cryptography, SSL/TLS, and digital certificates. The recurring skill is naming the right key for the right job. Cover each solution, attempt the prompt on paper, then compare.

## Source Route

- Syllabus **9618 A Level Section 17 - Security**.
- 17.1 Encryption, Encryption Protocols and Digital Certificates: symmetric and asymmetric key cryptography; sending a private message; sending a verified message; encrypting and decrypting data; quantum cryptography; SSL/TLS; digital certificates and digital signatures.
- Assessed in **Paper 3**.

The recurring skill is deciding which property a question asks for - secrecy, authenticity, or both - and then naming the key that achieves it. When the key pairs are owned by Alice and Ben, secrecy uses the recipient's public key, authenticity uses the sender's private key, and a certificate from a Certificate Authority (CA) binds a public key to an identity.

## Example 1: Compare symmetric and asymmetric cryptography for a scenario

**Prompt.** A company backs up large database files each night and wants to encrypt them. Explain whether symmetric or asymmetric key cryptography is the better choice, giving two reasons.

**Solution.** **Symmetric key cryptography** is the better choice. The files are large, and symmetric encryption is fast because it uses small keys and simple mathematics, which matters when encrypting bulk data nightly. It is also straightforward here because both the encrypting program and the recovery program are run by the same company, so the shared secret key can be distributed once and kept internally; the classic problem of sharing a secret over an open network does not arise.

Asymmetric cryptography would be unsuitable for the bulk data itself: it uses large keys and heavy mathematics, which makes it slow for large files. It is better reserved for key exchange and signatures than for bulk file encryption.

**Check.** Match the tool to the need: bulk data plus a controllable key distribution points to symmetric. Asymmetric is not wrong in principle, but it is unnecessarily slow for this workload, and its main advantage (public keys published openly) is not needed inside one company.

## Example 2: Send a private message using the recipient's public key

**Prompt.** Aisha wants to send a confidential order to Ben that only Ben can read. State the rule she follows, and trace the message step by step from Aisha to Ben.

**Solution.** The rule is: **encrypt with the recipient's public key; decrypt with the recipient's private key**.

1. Aisha obtains Ben's **public key**. It can be published openly; anyone may have it.
2. Aisha encrypts her plain text order with Ben's public key, producing **cipher text**.
3. Aisha sends the cipher text across the open network.
4. Ben receives the cipher text and decrypts it with his **private key**, which only he holds.
5. Even if an attacker intercepts the cipher text and already knows Ben's public key, they cannot decrypt it. The public key does not reverse its own encryption; only the matching private key does.

**Check.** Secrecy is about who can *read* the message, so the recipient's keys are the ones that matter. The private key never leaves Ben. A useful test: ask "whoever should be unable to read it - what stops them?" Here, anyone without Ben's private key is stopped.

## Example 3: Send a verified message using the sender's private key

**Prompt.** Aisha wants to publish an announcement that anyone can read but that anyone can also prove came from her and was not altered. State the rule she follows, and trace the verification.

**Solution.** The rule is the opposite of Example 2: **sign (encrypt) with the sender's private key; verify (decrypt) with the sender's public key**.

1. Aisha encrypts her announcement, or more usually a hash of it, with her **private key**. The output is her **digital signature**.
2. Aisha publishes the announcement together with the signature.
3. Any member of the public obtains Aisha's **public key** and uses it to decrypt the signature, recovering the hash.
4. The reader hashes the announcement independently. If the two hashes match, two things are proved:
   - the sender really is Aisha, because only Aisha's private key could have produced a signature her public key decrypts to the right hash;
   - the message is unaltered, because any change to the text would change its hash and break the match.

**Check.** Authenticity is about who *wrote* the message, so the sender's keys are the ones that matter. The signature proves identity and integrity; it does not provide secrecy, because the announcement itself is published in plain text.

## Example 4: A combined sign-then-encrypt flow

**Prompt.** Aisha must send Ben a secret contract that he can also prove came from her unaltered. She needs both secrecy and authenticity. Give the standard sign-then-encrypt flow, naming the key used at each step and what it achieves.

**Solution.** The standard order is **sign then encrypt**, so the signature is itself protected by the outer encryption.

1. Aisha hashes the contract to produce a small digest.
2. She encrypts the digest with her **private key**. This is her **digital signature**. It achieves authenticity.
3. She attaches the signature to the contract.
4. She encrypts the whole package (contract plus signature) with Ben's **public key**, producing cipher text. This achieves secrecy.
5. She sends the cipher text to Ben.
6. Ben decrypts the outer package with his **private key**, recovering the contract and the signature.
7. Ben decrypts the signature with Aisha's **public key**, recovering the digest.
8. Ben hashes the contract himself. If his digest matches the recovered one, the contract is authentic and unaltered.

| Step | Key used | Achieves |
|---|---|---|
| Sign | Aisha's private key | Authenticity and integrity |
| Encrypt | Ben's public key | Secrecy |
| Decrypt outer | Ben's private key | Recovers the secret package |
| Verify signature | Aisha's public key | Confirms sender and integrity |

**Check.** Sign with the sender's private key first, then encrypt with the recipient's public key. On Ben's side the order reverses: decrypt with his private key, then verify with Aisha's public key. Reversing the order on read mirrors the order on send.

## Example 5: Quantum cryptography - benefits and drawbacks

**Prompt.** Describe the purpose of quantum cryptography, give two benefits, and give two drawbacks.

**Solution.** The **purpose** of quantum cryptography (in 9618, **quantum key distribution**, QKD) is to distribute a shared secret key between two parties using the principles of quantum mechanics, so that the security of the key is guaranteed by the laws of physics rather than by the difficulty of a mathematical problem.

Two **benefits**:

- **Eavesdropping detection.** Measuring a quantum system changes it. If an attacker intercepts the photons carrying the key bits, the disturbance introduces errors that the legitimate parties can detect, so they know the key has been compromised and discard it.
- **Secure key distribution.** It removes the classic weakness of symmetric cryptography, which is how to share a secret key safely. The legitimate parties establish a key without ever sending it in a form an interceptor could copy. It is also not broken by a future quantum computer the way RSA would be.

Two **drawbacks**:

- **High cost.** QKD needs specialised hardware such as single-photon sources, detectors, and dedicated fibre links, which are expensive compared with conventional cryptography running on standard hardware.
- **Distance limitations and immaturity.** Signal loss over fibre limits the range unless trusted repeaters are used, and free-space versions need line of sight. The technology is still developing, with limited real-world deployment and few standards compared with RSA and AES.

**Check.** State what QKD actually does: it distributes a key, it does not encrypt the data itself. The data is then encrypted with a normal symmetric algorithm using the distributed key.

## Example 6: SSL/TLS - purpose and when appropriate

**Prompt.** State the purpose of SSL/TLS, describe its use in client-server communication at a high level, and give two situations where it is appropriate.

**Solution.** **SSL** is the older protocol and **TLS** its modern successor. The two names are used together in the syllabus. The **purpose** of TLS is to provide a secure channel between a client and a server by combining encryption, server authentication, and data integrity.

Its use in client-server communication, at a high level (the handshake):

1. The client contacts the server and lists the encryption methods it supports.
2. The server responds with its chosen methods and sends its **digital certificate**, which contains its public key.
3. The client verifies the certificate and trusts the server's public key.
4. Both sides agree on a **session key**. The client often encrypts a random value with the server's public key and sends it; this value seeds the session key.
5. The session key is a **symmetric** key used to encrypt the rest of the exchange, because symmetric encryption is fast for bulk data.

So TLS uses **asymmetric** cryptography for authentication and key exchange, then switches to **symmetric** cryptography for the data.

Two situations where SSL/TLS is appropriate:

- Online banking and e-commerce checkout, where payment and personal details cross an open network and must not be read or altered.
- Logging into webmail or any website where a username and password are submitted, so that credentials are protected in transit.

The `https://` scheme and the padlock icon in a browser indicate a TLS-protected connection.

**Check.** TLS is appropriate whenever sensitive data crosses an open network. The single most common error is to say "SSL is secure" without naming the three protections - encryption, server authentication, and integrity - so always state all three.

## Example 7: Acquire a digital certificate from a CA

**Prompt.** A website owner wants a digital certificate. Describe how it is acquired from a Certificate Authority (CA), naming what is sent, what the CA checks, and what the CA returns.

**Solution.**

1. The website owner generates a **key pair**: a public key and a private key.
2. The owner sends the **public key** and proof of identity (such as business registration or domain control) to a trusted **Certificate Authority (CA)**. The **private key is never sent**; only the owner holds it.
3. The CA **verifies the identity** of the applicant, checking the evidence supplied.
4. The CA creates a certificate containing the owner's identity, their public key, the validity period, and the CA's own details.
5. The CA **signs the certificate with the CA's private key** and returns it to the owner.
6. The owner publishes the certificate, for example by installing it on the web server so browsers can retrieve it.

**Check.** The owner sends only the public key. The CA's signature on the certificate is what makes it trustworthy, because the CA is the trusted third party that vouches for the binding between identity and public key.

## Example 8: How a certificate supports a digital signature

**Prompt.** Explain the role of a digital certificate in producing and verifying a digital signature, and explain how it prevents a man-in-the-middle attack.

**Solution.** A digital certificate **binds a public key to an identity**. The signature itself is produced with the private key, but without a certificate a recipient could not be sure that a given public key really belongs to the claimed sender. The certificate is what makes the signature trustworthy.

Producing and verifying a signed message:

1. The sender signs the message (or its hash) with their **private key**, producing the digital signature.
2. The sender attaches their **digital certificate**, so the recipient has the matching public key.
3. The recipient checks the certificate: it must be valid, not expired, and **signed by a trusted CA**. The recipient verifies the CA's signature using the CA's public key, which is built into browsers and operating systems.
4. Once the certificate is trusted, the recipient uses the public key inside it to verify the sender's signature on the message.

How it prevents a man-in-the-middle attack: without a trusted CA, an attacker could publish their own public key and claim it belongs to someone else. When the victim uses the attacker's key, the attacker can read or forge messages. The CA breaks this trick because the attacker cannot obtain a CA-signed certificate for an identity they do not own; the CA verifies identity before signing. A certificate signed by a CA the recipient already trusts therefore proves that the public key it contains genuinely belongs to the named owner.

**Check.** Keep the two roles separate: the certificate binds a key to an identity and is signed by the CA; the signature on the message is produced by the owner with their private key. The recipient trusts the key because they trust the CA, then uses the key to verify the signature.

## Study Routine

1. Read the prompt and decide the property: secrecy, authenticity, or both. This single decision fixes which key does what.
2. For secrecy, encrypt with the recipient's **public** key and decrypt with the recipient's **private** key. The private key never leaves the recipient.
3. For authenticity, sign with the sender's **private** key and verify with the sender's **public** key. The signature proves identity and integrity, not secrecy.
4. For both, use **sign then encrypt**: the sender signs with their private key, then encrypts the package with the recipient's public key; the recipient reverses the order on read.
5. For TLS, state the three protections (encryption, authentication, integrity) and remember the switch from asymmetric handshake to symmetric session key.
6. For certificates, separate acquisition (CA verifies identity and signs the certificate) from use (recipient trusts the CA, then uses the certified public key to verify a signature).
