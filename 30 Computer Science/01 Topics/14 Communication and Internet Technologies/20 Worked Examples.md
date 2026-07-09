---
title: Communication and Internet Technologies Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[Communication and Internet Technologies](00%20Overview.md)"
status: active
tags:
  - computerscience/networks
  - worked-examples
---

# Communication and Internet Technologies Worked Examples

These worked examples show how to reason through scenario questions on protocols, the TCP/IP four-layer suite, application protocols, circuit versus packet switching, and the router's role in moving packets across the internet. The recurring skill is naming the right layer or method first, then justifying it from the details of the scenario. Cover each solution, attempt the prompt on paper, then compare.

## Source Route

- Syllabus **9618 A Level Section 14 - Communication and Internet Technologies**.
- 14.1 Protocols: why protocols are essential; protocol stacks and layers; the **TCP/IP protocol suite** and its four layers (Application, Transport, Internet, Link); what happens at the Application layer when a message is sent host-to-host; application protocols **HTTP, FTP, POP3, IMAP, SMTP, BitTorrent**.
- 14.2 Circuit switching, packet switching: how each works, benefits, drawbacks and where applicable; the **router's function** in packet switching; how packet switching passes messages across a network including the internet.
- Assessed in **Paper 3**.

The recurring skill is method selection. For each scenario, name the layer, protocol, or switching method first, then justify it against the alternatives. Listing names alone is not enough; the marks are in the function tied to the scenario.

## Example 1: Why protocols are essential and how layers help

**Prompt.** A student says two computers could communicate by just sending bytes to each other. Explain in three sentences why a **protocol** is essential instead, and give two reasons why the work is divided into a **stack of layers**.

**Solution.** A protocol is an agreed set of rules covering message format, the order of messages, what each field means, and how errors are handled. It is essential because the sender and receiver are independent machines that share no common language unless they agree on every detail of the conversation; bytes alone carry no agreed meaning.

The work is divided into layers for two reasons. First, each layer owns one well-defined function and hides the detail below it from the layer above, so the Application layer need not know whether the link is fibre or WiFi. Second, layers can be designed and changed independently: a new physical medium only rewrites the Link layer, leaving the upper layers untouched.

**Check.** A protocol answer must mention agreement on format, order or error handling, and the independence of the two machines. A layering answer must mention either separate functions or independence/interchangeability.

## Example 2: Map the four TCP/IP layers to their jobs

**Prompt.** Name the four layers of the TCP/IP suite, and for each give its purpose and one concrete function. For each layer, name the address or unit of data it works with.

**Solution.**

| Layer | Purpose | One function | Address / unit |
| --- | --- | --- | --- |
| Application | Provides the interface and services user programs use (web, email, file transfer) | Formats application messages (e.g. an HTTP request) and encodes the data to send | Data / message |
| Transport | Provides end-to-end delivery between the two communicating programs | Breaks data into segments, assigns port numbers; TCP numbers and retransmits lost segments for reliable ordered delivery | Port number / segment |
| Internet | Moves packets across multiple networks from source host to destination host | Adds source and destination IP addresses to form a packet and routes it hop by hop | IP address / packet |
| Link | Delivers data across a single physical link to the next node | Encapsulates the packet into a frame with the hardware MAC address and signals it over the medium | MAC address / frame |

**Check.** The four layers from top to bottom are Application, Transport, Internet, Link. The address that identifies the *application* is the port number, the address that identifies the *host* is the IP address, and the address that identifies the *next device on the local link* is the MAC address. Confusing port, IP and MAC is the most common slip.

## Example 3: Trace a message down and up the stack

**Prompt.** A browser on Host A requests a web page from a server on Host B. Draw the journey of the request through the sender's TCP/IP stack and up the receiver's, labelling what each layer adds or reads.

**Solution.**

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

On Host A the message travels **down**: the Application layer forms the HTTP request, Transport adds the port number and a TCP sequence number, Internet stamps the source and destination IP addresses, and Link wraps it in a frame with the MAC address for the local link and puts it on the wire. On Host B the same message travels **up**: the Link layer reads the frame, the Internet layer checks the IP address, Transport reassembles the segments and acknowledges them, and the Application layer finally receives the original HTTP request and acts on it. Each layer on the receiver reads and removes the header its peer added on the sender, so the two Application layers behave as if they are talking directly.

**Check.** The diagram must show down on the sender, up on the receiver, and the medium in between. Each layer must be paired with what it adds (sender) or reads (receiver). Saying the data "jumps" the medium is wrong; it is encapsulated and decapsulated at every layer.

## Example 4: What happens at the Application layer

**Prompt.** A user clicks a link to fetch a web page. Describe what happens at the **Application layer** of the sender, and explain why the Application layer does not concern itself with addresses or wires.

**Solution.** At the Application layer, the browser forms an **HTTP request message**: the method (GET), the URL of the page, the headers (such as the host name), and an empty body. The Application layer encodes the data the user wants to send in the correct format for the HTTP protocol, then hands the message to the **Transport layer** below. It does not concern itself with addresses or wires because that work belongs to the lower layers: Transport handles ports and reliability, Internet handles IP addresses and routing, and Link handles the physical signalling. The Application layer trusts those lower layers to deliver what it produced, and on the receiving host the peer Application layer receives the reassembled data and acts on it.

**Check.** The Application layer answer must include "formats the message for its protocol" and "hands it to the Transport layer". Mentioning IP addresses, MAC addresses or routing here is wrong; that work belongs to the layers below.

## Example 5: Match an application protocol to its use

