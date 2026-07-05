# Sprint Planning — Local-Logistics Protocol

> Last updated: July 2026 | 6 Sprints, 12 Weeks to MVP + Beta Launch

---

## Sprint Overview

| Sprint | Duration | Theme | Key Deliverables |
|---|---|---|---|
| **Sprint 1** | Weeks 1-2 | Foundation & Auth | User registration, database schema, API scaffold |
| **Sprint 2** | Weeks 3-4 | Core Flows | Package creation, courier profiles, matching engine v1 |
| **Sprint 3** | Weeks 5-6 | Handshake Protocol | TOTP system, QR codes, pickup/delivery handshakes |
| **Sprint 4** | Weeks 7-8 | Payments & Staking | Stripe integration, escrow, courier payouts |
| **Sprint 5** | Weeks 9-10 | B2B Dashboard & Trust | Merchant portal, rating system, basic analytics |
| **Sprint 6** | Weeks 11-12 | Launch Prep | Admin panel, bug fixes, security audit, beta launch |

---

## Velocity Assumptions

| Parameter | Value | Notes |
|---|---|---|
| Team size (Sprint 1-2) | 2 engineers | Founder + Full-Stack Engineer #1 |
| Team size (Sprint 3-6) | 3 engineers | + Full-Stack Engineer #2 |
| Sprint duration | 2 weeks (10 working days) | Monday-Friday |
| Story points per engineer per sprint | 15-18 SP | Conservative for new team |
| Total velocity (Sprint 1-2) | 30-36 SP | 2 engineers |
| Total velocity (Sprint 3-6) | 45-54 SP | 3 engineers |
| Definition of Done | Code reviewed, tests passing, deployed to staging | — |

---

## Sprint 1: Foundation & Auth (Weeks 1-2)

**Sprint Goal:** All users can register, authenticate, and we have a deployable backend with database schema.

### Stories

| Story | Epic | Points | Assignee | Priority |
|---|---|---|---|---|
| S-01: Sender account registration | E1 | 5 | Engineer 1 | P0 |
| C-01: Courier registration + KYC upload | E1 | 8 | Founder | P0 |
| C-01: Selfie liveness check integration | E1 | 5 | Founder | P0 |
| Database schema V1 (Users, Packages, Matches) | Infra | 5 | Engineer 1 | P0 |
| API scaffold (Express/Fastify + auth middleware) | Infra | 5 | Engineer 1 | P0 |
| CI/CD pipeline (GitHub Actions → staging) | Infra | 3 | Founder | P0 |
| SMS OTP service (Twilio integration) | E1 | 3 | Founder | P0 |
| **Sprint Total** | | **34 SP** | | |

### Definition of Done — Sprint 1
- [ ] Users can register as Sender or Courier via phone OTP
- [ ] Couriers can upload ID document and complete selfie check
- [ ] PostgreSQL database running with core schema
- [ ] REST API serving from staging environment
- [ ] CI/CD deploying on every merge to main

### Dependencies
- Twilio account configured (pre-sprint)
- Onfido/Veriff API key obtained (pre-sprint)
- AWS/GCP infrastructure provisioned (pre-sprint)

---

## Sprint 2: Core Flows (Weeks 3-4)

**Sprint Goal:** Senders can create delivery requests and see courier quotes. Couriers can browse and accept jobs.

### Stories

| Story | Epic | Points | Assignee | Priority |
|---|---|---|---|---|
| S-02: Package creation form | E2 | 5 | Engineer 1 | P0 |
| S-03: View courier quotes | E2 | 5 | Engineer 1 | P0 |
| C-03: Courier rate setting | E3 | 3 | Founder | P0 |
| C-04: Browse available jobs (feed) | E3 | 5 | Founder | P0 |
| C-05: Accept job + navigation link | E3 | 3 | Founder | P0 |
| 3.1: Geo-proximity matching (PostGIS) | E3 | 8 | Engineer 1 | P0 |
| 3.3: Multi-factor ranking algorithm | E3 | 5 | Founder | P0 |
| S-02: Address autocomplete (Mapbox) | E2 | 3 | Engineer 1 | P1 |
| **Sprint Total** | | **37 SP** | | |

### Definition of Done — Sprint 2
- [ ] Sender creates delivery with addresses and package details
- [ ] Matching engine finds couriers within radius and ranks them
- [ ] Courier sees job feed and can accept a job
- [ ] Accepted job shows navigation to pickup
- [ ] End-to-end flow works in staging (minus handshake and payment)

