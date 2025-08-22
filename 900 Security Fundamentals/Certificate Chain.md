---
created: 2025-08-18T19:52
source: "[[Information Gathering - Web Edition#The Merkle Tree Structure]]"
related:
  - "[[SSL-TLS]]"
  - "[[Certificate Authorities (CA's)]]"
  - "[[Certificate Linking vs. Served Chains]]"
  - "[[TLS Handshake]]"
tags:
  - encryption
  - verification
  - security
---
# Certificate Chain (The Merkle Tree Structure)

## Summary
A certificate chain is a tree-like structure of TLS certificates that proves a server’s authenticity using cryptographic hashes, linking the server’s certificate to intermediate and root CAs.
## Details
- Crucial for authenticity and verification in [[SSL-TLS]].
- Root node is a trusted CA certificate, widely recognized by browsers and OSs.
	- DigiCert, Comodo, Sectigo, SSL.com
- Intermediate nodes connect the leaf (server) certificate to the root.
- Leaf nodes are certificates for domains/subdomains.
- Allows clients to verify certificates without contacting CAs in real time #review
- Anyone can validate a certificate by following the chain.
- To see how the chain is made see more in [[Certificate Linking vs. Served Chains]]

## Why It Matters
Certificate chains let clients efficiently verify server authenticity, ensuring secure communication and reducing the risk of impersonation attacks.
## References
<!-- - This is a list of other notes, sites, or docs you cross-referenced to understand the concept better.
- Can be multiple, can be internal (`[[Other Note]]`) or external (`https://...`).
- It answers: “What else informed this note?”-->
-  [[2025-08-18 Information Gathering - Web Edition Session#Information Gathering - Web Edition The Merkle Tree Structure The Merkle Tree Structure|Merkle Rough Notes]]