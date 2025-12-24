# AES Encryption & Decryption Tool

A beautiful, modern, and secure AES encryption/decryption web app built with pure HTML, CSS, and JavaScript. Instantly encrypt or decrypt any text using AES-128 in CBC mode with a custom secret key.

![AES Encryption & Decryption Tool Banner](image.png) 

## How It Works
- **Encryption**: Your text is encrypted using AES-128-CBC with a 16-byte random IV. The IV is prepended to the ciphertext and the entire thing is Base64-encoded for easy copying.
- **Decryption**: The Base64 string is decoded, the first 16 bytes are used as IV, the rest as ciphertext, and decrypted with the same derived key.
- **Key Handling**: Your secret key (any length) is hashed with SHA-256, and the first 32 hex characters (128 bits) are used as the AES key.