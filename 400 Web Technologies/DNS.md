---
created: 2025-08-21T16:56
source: "[[Information Gathering - Web Edition#DNS]]"
related: 
  - "[[Domain Name]]"
  - "[[WHOIS]]"
  - "[[Host File]]"
tags:
  - system
  - protocol
  - network
---
# DNS

## Summary
Stands for Domain Name System, and its purpose is to translate a human readable domain to an IP address for your device/browser. The process or steps for translating a domain can vary depending on how the DNS resolution happens (Cache's having the IP, starting the process by asking the TLD or authoritative server directly).
## Details
- Used in almost every HTTP request when IP is not known.
- The creation of this system has created a new outbound connection requirement before being able to browse a website. Introducing new security issues that attackers can intercept (*MITM*), manipulate (*cache tampering*), or abuse for [[Active Reconnaissance|reconnaissance]] (*Zone transfers*, *subdomain enum*)
- The whole process of actually resolving takes place in a DNS Server(*Recursive Resolving*).
- Multiple [[Domain Name|domain names]] can resolve to the same IP. (*Virtual Hosting*)
- DNS requests are done on port 53, and are not encrypted. (*In plaintext*)
	- Privacy options are now in place, such as VPNs or DoH/DoT
- Most routers default to using the ISP DNS server. (*Encryption is worthless unless you change DNS servers*)
- Domains and subdomains IPs are stored in a name server (NS), on a zone file that contains all types of records.
- Domains can be left expired, leaving trails or being open to someone stealing that domain.
	- Can also be forgotten and left running, being open to attacks. (*forgotten = no security updates*)
## Why It Matters
DNS is essential for every device to reach services, but it’s unencrypted by default, letting ISPs or attackers see your traffic. Misconfigured or insecure DNS can be abused for spoofing, hijacking, or recon. Proper understanding helps defend networks, investigate incidents, and apply mitigations like DNSSEC or DoH/DoT. 
## References
- [[2025-08-14 Information Gathering - Web Edition Session#Information Gathering - Web Edition DNS DNS (Domain Name System)|2025-08-14 Information Gathering - Web Edition Session]]
