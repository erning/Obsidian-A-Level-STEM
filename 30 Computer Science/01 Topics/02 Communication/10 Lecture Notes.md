---
title: Communication Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/02 Communication/00 Overview|Communication]]"
status: active
tags:
  - computerscience/networks
  - lecture-notes
---

# Communication Lecture Notes

A single computer can compute, but a networked computer can share, request and collaborate. This topic is about layered connectivity: how machines are physically wired or wireless-linked into local networks, how those networks are organised by topology and ownership model, and how the resulting collection of networks becomes the global internet that carries services such as the World Wide Web. Read it as three layers stacked on top of each other - the physical medium and hardware at the bottom, the local-area organisation in the middle, and the internet-wide addressing and naming scheme at the top - and you will keep the detail in the right order.

## Source Route

- Syllabus **9618 AS Section 2 - Communication**.
- 2.1 Networks including the internet (networking benefits, LAN/WAN, client-server vs peer-to-peer, thin vs thick client, topologies, cloud computing, media, LAN hardware, router, Ethernet/CSMA/CD, bit streaming, internet vs WWW, internet hardware, IP addressing, URL/DNS).
- Assessed in **Paper 1**.

## 1. Why network: LAN and WAN

A **network** is two or more computers connected so they can exchange data. Connecting devices brings the classic benefits of networking: **resource sharing** (one printer or file store serves many users), **communication** (email, messaging, VoIP), **centralised management and backup** of data, **shared internet access** through a single gateway, and **scalability** as new machines simply join the existing network.

Networks are first classified by geographic spread.

- A **LAN (local area network)** covers a small geographic area such as a single building, school or office. It is typically **owned and maintained by the organisation** that uses it, uses relatively **high data rates** and has **low error rates**, because the short distances allow good-quality cabling and switches. No external telecommunications line is usually needed.
- A **WAN (wide area network)** spans a **large geographic area** - cities, countries or continents - and links LANs and individual computers across those distances. WANs almost always **use third-party telecommunications links** (telephone lines, leased lines, fibre backbones, satellite, cellular), tend to have **lower data rates and higher error rates** than LANs, and the connecting hardware is owned by service providers rather than the end user. The internet is the best-known WAN.

| Aspect | LAN | WAN |
| --- | --- | --- |
| Geographic span | One building / site | Cities to global |
| Ownership | Usually the organisation | Third-party telecoms provider |
| Typical speed | High | Lower |
| Error rate | Low | Higher |
| Connecting media | Copper / fibre / WiFi internally | PSTN, leased lines, satellite, cellular |

## 2. Network models and client types

### Client-server vs peer-to-peer

In the **client-server model**, one or more dedicated **servers** provide services (file storage, printing, email, web hosting, authentication), and the remaining machines act as **clients** that request those services. Roles are fixed: the server is the authority, the client is the consumer.

- *Benefits*: centralised resources, data and backups; strong security and user accounts controlled in one place; good performance because powerful servers do the heavy work; easy to scale by upgrading the server.
- *Drawbacks*: requires specialist IT staff; the server is a **single point of failure** and can be expensive to buy and maintain; if the server is down, nobody can work.

In the **peer-to-peer (P2P) model** every computer has **equal status**: each node can act as both client and server, sharing its own files, printer or processing power directly with the others. There is no central authority.

- *Benefits*: cheap and simple to set up; no dedicated server or specialist staff; robust, because losing one peer does not bring down the whole network; easy to add peers.
- *Drawbacks*: weak security because there is no central control; backups must be done on each machine; performance falls as more peers are added; harder to locate files and manage users.

**Justify the model for the situation**: a bank or school that needs centralised, secure, well-managed data chooses client-server; a home network or a small team sharing a few files, or a file-sharing community that must survive peers leaving, chooses peer-to-peer.

### Thin-client vs thick-client

These describe how much processing each client does.

- A **thin-client** relies heavily on a **powerful central server**; the client machine is lightweight (little storage, modest CPU) and mainly handles input and display. All processing and data live on the server.
- A **thick-client** does most of the **processing locally** on its own CPU and storage, contacting the server only for data it cannot provide itself.

