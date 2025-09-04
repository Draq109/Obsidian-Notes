---
created: 2025-08-30T17:29
source: "[[CompTIA Network+ Study Guide Exam N10-008 EPUB#The Local Area Network]]"
related:
  - "[[Wide Area Network (WAN)]]"
  - "[[Metropolitan Area Network (MAN)]]"
tags:
  - network
  - foundation
---
# Local Area Network (LAN)

## Summary
Is a small network that involves at least two interconnected devices. Represents most household or small businesses. Where all outbound traffic is redirected usually through one router onto the internet. 

## Details
- Can contain multiple switches or hubs in place
- Can have upwards of 40 workstations (PCs) and servers in place
- Larger LAN's are split into smaller LAN workgroups to ease workload and management for administrators
### How to tell if its one LAN or Multiple LANs
To figure out if a network diagram shows one LAN or multiple LANs, think about broadcast domains and subnets. Look at where the router is and how it’s set up: if it’s running in Layer 3 routing mode, it splits the network into separate broadcast domains and usually gives each side its own subnet — that’s multiple LANs. If the router is in Layer 2 bridge mode, it lets broadcasts pass through, so all devices share the same subnet and broadcast domain, making it a single LAN. Essentially, one LAN means one subnet, one broadcast domain, and bridging; multiple LANs mean separate subnets, separate broadcast domains, and routing.
##### Simplified
**How to tell if it’s one LAN or multiple LANs:**

- **Is a router present?**
    
    - **Yes → Is it in routing mode (Layer 3)?**
        
        - **Yes → Multiple LANs** (separate broadcast domains, different subnets).
            
        - **No, it’s in bridge mode (Layer 2) → One LAN** (same broadcast domain, same subnet).
            
    - **No router present → One LAN** (all devices share the same broadcast domain).

## Why It Matters
Its the basis for any network layout found in the world. Stores, houses, businesses, all use a form of LAN. Understanding will help in troubleshooting, setting up multiple LAN workgroups, managing, etc..

