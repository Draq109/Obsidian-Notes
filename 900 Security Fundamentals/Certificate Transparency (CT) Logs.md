---
created: 2025-08-19T12:52
source: "[[Information Gathering - Web Edition#Certificate Transparency Logs]]"
related:
  - "[[Certificate Chain]]"
  - "[[SSL-TLS]]"
  - "[[Certificate Authorities (CA's)]]"
tags:
  - networking
  - security
---
# Certificate Transparency (CT) Logs

## Summary
CT logs are documented information about created certificates. Specifically, whenever a public trusted organization (DigiCert, Sectigo, Comodo) creates a new certificate for a domain owner. It helps in keeping a track record on the [[Certificate Authorities (CA's)]] and also the domain's. 

## Details
- Often the logs will show the same domain receiving constant certifcates for its domain. Often due to certificate expiration dates.
	- Other reasons include, replacements, revocations, or constant updating from owner.
- If theres bad case where a certificate was approved to a malicious domain, we can trace back the CA creator.
	- This helps keep CA's in check and also identify compromised certificates.
- Theres a timestamp associated with the log, Signed Certificate Timestamp or SCT. Sometimes used in the verification process of a certificate.
- Theres multiple organizations that host CT logs in case one of those providers goes down.
- Subdomains will appear in CT log searches due to the nature of a certificate covering multiple domains/subdomains, for better or worse.
	- Search tools like crt.sh will automatically show subdomains for a given domain search.

## Why It Matters
This is a great infastructure to have, it keeps CA accountable for their authorizations, helps security analyst identify fraudulent certifcates earlier, and gives a wealth of information of a domains history. From a pen test view, we can identify possible subdomains for a domain without interacting with the target and in a passive manner. 

## References
- [[2025-08-18 Information Gathering - Web Edition Session#Information Gathering - Web Edition Certificate Transparency Logs Certificate Transparency (CT) Logs|2025-08-18 Information Gathering - Web Edition Session]]
