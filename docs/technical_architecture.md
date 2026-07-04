# Technical Architecture

## 1. Core Stack
- **Client (Mobile):** React Native (Expo) - allows rapid deployment to both iOS and Android with a shared codebase.
- **Client (Web):** Next.js / React (for the B2B Retailer Dashboard).
- **Backend API:** Node.js (Express or NestJS) / TypeScript - highly scalable for concurrent WebSocket connections.
- **Database:** PostgreSQL with PostGIS extension - critical for the heavy geospatial matching algorithms.
- **Cloud Infrastructure:** Google Cloud Platform (Cloud Run for API, Cloud SQL for PostgreSQL).

## 2. Geospatial Matching Engine (PostGIS)
The core IP. Instead of pushing tasks to couriers, the engine relies on PostGIS spatial queries to match a package's (Origin A -> Destination B) with a courier's declared intent (Starting Point X -> Ending Point Y).
- Must calculate intersecting vectors and walking distance deviations in under 50ms.

## 3. Real-Time Tracking
- **Protocol:** WebSockets (Socket.io or raw ws).
- **Architecture:** Couriers push GPS coordinates every 10 seconds. Senders receive updates over the socket connection. Redis Pub/Sub used to scale WebSocket instances.

## 4. Third-Party Integrations
- **Payments:** Stripe Connect (handles holding sender funds in escrow and routing payouts to couriers).
- **Identity & Biometrics:** Onfido API (KYC and Liveness checks).
- **Maps/Routing:** Mapbox API or Google Maps Platform.

## 📝 Remaining Unknowns (TODOs)
- **Battery Drain:** Determine the exact battery drain on the Courier's phone when pushing GPS via WebSockets for 45 minutes.
