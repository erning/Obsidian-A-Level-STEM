---
title: Communication Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[Communication](00%20Overview.md)"
status: active
tags:
  - computerscience/networks
  - practice
---

# Communication Key Practice Problems

Work through these without looking at the solutions. Most prompts are scenario-based, so aim to justify your answer against the alternatives rather than just naming a term.

## A. Networks and models

1. A garage has three PCs and wants to share a single printer and a few spreadsheets, with no budget for a dedicated machine. State and justify whether a client-server or a peer-to-peer network is more suitable.

2. A college plans to store student records centrally, control staff access by username, and run a nightly backup. Justify whether client-server or peer-to-peer is the better model.

3. A call centre wants cheap terminals that are easy to maintain and patch centrally, with all processing kept on a powerful central server. State whether thin-client or thick-client is more appropriate and give one drawback of that choice.

4. Contrast a LAN and a WAN under the headings ownership, typical speed and error rate.

5. A design studio needs each workstation to run heavy rendering software locally and to keep working when the network is slow. State whether thin-client or thick-client is more appropriate and explain why.

## B. Topologies and hardware

6. A hospital's patient-monitoring system must keep running even if a single cable fails. Name the topology that best meets this requirement and explain how it tolerates a link failure.

7. A temporary two-day exam hall with eight desks needs the cheapest possible cabled network that is quick to install. Suggest a topology and give one reason it is unsuitable for permanent use.

8. Compare a switch and a router in one sentence each, and state which device is used to connect a home LAN to the internet.

9. Name the LAN hardware needed so that a laptop can join a WiFi network and reach a cabled file server, listing each device's role.

10. For a bus, a star and a mesh topology, describe how a packet travels from host A to host B.

## C. The internet and addressing

11. Explain why IPv6 was introduced, and state the size of the IPv4 and IPv6 address spaces as powers of two.

12. Correct the statement "the World Wide Web is the same as the internet" and give one service that runs on the internet but is not part of the WWW.

13. A home router is given the address `203.0.113.7` by its ISP, which changes whenever it reconnects. The laptop behind it has `192.168.1.20`. Classify each address on the public/private axis and on the static/dynamic axis, and explain how the laptop reaches the internet despite having a private address.

14. Distinguish a public IP address from a private IP address, and explain why a private address cannot be routed directly on the internet.

15. A small company wants its public web server always to be reachable at the same address, while office laptops should get whatever address is free when they join. State, with reasons, whether each should be static or dynamic.

## D. DNS and bit streaming

16. List, in order, the stages of a DNS lookup from the moment a user types a URL into a browser to the moment the browser obtains the IP address.

17. A user types `https://www.example.org/news`. Identify the scheme, the host and the path, and explain why a DNS lookup is needed before the request can be sent.

18. Distinguish real-time (live) streaming from on-demand streaming, and state which one is more affected by a connection that is slightly slower than the media bit rate.

19. A film streamed on demand has a bit rate of 5 Mbit/s but the viewer's broadband can only sustain 3 Mbit/s smoothly. Explain what the streaming player must do to keep playing.

20. A live video call suffers stuttering. Explain, in terms of bit rate and broadband speed, why real-time streaming cannot simply "buffer ahead" the way on-demand streaming does.
