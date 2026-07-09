---
title: Communication Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[Communication](00%20Overview.md)"
status: active
tags:
  - computerscience/networks
  - solutions
---

# Communication Key Practice Solutions

These solutions correspond to [Key Practice Problems](30%20Key%20Practice%20Problems.md).

## A. Networks and models

### Problem 1

Peer-to-peer is more suitable. With only three PCs and a small set of shared resources, no dedicated server is justified. Each PC can act as both client and server, sharing its printer and files directly with the others. This is cheap, needs no specialist staff, and is robust because losing one machine does not bring the whole network down.

### Problem 2

Client-server is better. Student records must be held centrally so that any authorised staff member can reach them, access must be controlled by user accounts held on a server, and a nightly backup of one server is far more reliable than backing up many scattered machines. The cost of one server is justified by the need for security and reliable backup.

### Problem 3

Thin-client is more appropriate. Thin-clients are cheap, lightweight terminals that rely on a powerful central server for all processing, which makes them easy to maintain and patch centrally because only the server needs updating. The drawback is that the whole operation depends on a fast, reliable network and a strong server; if either fails, every terminal stops working.

### Problem 4

- Ownership: a LAN is usually owned and maintained by the organisation that uses it, while a WAN uses third-party telecommunications links.
- Typical speed: a LAN is typically faster, while a WAN has lower data rates.
- Error rate: a LAN has a low error rate, while a WAN has a higher error rate.

### Problem 5

Thick-client is more appropriate. A thick-client does its processing locally on its own CPU and storage, so it can run heavy rendering software without depending on the network, and it keeps working even when the network is slow or briefly unavailable. The trade-off is higher cost per workstation and more effort to patch each machine.

## B. Topologies and hardware

### Problem 6

A mesh topology is best. In a mesh, each node has point-to-point links to several others, so if one cable fails the packet can be re-routed along an alternative path to its destination. This redundancy means a single link failure does not interrupt communication, which is essential for patient monitoring.

### Problem 7

A bus topology is the cheapest and quickest to install, because all eight desks can tap into a single backbone cable with terminators at each end. It is unsuitable for permanent use because a single break in the backbone or a faulty terminator disables the entire network, and collisions become frequent as more nodes share the channel.

### Problem 8

- A **switch** connects nodes inside one LAN and forwards each frame only to the destination port by reading its MAC address.
- A **router** connects separate networks and forwards packets between them by reading their IP address and consulting a routing table.
- A **router** is the device used to connect a home LAN to the internet, because it links the home network (one network) to the ISP's network (another network).

### Problem 9

- A **WNIC** in the laptop lets it join the WiFi network.
- A **WAP** (Wireless Access Point) connects the wireless laptops to the wired LAN.
- A **switch** connects the cabled devices, including the file server, and forwards frames only to the correct port.
- A **NIC** in the file server connects it to the wired network.
- **Cables** (copper) link the cabled devices to the switch.

### Problem 10

- **Bus**: host A broadcasts the packet onto the single backbone. Every node sees it, but only host B keeps it because its address matches. Terminators absorb the signal at each end.
- **Star**: host A sends the packet to the central switch, which forwards it only to the port that host B is connected to.
- **Mesh**: host A sends the packet along one of several direct links towards host B. If the chosen link is down, the packet is re-routed along another path through intermediate nodes.

## C. The internet and addressing

### Problem 11

IPv6 was introduced because the IPv4 address space is effectively exhausted; there are too few IPv4 addresses for the number of devices that now want to connect. IPv4 uses 32-bit addresses, giving

$$
2^{32}\approx 4.3\times 10^{9}
$$

addresses. IPv6 uses 128-bit addresses, giving

$$
2^{128}\approx 3.4\times 10^{38}
$$

addresses, which is so large that exhaustion is not a practical concern.

### Problem 12

The WWW is a service that runs over the internet, not the internet itself. The internet is the global infrastructure of interconnected networks, routers and cables that carries data; the WWW is the collection of web pages and resources, identified by URLs and linked by hyperlinks, accessed through protocols such as HTTP and viewed in a browser. A service that runs on the internet but is not part of the WWW is email (alternatively, file transfer or online gaming).

### Problem 13

- The home router's address `203.0.113.7` is **public** (it faces the ISP) and **dynamic** (it changes on each reconnect).
- The laptop's address `192.168.1.20` is **private** (it is in the `192.168.x.x` range, used only inside the LAN) and **dynamic** (it is handed out to the device when it joins).

The laptop reaches the internet because the router performs **Network Address Translation (NAT)**: it maps the laptop's private address to the router's single public address so that outgoing requests appear to come from the public address, and it translates the replies back to the private address. This hides the internal network and lets many private devices share one public address.

### Problem 14

A **public** IP address uniquely identifies a device on the global internet and is routable across it. A **private** IP address is used only inside a LAN (in ranges such as `192.168.x.x`, `10.x.x.x`, `172.16.x.x` to `172.31.x.x`) and is **not routable on the public internet**. Routers on the internet drop packets addressed to a private range, so a device with only a private address cannot be reached directly from outside its LAN; it must use NAT through a public address.

### Problem 15

- The public web server should be **static**, so that its DNS record always points to the same address and external users can always reach it. If it were dynamic, the address could change and the DNS record would have to be updated each time, risking downtime.
- The office laptops should be **dynamic**, so that a DHCP server can hand out whichever private address is free as each laptop joins and reclaim it when it leaves. This avoids the overhead of configuring a fixed address on every laptop and works because laptops do not need to be found at a fixed address.

## D. DNS and bit streaming

### Problem 16

1. The browser extracts the domain name from the URL.
2. The browser asks its configured DNS resolver for the IP address of that domain.
3. If the resolver does not know, it queries a root name server, which refers it to the TLD server for the domain's suffix.
4. The TLD server refers the resolver to the authoritative name server for the domain.
5. The authoritative server returns the IP address for the domain.
6. The resolver caches the answer and returns the IP address to the browser.

### Problem 17

- Scheme: `https`.
- Host: `www.example.org`.
- Path: `/news`.

A DNS lookup is needed because the browser must open a connection to the server's **IP address**, but the URL gives only the human-readable **domain name**. DNS translates the domain name into the IP address that the internet actually uses to route packets.

### Problem 18

- **Real-time (live) streaming** sends content as it happens, such as a live sports match or a video call. The viewer cannot pause to let it buffer, so low latency matters more than perfect quality.
- **On-demand streaming** sends pre-recorded content stored on a server, such as a film. The player can buffer ahead, so a slightly slow connection still gives smooth playback, just with a longer start delay.

Real-time streaming is more affected by a connection slightly slower than the media bit rate, because it cannot buffer ahead to smooth out the shortfall; quality drops or the stream stutters.

### Problem 19

Because the broadband speed (3 Mbit/s) is less than the media bit rate (5 Mbit/s), the data cannot arrive as fast as it is played. The player must **buffer** more often, pausing playback while it gathers enough data, and/or **drop to a lower-resolution stream** with a lower bit rate that the connection can sustain. Some players do both: switch down a quality level and buffer at the points where even that is too much.

### Problem 20

In real-time streaming the content is produced and sent as it happens, so there is no future data to buffer: the player can only play what has just been captured. Buffering ahead would add delay, which defeats the purpose of a live call, and it cannot fix a connection that simply cannot keep up with the bit rate. So if the broadband speed is below the media bit rate, the call has to drop quality or stutter. In on-demand streaming the whole file already exists on the server, so the player can fetch data ahead of the play position and use that buffer to ride out short-term slowdowns.
