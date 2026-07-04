# Technical Architecture

## 🏗️ High-Level Architecture
Given the need for live GPS tracking, biometric integrations, and real-time state changes, the architecture must be highly concurrent and real-time capable.

### Frontend
- **Mobile App:** React Native or Flutter for cross-platform deployment.
- **Web Dashboard:** React/Next.js for admin operations and business senders.

### Backend
- **API Layer:** Node.js (Express/NestJS) or Go (for high-concurrency websocket connections).
- **Real-time Engine:** WebSockets or Server-Sent Events (SSE) for live GPS updates and chat.

### Infrastructure (AWS / GCP)
- **Database:** PostgreSQL for relational data (users, orders, financial ledgers).
- **Geospatial Queries:** PostGIS extension for matching commuter routes with package locations.
- **Object Storage:** Amazon S3 / Google Cloud Storage for storing biometric photos, package photos, and ID documents (must be encrypted at rest).

### Third-Party Integrations
- **Identity & Background:** Onfido or Checkr (KYC, DBS, Liveness).
- **Payments:** Stripe Connect.
- **Mapping & Routing:** Google Maps API or Mapbox.

## 📝 TODO: Critical Unknowns
- [ ] Evaluate the latency of PostGIS for live routing vs using a dedicated geospatial engine like Redis GEO.
- [ ] Define the exact encryption standards for storing package photos to comply with GDPR.

## 🔗 Related Documents
- [System Design](system_design.md)
- [Database Design](database_design.md)
