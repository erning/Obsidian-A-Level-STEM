---
title: Communication and Internet Technologies Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[Communication and Internet Technologies](00%20Overview.md)"
status: active
tags:
  - computerscience/networks
  - review-checklist
---

# Communication and Internet Technologies Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can recall, trace, and explain the ideas without prompting.

## Ideas to Recall

- [ ] Define a protocol as agreed rules for message format, order, meaning, and error handling.
- [ ] Explain why communication functions are divided into a protocol stack of layers.
- [ ] Recall that each layer serves the layer above, uses the layer below, and communicates logically with its peer.
- [ ] Recall the four TCP/IP layers in order: Application, Transport, Internet, Link.
- [ ] State the purpose, function, address, and unit of data for each TCP/IP layer.
- [ ] Recall what happens at the Application layer when a host sends a message.
- [ ] Match HTTP, FTP, POP3, IMAP, SMTP, and BitTorrent to their purposes and carried data.
- [ ] Distinguish circuit switching from packet switching.
- [ ] Recall the benefits, drawbacks, billing pattern, and typical use of each switching method.
- [ ] Recall the router's three packet-switching actions: read destination IP, consult routing table, forward next hop.

## Skills to Perform

- [ ] Explain why two independent computers cannot communicate meaningfully without a protocol.
- [ ] Give two reasons layering makes protocol design easier to maintain and change.
- [ ] Map a web request down the sender's TCP/IP stack and up the receiver's stack.
- [ ] Name what each sender layer adds and what each receiver layer reads or removes.
- [ ] Distinguish a segment, packet, and frame by layer and address type.
- [ ] Distinguish port number, IP address, and MAC address by what each identifies.
- [ ] Choose HTTP, FTP, SMTP, POP3, IMAP, or BitTorrent for a scenario and justify it.
- [ ] Compare circuit switching and packet switching for a named communication need.
- [ ] Trace a packet through several routers, naming the next-hop decision at each router.
- [ ] Explain how later packets can still arrive after a router or link failure.

## Things to Trace or Explain

- [ ] Trace encapsulation down the sender's stack and decapsulation up the receiver's stack.
- [ ] Explain why HTTP is an application-layer protocol, not the Application layer itself.
- [ ] Explain why POP3 and IMAP are both email retrieval protocols but suit different client patterns.
- [ ] Explain why BitTorrent is peer-to-peer and how peers exchange file pieces.
- [ ] Trace circuit switching through setup, data transfer, and teardown.
- [ ] Trace packet switching through packet creation, independent routing, queuing, and reassembly.
- [ ] Explain why circuit switching has setup delay even though delay is predictable once connected.
- [ ] Explain why packet switching is efficient for bursty traffic but gives no guaranteed data rate.
- [ ] Connect this topic to [Communication](../02%20Communication/00%20Overview.md) by explaining how IP addressing, routers, DNS, and network hardware support protocols.
- [ ] Connect this topic to [Security](../17%20Security/00%20Overview.md) by explaining how SSL/TLS adds protection to client-server communication.

## Common Errors to Avoid

- [ ] Listing TCP/IP layer names without giving a function for each.
- [ ] Saying a protocol is the same thing as the layer it runs at.
- [ ] Confusing port numbers, IP addresses, and MAC addresses.
- [ ] Confusing frames with packets.
- [ ] Mixing up POP3 and IMAP.
- [ ] Forgetting that BitTorrent peers both upload and download.
- [ ] Saying circuit switching has no delay at all.
- [ ] Saying packet switching guarantees delivery or a fixed data rate.
- [ ] Claiming a router knows the entire route instead of choosing only the next hop.
- [ ] Forgetting that packet reassembly happens at the destination, with reliability handled by the Transport layer when needed.

## Ready to Move On When

- [ ] I can explain the need for protocols and layering without just naming the terms.
- [ ] I can describe all four TCP/IP layers using purpose, function, address, and unit of data.
- [ ] I can draw a host-to-host message moving down and up the stack.
- [ ] I can match application protocols to realistic tasks and distinguish email-send from email-retrieve protocols.
- [ ] I can compare circuit and packet switching using resource use, delay, robustness, data-rate guarantee, and billing.
- [ ] I can trace one packet through routers and explain why each router only needs a routing table for the next hop.
- [ ] I can explain how this topic extends [Communication](../02%20Communication/00%20Overview.md) from network structure into protocol behaviour.
- [ ] I can see why SSL/TLS and certificates in [Security](../17%20Security/00%20Overview.md) need the protocol-stack context from this topic.
