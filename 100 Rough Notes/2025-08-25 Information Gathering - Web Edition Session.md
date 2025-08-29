---
created: 2025-08-25T10:47
source: "[[Information Gathering - Web Edition]]"
tags:
  - "#session"
  - status/inprogress
  - source/HTB
---
# Study Session – 2025-08-25

## Notes

### [[Information Gathering - Web Edition#Search Engine Discovery|Search engine Discovery]]
- Using google or equivalent search engine to find information on a given target
- Also known as google dorking. Part of OSINT or Open source intelligence
- Important to learn how to query effectively with operators such as, site:, inurl:, filetype:, etc..
- [Google Dorking examples](https://www.exploit-db.com/google-hacking-database)
- Can uncover non listed login, files, or directories not listed on front of the page.

### [[Information Gathering - Web Edition#Web Archives|Web Archives]]
- Contains a historical view of a website over the years
- The most famous being the waybackmachine
- Uses crawling to gather the information, downloading all media, json, html, js files encountered.
- Valuable source of info can be discovered, such as forgotten sensitive data left up such as old web pages, directories, subdomains.
- Both previous methods do not interact directly with the site.

### [[Information Gathering - Web Edition#Automating Recon|Automating Recon]]
- DNS enumeration, CT logs, google dorking, web archives, WHOIS lookups, reverse dns lookups on IP for VH and HTTP headers all get automated with tools.
- Helps for efficiency and accuracy as opposed to manual.
	- Manual can still have its benefits for identifying unnoticed traits.
- Famous tools include FinalRecon, Recon-ng, theHarvester, SpiderFoot, OSINT Framework