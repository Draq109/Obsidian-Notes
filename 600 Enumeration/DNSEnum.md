---
created: 2025-08-29T08:32
source: "[[Information Gathering - Web Edition#DNSEnum]]"
related:
  - "[[Subdomain Bruteforcing]]"
  - "[[DNS]]"
  - "[[Active Reconnaissance]]"
  - "[[Subdomains]]"
  - "[[Zone File]]"
tags:
  - tool
  - web
  - recon
  - query
---
# DNSEnum

## Summary
DNSEnum is a tool used to bruteforce subdomains through dns queries. By providing a wordlist it substitutes it as a subdomain and creates a request. It also returns all A records for that domain, name servers, MX servers, and as well as zone transfer (if possible)

## Details
``` bash
dnsenum example.com #Returns avaliable records,bruteforces with default wordlist 
dnsenum --dnsserver 8.8.8.8  example.com #specifies dns server
dnsenum -f /.../wordlist example.com #provide wordlist for subdomains
dnsenum --enum example.com           #full features whois and reverse lookup
```

## Why It Matters
Good and simple tool thats easy to use for gathering subdomains. Great for semi stealth and a good place to start in recon. (assuming you have a domain name and its public)

## References
[[2025-08-15 Information Gathering - Web Edition Session]]