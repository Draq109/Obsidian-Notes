---
created: 2025-08-19T21:35
source: "[[ChatGPT - What happens when CA issues certificates]]"
related:
  - "[[SSL-TLS]]"
  - "[[Certificate Chain]]"
  - "[[TLS Handshake]]"
  - "[[Certificate Authorities (CA's)]]"
tags:
  - security
  - verification
  - chatGPT
---
# Certificate Linking vs. Served Chains #review 

## Summary
Certificates are linked at creation by the **issuer field** (who signed it), but the **full validation chain** only works when the server provides the intermediate certificates alongside its leaf (domain) certificate.  
So the org that wants a TLS certificate sends their CSR (Certificate Signing Request), which contains their domain name, org info, and public key. The CA then signs it for them, creating that link between them. BUT that does not naturally make a tree like structure only that link.

## Details
- **Natural Link (Issuer → Subject)**
  - When a CA signs a certificate, it embeds itself as the “issuer.”
  - This creates the natural link between your certificate and the CA’s certificate.
  - Example: `example.com` cert → Issuer: “Intermediate CA #3.”

- **Served Chain (Complete Validation Path)**
  - Your certificate alone isn’t enough — the server must provide:
    1. The leaf/domain certificate.
    2. Any intermediate CA certificates.
  - Browsers/clients walk the chain until they reach a trusted root in their local trust store.

- **Common Issue**
  - If intermediates aren’t served, clients fail with errors like:
    - *“unable to get local issuer certificate.”*
  - Even valid certificates can look “untrusted” if the chain isn’t properly delivered.

## Why It Matters
- Proper chain delivery is essential for browser trust.  
- Misconfigured or incomplete chains are a common source of TLS errors.  
- For security testing, broken chains can reveal weak setups, outdated intermediates, or mismanagement of trust.  

