# Database Design

## 🗄️ Relational Model (PostgreSQL)

### Core Tables
1. **Users:** `id`, `role` (sender, courier), `tier` (standard, gold), `dbs_cleared_at`, `kyc_status`.
2. **Packages:** `id`, `sender_id`, `recipient_name`, `size`, `declared_value`, `status`.
3. **Trips (Intent):** `id`, `courier_id`, `start_geom` (PostGIS), `end_geom` (PostGIS), `planned_time`.
4. **Deliveries:** Mapping table linking `Packages` to `Trips`, including `pickup_time`, `dropoff_time`, and `payout_amount`.

## 📦 Blob Storage (S3 / GCS)
- **Bucket 1 (Identity):** Strictly access-controlled bucket for ID scans.
- **Bucket 2 (Custody):** Stores the encrypted photos of the package contents taken by the courier through the transparent bag. Lifecycle rule: Delete after 30 days.

## 📝 TODO: Database Optimization
- [ ] Design the PostGIS indexing strategy for rapid matching of overlapping commuter routes.
