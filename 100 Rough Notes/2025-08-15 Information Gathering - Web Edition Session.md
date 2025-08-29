---
created: 2025-08-15T08:54:00
source: "[[Information Gathering - Web Edition]]"
tags:
  - "#session"
  - status/inprogress
  - source/HTB
---
# Study Session – 2025-08-15
## Focus Topics
- Subdomains
- DNS Zone Transfers
- Subdomain Bruteforcing
- Virtual Hosts

## Notes
### [[Information Gathering - Web Edition#Subdomains|Subdomains]]
- Its the first section of a URL link, www in www.example.com
- This extension offers a way to divide different services or sections
- Used often by companies for testing and feature environments
- mail, ftp, ns1, features, etc..
- Represented with an A or AAAA record in zones files
### Vulnerability of subdomain
- Subdomains can be security issue due to less attention to it or forgotten
	- hidden login portals, old legacy sites, sensitive information
- If old DNS records are still active, attackers can see subdomains that companies dont even know about due to migration changes, negligence, or new management. 
### [[Information Gathering - Web Edition#Subdomain Enumeration|Subdomain Enumeration]]
- Process of gathering as many subdomains from the DNS query as possible
- Two types of enumeration
	- Active
		- Much noisier, and will alert the target
		- Automated tools often used for this are gobuster, fnff
	- Passive
		- Stealthy, and goes under radar
		- Use of external resources such as Certificate Transparency (CT) logs or search engines such as google or duckduckgo.

### [[Information Gathering - Web Edition#Subdomain Bruteforcing|Subdomain Bruteforcing]]
- Brute forcing in the same way such as [[HTTP bruteforce]], but now we will be doing a DNS Lookup.
- Often used is a tool in which you provide a wordlist, the name server, the domain and any flag options.
- The tool then appends each word to the domain, acting as a subdomain, until we get back successful responses.
	- SOA response means N/A
	- Why it matters - A response means it has or had an active IP. (Gotta visit the site to see if active)
- DNSEnum,gobuster, fnff, fierce, dnsrecon, amass, puredns

### [[Information Gathering - Web Edition#DNSEnum|DNSEnum]]
- Bruteforce tool
- dnsenum --enum domain -f /.../seclist/wordlist.txt -r
	- -r runs a dns lookup on any valid subdomain, to see if its part of another name server (More information)

### [[Information Gathering - Web Edition#DNS Zone Transfers|DNS Zone Transfers]]
- A method of transferring a zone file from one server to another (ns1,ns2)
- This is done with the AXFR record using dig
- The flow of transfer
	- Zone Transfer Request
	- SOA Record Transfer (Verification happens as well)
	- DNS Records Transmission (Sending the records one by one)
	- Zone transfer complete (Through some packet of FIN)
	- Acknowledgement ACK
- This used to and can be a vulnerability if misconfigured
	- Why: because anyone could access the entire records of a domain, giving an attacker a starting infrastructure.
	- In early days this request was permitted to almost anyone, but now theres verification first.
#### Exploiting Zone Transfers (axfr)
- Not really an exploit more like using the axfr command
- Only works by directly querying the name server with '@'
	- dig axfr @nsztm1.digi.ninja zonetransfer.me
	- Returns back a full zone file listing a domain and its subdomains

## [[Information Gathering - Web Edition#Virtual Hosts|Virtual Hosts]]
- Is a configuration done by web servers to manage and host multiple domains/subdomains
- The main method used to select the appropriate domain content is through the "Host" header from an HTTP Request.
- Domains that are public and in the dns records are easy to access through a DNS query 

### [[Information Gathering - Web Edition#How Virtual Hosts Work Understanding VHosts and Subdomains|Accessing LAN domains on a VHost Web Server]]
- Often times there are domains that only resolve within the servers LAN
- These are often visible through that company or clients DNS Server
- These domains are hosted on private IPs, and obtaining info on them through public DNS query is not possible
- If theres a web server hosting multiple domains locally, you have to manually resolve it or direct those IPs for resolving by the LAN DNS server
	- Usually visiting an IP should redirect to an HTTP(S) site, but due to VHosting this will not work. Such as with Apache or Ngnix
- The trick is finding out the the domains a local web server is hosting.
	- Why this matters - Theres often important portals left to admins or employees. Unsupervised/unsecure links with various info.
	- How to obtain? Either querying the LAN DNS server, Brute forcing subdomains, or using passive subdomain enum.
- [[Information Gathering - Web Edition#Server VHost Lookup|VHost Lookup Flow]]

### [[Information Gathering - Web Edition#Types of Virtual Hosting|Types of Virtual Hosting]]
-  Name-based VHosting: This typically refers to web-servers using the Host header from a HTTP request to identify what site to visit.
	- This is the most common and has been the one referred in previous sections
- IP-Based VHosting: Assigns different IPs to each website hosted on the server. Requires  multiple IPs to lease to given hosts. Expensive and not scalable
- Port-Based VHosting: As the name implies uses ports to distinguish what site to provide, so users uses port 80 -> example.com, 545 -> ready.com. Not used often due to not being client friendly. Requiring users to specify the port. 

### Virtual Host Discovery Tools
- Tools used to brute force the virtual hosts of a webserver
- Fetches any possible url domains it can find
- Requires having the domain name discovered, at least for subdomains

### [[Information Gathering - Web Edition#gobuster|Targetting VHosts with gobuster]]
- Preconditions
	- Must have the public or private IP of the web server
	- Have at least one domain if trying to figure out subdomains
		- You could try to guess the domain names its hosting, but much harder
	- Have a substantial wordlist that will act as subdomains
- e.g. command 
``` shell
gobuster vhost -u http://inlanefreight.htb:81 -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-110000.txt --append-domain
```
- -u for URL, -w is our wordlist, and --append-domain is required for subdomain fuzzing



## Quick Tags & Links
<!-- Inline #tags and [[links]] for concepts you want to break out later -->
- 

## To Extract
<!-- List notes you know should become their own atomic note later -->
- [[Subdomains]]
- [[DNS Zone Transfers]]
- [[Virtual Hosts]]
- [[Subdomain Enumeration]]
- [[Certificate Transparency]]
- [[Subdomain Bruteforcing]]
- [[Server Vhost Lookup]]