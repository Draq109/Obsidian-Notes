---
created: 2025-08-14T18:16
source: "[[Information Gathering - Web Edition#Subdomains]]"
related:
  - "[[Domain Name]]"
  - "[[DNS]]"
  - "[[Host File]]"
  - "[[DNS Query Process]]"
  - "[[Zone File]]"
  - "[[Subdomain Enumeration]]"
  - "[[Subdomain Bruteforcing]]"
tags:
  - web
  - foundation
---
# Subdomains

## Summary
Are an extension of a [[Domain Name]], applied before it. They are used to separate different functions or extensions of a web app or website. Such as staging environments, login portals, or legacy apps. (*admin.example.com*)

## Details
- The subdomains are a great feature for keeping different sections organized.
- Used to give different sectors of a company their own environment.
	- finance department, HR, customer support, etc..
- Information for what subdomain are available are found in the [[Zone File]] or through[[Certificate Transparency (CT) Logs]]
- Fragments security since each subdomain will have different security measures in place.
- Subdomains can be nested, for example *dev1.admin.example.com* 

## Why It Matters
Subdomains help organize a company’s web presence but come with security tradeoffs. Fragmented environments can increase the attack surface, as forgotten or misconfigured subdomains may expose sensitive information. At the same time, separation limits the blast radius of an incident, allows custom security for each subdomain, and isolates development, staging, and production environments. Proper management is key — when handled well, subdomains improve security through compartmentalization, but poor management can create multiple weak points.
