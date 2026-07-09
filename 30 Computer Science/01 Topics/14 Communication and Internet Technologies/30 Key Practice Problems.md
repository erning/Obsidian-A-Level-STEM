---
title: Communication and Internet Technologies Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[Communication and Internet Technologies](00%20Overview.md)"
status: active
tags:
  - computerscience/networks
  - practice
---

# Communication and Internet Technologies Key Practice Problems

These problems cover the core skills of 9618 A Level Section 14. Attempt them on paper before reading [the solutions](31%20Key%20Practice%20Solutions.md). Most prompts are scenario-based, so aim to justify your answer against the alternatives rather than just naming a term. No answers are given here on purpose: the point is active recall and full written reasoning.

## A. Protocols and layers

1. Explain, in three sentences, why two computers on a network must follow a **protocol** in order to communicate, rather than simply sending bytes to each other.

2. A protocol stack is divided into **layers**. Give two distinct reasons why the functions of communication are organised into layers rather than handled by one single protocol.

3. State what is meant by each of the following statements about a layered protocol stack.
   (a) Each layer provides a service to the layer directly above it.
   (b) Each layer communicates logically with its peer layer on the other machine.
   (c) Each layer adds its own header on the sender and removes it on the receiver.

4. A student writes: "HTTP is the Application layer of TCP/IP." Explain why this statement is misleading, and reword it correctly.

## B. TCP/IP suite

5. Name the four layers of the TCP/IP protocol suite in order, from top to bottom. For each layer, state its purpose and one function it performs, and name the address or unit of data it works with.

6. For each of the four TCP/IP layers, give one concrete action that happens to a web request as it passes **down** the sender's stack.

7. Draw a diagram showing a message travelling from a sender host to a receiver host. Label the four layers on each host and state what each layer adds on the sender and reads on the receiver.

8. A browser on Host A sends an HTTP request to a web server on Host B. Describe exactly what happens at the **Application layer** of Host A, and explain why the Application layer does not concern itself with addresses or wires.

9. Distinguish between the following, naming the layer each belongs to:
   (a) a packet and a frame;
   (b) an IP address and a MAC address;
   (c) a port number and an IP address.

## C. Switching

10. A company must choose between circuit switching and packet switching for two services.
    (a) A live voice call that needs a steady, constant-rate channel for its whole duration.
    (b) Occasional bursts of web and email traffic from many staff.
    For each service, state which switching to use and justify with two reasons tied to the scenario.

11. Give two benefits and two drawbacks of **circuit switching**, and name its classic application.

12. Give two benefits and two drawbacks of **packet switching**, and explain why it is the method used by the internet.

13. Compare circuit switching and packet switching under the headings: resource use, delay, robustness, data-rate guarantee, and billing.

14. A tutor claims that "circuit switching has no delay." Explain why this claim is wrong, naming the type of delay that circuit switching does have.

## D. Routing and the internet

15. A packet arrives at a router. Describe, in order, what the router does to forward the packet, and state one thing the router does **not** know about the packet's overall journey.

16. Host A on Network 1 sends a packet to Host B on Network 2, passing through three routers. Draw the journey and describe what each router does, and what happens to the packet once it reaches Host B.

17. A link between two routers on the internet fails. Explain why later packets travelling the same source-to-destination route can still reach the destination, and why the receiver still reconstructs the complete message correctly.

18. For each task, name the most suitable protocol (HTTP, FTP, SMTP, POP3, IMAP, or BitTorrent) and state what it carries.
    (a) A browser fetches the HTML of a web page.
    (b) A user uploads a large video file to a file server.
    (c) A mail client pushes an outgoing email to its mail server.
    (d) A user reads the same mailbox from a phone and a laptop, both keeping the messages on the server.
    (e) A user downloads a film using a swarm of other users, none of whom holds the whole file.
    (f) A user downloads email to a single client so it is removed from the server.

---

After finishing, check your working against [the solutions](31%20Key%20Practice%20Solutions.md) and re-attempt any question you could not complete in full.
