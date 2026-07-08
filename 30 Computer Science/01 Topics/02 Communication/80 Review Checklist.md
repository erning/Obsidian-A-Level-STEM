---
title: Communication Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/02 Communication/00 Overview|Communication]]"
status: active
tags:
  - computerscience/networks
  - review-checklist
---

# Communication Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can recall, trace, and explain the ideas without prompting.

## Ideas to Recall

- [ ] Define a network and recall the main benefits of connecting computers.
- [ ] Distinguish LAN from WAN by geographic spread, ownership, typical speed, error rate, and connecting media.
- [ ] Distinguish client-server from peer-to-peer, and thin-client from thick-client.
- [ ] Recall the cost, performance, and fault-tolerance trade-offs of bus, star, mesh, and hybrid topologies.
- [ ] Distinguish public cloud from private cloud, including benefits and drawbacks.
- [ ] Recall the main transmission media: copper cable, fibre optic cable, radio or WiFi, microwave, and satellite.
- [ ] State the role of a switch, server, NIC, WNIC, WAP, cable, bridge, repeater, and router.
- [ ] Explain Ethernet and the four stages of CSMA/CD: carrier sense, multiple access, collision detection, and random back-off.
- [ ] Distinguish real-time bit streaming from on-demand bit streaming.
- [ ] Distinguish the internet from the World Wide Web, and recall the purpose of modems, PSTN, dedicated lines, and cell phone networks.
- [ ] Recall IPv4 and IPv6 address lengths, subnetting, NAT, public/private addresses, static/dynamic addresses, URLs, and DNS.

## Skills to Perform

- [ ] Draw bus, star, mesh, and hybrid topologies and trace how a packet travels between two named hosts.
- [ ] Choose a suitable network model for a scenario and justify it against the alternative.
- [ ] Choose a suitable client type, topology, medium, or LAN device for a named situation.
- [ ] Compare a switch and a router by the address each reads and the scope each works in.
- [ ] Trace CSMA/CD from listening to the medium through collision detection, jam signal, and random back-off.
- [ ] Classify an IP address situation on the public/private axis and the static/dynamic axis separately.
- [ ] Explain how NAT lets private-addressed devices communicate through a public address.
- [ ] Parse a URL into scheme, host, and path.
- [ ] Walk through DNS resolution from browser to resolver, root server, TLD server, authoritative server, and back.
- [ ] Explain whether a streaming problem is caused by media bit rate, broadband speed, buffering, or latency.

## Things to Trace or Explain

- [ ] Trace a packet in a bus, star, and mesh topology, naming who sees the packet and how the destination is reached.
- [ ] Explain why a router connects networks while a switch forwards inside one LAN.
- [ ] Explain why private IP addresses are not directly routable on the public internet.
- [ ] Trace how a browser gets from a human-readable domain name to an IP address using DNS.
- [ ] Explain why IPv6 was introduced and compare its address space with IPv4 using powers of two.
- [ ] Explain why a mesh topology tolerates a failed link while a bus topology does not.
- [ ] Explain why fibre is strong for long-distance, high-bandwidth links and why wireless media bring security and interference issues.
- [ ] Connect this topic to [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/00 Overview|Communication and Internet Technologies]] by explaining how protocols and packet switching build on IP, routers, and DNS.
- [ ] Connect this topic to [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|Security, Privacy and Data Integrity]] by explaining how network connectivity introduces threats and data-transfer checks.

## Common Errors to Avoid

- [ ] Treating the internet and the WWW as the same thing.
- [ ] Confusing public/private addressing with static/dynamic allocation.
- [ ] Saying a switch routes by IP address, or saying a router forwards by MAC address inside one LAN.
- [ ] Describing CSMA/CD as only detecting collisions without the random back-off that avoids repeated collisions.
- [ ] Forgetting that private IP addresses need NAT to communicate outside the LAN.
- [ ] Treating thin-client as if there is no client hardware at all.
- [ ] Assuming public cloud is automatically more secure because a provider runs it.
- [ ] Mixing up fibre optic cable, copper cable, microwave, and satellite transmission characteristics.
- [ ] Claiming DNS returns a web page rather than an IP address.
- [ ] Forgetting that live streaming cannot buffer far ahead in the way on-demand streaming can.

## Ready to Move On When

- [ ] I can describe the physical, local-network, and internet-wide layers of this topic without mixing them together.
- [ ] I can choose and justify a network model, topology, medium, and set of LAN devices for a realistic scenario.
- [ ] I can trace one packet through a topology and explain the failure points.
- [ ] I can classify IP addresses on both independent axes and explain NAT.
- [ ] I can distinguish the internet, the WWW, URL structure, IP addressing, and DNS in one coherent explanation.
- [ ] I can explain CSMA/CD as a timed process rather than as a single definition.
- [ ] I can diagnose a streaming scenario using bit rate, bandwidth, buffering, and latency.
- [ ] I can explain how this topic prepares for [[30 Computer Science/01 Topics/14 Communication and Internet Technologies/00 Overview|Communication and Internet Technologies]].
- [ ] I can connect network threats and transfer checks to [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|Security, Privacy and Data Integrity]] and protected communication in [[30 Computer Science/01 Topics/17 Security/00 Overview|Security]].
