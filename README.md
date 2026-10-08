# Cryptography & PKI Labs

## Project Overview

This repository documents a series of hands-on labs focused on **cryptography fundamentals** and **Public Key Infrastructure (PKI)**. Each lab explores a different aspect of securing data: symmetric encryption, asymmetric encryption, hashing, integrity verification, and digital certificates.

The goal is to demonstrate practical understanding of how cryptography protects data confidentiality, integrity, and authenticity.

---

## Labs Index

| # | Lab | Focus Area | Tools |
|---|-----|------------|-------|
| 01 | [Symmetric Encryption (AES)](01-symmetric-encryption-aes) | AES-256-CBC, key derivation, IV/salt | OpenSSL |
| 02 | [Asymmetric Encryption (RSA)](02-asymmetric-encryption-rsa) | Key pairs, public/private key exchange | OpenSSL, Python HTTP Server |
| 03 | [Hashing Algorithms](03-hashing-algorithms) | MD5, SHA-256, SHA-512, SHA3-256, RIPEMD-160, salting | OpenSSL |
| 04 | [Checksum Verification](04-checksum-verification) | File integrity verification (SHA-256) | sha256sum, GtkHash |
| 05 | [Self-Signed Certificate (IIS)](05-self-signed-certificate) | Certificate creation & HTTPS binding | IIS Manager |

---

## Skills Demonstrated

- Symmetric encryption with AES-256-CBC
- Key derivation using PBKDF2, salt, and IV
- Asymmetric encryption with RSA (2048-bit)
- Public/private key generation and exchange
- Hashing algorithms (MD5, SHA family, RIPEMD-160)
- Password hashing with salting
- File integrity verification via checksums
- Self-signed certificate creation and HTTPS binding
- Secure file transfer using Python HTTP server

---

## Tools Used

- OpenSSL
- sha256sum / GtkHash
- IIS Manager (Windows Server 2019)
- Python 3 (http.server)
- Linux

---

## Ethical Disclaimer

This repository documents my personal learning journey using standard, publicly available cryptographic tools. All analysis, commands, and observations are my own work, performed in isolated lab environments.
