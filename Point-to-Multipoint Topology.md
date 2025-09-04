---
created: "2025-09-02T11:12"
source:
related:
tags:
  - quick
---
# Point-to-Multipoint Topology

**Definition:**  
A **point-to-multipoint (P2MP) link** is a network connection where **one central device communicates with multiple endpoints**, either over a shared medium or separate physical/logical paths.

**Key Characteristics:**

- One device acts as the **central point**; multiple devices are the **endpoints**.    
- Can be **physical** (hub, wireless access point, leased lines) or **logical** (VPNs, MPLS hub-and-spoke).
- The central device often manages traffic, addressing, and access.
- Endpoints do not communicate directly with each other over the same link (unless routed through the central point).

**Contrast with Point-to-Point:**
- **Point-to-Point:** exclusive communication between exactly two devices.
- **Point-to-Multipoint:** one device communicates with multiple devices over the same medium or logical connection.

**Mental Shortcut:**
“One-to-many communication from a single central device is point-to-multipoint.”

**Examples:**
- Router connecting to multiple branch offices via MPLS.    
- Wi-Fi access point serving multiple clients.
- Satellite hub communicating with multiple terminals.