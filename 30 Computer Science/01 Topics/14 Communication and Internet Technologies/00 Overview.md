---
title: 14 Communication and Internet Technologies
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/networks
---

# 14 Communication and Internet Technologies

## Core Idea

This A Level topic extends section 2 with the protocols that let computers talk and the switching methods that move data across networks and the internet.

## Source Alignment

- 9618 A Level section 14 Communication and internet technologies
- 14.1 Protocols
- 14.2 Circuit switching, packet switching
- Paper 3

## What to Learn

- Why a protocol is essential for communication between computers.
- Protocol implementation as a stack, with each layer owning a function.
- The TCP/IP protocol suite: Application, Transport, Internet, and Link layers; purpose and function of each.
- What happens at the Application layer when a message is sent from one host to another.
- Protocols and their purposes: HTTP, FTP, POP3, IMAP, SMTP, BitTorrent (peer-to-peer file sharing).
- Circuit switching: benefits, drawbacks, and where it applies.
- Packet switching: benefits, drawbacks, and where it applies.
- Router function in packet switching; how messages cross a network and the internet.

## How to Study

- Place this topic after [[30 Computer Science/01 Topics/02 Communication/00 Overview|2 Communication]] so the network foundations are already in place.
- Draw the four TCP/IP layers and map a message's journey down the sender's stack and up the receiver's.
- Compare circuit and packet switching on delay, resource use, and robustness.

## Practice Directions

- Explain the purpose of each TCP/IP layer for a given message.
- Match a protocol (HTTP, FTP, SMTP, and so on) to its use.
- Compare circuit and packet switching for a given scenario.

## Learning Materials

- [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/10 Lecture Notes|Lecture Notes]]
- [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/10 Lecture Notes.zh-CN|中文讲义]]
- [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/20 Worked Examples|Worked Examples]]
- [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/30 Key Practice Problems|Key Practice Problems]]
- [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/31 Key Practice Solutions|Key Practice Solutions]]
- [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/80 Review Checklist|Review Checklist]]

## Connections and Extensions

- [[30 Computer Science/01 Topics/02 Communication/00 Overview|Communication]] provides the LAN/WAN, hardware, IP addressing, DNS, and router foundations that make protocol stacks and switching meaningful here.
- [[30 Computer Science/01 Topics/17 Security/00 Overview|Security]] builds directly on these protocol ideas: SSL/TLS uses the client-server network path to add encryption, authentication, and integrity.
- [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|Security, Privacy and Data Integrity]] explains the threats and transfer-integrity checks that motivate secure communication over the networks studied here.

## Common Traps

- Listing layer names without describing what each layer does.
- Confusing the protocol name with the layer it runs on.
- Forgetting that BitTorrent is a peer-to-peer protocol.
