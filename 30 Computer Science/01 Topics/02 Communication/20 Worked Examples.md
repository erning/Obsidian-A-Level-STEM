---
title: Communication Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/02 Communication/00 Overview|Communication]]"
status: active
tags:
  - computerscience/networks
  - worked-examples
---

# Communication Worked Examples

These examples model how to reason through scenario-based questions on networks, topologies, hardware, addressing and naming. The aim is not to recite definitions but to show how to choose and justify a network model, a topology, or an address type for a named situation.

## Source Route

- Syllabus: CAIE Computer Science 9618, AS Section 2 - Communication.
- Assessed in Paper 1.
- Topics: networks, client-server vs peer-to-peer, thin vs thick client, topologies, cloud, media, LAN hardware, Ethernet and CSMA/CD, bit streaming, internet vs WWW, internet hardware, IP addressing, URL and DNS.

## Example 1: Client-Server vs Peer-to-Peer for a Medical Practice

**Prompt.** A small medical practice with four doctors needs to store patient records centrally, control which staff can view them, and back them up nightly. Justify whether a client-server or a peer-to-peer model is more appropriate.

**Solution.** Client-server is more appropriate.

- The records are sensitive and must be secured with user accounts and access control, which a central server provides.
- Centralised backup of one server is straightforward and reliable, whereas a peer-to-peer network would require each machine to be backed up individually.
- A server gives a single, managed location for files, so any doctor can find a record quickly from any client.
- The cost and the need for IT support are acceptable because the practice is small enough that one server suffices and data integrity is critical.

A peer-to-peer model would be cheaper but would not give centralised control or reliable backup, so it is unsuitable for medical records.

**Check.** The deciding factors are central control, security and backup, all of which favour client-server.

## Example 2: Justifying a Star Topology for a School Lab

**Prompt.** A school is fitting out a computer lab of 30 PCs. Compare bus, star and mesh topologies and justify which is the best choice.

**Solution.**

- A **bus** topology is the cheapest, using a single backbone cable, but a break in the backbone or a terminator fault disables the whole network, and collisions become common as more PCs share the channel.
- A **star** topology connects each PC by its own cable to a central switch. The switch forwards frames only to the destination port, which reduces collisions, and a single faulty cable affects only one PC. The central switch is the single point of failure, but a school can keep a spare.
- A **mesh** topology gives every node multiple links, so traffic can be re-routed around failures, but it needs far more cabling than 30 PCs justify and is expensive to install.

A **star** topology is the best choice. It balances cost against performance and fault tolerance: it is far more reliable than a bus, and far cheaper than a mesh, for a fixed room of 30 machines.

**Check.** The chosen topology must be defended against each alternative, not just listed.

## Example 3: Choosing LAN Hardware for a Wireless Office

**Prompt.** A small office wants laptops to connect wirelessly and a desktop to connect by cable, with all devices sharing files held on one machine. Name the LAN hardware required and give the role of each.

**Solution.**

- A **switch** connects the cabled desktop and the file server to the LAN and forwards frames only to the correct port.
- A **server** (one of the machines) holds the shared files.
- The cabled desktop needs a **NIC** to connect to the wired network.
- Each laptop needs a **WNIC** to connect over WiFi.
- A **WAP** (Wireless Access Point) connects the wireless laptops to the wired LAN.
- **Cables** (copper) link the cabled devices to the switch.
- If any device is far from the switch, a **repeater** can regenerate the signal; a **bridge** is needed only if two separate segments must be joined and filtered.

A **router** is not strictly part of this LAN but would be added at the edge to connect the office to the internet.

**Check.** Each named device must actually appear in the scenario; do not list hardware the office does not need.

## Example 4: CSMA/CD as Detect then Avoid

**Prompt.** Two hosts on a shared Ethernet segment transmit at almost the same instant. Explain how CSMA/CD detects and then avoids a collision.

**Solution.**

1. *Before* either host transmits, it performs **carrier sense**: it listens to the medium and sends only if the channel is idle. Here both sensed idle, so both started.
2. While transmitting, each host keeps comparing the bits it sends with the bits it sees on the wire. Because both are transmitting at once, the signals garble, so what each host *sees* no longer matches what it *sends*. This mismatch is the **collision detection**.
3. Once a collision is detected, the host sends a **jam signal** so every station is informed, then **stops transmitting**.
4. Each host then waits a **random back-off time** before trying again. Because the two waits are random and independent, the hosts are unlikely to transmit at the same instant a second time, so the retry succeeds.