Thin-clients suit situations where central control, easy maintenance and cheap terminals matter (call centres, school labs, secure environments); thick-clients suit users who need local power and offline work (developers, designers, gaming). Thin-client reduces each machine's cost and management effort but depends on a fast, reliable network and a strong server; thick-client is more expensive per seat and harder to patch but works well even when the network is slow.

## 3. Topologies: bus, star, mesh, hybrid

A **network topology** is the physical or logical arrangement of the nodes and the links between them. Topology decides cost, performance and what happens when a component fails.

| Topology | Cost / wiring | Performance | Fault tolerance |
| --- | --- | --- | --- |
| **Bus** | Lowest; one backbone cable | Degrades as more nodes share the bus; collisions common | Poor; a backbone break or terminator fault takes down the whole network |
| **Star** | Moderate; one cable per node to a central device | Good; central switch isolates traffic; few collisions | Good for nodes (one dead cable affects one machine); central device is a single point of failure |
| **Mesh** | Highest; many point-to-point links | Excellent; multiple paths, no single bottleneck, easy to add nodes | Very high; traffic routes around failed links |
| **Hybrid** | Varies; combines two or more of the above | Tunable to each region's needs | Inherits the strengths and weaknesses of the parts it combines |

### How packets move in each

- **Bus**: all nodes tap into a single backbone cable. A packet from host A is broadcast onto the bus; every node sees it but only the host whose address matches keeps it. A terminator at each end absorbs the signal so it does not reflect. If two hosts transmit at once, a **collision** occurs.
- **Star**: every node has its own cable to a central switch. A packet from A goes to the switch, which forwards it only to the destination port. A cable fault on one link affects just that node.
- **Mesh**: each node has point-to-point links to several others. A packet can take many routes from source to destination, so if one link fails the packet is **re-routed** along another path. This redundancy is the mesh's key strength but it requires the most cabling.
- **Hybrid**: for example, several star networks joined by a bus or mesh backbone. Packets travel within a star via its central switch and cross between stars over the backbone.

**Justify the topology**: a cheap, small temporary lab may accept a bus; a typical office LAN uses a star because it balances cost and resilience; a hospital or military network that must stay up chooses a mesh; a large organisation with mixed needs uses a hybrid.

## 4. Cloud computing

**Cloud computing** means using computing resources - storage, processing, applications - that are hosted on remote servers and delivered over the internet, rather than running locally. The provider owns and maintains the hardware; the user pays for what they use.

- **Public cloud**: services and infrastructure are owned by a third-party provider (such as AWS, Azure) and shared over the internet between many customers. Cheap, no hardware to buy, scales instantly, but data leaves your premises and you depend on the provider and on internet quality.
- **Private cloud**: infrastructure is dedicated to a single organisation, hosted internally or by a provider but not shared. More secure and controllable, suits sensitive data, but costs more and needs in-house expertise.

**Benefits**: lower up-front cost (no capital hardware purchase), pay-as-you-go, easy scaling, access from anywhere, provider handles maintenance, security patches and backups. **Drawbacks**: needs a reliable internet connection; data is stored off-site raising privacy and security concerns; you depend on the provider; ongoing subscription cost can accumulate; possible vendor lock-in.

## 5. Transmission media and LAN hardware

### Wired vs wireless

**Wired networks** use physical cables. They give high speed, reliability and security (the signal is hard to intercept) and are not disrupted by weather or interference, but installation is costly, devices cannot move, and cabling is impractical over rough terrain or between buildings.

**Wireless networks** use electromagnetic waves through the air. They let devices be **portable** and are cheap to deploy without cabling, but signals suffer interference, attenuation and security risks (anyone in range can listen), and speeds are generally lower and more variable than wired links.

### Media characteristics

