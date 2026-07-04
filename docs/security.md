# Security & Chain of Custody

## 1. Above-Ground TOTP Handshakes
We have scrapped the offline Bluetooth Low Energy (BLE) mesh network due to extreme engineering complexity and Android fragmentation.
- **Mandatory 4G/5G Handshakes:** All physical handovers must occur above ground (e.g., outside Tube station entrances) where standard internet connectivity is available.
- **The Protocol:** Sender and Courier scan each other's dynamic TOTP QR codes via our standard HTTPS REST API, guaranteeing real-time GPS validation at the exact moment of handover.

## 2. Theft Deterrence
- **Earn Your Stake:** To overcome the onboarding friction of the £50 Collateralized Stake, new couriers are restricted to low-value items (<£10). Their earnings are withheld until they reach the £50 collateral threshold, at which point they unlock high-value deliveries.
- **Tamper-Evident Packaging:** Standardized, sealed bags prevent opportunistic snooping.
