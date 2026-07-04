# API Design

## 🔌 Core Endpoints (REST)

### Users
- `POST /api/v1/users/register`
- `POST /api/v1/users/verify-liveness` (Proxies to Onfido)

### Trips (Intent)
- `POST /api/v1/trips` - Courier logs their intent (start, end, mode of transport).
- `GET /api/v1/trips/matches` - Returns packages matching the courier's active trip.

### Packages
- `POST /api/v1/packages` - Sender creates a delivery request.
- `PATCH /api/v1/packages/{id}/status` - Courier updates state (requires QR payload).

## 📡 Real-Time (WebSockets)
- `WSS /ws/tracking/{delivery_id}` - Broadcasts courier GPS coordinates to the sender and recipient.

## 📝 TODO: API Security
- [ ] Implement rate limiting on the matching endpoint to prevent scraping of active packages.
- [ ] Define the JWT expiration and refresh token strategy for mobile clients.
