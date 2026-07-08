---
title: Communication and Internet Technologies Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/14 Communication and Internet Technologies/00 Overview|Communication and Internet Technologies]]"
status: active
tags:
  - computerscience/networks
  - solutions
---

# Communication and Internet Technologies Key Practice Solutions

This note gives worked solutions for [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/30 Key Practice Problems|Communication and Internet Technologies Key Practice Problems]]. Each solution shows the full reasoning so you can find the step where your argument diverged, not just compare final answers.

## A. Protocols and layers

### Problem 1

Two computers must follow a protocol because a protocol is an agreed set of rules covering message format, the order messages are sent, what each field means, and how errors are handled. The sender and receiver are independent machines that share no common language unless they agree on every detail of the conversation, so bytes sent without an agreed meaning could not be interpreted by the receiver. A protocol gives them that shared language, so each side knows when to transmit, what to expect, and how to detect and recover from errors.

### Problem 2

Two reasons the functions of communication are organised into layers:

1. Each layer owns one well-defined function and hides the detail of the layer below it from the layer above, so the Application layer need not know whether the physical link is fibre or WiFi. This separation keeps each layer simple.
2. Layers can be designed and changed independently: a new physical medium only rewrites the Link layer, leaving the upper layers untouched, and a new application protocol can be added without changing the lower layers at all.

### Problem 3

(a) Each layer provides a service to the layer directly above it and uses the service of the layer directly below it, so the work is divided into a chain of dependences rather than one monolithic block.
(b) Each layer behaves as if it communicates directly with its peer layer on the other machine (its counterpart at the same level), even though physically the data passes down through the lower layers and across the medium.
(c) On the sender, each layer adds its own header (control information) as the message passes down; on the receiver, the matching layer reads and removes that header as the message passes up, so the original data reaches the receiving application unchanged.

### Problem 4

The statement is misleading because it confuses a **protocol** with the **layer** it runs at. HTTP is a protocol that *operates at* the Application layer; it is not the layer itself. The Application layer is the whole TCP/IP layer that hosts many application protocols (HTTP, FTP, SMTP, and others), of which HTTP is just one. A correct wording is: "HTTP is an application-layer protocol that runs at the Application layer of the TCP/IP suite."

## B. TCP/IP suite

### Problem 5

| Layer | Purpose | One function | Address / unit |
| --- | --- | --- | --- |
| Application | Provides the interface and services user programs use (web, email, file transfer) | Formats application messages (e.g. an HTTP request) and encodes the data to send | Data / message |
| Transport | Provides end-to-end delivery between the two communicating programs | Breaks data into segments, assigns port numbers; TCP numbers and retransmits lost segments | Port number / segment |
| Internet | Moves packets across multiple networks from source host to destination host | Adds source and destination IP addresses to form a packet and routes it hop by hop | IP address / packet |
| Link | Delivers data across a single physical link to the next node | Encapsulates the packet into a frame with the hardware MAC address and signals it over the medium | MAC address / frame |

The four layers, from top to bottom, are Application, Transport, Internet, Link.

### Problem 6

Actions on the web request as it passes down the sender's stack:

- **Application layer:** the browser forms the HTTP request message (method GET, URL, headers, body).
- **Transport layer:** TCP breaks the data into segments and adds the port number (and a sequence number).
- **Internet layer:** IP adds the source and destination IP addresses to form the packet.
- **Link layer:** the NIC encapsulates the packet into a frame with the MAC address for the local link and signals it onto the medium.

### Problem 7

```
   SENDER HOST A                                  RECEIVER HOST B
   ------------                                   ---------------
                                              ^  4. Application   (web server reads HTTP GET,
   1. Application   (browser forms GET)        |                      returns page)
   2. Transport     (TCP adds port, seq no)    |  3. Transport     (TCP reassembles, sends ACK)
   3. Internet      (IP adds src/dst address)  |  2. Internet      (IP checks dst address)
   4. Link          (NIC frames it, MAC)       |  1. Link          (NIC reads frame)
        |                                          |
        +------> physical medium / routers ------>+
```

On the sender, the Application layer forms the GET request, Transport adds the port and sequence number, Internet stamps the source and destination IP addresses, and Link wraps it in a frame with the MAC address and puts it on the wire. On the receiver, Link reads the frame, Internet checks the IP address, Transport reassembles and acknowledges, and the Application layer finally receives the HTTP request and acts on it. Each layer on the receiver reads and removes the header its peer added on the sender.

### Problem 8

At the Application layer of Host A, the browser forms an HTTP request message: the method (GET), the URL of the page, the headers (such as the host name), and an empty body. It encodes the data the user wants to send in the correct format for the HTTP protocol, then hands the message to the Transport layer below. The Application layer does not concern itself with addresses or wires because that work belongs to the lower layers: Transport handles ports and reliability, Internet handles IP addresses and routing, and Link handles the physical signalling. The Application layer trusts those lower layers to deliver what it produced, and on Host B the peer Application layer receives the reassembled data and acts on it.

### Problem 9

(a) A **packet** is the unit of data at the Internet layer, carrying the source and destination IP addresses; a **frame** is the unit of data at the Link layer, carrying the hardware MAC address for a single physical link. The Link layer encapsulates an Internet-layer packet into a frame.
(b) An **IP address** identifies a host on the internet (logical address, used by the Internet layer for routing); a **MAC address** identifies a specific network interface on a local link (hardware address, used by the Link layer for the next physical hop).
(c) A **port number** identifies the application or service on a host (used by the Transport layer); an **IP address** identifies the host itself (used by the Internet layer). Together they identify a specific conversation on a specific host.

## C. Switching

