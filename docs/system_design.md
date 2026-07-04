# System Design

## 1. High-Level Components
- **API Gateway:** Routes incoming HTTP/WebSocket traffic. Handles rate limiting and JWT auth.
- **Matching Service:** Dedicated microservice for querying PostGIS. Scales independently.
- **Telemetry Service:** Ingests GPS pings via WebSockets. Writes to a fast in-memory store (Redis) for live tracking, and batches writes to PostgreSQL for historical retention.
- **Notification Service:** Handles push notifications (FCM/APNs) for status updates (e.g., "Package Picked Up").

## 2. The Cryptographic Handshake Flow
1. API generates a TOTP seed for the specific Delivery ID.
2. Sender's app generates QR code based on seed + current time.
3. Courier scans QR. Courier's app validates TOTP, generates the counter-signature.
4. Courier's app sends the validation payload to the API.
5. API updates state to `IN_TRANSIT` and fires Webhooks.

## 3. Offline Mode Architecture (Edge Case)
If the exchange happens deep underground:
- Apps exchange signed JWTs via Bluetooth Low Energy (BLE).
- The JWT contains the timestamp, Delivery ID, and device signatures.
- Once either device regains 4G/5G, the JWT is flushed to the API.

## 📝 Remaining Unknowns (TODOs)
- **Concurrency:** Load test the PostGIS Matching Service against 10,000 simulated concurrent couriers requesting routes.
