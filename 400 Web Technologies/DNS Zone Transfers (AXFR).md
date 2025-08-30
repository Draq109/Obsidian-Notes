---
created: 2025-08-29T09:33
source: "[[Information Gathering - Web Edition#DNS Zone Transfers]]"
related:
  - "[[DNS]]"
  - "[[Zone File]]"
  - "[[Subdomain Enumeration]]"
tags:
  - web
  - query
  - records
  - file
---
# DNS Zone Transfers (AXFR)

## Summary
A method for transferring the records to a backup or second server. The zone transfer is initiated by the second DNS server. Before initializing the transfer with the main server, it verifies who the second server is.  

## Details
- An AXFR can be initiated by anyone simply using `dig @199.43.135.53 example.com AXFR`
	- Must directly query the name server hosting the zone file. (`@199.43.153.53`)
- A from of verification is needed for a AXFR to work
- Transferring involves a 5 step process
- Typical AXFR flow :
	1.  **Zone Transfer Request (AXFR)**: ns2 (Second ns Server) initiates the process.
	2. **SOA Record Transfer**: ns1 (Primary ns server) sends its SOA record as proof of authentication
	3. **DNS Records Transmission**: ns1 begins sending each record individually to ns2. (MX, A, NS, PTR)
	4. **Zone Transfer Complete**: After all records sent, ns1 sends a completion notification to ns2
	5. **Acknowledge (ACK)**: ns2 sends an ACK back to ns1 confirming and ending the session

## Why It Matters
In recent times it was normal to have AXFR be available to anyone that initiated them. Now a days it requires authentication. If a DNS server has AXFR misconfigured then attackers can gain access to all subdomains and IPs tied to that domain. Abusing this misconfiguration is as easy enough that you run one dig command.

## References
[[2025-08-15 Information Gathering - Web Edition Session]]