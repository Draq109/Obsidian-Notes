---
created: 2025-08-19T20:35:00
source:
  - ChatGPT
related:
  - "[[SSL-TLS]]"
  - "[[TLS Handshake]]"
  - "[[Certificate Authorities (CA's)]]"
  - "[[Certificate Chain]]"
  - "[[Certificate Linking vs. Served Chains]]"
tags:
  - verification
  - encryption
  - cryptography
  - hashes
  - security
  - chatGPT
  - advanced
---
# Certificate Signature Verification (X.509) #review 

## Summary
(The issuer being the CA)
When a client verifies a certificate, it proves that the cert was signed by its issuer’s private key and that the chain terminates at a trusted root. It hashes the certificate’s “to-be-signed” section and checks the issuer’s signature with the issuer’s **public key**, repeating this for each hop up to a trusted root CA.

## Details
**What’s being verified (per certificate)**
- **TBSCertificate**: the exact bytes of the certificate content that were signed.
- **Signature Algorithm**: e.g., RSA-PKCS#1 v1.5/PSS or ECDSA with SHA-256.
- **Signature Value**: the bytes produced by the issuer using its private key.
- **Issuer Public Key**: taken from the *issuer’s certificate* (next link in chain).

**Step-by-step (per link in the chain)**
1. **Parse** the certificate and extract its **TBSCertificate**, **signature algorithm**, and **signature value**.  
2. **Hash** the TBSCertificate with the algorithm specified (e.g., SHA-256).  
3. **Verify signature** using the issuer’s public key from the issuer cert:  
   - *RSA*: check the signature (PKCS#1 v1.5 or PSS) unwraps to the expected hash.  
   - *ECDSA*: verify the `(r, s)` pair against the hash using the issuer’s public key.  
4. **Enforce certificate policies** on the issuer cert:  
   - `basicConstraints` must allow CA = TRUE for signing other certs.  
   - `keyUsage` must include **keyCertSign**.  
   - (Optional) `nameConstraints` and other path constraints must be satisfied.  
5. **Repeat** for the issuer certificate, using *its* issuer, until reaching a **trust anchor** (root).

**Whole-chain validation (context)**
- **Path building**: the client assembles a chain from the leaf to a root it trusts (may use served intermediates and, if allowed, AIA fetching).  
- **Trust anchor**: the chain must end at a root CA in the client’s OS/browser trust store (the root is *trusted by configuration*, not because its self-signature is “proven”).  
- **Additional checks** commonly performed alongside signature verification:  
  - **Time validity**: `NotBefore`/`NotAfter` for every cert in path.  
  - **Hostname match**: leaf’s SAN/CN must match the requested domain.  
  - **Revocation**: CRL/OCSP (optionally OCSP stapling) indicates the cert isn’t revoked.  
  - **Algorithm strength/policy**: reject weak hashes (e.g., SHA-1) or small keys per policy.  
  - **Complete served chain**: intermediates must be presented correctly by the server.

**Result**  
If every signature verifies, policies/constraints pass, the hostname and time are valid, revocation checks pass, and the path ends at a trusted root → the chain is accepted and the connection can proceed using the negotiated session keys.

## Why It Matters
This process is what prevents forged or tampered certificates from being trusted. Knowing the exact verification steps helps you spot misconfigurations (missing intermediates, wrong key usages), weak policies (SHA-1, small keys), and trust problems (untrusted roots, revoked certs) during assessments.

## References
- [[Certificate Chain]]
- [[Certificate Authorities (CAs)]]
- [[TLS Handshake]]
- RFC 5280 (X.509 PKI Certificate and CRL Profile)
- Cloudflare Learning: “What happens in a TLS handshake?”
