# Mobile App

## 📱 Tech Stack
- **Framework:** React Native or Flutter.
- **Maps Integration:** Mapbox SDK (better custom styling for routes than Google Maps).
- **Camera Module:** Custom native bridge required to ensure photos are NOT saved to the local camera roll (GDPR compliance).

## 🔑 Key Mobile Challenges
1. **Background Location:** iOS and Android strictly limit background location tracking. The app must request "Always On" permission and display a persistent notification while a delivery is active.
2. **Battery Drain:** High-frequency GPS pings drain batteries fast. We need an adaptive ping rate (e.g., ping every 10 seconds when walking, every 30 seconds when driving fast).
3. **Offline Mode:** If a courier loses signal in the London Underground, the app must cache GPS points and the delivery state, syncing them once back above ground.

## 📝 TODO: Mobile UX
- [ ] Design the "Intent Entry" screen to be frictionless (< 3 taps).
- [ ] Prototype the QR scanning UI for the digital handshake.