| Medium | How it carries data | Strengths | Weaknesses |
| --- | --- | --- | --- |
| **Copper cable** (twisted pair, coaxial) | Electrical signals | Cheap, widely supported, easy to install | Susceptible to electrical interference and eavesdropping; signal attenuates over distance |
| **Fibre-optic cable** | Pulses of light along glass | Very high bandwidth, immune to electromagnetic interference, hard to tap, long distances | Expensive; fragile; needs specialist installation and equipment |
| **Radio waves / WiFi** | Radio through air | Portable, no cabling, easy to add devices | Limited range, subject to interference and security risk, lower speed than wired |
| **Microwaves** | High-frequency radio, line of sight | High capacity over long distances (towers) | Needs line of sight; affected by weather and obstacles |
| **Satellites** | Microwave link to an orbiting satellite | Covers very wide areas including remote/ocean regions; useful for TV, GPS, communication | Expensive; noticeable signal delay (latency), especially geostationary; signal can degrade in bad weather |

### LAN hardware

| Device | Role in a LAN |
| --- | --- |
| **Switch** | Connects nodes; reads each frame's destination MAC address and forwards it **only** to the correct port, reducing collisions |
| **Server** | A powerful computer providing shared services (files, printing, authentication, email) to clients |
| **NIC** (Network Interface Card) | Connects a device to a wired network; handles the physical signalling and gives the device a MAC address |
| **WNIC** (Wireless NIC) | The wireless equivalent; connects a device to a WiFi network |
| **WAP** (Wireless Access Point) | A wireless base station that lets WiFi devices join the wired LAN; bridges wireless and wired segments |
| **Cables** | The physical medium (copper or fibre) linking devices |
| **Bridge** | Connects two similar network segments and filters traffic by MAC address so each segment only carries its own frames |
| **Repeater** | Cleans and regenerates a weakened signal so it can travel further without corruption |

### The router

A **router** operates at the network layer and connects **separate networks** together (for example, a home LAN to the internet). Its roles are to read the **IP address** on each packet, consult its **routing table**, and choose the **best path** to forward the packet towards its destination network. On a home network the router also typically acts as the gateway to the ISP, performs **network address translation** between private and public IP addresses, and may include a built-in switch and WAP. Because it routes by IP address and links whole networks, a router is more powerful than a switch, which works only inside one LAN using MAC addresses.

## 6. Ethernet and CSMA/CD

**Ethernet** is the dominant family of wired LAN technologies, defining the frame format, signalling and access method for networks built on cables and switches. Ethernet frames carry source and destination **MAC addresses**, and on older shared-media Ethernet (a bus or a hub-based star) multiple hosts share one channel, so collisions are possible.

**CSMA/CD** (Carrier Sense Multiple Access with Collision Detection) is the access method that lets hosts share that channel.

1. **Carrier sense**: before transmitting, a host listens to the medium. If it is idle, it sends; if it senses traffic, it waits.
2. **Multiple access**: all hosts share the same medium, so any of them can transmit.
3. **Collision detection**: while transmitting, the host keeps comparing what it sends with what it sees on the wire. If the two differ, a **collision** has occurred - another host transmitted at the same time, garbling both signals.
4. **Avoidance / back-off**: once a collision is detected, the host sends a **jam signal** so all stations know, then **stops transmitting** and waits a **random back-off time** before trying again. The random delay means the two hosts are unlikely to collide a second time, which is how collisions are *avoided* after being *detected*.

Modern switched Ethernet largely removes collisions (each switch port is its own collision domain), so CSMA/CD matters mainly for shared-media and historical understanding.

## 7. Bit streaming

**Bit streaming** is the continuous delivery of audio or video data over a network so that playback can begin before the whole file has downloaded. The browser or media player buffers a few seconds of data, then starts playing while more arrives.

- **Real-time (live) streaming**: content is sent as it happens (a live sports match, a video call). The viewer cannot pause to let it buffer; if the connection cannot keep up, quality drops or the stream stutters. Low latency matters more than perfect quality.
- **On-demand streaming**: content is pre-recorded and stored on a server (a film on a streaming service). The player can buffer ahead, so a slightly slower connection still gives smooth playback, just with a longer start delay.

The **bit rate** of the media and the **broadband speed** must be matched. If the media bit rate exceeds the available bandwidth, the stream must buffer frequently or drop to a lower resolution. High-definition video needs a much higher bit rate than audio or low-resolution video, so broadband speed directly limits the quality a user can watch smoothly.

