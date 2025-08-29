---
created: 2025-08-18T08:56
source: "[[Information Gathering - Web Edition]]"
tags:
  - "#session"
  - status/inprogress
  - source/HTB
---
# Study Session – 2025-08-18

## Notes
### [SSL/TLS Secure Sockets Layer/Transport Layer Security](https://www.cloudflare.com/en-gb/learning/ssl/what-is-ssl/)
- Provides encryption to most everyday use web applications or sites
- Helps verify the [authenticity](https://www.cloudflare.com/en-gb/learning/ssl/transport-layer-security-tls/) of the server you are connecting to
	- When a browser verifies the certificate the site sent, it is in essence a chain of certificates that show the CA's that issued it, as well as its own.
- SSL is depreciated now, and TLS is now the standard
	- SSL name is still used since it stuck with the public, kinda like java in javascript
- Runs on top of TCP and important for HTTPS
- Before encryption, the initial phase involves establishing a connection through handshake.
	- What set of cipher and version of TLS will be used
	- Generating the session keys to be used, usually through the use of the servers public key
	- verifying the certificate, through digital signature

### Certificate Authorities (CA's)
- These are vetted/trustworthy orgs that provide the SSL/TLS certificates to the server domains.
	- Each subdomain can have its own SSL/TLS certificate, depending on the [type](https://www.cloudflare.com/en-gb/learning/ssl/what-is-ssl/#:~:text=What%20are%20the%20types%20of%20SSL) its using.
- CA's are not contacted everytime you wish to verify a certificate, instead it provides its own certificate to you.
- A CA will have a certificate of its own called root certificate.
	- This is what is stored in your OS/Browser
	- The design of it is almost like a binary tree, with each leaf nodes containing the domains/subdomain certficates of a site
	- Its used in a clever way to verify the identity of a servers SSL/TLS certificate.
		- Look at Merkle Tree structure for more info
- Whenever a CA authorizes a certificate to a domain it must submit multiple logs, specifically a Certificate Transparency log (CT log), open to anyone to inspect it.

### [[Information Gathering - Web Edition#Certificate Transparency Logs|Certificate Transparency (CT) Logs]]
- These logs serve as a registry to see whats been verified and by which CA
- Holds CA's accountable for any suspicious site that was vouched for
- Helps in identifying fraudulent sites quickly
	- Before a site doing damage, security researchers can prevent by constantly monitoring the logs.
- Plays a part in the verification process with the Signed Certificate Timestamp (SCT).
	- Its applied to the SSL/TLS certificate during creation of it.
	- Used by browser to check and verify with CT logs

### [[Information Gathering - Web Edition#The Merkle Tree Structure|The Merkle Tree Structure]]
- The structure used by SSL/TLS and CA certificates
- Encapsules the whole idea of how TLS can work and how validation/verification can be done
- The root node is always the main CA
- Intermediate nodes act like mini CA's
	- These are made to prevent the main CA authenticating directly
	- Allows flexibility, assigning the intermediate nodes specific domains only
		- CA 1 only for companies, CA 2 only for cloud hosting, etc..
	- If the CA gets compromised the root can revoke it without affect all others nodes
	- divide and conquer approach
- The leaf nodes are the domains that got issued a certification by the previous CA

### [[Information Gathering - Web Edition#CT Logs and Web Recon|Why it all matters]]
- Certificates are now daily used in any website visited today
- Knowing how to analyze these certificates can help in identifying malicious CA's installed on your device
- CT Logs are a great passive way to recon a domain and showing its subdomains
	- You aren't reliant on a wordlist, but instead the domains history
	- Might find subdomains associated with old/expired certificates

### [[Information Gathering - Web Edition#Fingerprinting|Fingerprinting]]
- Is for identifying the parts running a website or web application
- By identifying the software or hardware details we can gather possible attacking points
- Helps in building a profile of the target
### [[Information Gathering - Web Edition#Fingerprinting Techniques|Fingerprinting techniques]]
- Banner grabbing, these banners usually show web-server software, versions and other details
- HTTP headers show plenty of information show. e.g. redirection, software, data accepted, etc..
- Probing for specific responses, such as errors, can show what software or components its using
- The actual page content can contain copyright info, version, included packages, and the framework being used
- **Wafwoof** (Web Application Firewall)
- **cURL** can banner grab, you look at headers
- **nikto** extensive test that returns various info on software versions,insecure files/configs, and security risks.
- [[Information Gathering - Web Edition#Fingerprinting inlanefreight.com|Some tool examples]]


## Quick Tags & Links
<!-- Inline #tags and [[links]] for concepts you want to break out later -->
- 

## To Extract
<!-- List notes you know should become their own atomic note later -->
- [[Topic Example]] → atomic note
- [[Another Concept]]
