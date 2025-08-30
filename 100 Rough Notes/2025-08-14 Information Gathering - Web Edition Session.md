---
created: 2025-08-14T08:07:00
source: "[[Information Gathering - Web Edition]]"
tags:
  - "#session"
  - source/HTB
  - status/finished
---
# Study Session – 2025-08-14

## Notes
<!-- Dump everything here as you go -->
### [[Information Gathering - Web Edition#Active Reconnaissance|Active Reconnaissance]]
- Gather info by directly interacting with the target (usually with nmap)
- Vulnerability scanning
- Tracerouting
- Banner grabbing
- OS Detection
- Service and SVersions
- Web Spidering
### [[Information Gathering - Web Edition#Passive Reconnaissance|Passive Reconnaissance]]
- Gather info without direct interaction with the target
- DNS search queries
- Search Engine queries
- WHOIS lookups
- Wayback Machine
- Social Media, usually on employees
- Code repos, gitHub

## [[Information Gathering - Web Edition#WHOIS|WHOIS]]
- Search query on domains that will return ownership and metadata information
- Can also provide information on IP block ownership, when given an IP
- Each query returns a WHOIS record
	- Registrar: The company that registered domain (GoDaddy, Namecheap)
	- Registrant Contact: Person who authorized domain registration
	- Administrative/technical Contact: The people in charge of managing or technical issues. (Not Registrar)
	- Creation/Expiration Date
	- Name Server (Valuable)
- Why it matters: 
	- It gives you potential social targets. Emails, names, phone #'s
	- Details on the host provider allowing insight on their security  
	- Name Servers. Shows network infrastructure 
	- Historical data can be used to compare, showing company changes in ownership, migration or any change.
	- Whether a domain is authenticate or suspicious
	- Often attackers that create phishing sites use anonymous/sketchy providers
		- Registration date is new, hidden registrant information, and suspicious hosting

## [[Information Gathering - Web Edition#DNS|DNS (Domain Name System)]]
- Is what translates human-readable domain names like "google.com" into its public IP address
- Its made browsing internet much easier, but also has introduced a system that provides information and another security issue to deal with
	- DNS lookups return plenty of information
	- Any device relies on DNS resolution, which can be a target for attackers swapping the real IP with a malicious one
	- [[Information Gathering - Web Edition#Why DNS Matters for Web Recon|Why DNS Matters for Recon]]
- DNS Flow
	- Computer requests DNS query for "google.com"
		- If available in local cache of browser/OS/router then issue solved.
	- DNS Resolver is contacted
		- Checks its own cache if not performs Recursive Lookup
	- Root name server
		- Points at the TLD name servers that contain .com
	- TLD name server
		- Points at the google.com authoritative servers (ns1.google.com)
	- DNS Resolver returns the IP associated
	- Device connects
### [[Information Gathering - Web Edition#The Hosts File|Host File]]
- Allows you to manually resolve an domain to an IP
- Can be useful when hosting a local server on a private IP
- Why it matters: DNS Servers cant resolve private IPs. You wanted to avoid DNS resolving traffic. There's a LAN web-server you are targeting and want to feasibly access subdomains without specifying it in "Host" header every time.
### [[Information Gathering - Web Edition#Key DNS Concepts|Zone File]]
- The file in which it contains all subdomains of a given domain.
- Located in the authoritative name server of that domain (ns1.google.com)
- Defines plenty records such as
	- MX Record
	- NS Records
	- TXT Records
	- SOA Record
	- SRV record
	- A/AAAA Records
- @ stands for the main domain name
- A records give actual IP

### [[Information Gathering - Web Edition#The Domain Information Groper|The Domain Information Groper (Dig)]]
- Tool that lets you do DNS Queries on a domain or IP
- Can query specific records such as A, MX, NS, etc..
- Can specify the DNS Resolver to use.
	- Depending on the DNS server you choose, you can bypass certain stages of the DNS Resolver. For example, specifying the TLD name server, skips the root server check and straight to TLD step.
- dig google.com NS
- [[Information Gathering - Web Edition#Common dig Commands|Dig Commands Examples]]
### Dig information Output
- [[Information Gathering - Web Edition#Groping DNS|Full dig response on google.com]]
- Header states the type of query, status and flags for DNS query
- Question section shows what you asked for with dig (dig google.com A)
- Answer Section contains the answer to the query, this case IP for google.com
- Footer shows metadata such as time taken, msg size, time, and DNS server used