### Problem 10

(a) Use **circuit switching** for the voice call.
1. A dedicated path is reserved for the whole call, so the data rate is guaranteed and the delay is low and constant, which a steady voice stream requires.
2. The continuous, constant-rate stream suits a reserved channel; packet switching would give no rate guarantee and the voice would arrive with variable delay.

(b) Use **packet switching** for the web and email traffic.
1. The links are shared by many users, so when one staff member is silent another can use the capacity; bandwidth is not wasted, unlike a circuit that sits idle when not transmitting.
2. The traffic is bursty and independent, and packet switching needs no setup time before each request; it is also robust because if one link fails, later packets re-route around it.

### Problem 11

Two benefits of circuit switching:

1. Once the circuit is established, the data rate is guaranteed and constant, and the delay is low and predictable because the path is fixed.
2. It is simple and well suited to a continuous stream such as voice, since there is no per-packet routing decision during the call.

Two drawbacks:

1. The dedicated path is wasted when idle: if no one is transmitting, the reserved bandwidth sits unused.
2. It is inflexible and has setup delay: if any link or switch on the path fails, the whole call drops and must be re-established.

Classic application: the traditional telephone network.

### Problem 12

Two benefits of packet switching:

1. Efficient use of bandwidth, because many users share the same links and when one source is silent another can use the capacity.
2. Robustness: if a link or router fails, packets can be re-routed along a different path, and there is no setup time before sending.

Two drawbacks:

1. Variable delay: packets may queue at busy routers and arrive at different times, with no guaranteed data rate.
2. Overhead and disorder: every packet carries a header, and packets may arrive out of order and must be resequenced at the destination.

Packet switching is the method used by the internet because internet traffic is bursty and comes from many independent users who must share the links efficiently, and because its ability to re-route around failures makes a large, geographically spread network reliable.

### Problem 13

| Aspect | Circuit switching | Packet switching |
| --- | --- | --- |
| Resource use | Dedicated path reserved for the whole call; wasted when idle | Links shared by many users; no idle waste, bandwidth reused |
| Delay | Low and constant once connected; setup delay before data flows | Variable delay; packets may queue; no setup delay |
| Robustness | Fragile: if a link on the path fails, the whole call drops | Robust: packets re-route around failed links or routers |
| Data-rate guarantee | Guaranteed constant rate | No guarantee; rate varies with load |
| Billing | Typically charged by the duration of the call | Typically charged by the volume of data transferred |

### Problem 14

The claim is wrong because circuit switching has **setup delay** before any data can flow: the path must be reserved end to end (call setup) before the conversation begins, and that reservation takes time. What circuit switching avoids is *variable, per-packet* delay during the call, since the path is fixed. So the accurate statement is that circuit switching has low and constant delay *once connected*, but it does have setup delay before the connection is usable, and the reserved path is wasted whenever the channel is idle.

## D. Routing and the internet

### Problem 15

The router performs three actions in order:

1. It reads the **destination IP address** on the arriving packet.
2. It consults its **routing table**, which records which of its links leads towards each destination network.
3. It chooses the **best next hop** for that destination and **forwards** the packet on that link. If the link is congested, it queues or drops the packet.

The router does **not** know the whole path the packet will take, and it keeps no memory of any individual conversation. It only chooses the next hop, so the path can adapt as links go up or down and later packets of the same message may travel via a different router.

### Problem 16

```
[ Host A ]--Network 1--[ Router 1 ]----[ Router 2 ]----[ Router 3 ]--Network 2--[ Host B ]
   src IP = A                                              (each router reads dst IP = B,
   dst IP = B                                               picks next hop toward B)
```

1. Host A's Application layer creates the data; the Internet layer stamps it with source IP = A and destination IP = B, forming the packet, which leaves over Network 1.
2. **Router 1** reads the destination IP (B), looks it up in its routing table, and decides the best next hop is towards Router 2; it forwards the packet on that link.
3. **Router 2** does the same: reads the destination IP, consults its routing table, and forwards to Router 3.
4. **Router 3** reads the destination IP and sees the packet now belongs to Network 2, B's local network, so it delivers it onto Network 2.
5. At **Host B**, the stack passes the packet up: Link reads the frame, Internet checks the IP address, Transport reassembles and acknowledges, and the Application layer finally receives the original data and acts on it.

Each router only chooses the next hop; none knows the whole path, and reassembly happens at the destination host.

### Problem 17

Because packet switching routes each packet independently by its destination IP address, the failure of one link or router does not break the journey. Later packets are forwarded by routers whose routing tables have been updated to avoid the failed link; they take an alternative next hop towards the same destination, so the packets still arrive. The receiver reconstructs the complete message correctly because the Transport layer on Host B reassembles the segments in order using their sequence numbers and requests retransmission (under TCP) of any packet that was lost, so the original message is rebuilt at the destination regardless of the route each packet took.

### Problem 18

(a) **HTTP.** It carries web pages (HTML) and other web resources identified by URLs, with request methods such as GET and responses from the server.
(b) **FTP.** It transfers whole files between a client and a server, with directory listing and separate control and data connections.
(c) **SMTP.** It sends outgoing email by pushing messages from a client to a mail server, and between mail servers towards the destination.
(d) **IMAP.** It lets a client access and manage email stored on the server; because mail stays on the server, several clients (phone and laptop) can read the same mailbox.
(e) **BitTorrent.** It is peer-to-peer file sharing: the file is split into pieces exchanged directly between many peers, each peer both downloading and uploading, with no central server holding the whole file.
(f) **POP3.** It retrieves email from a mailbox on a server to a single client and typically removes the messages from the server after download.