### Dependencies
- Sprint 1 complete (auth, database)
- Mapbox/Google Places API key (pre-sprint)
- PostGIS extension installed on database

---

## Sprint 3: Handshake Protocol (Weeks 5-6)

**Sprint Goal:** The TOTP handshake protocol is fully functional — cryptographic proof of pickup and delivery.

### Stories

| Story | Epic | Points | Assignee | Priority |
|---|---|---|---|---|
| 4.1: TOTP code generation (RFC 6238) | E4 | 5 | Engineer 2 | P0 |
| 4.2: QR code rendering | E4 | 3 | Engineer 2 | P0 |
| S-06: Pickup handshake (sender → courier) | E4 | 8 | Engineer 2 | P0 |
| C-06: Courier QR scanner | E4 | 5 | Founder | P0 |
| C-08: Delivery handshake (courier → recipient) | E4 | 8 | Founder | P0 |
| 4.5: Tamper-evident audit trail | E4 | 5 | Engineer 2 | P1 |
| S-05: Real-time delivery tracking (map) | E2 | 8 | Engineer 1 | P0 |
| C-07: Navigation to drop-off | E3 | 3 | Engineer 1 | P1 |
| S-12: In-app chat (WebSocket) | E2 | 5 | Engineer 1 | P1 |
| **Sprint Total** | | **50 SP** | | |

### Definition of Done — Sprint 3
- [ ] TOTP codes generate correctly (RFC 6238 compliant)
- [ ] QR codes display on sender/courier screens
- [ ] Scanning QR transitions delivery status (Picked Up / Delivered)
- [ ] GPS and timestamps recorded at each handshake
- [ ] Audit trail shows full chain-of-custody
- [ ] Live tracking shows courier position on map

### Dependencies
- Sprint 2 complete (matching, job acceptance)
- Camera permissions configured for mobile
- WebSocket infrastructure (Socket.io or similar)

### Risks
- Camera/QR scanning UX across device types — test on 5+ devices
- TOTP timing synchronization between client and server

---

## Sprint 4: Payments & Staking (Weeks 7-8)

**Sprint Goal:** Money flows work — senders pay, couriers receive payouts, stakes are managed.

### Stories

| Story | Epic | Points | Assignee | Priority |
|---|---|---|---|---|
| 5.1: Sender payment processing (Stripe) | E5 | 8 | Engineer 2 | P0 |
| 5.2: Courier payout system (Stripe Connect) | E5 | 8 | Engineer 2 | P0 |
| C-02: Collateral stake deposit | E5 | 5 | Engineer 2 | P0 |
| 5.3: Stake escrow management | E5 | 5 | Founder | P0 |
| S-04: Confirm and pay flow | E5 | 3 | Engineer 1 | P0 |
| C-09: View earnings dashboard | E5 | 5 | Engineer 1 | P1 |
| S-07: Delivery confirmation + receipt | E2 | 3 | Engineer 1 | P1 |
| S-10: Cancel delivery + refund | E5 | 5 | Founder | P1 |
| 5.5: Refund & dispute escrow | E5 | 5 | Founder | P1 |
| **Sprint Total** | | **47 SP** | | |

### Definition of Done — Sprint 4
- [ ] Sender's card charged at delivery confirmation
- [ ] Courier receives payout (85% of delivery fee) on schedule
- [ ] £50 stake collected and held in escrow
- [ ] Cancellation triggers appropriate refund
- [ ] Earnings dashboard shows real-time income data
- [ ] All financial flows use Stripe test mode (live mode in Sprint 6)

### Dependencies
- Sprint 3 complete (handshake confirms delivery)
- Stripe account verified for Connect payouts
- Stripe Connect onboarding for courier accounts

### Risks
- Stripe Connect onboarding complexity for individual couriers
- PSD2/SCA compliance for card payments

---

## Sprint 5: B2B Dashboard & Trust (Weeks 9-10)

**Sprint Goal:** Merchant dashboard functional for B2B customers. Rating and trust system live.

### Stories

