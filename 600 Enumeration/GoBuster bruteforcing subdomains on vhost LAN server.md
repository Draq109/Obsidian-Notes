---
created: 2025-08-25T17:28
tags:
  - quick
  - "#selfnote"
  - "#insight"
  - recon
related: 
  - "[[DNS]]"
  - "[[Host File]]"
  - "[[Domain Name]]"
  - "[[DNS Query Process]]"
---
# Quick Note – GoBuster bruteforcing subdomains on vhost LAN server

When bruteforcing a web server thats operating with vhosts on LAN, gobuster only needs one manual resolution set (In most cases the domain name itself, *example.com*).  

Apart from the fact it **needs** a domain name to append to for it to try to enumerate subdomains, why is it that it does not require an IP resolve for any of those new subdomains its requesting(*admin.example.com, support.example.com*).

Thats where the vhost option comes into play. Since webservers that have vhost setup revolve completely around the *host* header, you can send numerous guesses to subdomains/domains by editing the *host* header.

Which is why when running gobuster with vhost it only requires you to resolve at least the main domain IP. It will then make all subdomain guesses with that same IP by just changing the *host* header.

If you try to visit a site gobuster just found you'll notice it will not resolve, you have to manually resolve the new subdomain (*admin.example.com*), gobuster does not do that for you.