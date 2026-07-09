---
title: Communication and Internet Technologies Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[Communication and Internet Technologies](00%20Overview.md)"
status: active
tags:
  - computerscience/networks
  - lecture-notes
---

# Communication and Internet Technologies Lecture Notes

Computers on a network do not just send bytes and hope; they follow agreed **protocols** so that machines from different makers can understand each other, and they move that data with **switching** methods that decide how the journey from sender to receiver is organised. This A Level topic extends [AS section 2 Communication](../02%20Communication/00%20Overview.md): where the AS work covered the hardware, topologies and addressing that build a network, here we look at the rules that let hosts talk (the **TCP/IP protocol suite** and its application protocols) and at how data actually travels across the internet (circuit switching vs packet switching, and the role of the router).

## Source Route

- Syllabus **9618 A Level Section 14 - Communication and Internet Technologies**. Assessed in **Paper 3**.
- 14.1 Protocols: why protocols are essential; protocol stacks and layers; the **TCP/IP protocol suite** and its four layers (Application, Transport, Internet, Link); what happens at the Application layer when a message is sent host-to-host; application protocols **HTTP, FTP, POP3, IMAP, SMTP, BitTorrent**.
- 14.2 Circuit switching, packet switching: how each works, benefits, drawbacks and where applicable; the **router's function** in packet switching; how packet switching passes messages across a network including the internet.

## 1. Why protocols are essential; protocol stacks and layers

A **protocol** is a set of agreed rules that two computers must follow to communicate - the format of messages, the order they are sent, what each field means, and how errors are handled. Without a protocol, a sender and a receiver would have no shared language: bytes would arrive with no agreed meaning, and even the simple act of "who transmits next" would be undefined. Protocols are therefore essential precisely *because* the two ends are independent machines that must agree on every detail of the conversation.

The functions needed for communication are too many for one protocol to handle, so they are divided into a **protocol stack** of **layers**. Each layer:

