---
created: 2025-08-19T08:33
source: https://www.cloudflare.com/learning/ssl/what-happens-in-a-tls-handshake/
related: 
  - "[[SSL-TLS]]"
  - "[[Certificate Chain]]"
tags:
  - verification
  - encryption
  - protocol
  - keys
---
# TLS Handshake

## Summary
A negotiation process between client and server that establishes an encrypted channel. Both sides agree on the TLS version, cipher suite, and generate session keys. The client also verifies the server’s identity via its TLS certificate.

## Details
- Happens after the TCP connection is set up.
- Relies on Certificate Authorities (CAs) to validate the server’s certificate.
- Main steps (simplified modern ECDHE flow): #review
  - **ClientHello:** Client proposes TLS version, cipher suites, and sends a random value.
  - **ServerHello:** Server chooses version/cipher, sends its certificate (with public key + chain), and sends its own random value & ephemeral key.
  - **Certificate Validation:** Client verifies the server’s certificate against trusted CAs.
	  - This is the main validation point, you use your CA's keys to verify the servers TLS certificate. This is the digital fingerprint part.
  - **Key Exchange:** Both sides use the ephemeral keys to derive the shared session key.
  - **ChangeCipherSpec/Finished:** Both acknowledge, then switch to encrypted communication.
- End result: a secure symmetric session key is established for fast, encrypted data transfer.
- Depeding on the TLS variant, the establishment of keys will be different. See RSA or ECDHE (Diffie-Hellman variant) for more information.

## Why It Matters
- Weak TLS versions or ciphers (e.g., SSLv3, TLS 1.0, RSA key exchange) are exploitable.
- As a pentester, analyzing the handshake helps detect downgrade attacks, weak ciphers, or misconfigured certificates.
- Tools like `openssl s_client` or Wireshark can capture and analyze handshakes in practice.

## References
- [[SSL-TLS]]
- [[Certificate Chain]]
- [Cloudflare: What happens in a TLS handshake?](https://www.cloudflare.com/learning/ssl/what-happens-in-a-tls-handshake/)