The detection step notices the collision; the random back-off step *avoids* repeating it.

**Check.** CSMA/CD must include both halves: detect, then avoid by random back-off.

## Example 5: Internet vs World Wide Web

**Prompt.** A student writes "the World Wide Web is the same thing as the internet." Correct the statement and give one example of a service that runs on the internet but is not part of the WWW.

**Solution.** The statement is wrong.

- The **internet** is the global physical and logical infrastructure: the interconnected networks, routers, cables, fibre backbones and wireless links that carry data between devices worldwide. It is the *medium*.
- The **WWW** is a *service* that runs over the internet. It is the collection of web pages and resources, identified by URLs and linked by hyperlinks, accessed through protocols such as HTTP and viewed in a web browser.

A service that runs on the internet but is not part of the WWW is **email**: it uses protocols such as SMTP and is not, in essence, a set of hyperlinked resources viewed in a browser (even when a webmail interface exists, the underlying email system is distinct from the WWW). Other valid examples include file transfer, online gaming and VoIP.

**Check.** If a service is accessed through a browser as hyperlinked resources, it is part of the WWW; otherwise it is on the internet but not the WWW.

## Example 6: IPv4 vs IPv6 Address Space

**Prompt.** Explain why IPv6 was introduced and show, using powers of two, how much larger its address space is than IPv4's.

**Solution.** IPv4 uses 32-bit addresses, so the number of possible addresses is

$$
2^{32}=4\,294\,967\,296\approx 4.3\times 10^{9}.
$$

This is fewer than five billion, which is too few for the number of devices now wanting to connect, so the IPv4 address pool is effectively exhausted.

IPv6 uses 128-bit addresses, so the number of possible addresses is

$$
2^{128}\approx 3.4\times 10^{38}.
$$

This is so large that exhaustion is not a practical concern. The ratio of the two spaces is

$$
\frac{2^{128}}{2^{32}}=2^{96}\approx 7.9\times 10^{28},
$$

so IPv6 offers roughly $8\times 10^{28}$ times as many addresses as IPv4. IPv6 also simplifies routing and removes the need for the workarounds (such as NAT) that IPv4 relies on.

**Check.** The sizes should be quoted as $2^{32}$ for IPv4 and $2^{128}$ for IPv6.

## Example 7: Public/Private and Static/Dynamic as Two Axes

**Prompt.** For each address below, classify it on the public/private axis and on the static/dynamic axis, and give one reason for that combination.

(a) A company's public web server at `203.0.113.5`, configured by the administrator.
(b) A home router as seen by the ISP, assigned fresh each time it reconnects.
(c) An office file server at `192.168.10.4`, set in its configuration file.
(d) A visitor's phone joining the office WiFi.

**Solution.**

(a) **Public and static.** Public so it can be reached from anywhere on the internet; static so its DNS entry never has to change.
(b) **Public and dynamic.** Public because the router faces the ISP; dynamic because the ISP rotates addresses to conserve its pool.
(c) **Private and static.** Private because it is only used inside the LAN (the `192.168.x.x` range is not routable on the internet); static so clients can always find the file server at the same address.
(d) **Private and dynamic.** Private because it is on the internal LAN; dynamic because a DHCP server hands it an address for the visit, which may differ next time.

The key point is that public/private and static/dynamic are **independent** axes: any combination is possible, and each must be reasoned separately.

**Check.** Identify reachability (public/private) first, then allocation (static/dynamic), and never assume one from the other.

## Example 8: DNS Resolution Walkthrough

**Prompt.** A user types `https://www.cambridgeinternational.org/exams` into a browser for the first time. Walk through the DNS resolution that lets the browser contact the server.

**Solution.**

1. The browser extracts the domain name `www.cambridgeinternational.org` from the URL.
2. The browser asks its configured **DNS resolver** (often run by the ISP or a public resolver) for the IP address of that domain.
3. The resolver does not yet know the answer, so it queries a **root name server**, which replies with a referral to the **TLD server** responsible for `.org`.
4. The resolver asks the `.org` TLD server, which replies with a referral to the **authoritative name server** for `cambridgeinternational.org`.
5. The authoritative server holds the official records and returns the IP address for `www.cambridgeinternational.org`.
6. The resolver caches the answer for future use and passes the IP address back to the browser.
7. The browser now opens a connection to that IP address and sends the HTTP request for the path `/exams`.

DNS is what converts a human-readable domain name into the IP address that the internet actually routes packets to.

**Check.** The lookup order is browser, resolver, root, TLD, authoritative, then back along the chain to the browser.
