# System Design

## 🌐 Macro Architecture

The system follows a microservices or modular monolith architecture.

### 1. Identity & Auth Service
Handles user registration, JWT generation, and communicates with Onfido/Checkr APIs for background checks and Liveness verification.

### 2. Intent & Matching Engine
The core brain. It ingests courier intent (start, destination, time) and uses geospatial queries (PostGIS) to find overlapping unassigned packages.

### 3. State & Custody Manager
A state machine that tracks the exact status of a package:
`REQUESTED` -> `MATCHED` -> `INSPECTED` -> `PICKED_UP` -> `IN_TRANSIT` -> `DELIVERED` (or `DISPUTED`).

### 4. Tracking & Geofence Service
Ingests high-frequency GPS pings from the courier's mobile app via WebSockets. It calculates distance to destination, flags stagnation, and broadcasts the live location to the sender/recipient.

## 📝 TODO: System Design
- [ ] Diagram the sequence flow for the double QR-code handshake.
- [ ] Define the fallback mechanism if a courier's phone dies mid-transit.

## 🔗 Related Documents
- [Technical Architecture](technical_architecture.md)
- [Database Design](database_design.md)
