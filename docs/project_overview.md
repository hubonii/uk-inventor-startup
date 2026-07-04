# Project Overview

## 📦 What are we building?
A green, sustainable peer-to-peer (P2P) urban logistics platform designed specifically to optimize existing human commutes. It operates on an "intent-based" model, where couriers log their planned trips and the system matches them with packages needing to go to the same destination.

## 🔑 Core Features

### 1. Intent-Based Matching
Unlike traditional platforms that push randomized orders, our platform is deterministic. Couriers input their destination (e.g., "Mayfair, London"), and the algorithm displays supply tailored to that route. Senders can also post requests targeting specific courier destinations.

### 2. Bulletproof Security & Identity
- **DBS Checks:** Integration with APIs (Onfido/Checkr) for criminal record checks.
- **ID Verification:** Legal ID and National Insurance Number required.
- **Biometric Liveness:** Facial recognition at pickup and delivery to verify the courier's identity live.

### 3. Digital Chain of Custody
- Visual inspection of contents before pickup.
- Placement into a tamper-evident, transparent bag.
- Double QR code verification (Pickup & Dropoff).

### 4. Courier Economics & Tiering
- A tiered system restricting high-value goods (jewelry, electronics) to vetted "Gold Tier" couriers.
- Batching systems to make low-cost deliveries (£3-£5) economically viable.

## 🔗 Related Documents
- [Vision](vision.md)
- [Technical Architecture](technical_architecture.md)
- [Product Requirements](product_requirements.md)
