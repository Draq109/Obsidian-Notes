---
created: 2025-08-21T12:44
source: "[[Information Gathering - Web Edition#WHOIS]]"
related: "[[Passive Reconnaissance]]"
tags:
  - query
  - recon
  - osint
  - tool
  - web
---
# WHOIS

## Summary
Is a query search tool for returning information on a given domain, such as google.com. The information comes from either the TLD registry WHOIS server or the registrars WHOIS server. Contains registration, domain, and owner info if not privacy protected. IPs can also be queried, returning the IP block/CIDR its a part of and the IP block owner.

## Details
- Information given can be vast and can include
	- Registrant Name (Go Daddy)
	- Registrant Email/Phone
	- Administrative/Technical contact
	- Registration Date
	- Nameservers
	- Domain Status (clientTransferProhibited)
	- DNS Records/IP Addresses
	- Subdomains
-  One of the very few beginning steps in pen-testing

## Why It Matters
Its a great tool to gather info on a target domain or IP address. This helps in gathering the base information and possible targets to attack. It can also help you check what is available to others to see and whether or not that public information is a risk to your company's infrastructure. 

## References
- [[2025-08-14 Information Gathering - Web Edition Session#Information Gathering - Web Edition WHOIS WHOIS|2025-08-14 Information Gathering - Web Edition Session]]
- [WHOIS Lookup Tool](https://whois.domaintools.com/)  