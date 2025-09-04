---
created: 2025-09-02T08:48
source: "[[CompTIA Network+ Study Guide Exam N10-008 EPUB#Client-Server Networks]]"
related:
  - "[[Peer-to-Peer Networks (P2P)]]"
tags:
  - network
  - foundation
---
# Client-Server Networks

## Summary
In a client-server network, the server provides all the resources a client needs, as opposed to [[Peer-to-Peer Networks (P2P)|P2P]].
The server can handle multiple workstations request while maintaining all data in one location. Security measures are easier to manage due to the server being the central point of authentication for clients.

## Details
- Usernames and passwords all get stored on the same server.
- Network is much more organized, with files being easier to sync.
- Servers can be scaled to meet any further expansion needs.
- Very popular architecture used by any web application today.

## Why It Matters

- Centralizing a network makes management easier, but it also creates a **central repository** that becomes a **high-value target for attackers**.  
- Real environments aren’t just bare bones client-server setups like in textbooks. They usually operate as a **hybrid mix of client-server and peer-to-peer**, which spreads functionality but still leaves centralized components as **single points of compromise**. 