- owns one well-defined **function** (for example, physical signalling, addressing, or representing the application's data);
- provides a service to the layer **directly above** it and uses the service of the layer **directly below** it;
- communicates logically with its **peer** layer on the other machine (its counterpart at the same level), even though physically the data passes down through the lower layers.

This layering lets each layer be designed and changed independently: the Application layer does not need to know whether the physical link is fibre or WiFi, because the lower layers hide that detail. When the sender's application produces a message, it is passed **down** the stack, each layer adding its own header (its control information); on the receiver the same message is passed **up** the stack, each layer reading and stripping its header, until the original data reaches the receiving application.

## 2. The TCP/IP protocol suite and its four layers

The **TCP/IP protocol suite** is the layered set of protocols that runs the internet. It has **four layers**. Each layer has a purpose (what it is for) and a function (what it actually does).

| Layer | Purpose | Function |
| --- | --- | --- |
| **Application** | Provides the interface and services the user's programs use (web, email, file transfer) | Defines application-level message formats and protocols (HTTP, FTP, SMTP, etc.); encodes the data the user wants to send; passes it to the Transport layer |
| **Transport** | Provides end-to-end delivery between the two communicating programs | Breaks data into **segments**, assigns **port numbers** to identify the application, and handles reliability: **TCP** numbers and retransmits lost segments for reliable, ordered delivery; **UDP** sends datagrams with no guarantee, for speed |
| **Internet** | Moves packets across multiple networks from source host to destination host | Adds the **IP address** (source and destination) to form a **packet**; **routes** the packet hop by hop across networks using routers; handles logical addressing independent of the physical medium |
| **Link** | Delivers data across a single physical link to the next node | Encapsulates the packet into a **frame** with the hardware **MAC address** for the local link; handles the physical signalling over copper, fibre or wireless; passes the frame to the next device on that link |

Note how the layers split the work: the Application layer knows *what* to send, Transport guarantees it arrives, Internet routes it across the world, and Link carries it across one physical hop at a time.

### A message's journey down and up the stack

For a host-to-host message (say, a browser requesting a web page), the data travels **down** the sender's four layers, across the medium, then **up** the receiver's four layers, with each layer talking to its peer:

```
   SENDER HOST                                  RECEIVER HOST
   -----------                                  --------------
                                              ^  4. Application   (browser renders page)
   1. Application   (browser forms GET)      |  3. Transport     (TCP reassembles, ACKs)
   2. Transport     (TCP adds port, seq no)  |  2. Internet      (IP strips addresses)
   3. Internet      (IP adds src/dst addr)   |  1. Link          (NIC reads frame)
   4. Link          (NIC puts it on wire)    |
        |                                     |
        +-----> physical medium / network / routers ----->+
```

Each layer on the sender adds its header; the matching layer on the receiver removes and interprets that header. The two Application layers behave as if they are talking directly to each other, even though physically the data has been encapsulated, sent over wires, routed by routers, and reassembled.

### What happens at the Application layer

When a message is sent from one host to another on the internet, the **Application layer** is where the user-visible data is created and formatted for that particular service. For example, when you request a web page the browser forms an **HTTP** request message (method, URL, headers, body); when you send email the mail client forms an **SMTP** message. The Application layer does not worry about addresses or wires - it produces the correctly formatted message for its protocol and hands it to the **Transport layer** below, trusting the lower layers to deliver it. On the receiving host, the Application layer receives the reassembled data and acts on it (a web server reads the HTTP request and returns the page).

## 3. Application-layer protocols

Each application-layer protocol serves one purpose and carries one kind of data. Learn what each does and what it carries.

| Protocol | Purpose | What it carries |
| --- | --- | --- |
| **HTTP** (HyperText Transfer Protocol) | Transfers web pages and web resources between a browser and a web server | Web pages (HTML), images, and other resources identified by URLs; request methods (GET, POST) and responses |
| **FTP** (File Transfer Protocol) | Transfers files between a client and a server, with directory listing | Whole files uploaded or downloaded; uses separate control and data connections |
| **POP3** (Post Office Protocol v3) | Retrieves email from a mailbox on a server to a single client | Downloaded email messages; typically removes them from the server after download |
| **IMAP** (Internet Message Access Protocol) | Lets a client access and manage email stored on a server | Email messages that stay on the server; supports multiple clients reading the same mailbox and folder management |
| **SMTP** (Simple Mail Transfer Protocol) | Sends email from a client to a mail server, and between mail servers | Outgoing email messages being pushed towards their destination |
| **BitTorrent** | Provides **peer-to-peer file sharing** | File data split into pieces, exchanged directly between many peers (each peer is both a downloader and an uploader); no central server holds the whole file |

A useful way to group them: **HTTP/FTP** move files and web resources; **POP3, IMAP, SMTP** are the email trio (SMTP sends, POP3 and IMAP retrieve - but IMAP keeps mail on the server); **BitTorrent** is the odd one out because it is **peer-to-peer**, with every participant both serving and downloading.

## 4. Circuit switching

In **circuit switching**, a dedicated communication **path (circuit)** is set up between sender and receiver **before** any data is sent, and that path is held open for the whole conversation. The classic example is the **traditional telephone network**: when you make a call, switches along the route reserve a continuous path end to end, and it stays reserved - even when nobody is speaking - until you hang up.

The process has three phases: **call setup** (reserve the path), **data transfer** (the path is yours exclusively), and **call teardown** (release the path so others can use it).

**Benefits**:

- Once the circuit is established, the **data rate is guaranteed** and constant.
- **Low and predictable delay** once connected, because the path is fixed and there is no per-packet routing decision.
- Simple for continuous data: well suited to a steady stream like voice.

**Drawbacks**:

- The dedicated path is **wasted when idle** - if no one talks, the reserved bandwidth sits unused.
- **Call setup takes time** before communication can start.
- **Inflexible**: if any link or switch on the path fails, the whole call drops and must be re-established.
- Does not handle bursts of data from many different sources efficiently.

**Where applicable**: traditional telephony, and any scenario needing a guaranteed constant-rate channel for the duration of a call.

## 5. Packet switching

In **packet switching**, there is **no dedicated path**. The data is broken into small **packets**, each carrying its own header with the source and destination addresses. Every packet is sent into the network and **routed independently** towards the destination - they may take different routes and arrive out of order, where they are reassembled. This is exactly how **the internet** works.

**Benefits**:

- **Efficient use of bandwidth**: many users share the same links; when one source is silent another can use the capacity, so resources are not wasted.
- **Robust**: if a link or router fails, packets can be **re-routed** along a different path - no single point of failure breaks the whole journey.
- **No setup time** before sending - packets are sent as soon as they are formed.
- Suits **bursty** data (web requests, email) where traffic comes in spikes.

**Drawbacks**:

- **Variable delay**: packets may queue at busy routers and arrive at different times.
- **No guaranteed data rate** - under heavy load, packets can be delayed or even dropped.
- **Overhead**: every packet carries a header, and reassembly and error checking add processing.
- Packets can arrive **out of order** and must be resequenced by the receiver.

**Where applicable**: the internet, and any network carrying many independent, bursty data streams from different users.

## 6. Routers in packet switching; how a message crosses a network

A **router** is the device that makes packet switching work across multiple networks. Its functions in packet switching are:

- read the **destination IP address** on each arriving packet;
- consult its **routing table**, which records which of its links leads towards each destination network;
- choose the **best next hop** for that packet and **forward** it on the appropriate link;
- drop or queue the packet if a link is congested.

Each router only decides the **next hop**, not the whole route, so the path can adapt as links go up or down.

### A packet's journey across the network

Imagine host A on Network 1 sends a packet to host B on Network 2, several hops away:

```
[ Host A ]--Network 1--[ Router 1 ]----[ Router 2 ]----[ Router 3 ]--Network 2--[ Host B ]
   src IP = A                                            (each router reads dst IP = B,
   dst IP = B                                             picks next hop toward B)
```

1. **A's Application layer** creates the data (say an HTTP request) and passes it down the stack; the **Internet layer** stamps it with source IP = A and destination IP = B, forming the packet.
2. The packet leaves A over **Network 1** and reaches **Router 1**.
3. **Router 1** reads the **destination IP address (B)**, looks it up in its **routing table**, and decides the best **next hop** is towards Router 2. It forwards the packet on that link. (Router 1 does not need to know the whole path - only the next step.)
4. The packet arrives at **Router 2**, which does the same: reads the destination IP, consults its routing table, and forwards it to Router 3.
5. **Router 3** reads the destination IP and sees the packet now belongs to **Network 2**, B's local network, so it delivers the packet onto Network 2.
6. The packet reaches **Host B**, whose stack passes it **up**: the Link layer reads the frame, the Internet layer checks the IP address, the Transport layer reassembles and acknowledges it, and the **Application layer** finally receives the original data and acts on it.

Key points: each packet is routed **independently** by its destination IP address; routers do not keep per-conversation state; if one router or link fails, later packets can be re-routed via a different router; and the destination host's stack reassembles everything at the end.

## 7. Circuit switching vs packet switching

| Aspect | Circuit switching | Packet switching |
| --- | --- | --- |
| **Resource use** | A dedicated path is reserved for the whole call; **wasted when idle** | Links shared by many users; **no idle waste**, bandwidth reused |
| **Delay** | Low and constant once connected; **setup delay** before data flows | Variable delay; packets may queue; **no setup delay** |
| **Robustness** | Fragile - if a link on the path fails, the **whole call drops** | Robust - packets **re-route** around failed links/routers |
| **Data-rate guarantee** | Guaranteed constant rate | No guarantee; rate varies with load |
| **Billing / charging** | Typically charged by **duration** of the call (time connected) | Typically charged by **volume** of data transferred (per packet/Mb) |
| **Suited data type** | Continuous, constant-rate streams (voice) | Bursty, independent data streams (web, email, files) |
| **Typical use** | Traditional telephone network | The internet |

A simple memory hook: circuit switching reserves a "private road" for your whole journey; packet switching puts each piece of your data onto a "public road network" where it is routed piece by piece to the destination.

## Worked-Thinking Routine

1. For a "why are protocols needed" question, start from the fact that two independent machines must agree on message format, order and error handling - without a protocol they share no common language.
2. For a TCP/IP layer question, name each of the four layers and give *both* its purpose and one concrete function; never list layer names alone.
3. To trace a host-to-host message, draw it going **down** the sender's stack, across the medium, and **up** the receiver's stack, naming what each layer adds.
4. To match an application protocol to its use, recall the groups: web/file (HTTP, FTP), email (SMTP sends, POP3/IMAP retrieve), and the lone peer-to-peer one (BitTorrent).
5. For a switching question, decide whether the scenario values a guaranteed constant channel (circuit) or shared, robust, bursty delivery (packet), then justify with the table.
6. For a "how does a packet cross the network" question, walk one packet through each router: read destination IP, consult routing table, forward next hop - and finish with reassembly at the destination.

## Common Mistakes

- Listing the four TCP/IP layers without saying what each does; the marks are in the function, not the name.
- Confusing a protocol with its layer - for example saying "HTTP is the Application layer" rather than "HTTP runs at the Application layer".
- Forgetting that **BitTorrent is peer-to-peer**, with every peer both uploading and downloading and no central server holding the whole file.
- Mixing up POP3 and IMAP: POP3 typically downloads and removes from the server; IMAP keeps mail on the server so several clients share a mailbox.
- Describing circuit switching as "no delay" - it has setup delay, and the reserved path is wasted when idle.
- Saying packet switching guarantees delivery: it does not. Packets can be delayed, dropped or arrive out of order; reassembly and reliability (if needed) are handled at the destination (TCP at Transport).
- Claiming routers know the entire path of a packet; each router only chooses the **next hop** from its routing table.
- Forgetting the charging difference: circuit switching is usually billed by duration, packet switching by data volume.
- Confusing "frame" (Link layer, MAC address) with "packet" (Internet layer, IP address).

## Quick Self-Check

- Explain in two sentences why computers need a protocol to communicate.
- Describe, for each of the four TCP/IP layers, its purpose and one function it performs.
- Draw a message going down the sender's stack and up the receiver's, labelling what each layer adds.
- State what happens at the Application layer when a host sends a message to another host.
- Match HTTP, FTP, POP3, IMAP, SMTP and BitTorrent to their purposes, and say what each carries.
- Explain why BitTorrent is different from the others (peer-to-peer).
- Give two benefits and two drawbacks of circuit switching, and name its classic use.
- Give two benefits and two drawbacks of packet switching, and name its classic use.
- Describe the router's function in packet switching in one sentence.
- Walk one packet from host A through two routers to host B, saying what each router does.
- Compare circuit and packet switching on resource use, delay, robustness and billing.

## Connections

- [Communication](../02%20Communication/00%20Overview.md) (AS section 2) is the foundation this topic extends: it covered the LAN/WAN hardware, topologies, IP addressing and DNS that the protocols and switching here rely on.
- [Security](../17%20Security/00%20Overview.md) builds directly on these protocols - **SSL/TLS** sits between the Application and Transport layers to add encryption and authentication, and many security threats exploit the very protocols described here.

## Study Sequence

1. Read this note top to bottom; redraw the four TCP/IP layers and the up/down stack diagram from memory.
2. Memorise the application-protocol table until each protocol's purpose and what it carries is automatic.
3. Practise tracing a host-to-host message through the stack and through routers, naming each layer's action.
4. Drill the circuit-vs-packet comparison table until you can justify a choice for any given scenario.
5. Finish against the syllabus: confirm you can "show understanding" of each point in 14.1 and 14.2 without notes.
