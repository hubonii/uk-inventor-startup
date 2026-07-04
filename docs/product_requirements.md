# Product Requirements Document (PRD)

## 🎯 Objective
To build an intent-based P2P delivery platform that guarantees security via digital chain-of-custody, biometric verification, and geofenced tracking.

## 📱 User Flows

### Courier Flow
1. **Onboarding:** Upload ID, National Insurance Number, perform Liveness Check, consent to DBS check.
2. **Intent Declaration:** Input "Start Point", "Destination", and "Mode of Transport".
3. **Matching:** View available packages along the route.
4. **Pickup (Chain of Custody):** 
   - Visually inspect the item in front of sender.
   - Place in tamper-evident bag.
   - Take photo through the app.
   - Perform Liveness Face scan.
   - Scan Sender's QR Code to seal custody.
5. **Transit:** Live GPS tracking activates. Geofencing monitors for stalling.
6. **Dropoff:** Scan Recipient's QR Code to close custody. Receive payout.

### Sender Flow
1. **Request:** Input Pickup location, Dropoff location, package size/weight, and contents.
2. **Matching:** Wait for a commuter heading that way, or view commuters who have posted their routes.
3. **Handover:** Show item, place in bag, show QR code for pickup.
4. **Tracking:** View live GPS and courier photo.

## 📝 TODO: Missing Requirements
- [ ] Define the exact UX/UI for "Intent Declaration" (is it a map search, a dropdown, or a text input?).
- [ ] Specify how the app handles edge cases: What happens if the recipient is not home to scan the QR code?

## 🔗 Related Documents
- [Features](features.md)
- [MVP Definition](mvp.md)
