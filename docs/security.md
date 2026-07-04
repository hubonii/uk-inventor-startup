# Security Architecture

## 1. Physical & Digital Chain of Custody
The core security primitive of the platform is proving that a specific item was handed from Person A to Person B without tampering.

### The Double-QR Handshake
To prevent "I never received it" or "He never picked it up" fraud:
1. Both apps exchange dynamically generated QR codes at pickup and dropoff.

## 2. Identity Verification & Anti-Fraud
- **Onfido/Checkr Integration:** All couriers pass ID verification.
- **Biometric Liveness (The Deepfake Threat):** High-value pickups require a real-time "Face Match". The threat model here focuses on *Injection Attacks* (virtual cameras bypassing the OS). Our provider must maintain **iBeta Level 2 Presentation Attack Detection (PAD)** certification.

## 3. Application Security
- **Dynamic QR Codes (TOTP):** The QR codes contain Time-based One-Time Passwords.
- **Offline Handshake:** In low-signal areas (e.g., London Underground), the apps exchange cryptographically signed JWTs via Bluetooth LE.
