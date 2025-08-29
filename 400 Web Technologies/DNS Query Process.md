---
created: 2025-08-21T19:29
source: "[[Information Gathering - Web Edition#DNS]]"
related:
  - "[[DNS]]"
  - "[[Domain Name]]"
  - "[[Subdomains]]"
  - "[[Zone File]]"
tags:
  - web
---
# DNS Query Process

## Summary
The DNS query process translates a domain name into an IP address. It follows a hierarchical sequence, starting from local caches and recursive resolvers, down to authoritative servers, to resolve the requested domain.

## Details
1. **Client Request:**  
   The application requests a domain (e.g., `example.com`). The OS checks its local DNS cache first.

2. **Recursive Resolver:**  
   If the domain isn’t cached, the request goes to a recursive DNS resolver (ISP or manually configured) to locate the IP.

3. **Root Server Query:**  
   The resolver queries a root server for the TLD server for `.com`.

4. **TLD Server Query:**  
   The root responds with the `.com` TLD server IP. The resolver asks the TLD server for the authoritative server for `example.com`.

5. **Authoritative DNS Server:**  
   The TLD server points to the authoritative DNS server. The resolver queries it and receives the final IP address.

6. **Response to Client:**  
   The resolver sends the IP back to the client.

**Full trace example:**
```bash
dig +trace example.com    # Trace full query path
# Response
; <<>> DiG 9.18.16 <<>> +trace google.com
;; global options: +cmd
.                       518400  IN      NS      a.root-servers.net.
.                       518400  IN      NS      b.root-servers.net.
.                       518400  IN      NS      c.root-servers.net.
.                       518400  IN      NS      d.root-servers.net.
.                       518400  IN      NS      e.root-servers.net.
.                       518400  IN      NS      f.root-servers.net.
.                       518400  IN      NS      g.root-servers.net.
.                       518400  IN      NS      h.root-servers.net.
.                       518400  IN      NS      i.root-servers.net.
.                       518400  IN      NS      j.root-servers.net.
.                       518400  IN      NS      k.root-servers.net.
.                       518400  IN      NS      l.root-servers.net.
.                       518400  IN      NS      m.root-servers.net.

;; Received 239 bytes from 192.168.1.1#53(192.168.1.1) in 2 ms

com.                    172800  IN      NS      a.gtld-servers.net.
com.                    172800  IN      NS      b.gtld-servers.net.
com.                    172800  IN      NS      c.gtld-servers.net.

;; Received 120 bytes from 198.41.0.4#53(a.root-servers.net) in 15 ms

google.com.             172800  IN      NS      ns1.google.com.
google.com.             172800  IN      NS      ns2.google.com.
google.com.             172800  IN      NS      ns3.google.com.
google.com.             172800  IN      NS      ns4.google.com.

;; Received 112 bytes from 192.5.6.30#53(a.gtld-servers.net) in 20 ms

google.com.             300     IN      A       142.250.190.78

;; Received 48 bytes from 216.239.32.10#53(ns1.google.com) in 10 ms

```

## References
- [[2025-08-15 Information Gathering - Web Edition Session]]
