# Risk Register

This document tracks the most critical business, technical, and legal risks facing the startup.

## 🔴 Critical Risks

### 1. The Chicken-and-Egg Problem (Marketplace Liquidity)
- **Risk:** Without senders, couriers won't open the app. Without couriers, senders won't trust the platform.
- **Impact:** Platform stagnation and cash burn on marketing.
- **Mitigation:** Hyper-localized rollout. Seed supply artificially if necessary, or partner with local B2B vendors to guarantee base demand on specific routes.

### 2. Legal Liability of Contraband
- **Risk:** A sender hides illegal substances inside a closed object (e.g., inside a book) which passes the visual inspection. The courier is stopped by police.
- **Impact:** Courier arrest, severe PR damage, platform shutdown.
- **Mitigation:** See [Legal & Liability (UK)](legal_uk.md). Strict Terms of Service acting as a "good-faith facilitator" defense. Mandatory sender ID verification.

### 3. UK Gig Economy Employment Laws
- **Risk:** The UK Supreme Court classifies our couriers as "workers" (like Uber drivers), entitling them to minimum wage and holiday pay, destroying the low-cost P2P economics.
- **Impact:** Bankruptcy.
- **Mitigation:** Strict enforcement of the "commuter-share" model. We must not penalize couriers for rejecting orders, and we must not dictate their routes. See [Legal & Liability (UK)](legal_uk.md).

### 4. GDPR & Privacy Compliance
- **Risk:** Live GPS tracking, biometric capture, and photographing personal items triggers strict ICO (Information Commissioner's Office) penalties.
- **Impact:** Massive fines and app store removal.
- **Mitigation:** See [Privacy & GDPR](privacy_gdpr.md). Implementing automatic data purging and client-side encryption.

## 📝 TODO: Unknown Risks
- [ ] Evaluate the risk of physical assault on couriers carrying high-value tier items.
- [ ] Evaluate the risk of fake ID generation bypassing our onboarding API.
