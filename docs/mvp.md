# Minimum Viable Product (MVP)

## 🛑 What is NOT in the MVP
- "Gold Tier" and high-value item insurance.
- Integration with major B2B retailers.
- Complex batching algorithms (limit to 1 package per commuter initially).
- Android & iOS native apps (MVP will be a Progressive Web App or built in React Native but restricted to a single OS initially to save costs).

## ✅ What IS in the MVP
- **User Authentication:** Basic email/phone auth + 3rd party API integration for ID/Liveness (e.g., Onfido).
- **Core Matching Engine:** Hardcoded to a specific geographic zone (e.g., Zone 1-2 London). Simple intent-matching (A to B).
- **Chain of Custody:** The double QR code scanner, photo upload, and state machine (Requested -> Accepted -> In Transit -> Delivered).
- **Payments:** Stripe Connect integration for holding funds in escrow and paying out couriers.

## 🚀 MVP Launch Strategy
Launch within a single, highly dense demographic. Example: A specific London university campus where students commute between dorms and lecture halls.

## 🔗 Related Documents
- [Product Requirements](product_requirements.md)
- [Go-To-Market](go_to_market.md)
