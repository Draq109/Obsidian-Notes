---
created: 2025-08-25T17:38
source: "[[Information Gathering - Web Edition#Virtual Hosts]]"
related:
  - "[[DNS]]"
  - "[[Domain Name]]"
  - "[[Subdomains]]"
tags:
  - web
---
# Vhosts

## Summary
Its a feature used by web-servers, such as apache or nginx, to host various domains on a single IP. By only examining the **Host** header in an HTTP request, the server can identify and provide the correct content. 

## Details
- Vhosting is a great option for hosting multiple sites on one server
- It can be configured to identify by port or ip rather than the **Host** header, but are less common.
- Extremely common in apache or nginx frameworks; almost every shared hosting provider uses it.
- Wildcard vhosts or default catch-all configurations can reveal sensitive internal apps if accessed via unexpected hostnames.

## Why It Matters
- Compromising a vhost can potentially give access to **all domains hosted on that server**, making it a high-value target.
- Subdomain or vhost enumeration can uncover unlisted sites, internal tools, or forgotten portals.
- Misconfigurations, like overlapping vhosts or default vhost exposure, can allow attackers to bypass access controls or steal sensitive data.
- Attackers can exploit HTTP Host header-based logic in web apps (Host header attacks), including cache poisoning, SSRF, or password reset bypasses.

## References
- [[2025-08-15 Information Gathering - Web Edition Session]]
- 