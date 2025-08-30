---
created: 2025-08-29T10:11
source: "[[Information Gathering - Web Edition#Fingerprinting]]"
related: 
  - "[[Active Reconnaissance]]"
  - "[[Passive Reconnaissance]]"
tags:
  - recon
  - web
  - advanced
  - "#identity"
---
# Fingerprinting

## Summary
Is the process of capturing various sources of information to determine the identity of the person, place, or thing. In the cyber field its often associated with capturing software versions, frameworks, HTTP headers, banners, hardware, language, etc. It helps in identifying not only the software but also the OS of the system. 

## Details
- Various tools and methods can be used to capture information, such as curl or nikto
- cURL easily does banner grabbing, which contain plentiful information such as `Server:` or `X-Redirect-By:`
	- It also captures the full page content (HTML/JS/CSS), which often shows the framework and version being used for the web application
- nmap port scans and scripts that identify versions of the software being run.
- Probing for specific errors can help insinuate the software.

## Why It Matters
Fingerprinting can identify possible misconfigurations or vulnerabilities of the system. It helps in profiling the target and seeing potential attacking points on it. Fingerprinting can be gained in any form of connection being made, and its a valuable concept for reconnaissance. 

## References
[[2025-08-18 Information Gathering - Web Edition Session]]
