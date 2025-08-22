---
created: 2025-08-18T19:14
source: "[[Information Gathering - Web Edition]]"
related: 
- "[[Deprecation of SSL]]" 
- "[[TLS Handshake]]"
- "[[Certificate Authorities (CA's)]]"

tags:
  - protocol
  - security
  - encryption
  - cryptography
---
# SSL-TLS

## Summary
Is an encryption protocol that runs on top of TCP to provide secure communication and verifies the authenticity of the server (and optionally the client).
## Details
- Is used in in every HTTPS 
- Uses asymmetric cryptography to establish session keys #review
- Verifies authenticity with [[Certificate Chain]]
- SSL is deprecated; TLS is the current standard, though “SSL” is still used due to name popularity.
- Cipher suites and TLS versions are negotiated during the [[TLS Handshake]]
## Why It Matters
Its the main source of protection for any HTTP plaintext from being visible to attackers. Knowing how to analyze SSL/TLS encryption is crucial for identifying fraudulent certificates, downgrade attacks, or broken encryption (outdated TLS). Making it critical for analysis.
## References
<!-- - This is a list of other notes, sites, or docs you cross-referenced to understand the concept better.
- Can be multiple, can be internal (`[[Other Note]]`) or external (`https://...`).
- It answers: “What else informed this note?”-->
- [[2025-08-18 Information Gathering - Web Edition Session#[SSL/TLS Secure Sockets Layer/Transport Layer Security](https //www.cloudflare.com/en-gb/learning/ssl/what-is-ssl/)|2025-08-18 Information Gathering - Web Edition Session]]
-  [Cloudflare SSL/TLS](https://www.cloudflare.com/en-gb/learning/ssl/what-is-ssl/#:~:text=What%20are%20the%20types%20of%20SSL)
