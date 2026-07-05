# Product Roadmap

## Now (Month 1-3): Foundation
| Feature Group | Objective |
|---|---|
| Courier Onboarding + KYC | Verify identity via Onfido, collect bank details |
| Package Creation Flow | Sender creates drop request with pickup/dropoff, size, value |
| TOTP Handshake Protocol | Cryptographic chain-of-custody proof |
| PostGIS Matching Engine | Match packages to couriers by route overlap |
| Stripe Payment (Aggregated) | Weekly billing for senders, instant payout for couriers |
| Collateralized Staking | £50 card hold for high-value item access |

## Next (Month 4-6): Growth
| Feature Group | Objective |
|---|---|
| Courier Pricing Slider | True Marketplace: couriers set own rate/mile |
| B2B Merchant Dashboard | Web portal for pharmacies to bulk-dispatch |
| Rating & Trust System | Two-way ratings, courier tier progression |
| Referral System | Double-sided referral with credit incentives |
| Real-Time GPS Tracking | Live map view during active delivery |

## Later (Month 7-12): Scale
| Feature Group | Objective |
|---|---|
| Multi-Node Expansion | Replicate UCL wedge to 3+ university cities |
| API & POS Integrations | Allow merchants to trigger drops from their existing POS |
| Advanced Analytics | Courier heatmaps, demand forecasting, dynamic surge pricing |
| Insurance Integration | Optional premium tier with goods-in-transit coverage |
| International Prep | Localization, multi-currency, regulatory review for EU |

---

# Engineering Roadmap

## Infrastructure (Week 1-2)
- [ ] AWS account setup (VPC, RDS, ECS/Fargate)
- [ ] PostgreSQL + PostGIS provisioned
- [ ] CI/CD pipeline (GitHub Actions → ECR → ECS)
- [ ] Staging + Production environments
- [ ] Sentry error tracking, CloudWatch monitoring

## API Development (Week 3-8)
- [ ] Auth service (JWT + refresh tokens, OAuth2 social login)
- [ ] User service (profiles, KYC status, staking balance)
- [ ] Package service (CRUD, status machine, photo upload to S3)
- [ ] Matching service (PostGIS spatial queries, courier availability)
- [ ] Handshake service (TOTP generation, QR validation, GPS stamp)
- [ ] Payment service (Stripe Connect, aggregated billing, staking holds)

## Mobile App (Week 3-10)
- [ ] React Native project scaffold (Expo managed workflow)
- [ ] Sender flow: Create Package → View Matches → Confirm → Track → Receive
- [ ] Courier flow: Set Rate → View Available → Accept → Navigate → Handshake → Earn
- [ ] QR scanner integration (react-native-camera)
- [ ] Push notifications (Firebase Cloud Messaging)

## B2B Dashboard (Week 8-12)
- [ ] Next.js web dashboard for merchants
- [ ] Bulk dispatch UI (CSV upload or manual entry)
- [ ] Monthly invoice generation
- [ ] Analytics: drops/day, average delivery time, cost savings

## Security Audit (Week 10-12)
- [ ] OWASP Top 10 review
- [ ] Penetration testing (engage external firm)
- [ ] GDPR data flow audit
- [ ] Stripe PCI compliance verification

---

# Release Roadmap

## Alpha (Internal) — Week 8
**Audience:** Founders + 5 trusted testers
**Scope:** Core loop (create package → match → handshake → payment)
**Go/No-Go:** All P0 features functional. No crashes on happy path.

## Closed Beta — Week 10
**Audience:** 50 users (25 senders, 25 couriers) recruited from UCL
**Scope:** Full sender and courier flows, staking, aggregated billing
**Go/No-Go:** >80% drop completion rate. <3 critical bugs. NPS >20.

## Open Beta — Week 14
**Audience:** 500 users. Open signup within Bloomsbury geofence
**Scope:** All Beta features + referral system + ratings
**Go/No-Go:** >90% drop completion. <1% theft. 50+ drops/week.

## Soft Launch — Week 18
**Audience:** General public within UCL wedge. 5+ onboarded merchants.
**Scope:** Full product including B2B dashboard
**Go/No-Go:** 100+ drops/week. 3+ paying B2B merchants. Unit economics positive.

