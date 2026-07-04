# Privacy & GDPR Compliance

Operating in the UK requires strict adherence to the UK GDPR and the Data Protection Act 2018.

## 📡 Live Tracking & Geofencing
- **The Issue:** Tracking a user's location continuously is highly sensitive.
- **Compliance Strategy:** 
  - Location tracking must *only* activate when the courier explicitly taps "Start Journey".
  - It must automatically terminate the second the delivery is completed or canceled.
  - Historical route data must be anonymized within 24 hours unless needed for an active dispute.

## 👁️ Biometrics & Facial Recognition
- **The Issue:** Biometric data is "Special Category Data" under Article 9 of GDPR. Processing it requires explicit, unambiguous consent.
- **Compliance Strategy:**
  - The Liveness detection API (e.g., Onfido) must not store the biometric templates long-term.
  - We must provide a clear Privacy Notice explaining exactly why liveness checks are required (fraud prevention & client safety).

## 📸 Photos of Package Contents
- **The Issue:** Photographing a sender's personal items could inadvertently capture sensitive information (e.g., an address label, medical items).
- **Compliance Strategy:**
  - Photos taken through the app must NOT be saved to the courier's personal camera roll (sandbox the camera module).
  - Photos must be encrypted in transit and at rest, and purged automatically 30 days after a successful delivery, assuming no disputes are raised.

## 📝 TODO: Compliance Actions
- [ ] Draft a Data Protection Impact Assessment (DPIA), which is legally required for processing biometric data.
- [ ] Appoint a Data Protection Officer (DPO) or an external consultant.
