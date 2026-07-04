# Business Model

## Overview
Our business model is a multi-sided peer-to-peer marketplace connecting regular commuters (supply) with local e-commerce sellers and individuals needing rapid, cheap local delivery (demand).

## Revenue Streams
1. **Transaction Fees:** We charge the Sender a flat fee for the delivery (e.g. £5.00). The majority is passed to the Courier. We retain a platform margin.
2. **Micro-Insurance Premiums:** Senders pay an additional premium for the Gold Tier to insure high-value items. We act as the broker.
3. **B2B API Integrations:** Charging local retailers a monthly subscription for bulk-upload tools and priority matching.

## Threats to the Business Model
- **Stripe Micro-transaction Margin Destruction:** Standard Stripe UK fees are 1.5% + £0.20. On a £5.00 transaction, the 20p fixed fee destroys 20% of our £1.00 net margin. We must negotiate a custom micro-transaction pricing tier via Stripe Connect Sales.
- **Platform Leakage (Disintermediation):** As seen in the failure of TaskRabbit's early delivery model, if a local retailer finds a reliable courier, they often take the relationship off-app to avoid our £1.00 fee. We must offer strong intrinsic value (Insurance, automated dispatch tools) to keep B2B users on the platform.
