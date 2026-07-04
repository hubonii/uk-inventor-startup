# Security Architecture

## 1. Physical & Digital Chain of Custody
The core security primitive of the platform is proving that a specific item was handed from Person A to Person B without tampering.

### The Tamper-Evident Bag
- Senders must place items inside physical, transparent, tamper-evident bags (sold at local shops or mailed to power-users).
- The bag has a unique physical barcode/QR code printed on it.

### The Double-QR Handshake
To prevent "I never received it" or "He never picked it up" fraud:
1. **Pickup:** Sender generates a dynamic QR code on their screen. Courier scans it with their app. Courier generates a dynamic QR code on *their* screen. Sender scans it. Both apps report the cryptographic exchange to the backend.
2. **Drop-off:** Recipient generates a dynamic QR. Courier scans it. Courier generates a dynamic QR. Recipient scans it. Handover complete.

## 2. Identity Verification & Anti-Fraud
- **Onfido/Checkr Integration:** All couriers must pass a strict ID check (Passport/Driver's License) against global watchlists.
- **Biometric Liveness:** High-value package pickups require a real-time "Face Match" scan by the courier immediately before scanning the QR code, proving the registered courier is physically the one taking the package, not a friend borrowing their account.

## 3. Application Security
- **Dynamic QR Codes (TOTP):** The QR codes used in the handshake contain Time-based One-Time Passwords (valid for 30 seconds) to prevent screenshot-replay attacks.
- **GPS Spoofing Prevention:** The mobile app implements anti-spoofing checks (e.g., detecting mock locations on Android, analyzing Wi-Fi/Cellular triangulation drift vs GPS).
- **Offline Handshake:** In low-signal areas (e.g., London Underground), the apps exchange cryptographically signed JWTs via Bluetooth LE, which are synced to the backend once a connection is restored.

## 📝 Remaining Unknowns (TODOs)
- **Bluetooth Offline Sync:** Technical validation of Bluetooth LE reliability across fragmented Android devices.
- **Bag Supply Chain:** Sourcing a manufacturer for custom tamper-evident bags with serialized barcodes.
