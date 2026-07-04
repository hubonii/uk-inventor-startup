# API Design

## Core REST Endpoints (v1)

### Intent & Matching
- `POST /v1/intent` - Courier declares route (A to B). Returns a list of matched `package_ids`.
- `POST /v1/packages` - Sender creates a delivery request.
- `POST /v1/deliveries/accept` - Courier accepts a specific package from their matched list.

### Handshake & Security
- `GET /v1/deliveries/:id/totp` - Fetch the current time-based QR code seed.
- `POST /v1/deliveries/:id/verify-pickup` - Courier submits Sender's scanned QR data.
- `POST /v1/deliveries/:id/verify-dropoff` - Recipient submits Courier's scanned QR data.

### Identity
- `POST /v1/auth/liveness` - Submit a real-time biometric Face Match payload to Onfido. Returns pass/fail boolean.

## WebSockets
- `WS /v1/telemetry/:delivery_id`
  - Client Emits: `{ lat, lng, timestamp }`
  - Server Emits: `LOCATION_UPDATED` to Sender.

## 📝 Remaining Unknowns (TODOs)
- **Rate Limiting:** Define the strict rate limits for the `POST /v1/intent` endpoint to prevent scrapers from mapping out all local delivery demand.
