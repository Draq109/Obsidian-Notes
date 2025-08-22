---
created: 2025-08-19T19:11
tags:
  - quick
  - idea
  - chatGPT
  - cryptography
  - encryption
  - security
---
# Quick Note – Asymmetric Keys

Idea:   
If I use your public key to encrypt
- Only your private key can decrypt.
- Guarantees confidentiality (only you can read it).

If I use my private key to encrypt (or sign a hash)
- Anyone with my public key can check/decrypt it.
- Guarantees authenticity (it had to come from me, since only I have my private key).
TLDR
- **Public → Private** path = confidentiality.
- **Private → Public** path = authenticity.

Extra: Use hash to compress size
1. Hash the message.
2. Encrypt the hash with the private key (this is the _digital signature_).
3. Send (message + signature).
#### 4. Receiver uses the public key to check the signature matches the message’s hash.
Boom — authenticity without massive overhead.

This is how [[Certificate Authorities (CA's)]] give domains that are requesting certificates a certificate with their signature on it.

The domain that wants a TLS certificate, first makes their asymmetric keys. Then proceed to make a CSR (Certificate Signing Request) file with the keys they just made using openssl. This makes the csr file, 'server.csr'. Which contains their public key, identity info (domain, company name, country), and signature with their private key (Giving it [[#4. Receiver uses the public key to check the signature matches the message’s hash.|Authenticity]], its really the domain owner). This file shows they want a request, and is now ready to be sent to a CA.

The domain's CSR file is sent to a CA. The CA then verifies the authenticity, and if everything is good will generate the certificate, .crt. It hashes all the owners identity fields then encrypts it with their private key, giving it the CA's digital signature. This then is used later by users who have CA's public keys to see the hash. (*Your browsers set of CA public keys ready to unencrypt private key signatures*)

The certificate now contains an encrypted (by a CA private key) hash of the domains identity fields. The browser can then decrypt (with the CA public key) and unhash to show the certificates fields. 

Furthermore, it rehashes the contents and sees both hash values match to confirm integrity (Was not modified or altered in any shape or form. Thats the main purpose of hash).
Why not just send hash alone?: can be modified if intercepted by hacker, thats the reason for encryption. 
But anyone can decrypt the message then insert an altered/malicious hash message?:Yes but theres no way to encrypt it now since they would need the CA's private key. It would then be obvious that its not legit. A message anyone can see but no one can alter/recompose + hash = authenticity and integrity

So to summarize:

- **CSR** = your unsigned request + proof you own the private key.
    
- **CA** takes the CSR info, builds a certificate, and signs the certificate’s contents (not the CSR file).
    
- The signature = `Encrypt(Hash(certificate_data))` with CA’s private key.


Context: During [TLS Handshake Deep Dive and decryption with Wireshark](https://www.youtube.com/watch?v=25_ftpJ-2ME)
