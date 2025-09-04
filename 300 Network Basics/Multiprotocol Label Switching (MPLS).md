---
created: 2025-09-01T11:43
source: "[[CompTIA Network+ Study Guide Exam N10-008 EPUB#Multiprotocol Label Switching]]"
related: "[[Wide Area Network (WAN)]]"
tags:
  - networking
  - protocol
---
# Multiprotocol Label Switching (MPLS)

## Summary
MPLS is a WAN technology designed to improve speed, efficiency, and flexibility of data transport across large networks.  
- Uses **labels** to forward packets instead of relying purely on IP routing.  
- Allows **traffic prioritization**, multiple virtual paths, and predictable performance.  
- Labels are stripped at the edge when packets reach external networks like the Internet.  

---

## How MPLS Works
- Operates at **Layer 2.5**, between data link and network layers.  
- **Ingress router**: assigns labels to packets.  
- **Label Switching Routers (LSRs)**: forward packets based on labels, not full IP addresses.  
- **Egress router**: removes labels; packet continues to its IP destination.  
- Supports **traffic engineering**, **QoS**, and **VPNs**.  
- Enables **redundancy** and **load balancing** via multiple logical paths.  

---

## Deployment & Usage
- Mostly used in **private WANs** connecting offices, campuses, or data centers.  
- Often deployed via **service provider networks** (telcos/ISPs).  
- Not a “cloud” in the SaaS sense — it’s a provider-managed network overlay.  
- Physical links: fiber, copper, or other WAN connections.  
- MPLS overlays a **logical layer** for routing and prioritization.  

---

## Positives / Benefits
- High reliability and predictable performance for **critical traffic** (e.g., VoIP, video, backups).  
- Traffic prioritization with **Class of Service (CoS)**.  
- Multiple virtual paths over the same physical network.  
- Supports VPNs and strong segmentation.  
- Reduces reliance on the public Internet for sensitive traffic.  

---

## Negatives / Limitations
- Usually **expensive** compared to internet-based solutions.  
- **Complex to configure**, requires coordination with the provider.  
- Limited scalability compared to **SD-WAN** or cloud-native networks.  
- Less flexible for dynamic routing or quick network changes.  
- Cannot directly connect end-users without edge devices or tunnels.  

---

## Why It Matters / Perspectives
- **Enterprise POV**: guarantees reliability and low latency for mission-critical apps.  
- **Carrier POV**: allows tiered service with QoS guarantees.  
- **Modern viewpoint**: widely used but increasingly supplemented or replaced by **SD-WAN**.  

---

## Related Concepts
- [[SD-WAN]] – modern alternative to MPLS with more flexibility and cheaper internet links.  
- [[VPN]] – MPLS can provide secure, segmented network connections similar to a private VPN.  
- [[Traffic Engineering]] – optimization of paths for performance and reliability.  
