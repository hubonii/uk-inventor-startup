# Mobile Application Architecture

## 1. Technology Stack
- **Framework:** React Native (Expo Managed Workflow).
- **State Management:** Zustand (lightweight, avoids Redux boilerplate).
- **Navigation:** React Navigation v6.
- **Maps UI:** React Native Maps (using Apple Maps on iOS, Google Maps on Android).

## 2. Core Modules
- **Location Tracker:** A background service that hooks into OS-level location APIs. Must gracefully handle iOS's aggressive background task termination.
- **QR Scanner/Generator:** Uses `expo-camera` to scan. Uses `react-native-qrcode-svg` to generate dynamic TOTP codes.
- **Biometric API:** Bridges to the Onfido mobile SDK for the Face Match flow.
- **Camera Sandbox:** A custom UI built over `expo-camera` that intercepts the base64 image data and sends it directly to the API, bypassing the camera roll.

## 📝 Remaining Unknowns (TODOs)
- **Background Location:** Getting approval from the Google Play Store for background location access is notoriously difficult. Need to draft the justification video for the reviewers.
