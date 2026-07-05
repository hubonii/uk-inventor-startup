# Epics & Features — Local-Logistics Protocol

> Last updated: July 2026 | Product Backlog Definition

---

## Overview

The product is decomposed into **8 Epics**, each representing a major capability area. Under each epic, **3-5 features** are defined with descriptions, priority levels, and dependencies. Features are sized as **S** (1-3 days), **M** (3-7 days), or **L** (1-3 weeks) of engineering effort.

---

## Epic 1: Courier Onboarding & KYC

> **Goal:** Enable anyone with a smartphone to become a verified courier within 15 minutes, while maintaining regulatory compliance and building initial trust score.

| # | Feature | Description | Size | Priority |
|---|---|---|---|---|
| 1.1 | **Phone Number Verification** | OTP-based phone verification via SMS (Twilio). Serves as primary identity anchor. Rate-limited to prevent abuse. | S | P0 |
| 1.2 | **Identity Document Upload** | Courier uploads government-issued ID (passport, driving licence, BRP). Image quality validation. Stored encrypted (AES-256) with automatic 90-day deletion after verification. | M | P0 |
| 1.3 | **Selfie Liveness Check** | Real-time selfie capture matched against uploaded ID using facial recognition API (e.g., Onfido or Veriff). Anti-spoofing (blink detection). | M | P0 |
| 1.4 | **Collateral Stake Deposit** | Courier deposits £50 refundable stake via Stripe. Held in escrow. Returned on clean account closure (zero disputes, 14-day cool-off). Acts as behavioural bond. | M | P0 |
| 1.5 | **Courier Profile Setup** | Set display name, profile photo, preferred zones, availability hours, and transport mode (walking, cycling, e-bike, car). Generates courier rating seed. | S | P1 |

---

## Epic 2: Sender Package Creation

> **Goal:** Allow any sender to create a delivery request in under 60 seconds — describe the package, set pickup/drop-off locations, and see instant price quotes from available couriers.

| # | Feature | Description | Size | Priority |
|---|---|---|---|---|
| 2.1 | **Package Description Form** | Structured form: package type (document, small parcel, fragile, food), dimensions (S/M/L), weight estimate, special instructions. Photo upload optional. | M | P0 |
| 2.2 | **Address Autocomplete & Geocoding** | Google Places / Mapbox autocomplete for pickup and drop-off addresses. Geocoded to lat/lng. Distance calculated. Validates both addresses are within service zone. | M | P0 |
| 2.3 | **Delivery Time Window Selection** | Sender selects: ASAP (within 1 hour), Scheduled (2-hour window today/tomorrow), or Flexible (cheapest available slot). Time windows feed into matching engine. | S | P1 |
| 2.4 | **Price Quote Display** | After package details and addresses entered, display real-time quotes from available couriers. Show courier name, rating, price, and estimated time. Sender selects preferred courier. | M | P0 |
| 2.5 | **Recipient Details & Notifications** | Sender enters recipient name + phone number. Recipient receives SMS with tracking link. No app download required for recipients. | S | P1 |

---

## Epic 3: Matching Engine

> **Goal:** Intelligently match delivery requests with available couriers based on proximity, price, rating, transport mode, and time constraints — optimising for speed, cost, and reliability.

| # | Feature | Description | Size | Priority |
|---|---|---|---|---|
| 3.1 | **Geo-Proximity Matching** | Real-time query of active couriers within configurable radius (default: 2km) of pickup location. Uses PostGIS spatial queries on courier GPS positions. | L | P0 |
| 3.2 | **Courier Rate Submission** | Couriers set their own rates per delivery. Can set default rate or bid per-job. Rate must be ≥ £2.50 minimum floor. Historical rate data informs suggested pricing. | M | P0 |
| 3.3 | **Multi-Factor Ranking Algorithm** | Rank eligible couriers by weighted score: proximity (30%), price (25%), rating (25%), transport suitability (10%), completion rate (10%). Configurable weights for A/B testing. | L | P0 |
| 3.4 | **Merchant Priority Matching** | B2B merchant jobs surfaced first in courier feed. Optional "dedicated courier" mode where specific couriers are pre-assigned to merchant accounts. | M | P1 |
| 3.5 | **Batch Matching (B2B)** | Merchants submit multiple deliveries simultaneously. Engine optimises courier assignment across the batch for route efficiency and cost minimisation. | L | P2 |

---

