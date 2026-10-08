# Lab 01: Symmetric Encryption with AES

## Overview

In this lab, I explored **symmetric encryption** using the **AES-256-CBC** algorithm via **OpenSSL**. The goal was to understand how a single shared key is used for both encryption and decryption, and how supporting mechanisms like salt, IV, and PBKDF2 strengthen the encryption process.

---

## Lab Environment

- **Operating System:** Ubuntu Linux
- **Tool:** OpenSSL
- **File Used:** A confidential text file

---

## Background Concepts

### What is Symmetric Encryption?

Symmetric encryption uses a **single secret key** for both encryption and decryption. It is fast and efficient, making it ideal for encrypting large amounts of data.

Common symmetric algorithms include:
- **AES** (Advanced Encryption Standard)
- **DES** (Data Encryption Standard – deprecated)
- **3DES** (Triple DES – legacy)

### What is AES-256-CBC?

- **AES:** A symmetric encryption standard established by NIST in 2001.
- **256:** Refers to the key size in bits (AES supports 128, 192, and 256).
- **CBC (Cipher Block Chaining):** A mode of operation where each block of plaintext is XORed with the previous ciphertext block before encryption.

### Supporting Mechanisms

| Mechanism | Purpose |
|-----------|---------|
| **Salt** | A random value added to strengthen the key derivation process |
| **IV (Initialization Vector)** | Ensures unique ciphertext even when encrypting identical data |
| **PBKDF2** | A key derivation function that strengthens the encryption key based on a password |

---

## Lab Objectives

1. Understand how symmetric encryption works.
2. Encrypt a text file using AES-256-CBC.
3. Decrypt the file and verify its contents.

---

## Methodology

### Step 1: Verify OpenSSL Installation

Checked that OpenSSL was installed and available on the system.

### Step 2: Review Available Ciphers

Listed the supported ciphers to confirm that AES-256-CBC was available.

### Step 3: Encrypt the Text File

Used OpenSSL to encrypt the confidential text file with AES-256-CBC and PBKDF2:

```text
openssl enc -aes-256-cbc -pbkdf2 -p -in confidential-data.txt -out encrypted_file.enc
```

Command breakdown:

Flag Meaning
-aes-256-cbc Specifies the encryption algorithm
-pbkdf2 Uses PBKDF2 for stronger key derivation
-p Prints the key, salt, and IV used
-in Specifies the input file
-out Specifies the output file

I was prompted for a password, which was used to derive the actual encryption key.

Step 4: Verify Encryption

Attempted to view the encrypted file:

```text
cat encrypted_file.enc
```

The output was unreadable, confirming that the data was successfully encrypted.

Step 5: Decrypt the File

Used OpenSSL to decrypt the file back to plaintext:

```text
openssl enc -d -aes-256-cbc -pbkdf2 -p -in encrypted_file.enc -out decrypted_file.txt
```

Key difference: The -d flag specifies decryption.

I entered the same password used during encryption, and the file was successfully decrypted.

Step 6: Verify Decryption

Compared the decrypted file with the original:

```text
cat decrypted_file.txt
```

The contents matched the original file, confirming that encryption and decryption worked correctly.

---

Key Observations

· The salt and IV are randomly generated each time, so encrypting the same file twice produces different ciphertext.
· The password is not the encryption key itself — it is used to derive the key via PBKDF2.
· Without the correct password, the data cannot be decrypted.
· The -p flag is helpful for learning, but in production, printing the key and IV is a security risk.

---

Screenshots

(Add your screenshots here — e.g., encryption command, encrypted file content, decryption command, decrypted file content.)

---

Lessons Learned

· Symmetric encryption is fast and efficient but requires secure key exchange.
· Salt, IV, and PBKDF2 are essential for strengthening password-based encryption.
· OpenSSL is a powerful and flexible tool for cryptographic operations.
· Proper key management is critical — losing the password means losing the data.

---

Tools Used

· OpenSSL
· Linux
· Terminal