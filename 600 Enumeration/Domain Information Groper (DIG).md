---
created: 2025-08-26T17:11
source: "[[Information Gathering - Web Edition#The Domain Information Groper]]"
related:
  - "[[DNS]]"
  - "[[DNS Query Process]]"
  - "[[Zone File]]"
  - "[[Subdomains]]"
tags:
  - recon
  - enumeration
  - tool
  - query
---
# Domain Information Groper (DIG)

## Summary
Is a tool used to do a DNS resolve on a domain, subdomain, or IP. *dig* can return the records you ask for, such as MX or A/AAAA records. All information originates from the nameserver, from either the owner of the domain or chosen provider. Not all records will be available to retrieve.
## Details
- Not used as dependency for other applications but rather a tool used by security experts or system administrators.
- Used to test the functionality of a nameserver
- Can target specific records for a nameserver
- Allows you to trace to see the complete resolve process from root to authoritative.
## How to use
```
dig domain [record_type] [@server]     # Default syntax
dig google.com NS                      # Retrieving NS for domain
dig google.com A                       # Retrieving IP for domain
dig @8.8.8.8 google.com A              # Selecting specific DNS server
dig -x 8.8.8.8                         # Reverse lookup
dig +trace google.com                  # Tracing the route
```

## Why It Matters
*Dig* is a great tool to test what records are listed, what A record they are linked to, and what subdomains are visible. It can help troubleshoot DNS resolve issues clients have or be a good starting point for attackers. Its a great tool for gathering information on a domain so long as the domains publicly registered.

## References
- [[2025-08-14 Information Gathering - Web Edition Session]]
