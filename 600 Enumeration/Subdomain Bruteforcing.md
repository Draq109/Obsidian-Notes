---
created: 2025-08-28T15:53
source: "[[Information Gathering - Web Edition#Subdomain Bruteforcing]]"
related:
  - "[[Subdomains]]"
  - "[[DNS]]"
  - "[[Active Reconnaissance]]"
  - "[[Vhosts]]"
tags:
  - web
  - recon
---
# Subdomain Bruteforcing

## Summary
Bruteforcing subdomains involves guessing for subdomains using a wordlist. Simply, you substitute a subdomain for a word in your list then try to reach it with either a browser or DNS request. From a practical perspective, one might wonder *why*  we wouldn’t always do it; however, it comes with both advantages and disadvantages.

## Details
- Bruteforcing is done with tools such as gobuster or fnff which can iterate and request at a higher rate than manually.
- Can clear various possible subdomains within seconds, in exchange for stealth/anonymity
- This activity is very likely to triggers red flags and alarms for the target.
- Bruteforcing can be done directly to the web server or towards the name server
	- In some cases the name server is hosted by a third party.
- DNS bruteforcing tends to be stealthier especially if the name server is not owned by the target

## Why It Matters
Bruteforcing is a great way for pen testers to try to gather as many possible paths to attack. It broadens up the attack zone and can be a gold mine for admin portals, config, or sensitive documents. Great when allowed to be loud or ran out of resources to gather information passively.

## References
[[2025-08-15 Information Gathering - Web Edition Session]]
