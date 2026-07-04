# Minimum Viable Product (MVP)

## Scope Restrictions for V1
To launch within 3 months, we will cut the following features:
- ❌ No B2B Web Dashboard (Retailers must use the consumer app).
- ❌ No Offline Bluetooth Exchange (London Underground drops will fail in MVP, require surface-level exchange).
- ❌ No automated Stripe Connect payouts (We will manually process payouts via bank transfer every Friday for the first 100 couriers).
- ❌ No advanced routing algorithms (Simple straight-line ST_Distance threshold).

## Must-Haves for V1
- ✅ Real-time Liveness check integration (Critical for security).
- ✅ The Double-QR cryptographic handshake (Cannot compromise on chain-of-custody).
- ✅ Basic iOS & Android client.
- ✅ In-app Camera Sandbox.

## 📝 Remaining Unknowns (TODOs)
- **TestFlight Launch:** Confirm Apple App Store review policies regarding P2P marketplaces and background location tracking.
