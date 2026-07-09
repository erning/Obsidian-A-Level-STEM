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

- Place this topic after [2 Communication](../02%20Communication/00%20Overview.md) so the network foundations are already in place.
- Draw the four TCP/IP layers and map a message's journey down the sender's stack and up the receiver's.
- Compare circuit and packet switching on delay, resource use, and robustness.

## Practice Directions

- Explain the purpose of each TCP/IP layer for a given message.
- Match a protocol (HTTP, FTP, SMTP, and so on) to its use.
- Compare circuit and packet switching for a given scenario.

## Learning Materials

- [Lecture Notes](10%20Lecture%20Notes.md)
- [中文讲义](10%20Lecture%20Notes.zh-CN.md)
- [Worked Examples](20%20Worked%20Examples.md)
- [Key Practice Problems](30%20Key%20Practice%20Problems.md)
- [Key Practice Solutions](31%20Key%20Practice%20Solutions.md)
- [Review Checklist](80%20Review%20Checklist.md)

## Connections and Extensions

- [Communication](../02%20Communication/00%20Overview.md) provides the LAN/WAN, hardware, IP addressing, DNS, and router foundations that make protocol stacks and switching meaningful here.
- [Security](../17%20Security/00%20Overview.md) builds directly on these protocol ideas: SSL/TLS uses the client-server network path to add encryption, authentication, and integrity.
- [Security, Privacy and Data Integrity](../06%20Security%2C%20Privacy%20and%20Data%20Integrity/00%20Overview.md) explains the threats and transfer-integrity checks that motivate secure communication over the networks studied here.

## Common Traps

- Listing layer names without describing what each layer does.
- Confusing the protocol name with the layer it runs on.
- Forgetting that BitTorrent is a peer-to-peer protocol.
