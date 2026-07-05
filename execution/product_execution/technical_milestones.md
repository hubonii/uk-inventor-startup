# Technical Milestones — Local-Logistics Protocol

> Last updated: July 2026 | Engineering Milestones Mapped to Product Milestones

---

## Overview

Technical milestones are gate-checked deliverables that must be completed before dependent product features can ship. Each milestone has clear acceptance criteria, an owner, and a target date aligned to the sprint plan.

---

## Milestone Timeline

```
Week:  1    2    3    4    5    6    7    8    9   10   11   12   13   14   15   16
       │    │    │    │    │    │    │    │    │    │    │    │    │    │    │    │
TM-01  ████████                                                                    Database Schema V1
TM-02       ████████                                                               API v1 Core
TM-03            ████████                                                          Matching Engine
TM-04                 ████████████                                                 TOTP Handshake
TM-05                      ████████████                                            Mobile App Alpha
TM-06                           ████████████                                       Payment Integration
TM-07                                     ████████                                 B2B Dashboard Beta
TM-08                                          ████████                            Trust System
TM-09                                               ████████                       Admin Panel
TM-10                                                    ████████                  Security Audit
TM-11                                                         ██████████           Performance & Scale
TM-12                                                              ████████████    Production Launch
```

---

## TM-01: Database Schema Complete

| Attribute | Detail |
|---|---|
| **Target** | Week 2 (Sprint 1) |
| **Owner** | Full-Stack Engineer #1 |
| **Product Dependency** | All features depend on data model |
| **Sprint** | Sprint 1 |

### Acceptance Criteria
- [ ] PostgreSQL 15+ with PostGIS extension deployed
- [ ] Core tables created: `users`, `courier_profiles`, `packages`, `matches`, `deliveries`
- [ ] Auth tables: `sessions`, `otp_codes`, `kyc_documents`
- [ ] Indexes on: `users(phone)`, `courier_profiles(location)` (GiST), `packages(status, created_at)`
- [ ] Database migrations framework configured (Knex.js / Prisma)
- [ ] Seed data script for development environment
- [ ] Schema documentation auto-generated

### Technical Specifications
```
Tables (V1):
├── users (id, phone, name, role, created_at, updated_at)
├── courier_profiles (user_id, transport_mode, zones, rating, trust_score, location, is_online)
├── packages (id, sender_id, type, size, description, pickup_addr, dropoff_addr, pickup_geo, dropoff_geo)
├── matches (id, package_id, courier_id, status, courier_rate, platform_fee, created_at)
├── deliveries (id, match_id, status, pickup_at, delivered_at, audit_trail)
├── otp_codes (id, phone, code, expires_at, verified)
└── kyc_documents (id, user_id, type, file_url, status, verified_at)
```

---

## TM-02: API v1 Deployed

| Attribute | Detail |
|---|---|
| **Target** | Week 4 (Sprint 2) |
| **Owner** | Founder |
| **Product Dependency** | All client applications |
| **Sprint** | Sprint 1-2 |

### Acceptance Criteria
- [ ] RESTful API running on staging (Node.js + Express/Fastify)
- [ ] Auth endpoints: `POST /auth/otp/send`, `POST /auth/otp/verify`, `POST /auth/register`
- [ ] Package endpoints: `POST /packages`, `GET /packages/:id`, `GET /packages/active`
- [ ] Courier endpoints: `GET /couriers/available`, `POST /couriers/rate`, `PUT /couriers/status`
- [ ] Match endpoints: `POST /matches`, `GET /matches/:id`, `PUT /matches/:id/accept`
- [ ] Request validation (Joi/Zod schemas)
- [ ] Error handling middleware (consistent error format)
- [ ] Rate limiting (100 req/min per IP)
- [ ] API documentation (Swagger/OpenAPI)
- [ ] Health check endpoint: `GET /health`

