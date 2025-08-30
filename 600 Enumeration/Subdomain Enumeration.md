---
created: 2025-08-28T11:19
source: "[[Information Gathering - Web Edition#Subdomains]]"
related:
  - "[[DNS]]"
  - "[[Domain Information Groper (DIG)]]"
  - "[[Subdomains]]"
  - "[[Vhosts]]"
  - "[[Zone File]]"
tags:
  - recon
  - enumeration
---
# Subdomain Enumeration

## Summary
Is the idea of listing and gathering as many possible subdomains from a given domain. Done by either active or passive methods. With the majority of the work being automated by tools. Dependent on what approach taken, will decide the yielded results.

## Details
#### Active Enumeration
Involves directly targeting the target domain, with tools such as gobuster or fnff. Usually through the process of brute forcing or crawling. Other methods involve querying the name server directly for records, possibility for zone transfer (AXFR). This approach is exposing who you are to the targeted web server, giving the target warnings/time to fully secure or hardened their security. 

#### Passive Enumeration
As the name suggests, the approach taken is more passive in that we dont engage with the target directly. Using [[Certificate Transparency (CT) Logs]] to list subdomain certificates, wayback machine to visit old versions of the site, [[WHOIS]], google dorking, [[Domain Information Groper (DIG)|Dig]], etc.. None of these actions will make your presence know to the web server/target.


## Why It Matters
When pen testing you are often limited or in a constraining environment. With companies allowing you to probe part of their infrastructure or with a probe threshold. Other times you will be tasked with being under the radar. Knowing which approach and methods is important not only for the goal but for the companies specified rules. 

You lose nothing for trying to passively gain information, while also allowing you to gather enough to do a complete overhaul of the target without a sense of urgency due to no alertness. As opposed to active, giving you set amount of time before the target notices.

## References
- [[2025-08-15 Information Gathering - Web Edition Session]]
