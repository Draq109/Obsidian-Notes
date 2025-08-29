---
created: 2025-08-21T19:26
source: "[[Information Gathering - Web Edition#Key DNS Concepts]]"
related:
  - "[[DNS]]"
  - "[[Domain Name]]"
  - "[[Subdomains]]"
  - "[[Domain Information Groper]]"
tags:
  - file
  - records
  - web
---
# Zone File

## Summary
The file located in a name server (NS), listing IPs and subdomains for a given domain. This includes records such as MX, TXT, SRV, NS, and A/AAAA records. It defines how the domain is resolved and delegated to other name servers.

## Details
- Contains **resource records (RRs)** that map hostnames to IPs or provide other domain info.  
- Common record types:  
  - **A/AAAA** → IPv4/IPv6 addresses  
  - **NS** → authoritative name servers for the zone  (Usually where you host the main file)
  - **MX** → mail servers  
  - **TXT** → arbitrary text (e.g., SPF, DKIM)  
  - **SRV** → service location records  
- May include **SOA (Start of Authority)** record defining zone properties: serial, refresh, retry, expire, TTL.  
- Example snippet of a zone file:
```
$TTL 3600  
@ IN SOA ns1.example.com. admin.example.com. (  
2025082101 ; serial  
3600 ; refresh  
1800 ; retry  
604800 ; expire  
86400 ) ; minimum TTL  
@ IN NS ns1.example.com.  
@ IN NS ns2.example.com.  
www IN A 203.0.113.10  
mail IN MX 10 mail.example.com.
```

- Usually stored on **authoritative DNS servers** and used by recursive resolvers during queries.
- The @ stands for the domain (*example.com*)
	- for instance `@ IN NS ns1.example.com`
	- **IN** -> internet
	- So it reads *example.com* internet name server is *ns1.example.com* 
## Why It Matters
- Zone files define how a domain resolves, which is fundamental to web services, email, and other network operations.  
- Misconfigurations can lead to downtime, email delivery failure, or security risks (e.g., exposing subdomains, allowing DNS hijacking).  
- Penetration testers and attackers can analyze zone files to enumerate hosts, subdomains, or services for reconnaissance.
## References
- [[2025-08-14 Information Gathering - Web Edition Session#Information Gathering - Web Edition Key DNS Concepts Zone File|2025-08-14 Information Gathering - Web Edition Session]]
