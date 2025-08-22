---
created: 2025-08-21T18:01
source: "[[Information Gathering - Web Edition#DNS]]"
related:
  - "[[DNS]]"
  - 
tags:
  - foundation
---
# Domain Name

## Summary
Its the name given to an IP address for a website or service. This was created to avoid having to remember IP numbers *109.55.34.123*. The name can consist of three different parts, a subdomain, 2nd level domain, and top level domain.

## Details
- Example: `mail.example.com`
  - `.` → root
  - `com` → top-level domain (*TLD*)
  - `example.com` → second-level domain (registered by an entity)
  - `mail.example.com` → subdomain
-  Fully qualified domain names (*FQDNs*) always end with a dot (`mail.example.com.`).
-  Domains rely on [[DNS]] to be translated to their IP address (*A/AAAA records*)
- To obtain a domain you must have a public IP, and apply with a registrar to have them provide a domain to you. (*GoDaddy*)
## Why It Matters
- Domains are the starting point for most network activity.  
- Attackers can abuse domains for **phishing** (lookalike names), **C2 infrastructure**, and **DNS hijacking**.  
- Recon often begins with discovering target domains and subdomains.  
- Understanding the hierarchy is crucial when analyzing DNS queries, investigating spoofing, or conducting penetration tests.  

## References
- [[2025-08-14 Information Gathering - Web Edition Session#Information Gathering - Web Edition DNS DNS (Domain Name System)|2025-08-14 Information Gathering - Web Edition Session]]
