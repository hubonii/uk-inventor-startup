# Risk Register & Mitigation Strategy

## Existential Risks (Severity: Critical)

### 1. Gig Economy Worker Reclassification
- **Risk:** UK Employment Tribunals classify couriers as workers, forcing us to pay minimum wage, holiday pay, and back taxes.
- **Mitigation:** Strictly adhere to the "Intent-Based" routing model. No dispatching, no penalties for refusal, and hard caps on daily earnings to prove this is expense-sharing, not full-time employment.

### 2. The "Chicken-and-Egg" Liquidity Trap
- **Risk:** Senders open the app, find no couriers, and leave. Couriers open the app, find no packages, and leave.
- **Mitigation:** The "University Campus" wedge strategy. Subsidize supply heavily in a hyper-dense, hyper-local geofence (e.g., UCL campus) until network effects take hold, before expanding to Zone 1 London.

### 3. High Profile Contraband Incident
- **Risk:** A courier is arrested carrying a bomb or heavy narcotics, resulting in terrible PR and police scrutiny.
- **Mitigation:** Strict enforcement of transparent bags. Mandatory photo uploads of the contents before sealing. Rapid cooperation and data-sharing pipeline with UK Law Enforcement.

## Operational Risks (Severity: High)

### 4. Unit Economics Collapse
- **Risk:** The cost of Stripe transaction fees + Onfido API identity checks exceeds the £1-£2 platform take per delivery.
- **Mitigation:** Implement batching (couriers take 3-5 packages on one route). Move Liveness checks to randomized intervals rather than every single delivery to save API costs.

### 5. GPS Spoofing & Package Theft
- **Risk:** Organized rings use mock locations to steal high-value electronics and claim they were delivered.
- **Mitigation:** The Double-QR cryptographic handshake (which requires physical proximity). Enforce Biometric Face Match for high-value items. Limit new accounts to a max package value of £50.

## 📝 Remaining Unknowns (TODOs)
- **Insurance Underwriting:** Find an insurance partner willing to underwrite the P2P transit risk without exorbitant premiums.
