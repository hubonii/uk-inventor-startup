# Unit Economics

## 1. Margin Crisis & Solution
Relying on £5 micro-transactions was unviable due to fixed API fees (Stripe 20p + Onfido 13p). We have restructured our unit economics around **Aggregated Billing** and **Reduced API Calls**.

## 2. API Cost Reduction
- **Onfido KYC:** £0.13 per courier *only once* at onboarding. No per-transaction identity API calls.
- **Handshakes:** Powered by our free TOTP Double-QR algorithm instead of third-party APIs.

## 3. Stripe Aggregation
Instead of charging per trip, we use:
- **B2B Monthly Invoicing:** Pharmacies are billed once at the end of the month via Stripe BACS or Invoice (massively reducing fixed card fees).
- **Casual Sender Weekly Billing:** Consumer cards are charged once every Friday for all trips accumulated that week.

## 4. Target Transaction Model (Average Order)
- Courier Rate (Self-Set): £4.00
- Platform Fee (15%): £0.60
- Aggregated Stripe Fee (amortized): -£0.03
- Gross Margin per Drop: £0.57 (A 54% improvement over the unaggregated model).
