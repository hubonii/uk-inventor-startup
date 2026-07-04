# Mobile App Architecture & UX

## 1. Courier App Additions
- **Pricing Slider:** A UI component allowing couriers to set their "Minimum Rate per Mile" (e.g., £2.50 to £10.00).
- **Staking Dashboard:** UI showing their current "Withheld Stake" progression towards the £50 high-value unlock.

## 2. Sender App Additions
- **Aggregated Billing UI:** Consumers see an "Accumulated Weekly Bill" rather than being charged per drop.
- **B2B Portal:** Pharmacies and local shops get a web dashboard (or tablet app) to dispatch bulk drops (e.g., 5 prescriptions to 5 different addresses) using the "Anchor Courier" network.

## 3. Simplification
- The offline BLE bridging libraries have been removed from the React Native build, drastically reducing app size, battery drain, and background permission requirements.
