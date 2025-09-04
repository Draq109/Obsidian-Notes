---
created: 2025-09-02T10:14
source: "[[CompTIA Network+ Study Guide Exam N10-008 EPUB#Point-to-Point Topology]]"
related:
tags:
  - quick
---
# Point-to-Point Topology

**Definition:**  
A **point-to-point link** is a network connection with **exactly two endpoints**, where no other device shares the link.
- Only two devices communicate over the link.
- Can be physical (cable, fiber) or virtual (WAN circuit).
- Exclusive use: no other hosts can send traffic over the same link.
- High reliability and predictable performance since there’s no shared medium.

**Contrast with Shared Topologies:**
- **Bus/Ring:** multiple devices share the same medium → not point-to-point.
- **Switch connections:** the cable from a workstation to a switch is point-to-point, even though the switch forwards traffic for other devices (each port has its own dedicated link).


**Mnemonic / Mental Shortcut:**
**Physically**: “If no other device can use the line without its own dedicated connection, it’s point-to-point.”
**Logically:** “If only two devices communicate over the link regardless of the underlying medium, it’s point-to-point.”