## Epic 4: TOTP Handshake Protocol

> **Goal:** Implement the cryptographic chain-of-custody protocol that eliminates the need for courier vetting by creating an irrefutable proof-of-delivery.

| # | Feature | Description | Size | Priority |
|---|---|---|---|---|
| 4.1 | **TOTP Code Generation** | Generate time-based one-time passwords (RFC 6238) unique to each delivery. 6-digit codes with 5-minute validity window. Codes rotate every 30 seconds. | M | P0 |
| 4.2 | **QR Code Rendering** | Encode TOTP + delivery metadata into QR codes displayed on sender/recipient screens. QR contains: delivery ID, TOTP seed, timestamp, package hash. | S | P0 |
| 4.3 | **Pickup Handshake (Sender → Courier)** | Sender displays QR code. Courier scans with app camera. Server validates TOTP, records GPS + timestamp. Package status transitions to "In Transit." Generates custody receipt. | L | P0 |
| 4.4 | **Delivery Handshake (Courier → Recipient)** | Courier presents QR code (generated from delivery-specific TOTP). Recipient scans or enters 6-digit code manually (for recipients without smartphones). Server validates and records proof-of-delivery. | L | P0 |
| 4.5 | **Tamper-Evident Audit Trail** | Every handshake event is logged with cryptographic hash chaining (each event includes hash of previous event). Creates immutable delivery timeline. Exportable as PDF custody report for merchants. | L | P1 |

---

## Epic 5: Payment & Staking

> **Goal:** Handle all money flows — sender payments, courier payouts, merchant billing, and collateral stake management — with security, compliance, and transparency.

| # | Feature | Description | Size | Priority |
|---|---|---|---|---|
| 5.1 | **Sender Payment Processing** | Stripe payment intent created at match confirmation. Card charged when delivery confirmed. Supports Apple Pay, Google Pay, and saved cards. PCI DSS compliant (Stripe handles). | L | P0 |
| 5.2 | **Courier Payout System** | 85% of delivery fee paid to courier. Configurable payout schedule: instant (£0.25 fee), daily batch (free), or weekly. Uses Stripe Connect for compliant payouts. | L | P0 |
| 5.3 | **Stake Escrow Management** | £50 courier stakes held in Stripe escrow. Automatic deductions for proven fraud/damage (via dispute resolution). Full refund on clean account closure (14-day processing). Dashboard shows stake balance and history. | M | P0 |
| 5.4 | **Merchant Aggregated Billing** | Monthly invoice for B2B merchants. Aggregates: SaaS subscription + per-drop delivery fees. Net-30 payment terms. Auto-generated PDF invoices. Stripe Billing for recurring subscriptions. | M | P1 |
| 5.5 | **Refund & Dispute Escrow** | Disputed deliveries trigger payment hold. Funds held in escrow until resolution (max 7 days). Automated refund for clear-cut cases (courier no-show, TOTP never validated). Manual review for complex disputes. | M | P1 |

---

## Epic 6: B2B Merchant Dashboard

> **Goal:** Provide merchants with a professional SaaS dashboard that makes Local-Logistics Protocol their default delivery infrastructure — replacing ad-hoc courier arrangements with a managed service.

| # | Feature | Description | Size | Priority |
|---|---|---|---|---|
| 6.1 | **Merchant Onboarding Flow** | Self-serve registration: business name, address, category (pharmacy, hardware, etc.), company number (Companies House lookup). KYB verification. Stripe billing setup. | M | P1 |
| 6.2 | **Batch Dispatch Queue** | Upload CSV or enter multiple deliveries manually. Queue shows status of all pending, active, and completed deliveries. Bulk actions: cancel, reschedule, re-dispatch. | L | P1 |
| 6.3 | **Real-Time Delivery Tracking** | Live map view showing all active deliveries. Status timeline for each: Created → Matched → Picked Up → In Transit → Delivered. Push/email notifications at each stage. | L | P1 |
| 6.4 | **Analytics & Reporting** | Dashboard showing: deliveries/day, average delivery time, cost per drop, courier ratings, busiest hours, delivery heatmap. Monthly PDF report auto-generated. Date range filters. | L | P2 |
| 6.5 | **API Access & Webhooks** | REST API for POS/inventory integration. Endpoints: create delivery, get status, list history. Webhooks for status changes. API keys managed in dashboard. Rate-limited. Swagger docs. | L | P2 |

---

