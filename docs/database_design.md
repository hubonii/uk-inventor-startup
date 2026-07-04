# Database Design

## Core PostgreSQL Schema

### 1. `users` Table
- `id` (UUID, PK)
- `role` (Enum: SENDER, COURIER, BOTH)
- `kyc_status` (Enum: PENDING, VERIFIED, FAILED)
- `stripe_account_id` (String)

### 2. `packages` Table
- `id` (UUID, PK)
- `sender_id` (UUID, FK)
- `status` (Enum: DRAFT, SEEKING_COURIER, IN_TRANSIT, DELIVERED, DISPUTED)
- `origin` (Geography Point) - Indexed with GiST
- `destination` (Geography Point) - Indexed with GiST
- `manifest_photo_url` (String, Encrypted)
- `tier` (Enum: STANDARD, GOLD)

### 3. `courier_intents` Table
- `id` (UUID, PK)
- `courier_id` (UUID, FK)
- `start_location` (Geography Point)
- `end_location` (Geography Point)
- `expires_at` (Timestamp)

### 4. `deliveries` (The Join/Transaction Table)
- `id` (UUID, PK)
- `package_id` (UUID, FK)
- `courier_id` (UUID, FK)
- `pickup_time` (Timestamp)
- `dropoff_time` (Timestamp)
- `payout_amount` (Decimal)

## 📝 Remaining Unknowns (TODOs)
- **PostGIS Indexing:** Finalize the exact bounding box (ST_DWithin) query structure to optimize index usage for the matching engine.
