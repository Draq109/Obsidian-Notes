---
created: 2025-08-19T16:21
tags:
  - quick
  - question
  - chatGPT
  - source
---
# Answer

## 🔑 What happens when a CA issues a TLS certificate

### 1. **Domain owner proves control**

- The site owner (or company) generates a **Certificate Signing Request (CSR)**.
    
    - Contains: their domain name(s), organization info (if EV/OV cert), and the **public key**.
        
    - Signed with their private key to prove they control that keypair.
        
- They submit this CSR to the Certificate Authority.
    
- CA validates ownership:
    
    - **Domain Validation (DV):** responding to an email, DNS TXT record, or HTTP file challenge.
        
    - **Organization Validation (OV) / Extended Validation (EV):** includes business documents, legal entity verification, etc.
        

---

### 2. **CA signs the certificate**

- Once verified, the CA takes the CSR and creates a **certificate** that includes:
    
    - The domain name(s) it’s valid for.
        
    - The subject public key (from the CSR).
        
    - Metadata (validity period, extensions, usage).
        
- The CA then **digitally signs** this certificate with its **private key** (either root or more commonly intermediate CA key).
    

---

### 3. **Distribution of the certificate**

- The CA gives the signed certificate back to the domain owner.
    
- The domain owner installs it on their server (usually along with the intermediate certificate so browsers can build the chain).
    

---

### 4. **Transparency and accountability**

- The CA submits the new certificate to **Certificate Transparency (CT) logs**.
    
    - This makes issuance visible and auditable (so if a malicious or mistaken cert is created, it can be caught).
        

---

### 5. **Client verification during TLS**

When a user connects to the site:

1. The server presents its certificate (and intermediates).
    
2. The client checks:
    
    - **Does the cert chain up to a trusted root CA in my system’s trust store?**
        
    - **Is the domain name in the certificate?** (CN/SAN check)
        
    - **Is the certificate valid (time, extensions, revocation)?**
        
3. If all checks pass → the cert is accepted, and the TLS handshake can proceed.
    

---

⚔️ **Why this matters for security/pentesting**

- If the CA is sloppy or compromised, attackers can get valid certs for domains they don’t own → enabling MITM attacks.
    
- CT logs are now a way to _spot unauthorized certificates_ issued for a target org (intel value).
    
- Weak or expired intermediates can break trust, and some servers misconfigure the chain, which you can exploit in testing.
    

---

Would you like me to also map this process into a **flow diagram (Obsidian-friendly)**? That way you can visually track CSR → CA → Cert → CT logs → Client verification.