## General Availability — Week 24
**Audience:** London-wide (initially 3 university wedges)
**Scope:** Multi-node, full marketing push, PR
**Go/No-Go:** 500+ drops/week. 15+ paying merchants. Series Seed closed.

---

# API Development Order

## Priority 1 — MVP (Week 3-6)
| Endpoint | Method | Description |
|---|---|---|
| POST /auth/register | POST | User registration (email, phone, role) |
| POST /auth/login | POST | JWT authentication |
| POST /auth/refresh | POST | Refresh expired tokens |
| GET /users/me | GET | Get current user profile |
| PATCH /users/me | PATCH | Update profile, KYC status |
| POST /packages | POST | Create new package request |
| GET /packages/:id | GET | Get package details + status |
| PATCH /packages/:id/status | PATCH | Update package status (state machine) |
| POST /matches/search | POST | Find couriers matching package route |
| POST /matches/accept | POST | Courier accepts a match |
| POST /handshakes/initiate | POST | Generate TOTP QR for sender |
| POST /handshakes/verify | POST | Courier scans QR, GPS validated |

## Priority 2 — Payments & Staking (Week 6-8)
| Endpoint | Method | Description |
|---|---|---|
| POST /payments/setup-intent | POST | Save sender payment method |
| POST /payments/charge-weekly | POST | Aggregate and charge weekly bill |
| POST /staking/authorize | POST | Create £50 card hold for courier |
| POST /staking/slash | POST | Slash stake on theft/loss incident |
| POST /staking/release | POST | Release hold after successful delivery |
| GET /earnings/me | GET | Courier earnings dashboard |
| POST /payouts/instant | POST | Trigger instant Stripe Connect payout |

## Priority 3 — B2B & Analytics (Week 8-12)
| Endpoint | Method | Description |
|---|---|---|
| POST /merchants/register | POST | Merchant account creation |
| POST /merchants/bulk-dispatch | POST | Create multiple packages at once |
| GET /merchants/analytics | GET | Drops, costs, delivery times |
| GET /admin/analytics/overview | GET | Platform-wide KPIs |
| POST /webhooks/stripe | POST | Handle Stripe payment events |
| POST /webhooks/onfido | POST | Handle KYC completion events |

---

# Database Migration Plan

## V1: Core Schema (Week 3)
```
users (id, email, phone, role, kyc_status, created_at)
packages (id, sender_id, pickup_point, dropoff_point, size, value, status, created_at)
matches (id, package_id, courier_id, status, matched_at, accepted_at)
handshakes (id, match_id, totp_secret, sender_scanned_at, courier_scanned_at, gps_lat, gps_lng)
```
**Rollback:** DROP tables, re-run V1 migration.

## V2: Payments & Staking (Week 6)
```
payment_methods (id, user_id, stripe_pm_id, is_default)
transactions (id, package_id, sender_id, courier_id, amount, platform_fee, status, charged_at)
weekly_bills (id, sender_id, total_amount, stripe_pi_id, period_start, period_end, status)
stakes (id, courier_id, stripe_hold_id, amount, status, created_at, released_at)
```
**Rollback:** DROP V2 tables only. V1 data preserved.

## V3: Ratings, Merchants & Analytics (Week 9)
```
ratings (id, match_id, rater_id, ratee_id, score, comment, created_at)
courier_tiers (id, courier_id, tier, total_drops, avg_rating, staking_balance)
merchants (id, user_id, business_name, address, subscription_tier, billing_email)
merchant_invoices (id, merchant_id, amount, period, stripe_invoice_id, status)
analytics_events (id, event_type, user_id, metadata, created_at)
```
**Rollback:** DROP V3 tables only. V1+V2 data preserved.

## Migration Strategy
- All migrations are versioned and idempotent (using node-pg-migrate or Prisma Migrate)
- Every migration has an explicit `up()` and `down()` function
- Migrations run automatically on deployment via CI/CD pipeline
- Production migrations require manual approval gate in GitHub Actions
