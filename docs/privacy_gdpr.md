# Privacy & GDPR Compliance

## 1. Data Protection Impact Assessment (DPIA)
Given the platform's processing of biometric data (facial scans for Liveness checks) and real-time geolocation, a DPIA is legally mandated under UK GDPR Article 35.

## 2. Article 6 & Article 9 Legal Basis
- **Standard PII (Name, Email):** Article 6(1)(b) - Processing necessary for the performance of a contract.
- **Geolocation (GPS Tracking):** Article 6(1)(f) - Legitimate interests (ensuring the safety of the package and providing the sender with peace of mind). GPS tracking only activates when the courier has physical possession of a package.
- **Biometric Data (Face Match):** Article 9(2)(a) - Explicit consent. Used exclusively for anti-fraud and identity verification.

## 3. Data Retention Schedule
To avoid ICO fines for data hoarding, the following automated purging schedule is enforced:
- **Biometric Scans (Liveness):** Deleted immediately upon successful match verification. (We store the Boolean result, not the photo).
- **Package Photos (Visual Manifest):** Encrypted at rest. Deleted 30 days after successful delivery confirmation, unless a dispute is raised.
- **GPS Telemetry:** Aggregated and anonymized after 7 days. Raw tracking data deleted after 30 days.
- **Account Deletion:** All user PII hard-deleted within 14 days of account closure request.

## 4. Privacy by Design Features
- **Camera Sandbox:** When users take a photo of the package, the app uses a sandboxed camera view. The photo is *never* saved to the user's local iOS/Android camera roll.
- **Phone Number Masking:** Senders and Couriers communicate via in-app VoIP or Twilio masked numbers. Real phone numbers are never exchanged.

## 📝 Remaining Unknowns (TODOs)
- **Data Subject Access Requests (DSAR):** Automate the JSON export functionality for users requesting their data.
- **Third-Party Audits:** Select an independent GDPR auditor to review our DPIA prior to the public beta.