## 8. The internet vs the WWW, and internet hardware

The **internet** is the **global physical infrastructure**: the millions of interconnected networks, routers, cables, fibre backbones and wireless links that carry data between devices worldwide. It is the *medium*.

The **World Wide Web (WWW)** is a **service that runs over the internet**. It is the collection of **web pages and resources**, identified by URLs and linked by hyperlinks, that are accessed using protocols such as HTTP and viewed in a **web browser**. Other services - email, file transfer, gaming, messaging - also run over the internet but are not part of the WWW.

A useful check: **email is on the internet but is not part of the WWW**; a web page viewed in a browser is both. The internet can exist without the WWW (and did, for years); the WWW cannot exist without the internet.

### Internet hardware

| Hardware | Role |
| --- | --- |
| **Modem** (modulator-demodulator) | Converts digital data to and from a form that can travel over the physical telephone/cable line, so a computer can use an analogue telecommunications link |
| **PSTN** (Public Switched Telephone Network) | The traditional public telephone line network, originally designed for voice, often used to carry dial-up or DSL internet traffic |
| **Dedicated (leased) lines** | A permanent, high-quality, high-bandwidth connection reserved for one customer's use, suitable for businesses needing reliable always-on internet |
| **Cell phone network** | Mobile telephone infrastructure (cell towers) that carries data for smartphones and mobile hotspots, giving internet access without fixed cabling |

## 9. IP addressing, subnetting, public/private and static/dynamic

Every device on the internet needs an **IP address** so packets can be routed to it. An IP address is associated with a device through its NIC/WNIC, which is configured (manually or by a server) with the address; the address is tied to the network interface, and a device with several interfaces can have several.

### IPv4 vs IPv6

| Feature | IPv4 | IPv6 |
| --- | --- | --- |
| Length | **32 bits**, written as four decimal octets (e.g. `192.168.0.10`) | **128 bits**, written as eight groups of hex (e.g. `2001:0db8::1`) |
| Address space | About $4.3 \times 10^9$ addresses - now exhausted | About $3.4 \times 10^{38}$ addresses - effectively unlimited |
| Why introduced | The original scheme | To solve IPv4 exhaustion and simplify routing |
| Readability | Easy for humans | Longer but more structured |

### Subnetting

**Subnetting** splits one large network into smaller logical **subnets**. An IPv4 address has two parts: a **network prefix** (identifies the network) and a **host part** (identifies the device within that network). The split point is shown by a **subnet mask** (e.g. `255.255.255.0`) or a **CIDR** length (e.g. `/24`). Subnetting lets an organisation divide its address space to match its physical or departmental layout, improves security by isolating groups of machines, and reduces broadcast traffic in each subnet. For example, `192.168.1.0/24` keeps the first three octets as the network and uses the last octet for up to 254 hosts.

### Public vs private IP (the security axis)

| Type | Use | Routing |
| --- | --- | --- |
| **Public IP** | Uniquely identifies a device on the global internet | Routable across the internet |
| **Private IP** | Used only inside a LAN (ranges such as `192.168.x.x`, `10.x.x.x`) | **Not** routable on the public internet |

**Security implication**: private addresses give a degree of protection because they cannot be reached directly from the internet; a router performing **Network Address Translation (NAT)** maps many private addresses to one public address, hiding the internal structure and conserving public addresses. Public addresses are exposed and so need firewalls and other protection.

### Static vs dynamic IP (the allocation axis)

| Type | How obtained | Typical use |
| --- | --- | --- |
| **Static** | Fixed, set manually, never changes | Servers, printers, web hosts that must always be found at the same address |
| **Dynamic** | Assigned automatically by a **DHCP** server when the device joins, may change | Most home and office devices |

Note that **public/private** and **static/dynamic** are **two independent axes**: an address can be public-static (a web server), public-dynamic (a home connection whose ISP address rotates), private-static (a fixed internal server) or private-dynamic (a laptop joining the office WiFi). Do not mix them up in an exam answer.