## Epic 7: Rating & Trust

> **Goal:** Build a robust trust system that rewards reliable behaviour and progressively increases privileges for high-trust users — creating a self-policing network.

| # | Feature | Description | Size | Priority |
|---|---|---|---|---|
| 7.1 | **Post-Delivery Rating** | Both sender and courier rate each other (1-5 stars + optional comment). Mandatory before next delivery can be created/accepted. Ratings displayed publicly (average of last 50). | M | P0 |
| 7.2 | **Trust Score Algorithm** | Composite score (0-100) based on: rating average (40%), completion rate (25%), disputes (20%), account age (10%), stake amount (5%). Recalculated after every delivery. | M | P1 |
| 7.3 | **Trust Tier System** | Bronze (0-30 deliveries): Standard matching. Silver (30-100): Priority matching, reduced stake. Gold (100+): Premium jobs, merchant dedicated pools, stake reduction to £25. | M | P1 |
| 7.4 | **Automated Flagging & Suspension** | Auto-flag accounts: <3.5 star average (last 20), >15% cancellation rate, or 2+ disputes in 30 days. Flagged accounts receive warning → temporary suspension → permanent ban. | M | P1 |
| 7.5 | **Dispute Resolution Workflow** | In-app dispute filing with evidence upload (photos, screenshots). 72-hour resolution SLA. Three tiers: automated (clear-cut), human review (ambiguous), arbitration (escalated). | L | P1 |

---

## Epic 8: Admin & Analytics

> **Goal:** Give the operations team full visibility and control over the platform — user management, financial oversight, operational metrics, and system health monitoring.

| # | Feature | Description | Size | Priority |
|---|---|---|---|---|
| 8.1 | **Admin User Management** | View/search all users (couriers, senders, merchants). Edit profiles, suspend/ban accounts, reset passwords, view activity logs. Role-based access (admin, support, viewer). | M | P1 |
| 8.2 | **Operational Dashboard** | Real-time metrics: active deliveries, couriers online, average match time, delivery success rate, revenue today/week/month. Alerting for anomalies (e.g., match time > 10 min). | L | P1 |
| 8.3 | **Financial Dashboard** | Revenue breakdown (platform fees vs SaaS), payout summary, outstanding stakes, dispute escrow balance, monthly P&L auto-generated. Integrates with Xero/QuickBooks. | L | P2 |
| 8.4 | **Content & Configuration Management** | Manage service zones (draw on map), set rate floors/ceilings, configure matching weights, manage notification templates, toggle feature flags. No code deploys required for config changes. | M | P2 |
| 8.5 | **Audit & Compliance Reports** | Generate compliance reports: GDPR data requests, KYC verification status, stake balances, delivery chain-of-custody exports. Exportable as CSV/PDF. Scheduled auto-reports. | M | P2 |

---

## Epic Dependency Map

```
Epic 1: Courier Onboarding ──────────────────┐
                                              │
Epic 2: Sender Package Creation ──────────────┤
                                              ▼
                                    Epic 3: Matching Engine
                                              │
                                              ▼
                                    Epic 4: TOTP Handshake
                                              │
                                              ▼
                                    Epic 5: Payment & Staking
                                              │
                                    ┌─────────┴─────────┐
                                    ▼                   ▼
                          Epic 7: Rating         Epic 6: B2B Dashboard
                                    │                   │
                                    └─────────┬─────────┘
                                              ▼
                                    Epic 8: Admin & Analytics
```

---

## Epic Priority Matrix

| Epic | Priority | MVP Required? | Sprint Target |
|---|---|---|---|
| 1. Courier Onboarding | P0 | ✅ Yes | Sprint 1-2 |
| 2. Sender Package Creation | P0 | ✅ Yes | Sprint 1-2 |
| 3. Matching Engine | P0 | ✅ Yes | Sprint 2-3 |
| 4. TOTP Handshake | P0 | ✅ Yes | Sprint 3-4 |
| 5. Payment & Staking | P0 | ✅ Yes | Sprint 3-4 |
| 6. B2B Merchant Dashboard | P1 | Partial | Sprint 5-6 |
| 7. Rating & Trust | P1 | Basic version | Sprint 4-5 |
| 8. Admin & Analytics | P1 | Basic version | Sprint 5-6 |

---

*Features are refined in sprint planning. Acceptance criteria are defined in user_stories.md. Technical specifications are in engineering_roadmap.md.*
