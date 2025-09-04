---
created: 2025-08-22T08:45
source: "[[Information Gathering - Web Edition]]"
tags:
  - "#session"
  - status/inprogress
---
# Study Session – 2025-08-22

## Notes
### [[Information Gathering - Web Edition#Crawling|Crawling]]
It refers to a spider crawling on a web, depending on the string and path taking where it leads. Visiting a normal site will have many redirections each going deeper and showing more internal/external links. Crawling tools automate this exploration collecting the information as it goes, mapping the whole structure of that web app, link wise. Crawling can not only extract links but also **comments**, **metadata**, and **sensitive files**.
Crawling can be done as
- **Breath-first crawling**: Explores each link recently discovered before going deeper
	- Means going back to root to explore more. 
- **Depth-first crawling**: Explores one link path until it reaches an end with no further links. (*rabbit hole*)
	- It goes back to root and starts the rabbit hole again.

### [[Information Gathering - Web Edition#robots.txt|robots.txt]]
- Text file locate in most web servers. As the name implies, its targeted at automated crawling bots
- This file usually contains info on what directories are and are not allowed to be crawled on.
- Not really used other than to set a crawl delay on specific bots like GoogleBot
- Used as a **honeypot** for malicious bots
- User-agent: Used to target specific platforms/OSs
- Disallow: /dir/ (Not allowed to crawl that path)
- Usually give a mapping of the site for bots to crawl better
- Example:
```txt
User-agent: *
Disallow: /admin/
Disallow: /private/
Allow: /public/

User-agent: Googlebot
Crawl-delay: 10

Sitemap: https://www.example.com/sitemap.xml
```

### [[Information Gathering - Web Edition#Well-Known URIs|Well-Known URIs]]
- These URIs are a default set of links that a web server provide that show configuration files, software version, protocols, and security mechanisms
- This completely optional and not all sites will provide this information
- Facebook has implemented this information
- Standard is set by the [RFC 8615](https://datatracker.ietf.org/doc/html/rfc8615)
- files such as **security.txt**, **openid-configuration**, and much more
- eg of uri, `https://example.com/.well-known/security.txt`.
- Useful for discovering endpoints or config details
- Why it matters? Can contain important details on versions, configs, and security implementations.

### [[Information Gathering - Web Edition#Web Recon and .well-known|openid-configuration]] #learn
- This well-known uri contains information on the authorization endpoint
- Where to send people to log in → “Go here to type your username and password.”
- Where to get the tokens → “After login, get this token from here to prove who you are.”
- Where to check user info → “If you need the person’s name or email, go here.”
- Where to get the keys → “Here’s the public key to make sure the token wasn’t faked.”
- Other rules → “These are the types of logins, tokens, and info I support.”
### Popular crawling tools
- Burp Suite Spider
- OWASP ZAP (Zed Attack Proxy)
- Scrapy
- Apache Nutch (Scalable Crawler)

### [[Information Gathering - Web Edition#Scrapy|Scrapy]]
- Scrapy is a well know versatile tool that can scrape the contents of pages or crawl to map the infrastructure
- scrapy requires you to create your own project. Within this project you will adjust and tweak it to your liking
	- They have some default templates to use but you will have to tweak it.
- scrapy by default visits pages, and you decide the parse logic
- Found on https://www.scrapy.org/, can be installed with pip
	- Recommended to use a virtual environment before installing to avoid future version conflicts down the line
#### [[Information Gathering - Web Edition#ReconSpider|ReconSpider.py]]
- HTB provides a python file named **ReconSpider.py**, which makes use of the scrapy library.
- When ran, it analyzes the specified domain site, http://inlanefreight.com, retrieves all urls, emails, external files, js files, and html comments.
- Outputs the result to "results.json"
