# Privacy & GDPR Compliance

## 1. Biometric Data (Special Category Data)
Under the UK GDPR, biometric data used to uniquely identify someone for anti-fraud purposes (Liveness Checks) is classified as **Special Category Data** (Article 9).

- **Lawful Basis:** Explicit, freely-given consent is legally required.
- **Necessity and Proportionality (ICO Guidelines):** We must prove biometrics are strictly necessary and that a standard ID check is insufficient to prevent package theft. 
- **Mandatory DPIA:** A Data Protection Impact Assessment is legally mandated before processing this data.

## 2. Article 6 Legal Basis
- **Standard PII:** Article 6(1)(b) - Processing necessary for the performance of a contract.
- **Geolocation (GPS Tracking):** Article 6(1)(f) - Legitimate interests.

## 3. Data Retention & Minimization Schedule
- **Biometric Scans (Liveness):** Deleted immediately by the API. Only the Boolean "Match/No Match" result is stored in our database.
- **Package Photos:** Encrypted at rest. Deleted 30 days after successful delivery.
- **GPS Telemetry:** Anonymized after 7 days.

## 4. Privacy by Design
- **Camera Sandbox:** The React Native camera UI intercepts the image buffer. The photo of the package contents is *never* saved to the courier/sender's personal iCloud/Google Photos.