### Technical Specifications
- Runtime: Node.js 20 LTS
- Framework: Fastify (performance) or Express (ecosystem)
- ORM: Prisma or Knex.js
- Validation: Zod
- Auth: JWT (access token 15min, refresh token 7 days)
- Deployment: Docker container on AWS ECS / GCP Cloud Run

---

## TM-03: Matching Engine Live

| Attribute | Detail |
|---|---|
| **Target** | Week 4 (Sprint 2) |
| **Owner** | Full-Stack Engineer #1 |
| **Product Dependency** | Courier quotes, job feed |
| **Sprint** | Sprint 2 |

### Acceptance Criteria
- [ ] PostGIS spatial query finds couriers within configurable radius
- [ ] Multi-factor ranking algorithm implemented (proximity 30%, price 25%, rating 25%, transport 10%, completion 10%)
- [ ] Matching completes in <500ms for 95th percentile
- [ ] Results returned as sorted list with score breakdown
- [ ] A/B test framework for weight configuration
- [ ] Unit tests covering edge cases (no couriers, equal scores, boundary distance)

### Performance Targets
| Metric | Target |
|---|---|
| Match latency (p50) | <100ms |
| Match latency (p95) | <500ms |
| Match latency (p99) | <1000ms |
| Concurrent match requests | 50/second |

---

## TM-04: TOTP Handshake System

| Attribute | Detail |
|---|---|
| **Target** | Week 6 (Sprint 3) |
| **Owner** | Full-Stack Engineer #2 |
| **Product Dependency** | Core value proposition — chain-of-custody |
| **Sprint** | Sprint 3 |

### Acceptance Criteria
- [ ] TOTP generation compliant with RFC 6238 (HMAC-SHA1, 6-digit, 30-second step)
- [ ] Unique TOTP seed per delivery (not per user)
- [ ] QR code encodes: delivery ID + TOTP URI + timestamp + package hash
- [ ] Pickup handshake: courier scans sender QR → server validates → status = "in_transit"
- [ ] Delivery handshake: recipient scans/enters courier QR → server validates → status = "delivered"
- [ ] Hash chain: each event includes SHA-256 hash of previous event
- [ ] Handshake fails gracefully on network interruption (retry + offline cache)
- [ ] Manual fallback: 6-digit code entry when camera fails
- [ ] Unit tests: valid TOTP, expired TOTP, replayed TOTP, wrong delivery TOTP

### Security Requirements
- TOTP seeds stored encrypted (AES-256-GCM)
- Seeds rotated per delivery (never reused)
- Clock drift tolerance: ±1 step (±30 seconds)
- Rate limiting on verification attempts: 5 per minute per delivery

---

## TM-05: Mobile App Alpha

| Attribute | Detail |
|---|---|
| **Target** | Week 8 (Sprint 4) |
| **Owner** | Founder (pre-Mobile Engineer hire) |
| **Product Dependency** | Courier experience, QR scanning |
| **Sprint** | Sprint 3-4 |

### Acceptance Criteria
- [ ] React Native app running on iOS and Android
- [ ] Courier flow: register → browse jobs → accept → pickup handshake → navigate → deliver
- [ ] Sender flow: create package → view quotes → confirm → track → receive confirmation
- [ ] Camera integration for QR scanning (react-native-camera)
- [ ] GPS tracking (background location when online)
- [ ] Push notifications (Firebase Cloud Messaging)
- [ ] Offline-tolerant: queue actions when network lost, sync on reconnect
- [ ] App loads in <3 seconds on 4G

### Platform Requirements
- iOS: 15.0+
- Android: API 26+ (Android 8.0)
- React Native: 0.73+
- Distribution: TestFlight (iOS) + Internal Testing (Android) for alpha

---

## TM-06: Payment Integration Live

| Attribute | Detail |
|---|---|
| **Target** | Week 8 (Sprint 4) |
| **Owner** | Full-Stack Engineer #2 |
| **Product Dependency** | Revenue generation, courier payouts, staking |
| **Sprint** | Sprint 4 |

