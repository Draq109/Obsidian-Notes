---
created: 2025-08-21T13:46
source: "[[Information Gathering - Web Edition#Active Reconnaissance]]"
related: 
  - "[[WHOIS]]"
  - "[[Passive Reconnaissance]]"
tags:
  - recon
---
# Active Reconnaissance

## Summary
Active reconnaissance involves directly interacting with a target to gather information. It is a more aggressive approach that may be detected by security systems, but it provides detailed and accurate data about the target’s infrastructure and vulnerabilities.  

## Details
- **Vulnerability scanning:** Use tools like `nmap` or `OpenVAS` to identify exploitable weaknesses.  
- **Tracerouting:** Map the network path between you and the target to identify routers and intermediate systems.  
- **Banner grabbing:** Extract service information from open ports to identify software versions.  
- **OS Detection:** Determine the operating system running on target machines using fingerprinting techniques.  
- **Service and version enumeration:** Identify running services and their versions.  
- **Web Spidering:** Crawl websites to discover hidden pages, endpoints, and structure.

## Why It Matters
- Provides precise information for exploitation, penetration testing, and vulnerability assessments.  
- Helps understand the target’s network layout, operating systems, and running services.  
- Supports planning of subsequent attack phases with accurate data.  

## References
- [[2025-08-14 Information Gathering - Web Edition Session#Information Gathering - Web Edition Active Reconnaissance Active Reconnaissance|2025-08-14 Information Gathering - Web Edition Session]]  
- [Nmap Official Documentation](https://nmap.org/book/man.html)  
- [OWASP Reconnaissance Guide](https://owasp.org/www-community/Reconnaissance)  
