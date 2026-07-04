# Unit Economics

## 1. Single Transaction Breakdown (Base Tier)
- **Sender Pays:** £5.00
- **Courier Receives:** £3.50
- **Platform Gross Margin:** £1.50

## 2. Variable Costs per Transaction
- **Payment Processing (Stripe):** ~£0.27 (1.4% + 20p)
- **Identity Check (Amortized Onfido):** ~£0.10 (Assuming 1 Liveness check per 5 deliveries, at £0.50 per API call).
- **SMS / Twilio Routing:** ~£0.05
- **Platform Net Margin:** **£1.08 per delivery**

## 3. The Power of Batching
The £3.50 payout is not a livable wage for a 45-minute trip. However, because couriers are taking a fixed route (e.g., the Central Line), they can *batch*.
- If a courier accepts 3 packages along the same Tube line, their payout is £10.50.
- The platform's net margin becomes £3.24 for that single commuter trip.
- This creates the density flywheel: higher density = more batching = happier couriers = faster delivery times.

## 4. Customer Acquisition Cost (CAC)
- Goal CAC for Senders (Vinted power-users): < £5.00
- Goal CAC for Couriers (University Students): < £10.00
- **LTV/CAC Ratio Target:** 3:1 within 12 months.

## 📝 Remaining Unknowns (TODOs)
- **Insurance Loss Ratio:** We lack actuarial data to determine how much of our Net Margin will be eaten by legitimate "lost package" claims.