### Acceptance Criteria
- [ ] Stripe Payment Intents for sender charges
- [ ] Stripe Connect accounts for courier payouts
- [ ] Stripe Escrow for stake management
- [ ] Apple Pay + Google Pay support
- [ ] PCI DSS compliance (Stripe.js handles card details — never touch our server)
- [ ] Payout schedules: instant (£0.25 fee), daily (free), weekly (free)
- [ ] Refund flow: full and partial refunds via Stripe
- [ ] Webhook handlers for: `payment_intent.succeeded`, `payout.paid`, `charge.refunded`
- [ ] All financial transactions logged in `transactions` table with idempotency keys
- [ ] Test mode verified with £0.50 test transactions
- [ ] Live mode activated with production Stripe keys

### Compliance Requirements
- PSD2/SCA (Strong Customer Authentication) for EU/UK cards
- Stripe Identity for courier onboarding (KYC)
- VAT handling on platform fees
- Financial transaction audit trail (7-year retention)

---

## TM-07: B2B Dashboard Beta

| Attribute | Detail |
|---|---|
| **Target** | Week 10 (Sprint 5) |
| **Owner** | Full-Stack Engineer #1 |
| **Product Dependency** | Merchant revenue stream |
| **Sprint** | Sprint 5 |

### Acceptance Criteria
- [ ] React web dashboard (responsive, desktop-first)
- [ ] Merchant registration with Companies House KYB
- [ ] Single delivery creation (pre-filled merchant address)
- [ ] CSV batch upload with validation and preview
- [ ] Real-time delivery tracking (map + list views)
- [ ] Active deliveries dashboard with status filters
- [ ] Basic analytics: deliveries/day, avg time, avg cost
- [ ] Stripe Billing subscription (£49/mo auto-charge)
- [ ] Monthly invoice generation (PDF)

### Design Specifications
- Framework: React 18 + TypeScript
- Styling: Tailwind CSS
- Charts: Recharts or Chart.js
- Maps: Mapbox GL JS
- State: React Query for server state
- Auth: JWT with httpOnly cookies

---

## TM-08: Trust System

| Attribute | Detail |
|---|---|
| **Target** | Week 10 (Sprint 5) |
| **Owner** | Founder |
| **Product Dependency** | Quality control, trust tiers |
| **Sprint** | Sprint 5 |

### Acceptance Criteria
- [ ] Rating system: 1-5 stars, bidirectional (sender ↔ courier)
- [ ] Trust score: composite 0-100 (recalculated after each delivery)
- [ ] Tier system: Bronze (0-30), Silver (30-100), Gold (100+) deliveries
- [ ] Auto-flag: <3.5 avg (last 20) OR >15% cancellation OR 2+ disputes/30 days
- [ ] Flagged → Warning email → 7-day probation → Suspension → Ban (escalation chain)
- [ ] Trust score visible in courier profile and matching algorithm

---

## TM-09: Admin Panel

| Attribute | Detail |
|---|---|
| **Target** | Week 12 (Sprint 6) |
| **Owner** | Full-Stack Engineer #1 |
| **Product Dependency** | Operations management |
| **Sprint** | Sprint 6 |

### Acceptance Criteria
- [ ] Admin login with role-based access (admin, support, viewer)
- [ ] User search and management (view, suspend, ban)
- [ ] Real-time operations dashboard (active deliveries, couriers online, revenue)
- [ ] Service zone management (draw/edit zones on map)
- [ ] Dispute queue with resolution actions
- [ ] Platform configuration (fee %, rate floor, matching radius)
- [ ] Activity log showing all admin actions

---

## TM-10: Security Audit Passed

| Attribute | Detail |
|---|---|
| **Target** | Week 11 (Sprint 6) |
| **Owner** | External security firm |
| **Product Dependency** | Production launch approval |
| **Sprint** | Sprint 6 |

