# Security Protocols

## 🛡️ Courier Onboarding Security
- **DBS API Integration:** Automated background checks for unspent criminal convictions.
- **Identity:** Cross-referencing Passport/Driving License with National Insurance Numbers to prevent synthetic identities.

## 📦 Anti-Theft & Chain of Custody
1. **The Tamper-Evident Bag:** A physical barrier. Once sealed, it cannot be opened without leaving visible damage.
2. **The Visual Record:** A photo uploaded to our servers proves the state of the item *before* it was sealed.
3. **Double Cryptographic Handshake:** The pickup and drop-off are verified by scanning dynamic QR codes generated on the client's phone. A screenshot of a QR code will not work (time-based regeneration).

## 🛑 Geofencing Anti-Hoarding
To prevent a courier from accepting a package and holding it hostage:
- The app monitors GPS ping frequency.
- If the courier deviates significantly from the stated intent-route, or stops at a residential address for an extended period, an automated warning is sent.
- If ignored, the sender is notified and the courier's account is suspended.

## 📝 TODO: Technical Security
- [ ] Define the exact cryptographic rotation speed for the QR codes.
- [ ] Architecture review: How do we prevent spoofed GPS locations (mock location apps on Android)?
