# AES Encryption & Decryption Tool

A beautiful, modern, and secure AES encryption/decryption web app built with pure HTML, CSS, and JavaScript. Instantly encrypt or decrypt any text using AES-128 in CBC mode with a custom secret key.

![AES Encryption & Decryption Tool Banner](image.png) 

## How It Works
- **Encryption**: Your text is encrypted using AES-128-CBC with a 16-byte random IV. The IV is prepended to the ciphertext and the entire thing is Base64-encoded for easy copying.
- **Decryption**: The Base64 string is decoded, the first 16 bytes are used as IV, the rest as ciphertext, and decrypted with the same derived key.
- **Key Handling**: Your secret key (any length) is hashed with SHA-256, and the first 32 hex characters (128 bits) are used as the AES key.

## Features
- **Instant Encryption & Decryption** — Real-time processing as soon as you click the button
- **AES-128 CBC Mode** — Secure encryption using PKCS7 padding and random IV (IV is prepended to ciphertext)
- **Toggle Password Visibility** — Eye icon to show/hide your secret key
- **Responsive Layout** — Looks great and works perfectly on desktop, tablet, and mobile devices
- **Success/Error Notifications** — Toast messages with optional vibration feedback on mobile
- **No Backend Required** — Everything runs client-side in the browser
- **Modern Dark Design** — Pink-to-magenta gradients, floating animated backgrounds, and parallax effects

## Libraries Used
- [**CryptoJS**](https://github.com/brix/crypto-js) – Industry-standard AES implementation in JavaScript (loaded via CDN)
- [**Font Awesome**](https://fontawesome.com) – Icons for password visibility toggle and lock branding

All dependencies are loaded via CDN – no build tools or installation required.

## Default Secret Key
For quick testing, the tool comes pre-filled with the secret key `lorainecastro-secretKey`. Feel free to change it to anything you like.

## Security Notes
- **Client-Side Only**: All encryption and decryption happen entirely in your browser. Your text, secret key, and results never leave your device or get sent to any server.
- **Random IV per Encryption**: A unique, cryptographically random 16-byte Initialization Vector (IV) is generated for every encryption and automatically prepended to the ciphertext. This follows AES-CBC best practices and prevents identical plaintexts from producing identical ciphertexts.
- **Key Derivation**: Your secret key (passphrase) is strengthened by hashing it with SHA-256 before use, providing consistent 128-bit key strength regardless of input length.
- **Recommendations**:
  - Always use a strong, unique, and unpredictable secret key/phrase in real-world applications.
  - Treat encrypted output as sensitive if the key is reusable—anyone with the key can decrypt it.
  - For maximum security in production systems, consider authenticated encryption modes (e.g., AES-GCM) or professionally audited libraries.
- **Limitations**: This is a client-side educational/demo tool. It is secure for casual use but not a replacement for server-side encryption or compliance-grade solutions (e.g., GDPR, HIPAA).