### Acceptance Criteria
- [ ] Penetration test: no critical or high severity findings
- [ ] OWASP Top 10 review: all addressed
- [ ] TOTP implementation review: cryptographically sound
- [ ] Data encryption: at-rest (AES-256) and in-transit (TLS 1.3)
- [ ] GDPR compliance check: data minimisation, consent, deletion capability
- [ ] Authentication review: JWT security, session management
- [ ] Payment security: PCI DSS compliance verified (via Stripe)
- [ ] Remediation of all medium findings within 1 week

---

## TM-11: Performance & Scale Ready

| Attribute | Detail |
|---|---|
| **Target** | Week 12 (Sprint 6) |
| **Owner** | Full-Stack Engineer #2 |
| **Product Dependency** | Production reliability |
| **Sprint** | Sprint 6 |

### Acceptance Criteria
- [ ] Load test: 100 concurrent deliveries without degradation
- [ ] API response time: p95 < 200ms, p99 < 500ms
- [ ] Database query performance: no queries > 100ms
- [ ] WebSocket: 500 concurrent connections stable
- [ ] Auto-scaling configured (min 2, max 10 instances)
- [ ] Monitoring: Datadog/New Relic dashboards + PagerDuty alerts
- [ ] Uptime target: 99.5% (measured over 7-day pre-launch period)
- [ ] Backup: automated daily database backups with 30-day retention
- [ ] Disaster recovery: RTO < 4 hours, RPO < 1 hour

---

## TM-12: Production Launch

| Attribute | Detail |
|---|---|
| **Target** | Week 13-14 (post-Sprint 6) |
| **Owner** | Founder |
| **Product Dependency** | Revenue generation |
| **Sprint** | Post-sprint |

### Launch Checklist
- [ ] All TM-01 through TM-11 complete ✅
- [ ] Stripe live mode enabled and tested
- [ ] Domain and SSL configured (locallogistics.co)
- [ ] App submitted to App Store and Google Play
- [ ] Terms of Service and Privacy Policy published
- [ ] GDPR cookie consent implemented
- [ ] Error tracking (Sentry) configured
- [ ] Customer support channel (Intercom/Zendesk) live
- [ ] Analytics (Mixpanel/Amplitude) events instrumented
- [ ] Beta users migrated to production
- [ ] Anchor Couriers onboarded and staked
- [ ] First B2B merchant live
- [ ] Runbook documented for on-call incidents

### Go/No-Go Criteria
| Criterion | Required | Status |
|---|---|---|
| Security audit: 0 critical/high | Yes | ⬜ |
| Load test: 100 concurrent | Yes | ⬜ |
| Payment flow tested (live £1) | Yes | ⬜ |
| 25+ beta deliveries completed | Yes | ⬜ |
| Monitoring & alerting active | Yes | ⬜ |
| Rollback procedure tested | Yes | ⬜ |
| Legal review complete | Yes | ⬜ |
| Founder sign-off | Yes | ⬜ |

---

## Milestone-to-Sprint Mapping

| Milestone | Sprint 1 | Sprint 2 | Sprint 3 | Sprint 4 | Sprint 5 | Sprint 6 |
|---|---|---|---|---|---|---|
| TM-01: DB Schema | ████ | | | | | |
| TM-02: API v1 | ██ | ████ | | | | |
| TM-03: Matching | | ████ | | | | |
| TM-04: TOTP | | | ████ | | | |
| TM-05: Mobile Alpha | | | ██ | ████ | | |
| TM-06: Payments | | | | ████ | | |
| TM-07: B2B Dashboard | | | | | ████ | |
| TM-08: Trust System | | | | | ████ | |
| TM-09: Admin Panel | | | | | | ████ |
| TM-10: Security Audit | | | | | | ████ |
| TM-11: Performance | | | | | | ████ |
| TM-12: Launch | | | | | | ██ |

---

*Technical milestones are reviewed at each sprint retrospective. Blockers escalated immediately to founder. External dependencies (security audit, Stripe approval) tracked separately.*
