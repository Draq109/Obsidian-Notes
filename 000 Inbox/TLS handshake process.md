---
created: 2025-08-22T16:53
tags:
  - quick
  - video
source: https://youtu.be/25_ftpJ-2ME?si=XzqVU_Z1yVr4B_M4
---
# Quick Note – TLS handshake process
The main objective for a TLS handshake is to establish safe communications between two clients by using symmetric encryption or pair of session keys. There are three steps that must be fulfilled that are Confidentiality, Integrity, and Authentication or CIA. 

Once both clients have established the shared key, we then use M.A.C (Hashing) to rewrite our text in our message. This is part of the Integrity step. The concept for hashing is sending your original message, plus a hashed version of your message.  Now the receiver can confirm the message matches what was sent by rehashing the message and comparing it with the sent hash.

Hashing alone is not enough since the message could be intercepted and changed, with the attacker filling the content to his liking.

With the addition of a symmetric key + hashing the sending party can hash the message + encrypt it. This prevents anyone from swapping the content, and we also verify the hashed content was not tampered/modified with by verifying the raw hash values.

The difficulty is getting the keys to both clients safely over the network. To achieve this, a process called asymmetric encryption is used, where each party uses a pair of keys to encrypt or decrypt. Usually called public key and private key. The public key is used by others to confidently reach you. The private key will not be known by anyone but that person, and will decrypt all public key encryptions.

The CIA concept takes place again from scratch when dealing with asymmetric keys, but concepts are the same as symmetric.