| Story | Epic | Points | Assignee | Priority |
|---|---|---|---|---|
| M-01: Merchant registration + KYB | E6 | 5 | Engineer 2 | P1 |
| M-02: Create single delivery (merchant) | E6 | 3 | Engineer 2 | P1 |
| M-04: Track active deliveries dashboard | E6 | 8 | Engineer 1 | P1 |
| 6.2: Batch dispatch queue (CSV upload) | E6 | 8 | Engineer 2 | P1 |
| S-08 / C-11: Post-delivery rating | E7 | 5 | Founder | P0 |
| 7.2: Trust score algorithm | E7 | 5 | Founder | P1 |
| 7.4: Automated flagging & suspension | E7 | 5 | Founder | P1 |
| 5.4: Merchant aggregated billing | E5 | 5 | Engineer 1 | P1 |
| M-06: Basic analytics dashboard | E6 | 5 | Engineer 1 | P2 |
| **Sprint Total** | | **49 SP** | | |

### Definition of Done — Sprint 5
- [ ] Merchants can register and create deliveries
- [ ] CSV batch upload parses and dispatches multiple deliveries
- [ ] Merchant dashboard shows live delivery tracking
- [ ] Both parties rate each other after delivery
- [ ] Trust scores calculated and displayed
- [ ] Low-rated accounts auto-flagged

### Dependencies
- Sprint 4 complete (payments work for merchants)
- Companies House API integration for KYB
- Stripe Billing configured for subscriptions

---

## Sprint 6: Launch Prep (Weeks 11-12)

**Sprint Goal:** Platform is production-ready. Admin tools functional. Security audit passed. Beta launch.

### Stories

| Story | Epic | Points | Assignee | Priority |
|---|---|---|---|---|
| A-01: Admin platform dashboard | E8 | 5 | Engineer 1 | P1 |
| A-02: Admin user management | E8 | 5 | Founder | P1 |
| A-03: Service zone management (map) | E8 | 5 | Engineer 1 | P1 |
| A-04: Dispute review queue | E8 | 5 | Engineer 2 | P1 |
| Security audit + penetration testing | Infra | 8 | External | P0 |
| Stripe live mode activation | Infra | 3 | Founder | P0 |
| Performance testing (load test) | Infra | 3 | Engineer 2 | P0 |
| Bug fixes & polish | All | 10 | All | P0 |
| S-09: Delivery history | E2 | 3 | Engineer 1 | P1 |
| C-10: Availability toggle | E1 | 3 | Engineer 2 | P1 |
| **Sprint Total** | | **50 SP** | | |

### Definition of Done — Sprint 6
- [ ] Admin can view dashboard, manage users, review disputes
- [ ] Service zones configured for UCL/Bloomsbury
- [ ] Security audit completed with no critical/high findings
- [ ] Stripe live mode enabled and tested
- [ ] Load test passed: 100 concurrent deliveries
- [ ] All critical bugs resolved
- [ ] Beta launch to 50 users

### Dependencies
- Sprint 5 complete
- Security audit vendor contracted (book 2 weeks in advance)
- Stripe live account approved
- Beta test users recruited (25 senders + 25 couriers)

---

## Sprint Velocity Tracking Template

| Sprint | Planned SP | Completed SP | Velocity | Carryover |
|---|---|---|---|---|
| Sprint 1 | 34 | — | — | — |
| Sprint 2 | 37 | — | — | — |
| Sprint 3 | 50 | — | — | — |
| Sprint 4 | 47 | — | — | — |
| Sprint 5 | 49 | — | — | — |
| Sprint 6 | 50 | — | — | — |

---

## Sprint Ceremonies

| Ceremony | Cadence | Duration | Participants |
|---|---|---|---|
| Sprint Planning | Day 1 of sprint | 2 hours | All engineers + founder |
| Daily Standup | Daily (async on Slack) | 15 min | All engineers |
| Sprint Review / Demo | Last day of sprint | 1 hour | All team + stakeholders |
| Sprint Retrospective | Last day of sprint | 30 min | All engineers |
| Backlog Grooming | Mid-sprint | 1 hour | Founder + tech lead |

---

## Post-MVP Sprints (Weeks 13+)

| Sprint | Theme | Key Features |
|---|---|---|
| Sprint 7-8 | **Mobile Excellence** | Native mobile app (courier), push notifications, offline support |
| Sprint 9-10 | **B2B Advanced** | Merchant API, webhooks, branded tracking pages |
| Sprint 11-12 | **Growth & Scale** | Referral system, advanced analytics, multi-zone support |
| Sprint 13-14 | **Enterprise** | Enterprise tier, SLA management, dedicated couriers |

---

*Sprint plans are adjusted at the start of each sprint based on actual velocity. Story points are re-estimated if scope changes. Carryover stories get priority in the next sprint.*
