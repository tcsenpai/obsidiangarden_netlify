---
{"dg-publish":true,"permalink":"/bookmarks/tech/how-ssh-really-works/","tags":["interesting","internet","tutorial"]}
---


See the SSH cheatsheet: [[ssh\|ssh]]

## Summary

> [!NOTE]
>
> SSH (Secure Shell) is an essential protocol that secures remote connections over unsecured networks, making it a cornerstone of modern network security. In this video, we focus on SSH2, the version standardized by the Internet Engineering Task Force, which provides significant security improvements over its predecessor, including stronger encryption algorithms and enhanced authentication methods.
>
> ## Initial Connection and Handshake
>
> 1. **TCP Connection**: The SSH client begins by establishing a TCP connection with the server, typically over Port 22.
> 2. **Version Negotiation**: Both parties agree on which version of the SSH protocol to use for the session.
> 3. **Algorithm Negotiation**: They decide which cryptographic algorithms to use for tasks like key exchange, encryption, and integrity checking.
> 4. **Key Exchange**: The client and server generate ephemeral key pairs and exchange their public keys using the Elliptic Curve Diffie-Hellman method to create a shared secret key. This provides perfect forward secrecy, ensuring that even if keys are compromised in the future, past session data remains secure.
>
> ## Authentication
>
> 1. **Public Key Authentication**: The server checks the client's public key against its authorized key files (e.g., `~/.ssh/authorized_keys` on Unix systems).
> 2. **Challenge-Response**: If a matching key is found, the server encrypts a random number using the client's public key and sends it back to the client. The client decrypts this number using its private key, proving its identity.
> 3. **Password-Based Authentication (less secure)**: SSH also supports password-based authentication but is less secure compared to public key authentication.
>
> ## Establishing the Secure Session
>
> Once authenticated, an encrypted session is established using the shared secret key for symmetric encryption. All commands sent from the client to the server and their results are encrypted with this session key. This ensures that the data transmitted during the SSH session remains secure.
>
> ## Additional Features
>
> - **SSH Local Forwarding**: Tunnels other network services through the SSH connection, useful for accessing blocked services or adding a layer of security to encrypted protocols.
>
> If you enjoy learning about system design and trends in large-scale systems, consider subscribing to our newsletter at [blog.bybgo.com](http://blog.bybgo.com).

## Video

[[IMG-20241106232537880.mp4|Open: How SSH Really Works-rlMfRa7vfO8.mp4]]
![[IMG-20241106232537880.mp4]]
