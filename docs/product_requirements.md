# Product Requirements Document (PRD)

## The Core Loop (Courier)
1. Open App. 
2. Enter Destination (or select saved commute like "UCL to Kings Cross").
3. See matches overlaid on a map with detours < 5 mins.
4. Tap "Accept".
5. Navigate to Pickup. Scan Sender's QR. (If Gold Tier: Pass Face Match first).
6. Take Tube/Bus/Walk.
7. Navigate to Dropoff. Scan Recipient's QR.
8. Receive £4.00 instantly to Wallet.

## The Core Loop (Sender)
1. Open App.
2. Put item in tamper-evident bag.
3. Take photo using the in-app Camera Sandbox.
4. Enter recipient phone number & destination.
5. Pay £5.00 via Apple/Google Pay.
6. Wait for Courier arrival. Show QR Code.

## Non-Functional Requirements
- **Performance:** Matching algorithm must return results within 2 seconds of Courier declaring intent.
- **Privacy:** Photos of package contents must be encrypted at rest and never accessible by support staff unless a dispute is triggered.

## 📝 Remaining Unknowns (TODOs)
- **Accessibility:** Ensure the high-contrast mode is fully compliant for visually impaired Couriers.
