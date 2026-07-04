# Mobile Application Architecture

## 1. Technology Stack
- **Framework:** React Native (Expo).
- **QR Generation:** We use `react-native-nitro-totp` combined with `react-native-qrcode-svg` to generate the secure 30-second TOTP handshakes.

## 2. Core Constraints & Mitigations

### Background Location Tracking (App Store Policy)
- **The Threat:** Apple strictly rejects apps tracking background location without direct, immediate user value (e.g., fitness tracking).
- **The Mitigation:** We cannot use high-frequency background GPS. We must rely on `startMonitoringSignificantLocationChanges` and clearly justify the "Sender Peace of Mind" in our permission purpose strings.

### Offline Bluetooth (BLE) Handshake
- **The Threat:** Budget Android OS skins aggressively kill background BLE processes, causing GATT errors (Status 133).
- **The Mitigation:** We must run the BLE listener as a Foreground Service with a persistent notification. Additionally, all GATT operations must run through a serialized queue, as parallelizing them breaks the Android Bluetooth stack.

## 3. Camera Sandbox
- A custom UI built over `expo-camera` intercepts the base64 image data and sends it directly to the API, bypassing the camera roll to ensure Sender privacy.
