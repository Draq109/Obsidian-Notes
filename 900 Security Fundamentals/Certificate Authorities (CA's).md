---
created: 2025-08-19T10:46
source: "[[Information Gathering - Web Edition#Certificate Transparency Logs]]"
related:
  - "[[SSL-TLS]]"
  - "[[TLS Handshake]]"
  - "[[Certificate Chain]]"
  - "[[Certificate Linking vs. Served Chains]]"
  - "[[Certificate Transparency (CT) Logs]]"
tags:
  - security
  - verification
  - trust
---

# Certificate Authorities (CAs) #review 

## Summary
A Certificate Authority (CA) is a trusted organization that issues digital certificates. The CA’s creates a certificate that shows a signature from the CA, which provides authenticity, and the information of the requester (info is provided from the CSR file sent by the requester). Browser clients can then verify through the [[Certificate Chain]] back to the trusted root CA that signed it.

## Details
- Certificates are signed by a CA using its private key; clients verify using the CA’s public key (already trusted in their root store of your browser).
- CAs validate domain ownership and sometimes organization details before issuing certificates.
- Verification normally happens locally using the certificate chain. CAs are only contacted for **revocation checks** (CRL, OCSP).
- Root CAs rarely sign end-entity certificates directly; they delegate to **intermediate CAs** for security and scalability.
- Modern CAs must log issued certificates into **Certificate Transparency (CT) logs** to allow public auditing and detection of mis-issuance.
- Subdomains can either be included in the main domains certificate or have their own designated certificate.

## Why It Matters
CAs are the cornerstone of trust in [[SSL-TLS]]. If a CA is compromised or issues certificates improperly, attackers can impersonate legitimate domains in man-in-the-middle attacks. For pentesters, analyzing certificate chains, CT logs, and revocation status can reveal misconfigurations, outdated CAs, or weak trust anchors.

## References
- [[2025-08-18 Information Gathering - Web Edition Session#Certificate Authorities (CAs)]]