## 10. URL and DNS

A **URL (Uniform Resource Locator)** is the address of a resource on the WWW. Its parts identify the access method, the host, and the path to the resource:

```
https://www.example.com/courses/page.html
  \_/   \______________/\________________/
scheme      host               path
```

- **Scheme** (`https`) - the protocol used to fetch the resource.
- **Host** (`www.example.com`) - the **domain name** of the server, which is a human-readable label.
- **Path** (`/courses/page.html`) - the location of the resource on that server.

But the internet routes packets by **IP address**, not by name, so the domain name must be resolved first. That is the job of the **DNS (Domain Name System)**, a global, distributed database that maps domain names to IP addresses.

### DNS resolution, step by step

1. The user types a URL into a browser. The browser extracts the domain name.
2. The browser asks its configured **DNS resolver** (often run by the ISP or a public resolver) for the IP address of that domain.
3. If the resolver does not already know, it queries the **root name server**, which points it to the correct **top-level domain (TLD) server** for the suffix (`.com`, `.org`, etc.).
4. The TLD server points to the **authoritative name server** for the domain, which holds the official records.
5. The authoritative server returns the IP address for the domain.
6. The resolver caches the answer and passes the IP address back to the browser.
7. The browser now opens a connection to that IP address and requests the resource using HTTP.

DNS is what makes the human-friendly names of the WWW usable on the IP-numbered internet.

## Worked-Thinking Routine

1. For a "describe the network" question, place the scenario first: is it LAN or WAN, what model, what topology, what media.
2. For a topology question, trace the actual path of one packet between two named hosts, then judge cost, performance and fault tolerance from that path.
3. For an IP question, identify the two axes separately: is the address public or private, and is it static or dynamic - then give the implication of each.
4. For a DNS question, walk the lookup from browser to resolver to root to TLD to authoritative server and back.
5. For CSMA/CD, remember the order: **sense first, then detect, then back off at random**.

## Common Mistakes

- Saying the internet and the WWW are the same thing; the WWW is a service on the internet.
- Confusing public/private (reachability) with static/dynamic (allocation); they are independent axes.
- Describing CSMA/CD as only detecting collisions; it must also *avoid* them via random back-off.
- Listing a router's job as "switching by MAC address"; that is a switch. A router routes by IP between networks.
- Forgetting that private IP addresses are not routable on the public internet and rely on NAT.
- Treating thin-client as meaning "no client at all"; it still has input/output hardware, just little processing.
- Mixing up fibre-optic (light, immune to electrical interference) with copper (electrical, susceptible to it).
- Claiming microwaves or satellites need no line of sight; both are affected by obstacles and weather.

## Quick Self-Check

- Give two benefits of networking computers and one drawback.
- Contrast a LAN and a WAN on ownership, speed and error rate.
- For a small law firm with sensitive central records, justify client-server over peer-to-peer.
- For each of bus, star and mesh, describe how a packet gets from host A to host B.
- Explain why a mesh tolerates link failure better than a bus.
- Name the medium best suited to very long-distance, high-bandwidth links and say why.
- State the difference between a switch and a router in one sentence each.
- Describe the four stages of CSMA/CD in order.
- Distinguish real-time from on-demand bit streaming and say which needs the lower latency.
- Give one service that runs on the internet but is not part of the WWW.
- For `192.168.1.5`, classify it on both the public/private and static/dynamic axes (what do you know, what do you not?).
- List the DNS lookup stages from browser to authoritative server.

## Connections

- [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/00 Overview|Communication and Internet Technologies]] (A Level) extends this with protocols, switching and security.
- [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|Security, Privacy and Data Integrity]] covers the threats that networks introduce and how they are countered.

## Study Sequence

1. Read this note top to bottom; redraw each topology and trace one packet through it.
2. Memorise the topology and media comparison tables until the trade-offs are automatic.
3. Drill the two independent IP axes (public/private, static/dynamic) until you never conflate them.
4. Walk through DNS resolution aloud until each stage and its server is automatic.
5. Finish with the syllabus checklist: tick each "show understanding" point against what you can now explain.
