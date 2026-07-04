# Unit Economics

## 1. Single Transaction Breakdown (Base Tier)
- **Sender Pays:** £5.00
- **Courier Receives:** £3.50
- **Platform Gross Margin:** £1.50

## 2. Variable Costs per Transaction
- **Payment Processing (Stripe Connect):** £0.275 (1.5% + 20p fixed fee). *Note: The 20p fixed fee is a critical threat to profitability on £5 payments.*
- **Identity Check (Amortized Onfido):** £0.13 (Assuming Onfido enterprise volume pricing of ~$0.65 per check, amortized over 5 deliveries). *Note: Onfido requires a ~$50,000/year annual commitment.*
- **SMS / Twilio Routing:** £0.05
- **Platform Net Margin:** **£1.04 per delivery**

## 3. The Power of Batching
The £3.50 payout is not a livable wage for a 45-minute trip, reinforcing our legal defense that couriers are not "workers". However, because couriers are taking a fixed route (e.g., the Central Line), they can *batch*.
- If a courier accepts 3 packages along the same Tube line, their payout is £10.50.
- The platform's net margin becomes £3.12 for that single commuter trip.

## 4. Customer Acquisition Cost (CAC)
- Goal CAC for Senders (Vinted power-users): < £5.00
- Goal CAC for Couriers (University Students): < £10.00
- **LTV/CAC Ratio Target:** 3:1 within 12 months.