**Prompt.** For each task, name the most suitable protocol and state what it carries.
(a) A browser fetches the HTML of a web page.
(b) A user uploads a large video file to a file server.
(c) A mail client pushes an outgoing email to its mail server.
(d) A user reads email from the same mailbox on a phone and a laptop, both keeping the messages.
(e) A user downloads a film using a swarm of other users, none of whom holds the whole file.

**Solution.**
(a) **HTTP.** It carries web pages (HTML) and other web resources identified by URLs, with request methods such as GET and responses from the server.
(b) **FTP.** It transfers whole files between a client and a server, with directory listing and separate control and data connections.
(c) **SMTP.** It sends outgoing email by pushing messages from a client to a mail server, and between mail servers towards the destination.
(d) **IMAP.** It lets a client access and manage email stored on the server; because mail stays on the server, several clients can read the same mailbox.
(e) **BitTorrent.** It is peer-to-peer file sharing: the file is split into pieces exchanged directly between many peers, each peer both downloading and uploading, with no central server holding the whole file.

**Check.** Group the six protocols to avoid slips: HTTP and FTP move web resources and files; SMTP, POP3 and IMAP are the email trio (SMTP sends, POP3 and IMAP retrieve); BitTorrent is the lone peer-to-peer one. For (d), POP3 would be wrong because it typically downloads and removes mail from the server, so the phone and laptop could not share a single mailbox.

## Example 6: Compare circuit and packet switching for a scenario

**Prompt.** A company must choose between circuit switching and packet switching for two services: (a) a live telephone-style voice call that needs a steady constant-rate channel for its whole duration, and (b) occasional bursts of web and email traffic from many staff. For each service, state which switching to use and justify with two points.

**Solution.**
(a) Use **circuit switching** for the voice call.
1. A dedicated path is reserved for the whole call, so the **data rate is guaranteed** and the delay is low and constant, which voice needs.
2. The steady continuous stream suits a reserved channel; the alternative (packet switching) gives no rate guarantee and voice would arrive with variable delay.

(b) Use **packet switching** for the web and email traffic.
1. The links are shared by many users, so when one staff member is silent another can use the capacity; bandwidth is not wasted, unlike a circuit that sits idle when not transmitting.
2. The traffic is bursty and independent, and packet switching needs no setup time before each request; it is also robust because if one link fails, later packets re-route around it.

**Check.** Decide by what the data values. A guaranteed constant-rate stream points to circuit switching; bursty, shared, robust delivery points to packet switching. Never say circuit switching has "no delay"; it has setup delay, and the reserved path is wasted when idle.

## Example 7: Explain the router's function in packet switching

**Prompt.** A packet arrives at a router on the internet. Describe, in order, what the router does to forward it, and state what the router does **not** know about the packet's journey.

**Solution.**
1. The router reads the **destination IP address** on the arriving packet.
2. It consults its **routing table**, which records which of its links leads towards each destination network.
3. It chooses the **best next hop** for that destination and **forwards** the packet on that link. If the link is congested, it queues or drops the packet.

The router does **not** know the whole path the packet will take, and it keeps no memory of any individual conversation. It only chooses the **next hop**, so the path can adapt as links go up or down and later packets may travel via a different router.

**Check.** The three steps are: read destination IP, consult routing table, forward next hop. The common error is claiming the router knows the entire route; it decides only the next link, packet by packet.

## Example 8: Trace a packet's journey across routers

**Prompt.** Host A on Network 1 sends a packet to Host B on Network 2, several hops away across the internet. Draw the journey and describe what each router does, and what happens at Host B.

**Solution.**

```
[ Host A ]--Network 1--[ Router 1 ]----[ Router 2 ]----[ Router 3 ]--Network 2--[ Host B ]
   src IP = A                                              (each router reads dst IP = B,
   dst IP = B                                               picks next hop toward B)
```

1. Host A's Application layer creates the data; the **Internet layer** stamps it with source IP = A and destination IP = B, forming the packet, which leaves over Network 1.
2. **Router 1** reads the destination IP (B), looks it up in its routing table, and decides the best next hop is towards Router 2; it forwards the packet on that link.
3. **Router 2** does the same: reads the destination IP, consults its routing table, and forwards to Router 3.
4. **Router 3** reads the destination IP and sees the packet now belongs to Network 2, B's local network, so it delivers it onto Network 2.
5. At **Host B**, the stack passes the packet **up**: Link reads the frame, Internet checks the IP address, Transport reassembles and acknowledges, and the Application layer finally receives the original data and acts on it.

Each packet is routed **independently** by its destination IP address; if a router or link fails, later packets are re-routed via a different router, and reassembly happens at the destination.

**Check.** Every router performs the same three actions (read IP, consult table, forward next hop), and none knows the whole path. The journey must end at Host B with the packet travelling **up** the receiver's stack, not stopping at the last router.

## Study Routine

1. For a "why protocols" question, start from the independence of the two machines and the need to agree on format, order and errors.
2. For a TCP/IP layer question, name all four layers and give both purpose and function plus the address or unit for each.
3. To trace a host-to-host message, draw it going **down** the sender's stack, across the medium, and **up** the receiver's stack, naming what each layer adds or reads.
4. To match an application protocol, recall the groups: web/file (HTTP, FTP), email (SMTP sends, POP3/IMAP retrieve), peer-to-peer (BitTorrent).
5. For a switching scenario, decide whether the data values a guaranteed constant channel (circuit) or shared, robust, bursty delivery (packet), then justify from the table.
6. For a "how does a packet cross the network" question, walk one packet through each router with the three actions, and finish with reassembly at the destination host.
