---
title: Security Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[Security](00%20Overview.md)"
status: active
tags:
  - computerscience/computer-systems
  - solutions
---

# Security Key Practice Solutions

This note gives worked solutions for [Security Key Practice Problems](30%20Key%20Practice%20Problems.md). Each solution shows the full reasoning, naming the exact key used at each step (sender or recipient, public or private) and what it achieves, so you can find where your reasoning diverged, not just compare final wording.

## A. Encryption

### Problem 1

- **Plain text** is the readable, unencrypted original message or data.
- **Cipher text** is the scrambled output produced by applying an encryption algorithm to the plain text; without the correct key it should be meaningless.
- **Encryption** is the process that converts plain text into cipher text.
- **Decryption** is the reverse process that converts cipher text back into plain text, using the correct key.

### Problem 2

| Aspect | Symmetric key cryptography | Asymmetric key cryptography |
|---|---|---|
| Number of keys | One shared key used by both parties | A key pair: a public key and a private key |
| Speed | Fast, because it uses small keys and simple mathematics | Slow, because it uses large keys and heavy mathematics |
| Key distribution | Hard; both parties must share the same secret over a safe channel before communicating | Easier; the public key can be published openly, and the private key never leaves its owner |

### Problem 3

Symmetric key cryptography is suitable because the backup files are large, and symmetric encryption is fast for bulk data thanks to its small keys and simple mathematics. Key distribution is not a problem here either, because the backup program and the recovery program are run by the same company, so the shared key can be distributed once and kept internally rather than sent across an open network.

Asymmetric key cryptography would be less suitable for the workload itself because it uses large keys and heavy mathematics, which makes it slow for encrypting large files. Its main advantage, that public keys can be published openly, is not needed when one organisation controls both ends.

### Problem 4

- **Symmetric:** AES (also DES or 3DES). Typical use: bulk data encryption such as file, disk, or backup encryption.
- **Asymmetric:** RSA (also ECC). Typical use: key exchange, digital signatures, and small messages where secure key distribution or proof of identity is needed.

## B. Private and verified messages

### Problem 5

Aisha encrypts the message with Ben's **public key**. Ben decrypts it with his **private key**, which only he holds.

An attacker who intercepts the cipher text cannot read it even though they know Ben's public key, because the public key does not reverse its own encryption. Only the matching private key can decrypt the cipher text, and that private key never leaves Ben. The public key is like an open padlock anyone can snap shut, but only the owner has the key to open.

### Problem 6

Aisha produces the signature by encrypting the message, or more usually a hash of it, with her **private key**. The public verifies it by decrypting the signature with Aisha's **public key**.

A successful verification proves two things: the sender really is Aisha, because only her private key could have produced a signature that her public key decrypts to the correct hash; and the message is unaltered, because any change to the text would change its hash and break the match. The signature proves identity and integrity; it does not provide secrecy, because the announcement itself is readable.

### Problem 7

A private message is about who can **read** it, so the recipient controls access: the sender encrypts with the recipient's public key, and only the recipient's private key can decrypt. The recipient's keys are the ones that matter.

A verified message is about who **wrote** it, so the sender must be the only party able to produce the signature: the sender signs with their private key, and anyone can check it with the sender's public key. The sender's keys are the ones that matter. Mixing these up, by using the sender's key for secrecy or the recipient's key for authenticity, is the most common error in this topic.

### Problem 8

The standard order is **sign then encrypt**, so the signature is protected by the outer encryption.

1. Aisha hashes the contract to produce a digest.
2. She encrypts the digest with her **private key**. This is her **digital signature**. It achieves authenticity and integrity.
3. She attaches the signature to the contract.
4. She encrypts the whole package (contract plus signature) with Ben's **public key**, producing cipher text. This achieves secrecy.
5. She sends the cipher text to Ben.
6. On receipt, Ben decrypts the outer package with his **private key**, recovering the contract and the signature.
7. Ben decrypts the signature with Aisha's **public key**, recovering the digest.
8. Ben hashes the contract himself. If his digest matches the recovered one, the contract is authentic and unaltered.

| Step | Key used | Achieves |
|---|---|---|
| Sign | Aisha's private key | Authenticity and integrity |
| Encrypt | Ben's public key | Secrecy |
| Decrypt outer | Ben's private key | Recovers the secret package |
| Verify signature | Aisha's public key | Confirms sender and integrity |

### Problem 9

The signature is produced before the outer encryption so that the signature is included inside the encrypted package. This means the signature itself is confidential: an eavesdropper cannot see it or strip it off, because the whole package is cipher text until Ben decrypts it with his private key. If the signature were produced after encryption, it would be applied to cipher text rather than to the contract, so verification would not prove anything about the original message content, and the signature would be visible to anyone who intercepted the transmission.

## C. SSL/TLS and quantum

### Problem 10

The purpose of SSL/TLS is to provide a secure channel between a client and a server. The three protections it provides are:

- **Encryption** of data in transit, so it cannot be read.
- **Authentication** of the server, via its digital certificate, so the client knows it is connected to the genuine site.
- **Data integrity**, through message authentication codes, so any tampering with the data in transit is detected.

### Problem 11

The handshake, at a high level:

1. The client contacts the server and lists the encryption methods it supports.
2. The server responds with its chosen methods and sends its **digital certificate**, which contains its public key.
3. The client verifies the certificate and trusts the server's public key.
4. Both sides agree on a **session key**. The client often encrypts a random value with the server's public key and sends it; this value seeds the session key.
5. The session key is a **symmetric** key used to encrypt the rest of the exchange.

TLS switches from asymmetric to symmetric cryptography because asymmetric encryption is slow for large amounts of data. Asymmetric cryptography is used only for the parts that need it, authenticating the server and securely exchanging the session key, and then a symmetric session key is used for the bulk data because symmetric encryption is fast.

### Problem 12

- **Online banking or e-commerce checkout.** Payment card numbers, account details, and personal data cross an open network. Without TLS an attacker could read the details or alter a transaction.
- **Logging into a website where a username and password are submitted.** Without TLS the credentials could be intercepted in plain text and reused by an attacker to impersonate the user.

In both cases the risk without TLS is that sensitive data is exposed or tampered with while crossing an untrusted network.

### Problem 13

The purpose of quantum cryptography, in the form of **quantum key distribution (QKD)**, is to distribute a shared secret key between two parties using the principles of quantum mechanics, so that the security of the key is guaranteed by the laws of physics rather than by the difficulty of a mathematical problem. The data itself is later encrypted with a normal symmetric algorithm using the distributed key.

Two benefits:

- **Eavesdropping detection.** Measuring a quantum system changes it, so any interception of the photons disturbs the bits and is detected by the legitimate parties.
- **Secure key distribution** and future-proofing. It removes the classic weakness of sharing a secret key over a channel, and it is not broken by a future quantum computer the way RSA would be.

Two drawbacks:

- **High cost.** It requires specialised hardware such as single-photon sources, detectors, and dedicated fibre links.
- **Distance limitations and immaturity.** Signal loss over fibre limits range without trusted repeaters, and the technology is still developing with limited real-world deployment compared with RSA and AES.

### Problem 14

Quantum cryptography detects eavesdropping because of the quantum principle that observing a system changes it. If an attacker measures the photons carrying the key bits, the measurement disturbs their quantum state, which introduces errors in the bits received by the legitimate parties. When the parties compare a sample of the bits over a conventional channel, the raised error rate reveals the interception. Once an interception is detected, the parties discard the compromised key material and start the key distribution again, so the attacker never obtains a usable key.

## D. Digital certificates

### Problem 15

1. The website owner generates a **key pair**: a public key and a private key.
2. The owner sends the **public key** and proof of identity (such as business registration or domain control) to a trusted **Certificate Authority (CA)**.
3. The CA **verifies the identity** of the applicant against the evidence supplied.
4. The CA creates a certificate containing the owner's identity, their public key, the validity period, and the CA's own details.
5. The CA **signs the certificate with the CA's private key** and returns it to the owner.
6. The owner publishes the certificate, for example by installing it on the web server.

The **private key is never sent** to the CA or to anyone else; only the owner holds it.

### Problem 16

1. The sender signs the message, or its hash, with their **private key**, producing the digital signature.
2. The sender attaches their **digital certificate**, which contains the matching public key.
3. The recipient checks the certificate: it must be valid, not expired, and **signed by a trusted CA**. The recipient verifies the CA's signature using the CA's public key, which is built into browsers and operating systems.
4. Once the certificate is trusted, the recipient uses the public key inside it to verify the sender's signature on the message.

The check on the certificate is what makes the verification meaningful: before trusting the public key, the recipient confirms that a trusted CA has vouched for the binding between that key and the claimed identity.

### Problem 17

The Certificate Authority is a **trusted third party** that vouches for the binding between an identity and a public key. Its role is to verify identity before signing a certificate, and its signature on the certificate is what makes that binding trustworthy.

This prevents a man-in-the-middle attack as follows. Without a trusted CA, an attacker could publish their own public key and claim it belongs to someone else; when a victim used that key, the attacker could decrypt or forge messages. But the attacker cannot obtain a CA-signed certificate for an identity they do not own, because the CA verifies identity first. A certificate signed by a CA the recipient already trusts therefore proves that the public key it contains genuinely belongs to the named owner, and an attacker's counterfeit key has no matching certificate and is rejected.

### Problem 18

- A **digital certificate** is an electronic document that binds a public key to an identity, and is signed by a Certificate Authority. It is used so that a stranger can trust that a given public key really belongs to the claimed owner, rather than to an attacker.
- A **digital signature** is the value produced when the owner signs a message or its hash with their private key. It is used to prove that the message came from the claimed sender and has not been altered.

The two work together: the certificate makes the public key trustworthy, and the signature, verified with that trustworthy public key, proves authenticity and integrity. The certificate is not the signature itself.
