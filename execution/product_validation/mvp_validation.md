# MVP Validation Strategy

## 1. The Minimum Viable Product Definition
Our MVP is NOT a full marketplace app. It is a **Concierge MVP** — a manually-operated proof that the core value proposition works before investing in engineering.

### What's IN the MVP
| Feature | Justification |
|---|---|
| WhatsApp-based package request | Zero engineering cost, tests demand |
| Manual courier matching (by founder) | Tests matching logic before building algorithm |
| TOTP QR code handshake (paper-based) | Tests the chain-of-custody protocol with zero app |
| Stripe payment link | Tests willingness to pay without building payment infra |
| £50 courier card hold (manual Stripe auth) | Tests staking acceptance |

### What's OUT of the MVP
| Feature | Why Deferred |
|---|---|
| Native mobile app | Not needed to validate core hypothesis |
| Automated matching algorithm | Manual matching proves the model first |
| B2B merchant dashboard | Enterprise features come after consumer validation |
| Rating system | Trust is validated via staking, not ratings, at MVP |
| Real-time GPS tracking | Adds engineering complexity without validating demand |

## 2. Concierge MVP Plan
- **Week 1-2:** Recruit 10 couriers from UCL campus. Verify KYC manually via Onfido dashboard.
- **Week 3-4:** Recruit 20 senders via UCL Facebook groups. Process requests via WhatsApp.
- **Week 5-8:** Operate 5-10 drops/day manually. Founder matches courier to sender based on route overlap.
- **Success Criteria:** 50 successful drops with <5% failure rate and >70% repeat usage.
- **Kill Criteria:** <20 drops in 4 weeks despite active recruitment. >20% theft/loss rate.

## 3. Wizard of Oz Tests
| Test | What We Fake | What We Measure |
|---|---|---|
| Matching speed | Founder matches manually but tells user "algorithm found a match" | Does the user care about the matching mechanism, or just the result? |
| Pricing | Founder suggests £4.50 but tells courier "you set this rate" | Do couriers actually want to set rates, or prefer fixed? |
| Staking | Founder asks courier to Venmo £50 as deposit | What % of couriers accept the deposit requirement? |

## 4. Graduation Criteria (MVP → Beta)
- 50+ successful drops completed
- <5% package loss/theft rate
- >60% courier retention (Week 4 vs Week 1)
- >40% sender repeat rate
- Average NPS >30
- At least 3 merchants express interest in paid SaaS tier

---

# Feature Prioritization Matrix (RICE Scoring)

| # | Feature | Reach | Impact | Confidence | Effort | RICE Score | Priority |
|---|---|---|---|---|---|---|---|
| 1 | TOTP QR Handshake | 10 | 10 | 9 | 3 | 300 | P0 |
| 2 | Courier Registration + Onfido KYC | 10 | 9 | 9 | 4 | 203 | P0 |
| 3 | Package Creation Flow | 10 | 9 | 9 | 4 | 203 | P0 |
| 4 | PostGIS Route Matching | 8 | 10 | 7 | 6 | 93 | P0 |
| 5 | Stripe Payment (Aggregated) | 10 | 8 | 8 | 5 | 128 | P0 |
| 6 | Collateralized Staking (Card Hold) | 7 | 9 | 7 | 4 | 110 | P1 |
| 7 | Courier Pricing Slider | 8 | 7 | 6 | 3 | 112 | P1 |
| 8 | Push Notifications | 9 | 6 | 9 | 2 | 243 | P1 |
| 9 | In-App Chat (Sender↔Courier) | 6 | 5 | 7 | 5 | 42 | P2 |
| 10 | B2B Merchant Dashboard | 4 | 8 | 6 | 7 | 27 | P2 |
| 11 | Rating & Review System | 7 | 4 | 8 | 3 | 75 | P2 |
| 12 | Courier Earnings Dashboard | 8 | 5 | 8 | 3 | 107 | P1 |
| 13 | Sender Delivery History | 7 | 4 | 9 | 2 | 126 | P1 |
| 14 | Real-Time GPS Tracking | 6 | 6 | 5 | 6 | 30 | P2 |
| 15 | Referral System | 5 | 7 | 5 | 4 | 44 | P2 |
| 16 | Tamper-Evident Bag Ordering | 3 | 3 | 8 | 2 | 36 | P3 |
| 17 | Admin Analytics Dashboard | 2 | 6 | 7 | 5 | 17 | P3 |
| 18 | Multi-language Support | 3 | 3 | 6 | 4 | 14 | P3 |
| 19 | Dark Mode | 8 | 2 | 9 | 1 | 144 | P2 |
| 20 | Apple/Google Pay | 6 | 4 | 7 | 3 | 56 | P2 |

---

# Kano Analysis

## Must-Have (Basic Expectations)
Users will be dissatisfied if these are missing, but not delighted if present.
- Courier identity verification (KYC)
- Secure payment processing
- Package tracking (at least status updates)
- Customer support channel
- Push notifications for match/delivery status

## Performance (Linear Satisfaction)
More of these = more satisfaction. These are the competitive battleground.
- Delivery speed (faster = happier)
- Courier earnings per hour (higher = better retention)
- Matching accuracy (closer route overlap = less detour)
- Price (lower sender price = higher adoption)

## Delighters (Unexpected Value)
Users don't expect these. Their presence creates disproportionate loyalty.
- Carbon savings tracker ("You saved 2.3kg CO2 this month")
- Courier "Streak Rewards" (5 drops in a row = bonus)
- Real-time animated map showing courier walking to you
- "Delivered by LocalLogistics" branded receipt for merchants
- Earn-Your-Stake gamification progress bar

## Indifferent (No Impact)
Features that users neither notice nor care about.
- Blockchain-based receipts
- Multi-currency support (UK-only at launch)
- Desktop web app for couriers

---

# Assumption Mapping

| # | Assumption | Risk | Evidence For | Evidence Against | Validation Method | Status |
|---|---|---|---|---|---|---|
| 1 | Students will carry strangers' packages for £3.50 | CRITICAL | Gig economy adoption is high among students | £3.50 may be below minimum acceptable effort | Concierge MVP: measure signup-to-first-drop conversion | Unvalidated |
| 2 | Couriers will accept a £50 security deposit | CRITICAL | Uber/Bolt require car insurance deposits | Students are cash-poor | Wizard of Oz test with Venmo deposit | Unvalidated |
| 3 | Merchants will pay £49/mo for SaaS delivery | HIGH | Similar SaaS (Stuart) charges more | Independent shops are notoriously cheap | 15 cold calls to UCL-area pharmacies | Unvalidated |
| 4 | TOTP QR handshake is user-friendly | HIGH | QR scanning is mainstream (COVID menus) | Adding a second scan adds friction | Usability test with 10 non-technical users | Unvalidated |
| 5 | Route matching density is achievable in 1-mile radius | CRITICAL | UCL has 40,000+ students in Bloomsbury | Not all students commute through the same corridors | PostGIS simulation with TfL Oyster data | Unvalidated |
| 6 | Aggregated weekly billing is acceptable to senders | MEDIUM | Uber charges post-ride without complaint | Users may want per-trip receipts | Survey of 50 target users | Unvalidated |
| 7 | Package theft rate will be <5% with staking | HIGH | Collateral deters rational actors | Irrational actors or chargeback fraud | Track theft rate during beta | Unvalidated |
| 8 | Local pharmacies need same-day delivery | HIGH | NHS repeat prescriptions are growing | Most pharmacies have their own delivery staff | Interview 10 pharmacy owners | Unvalidated |
| 9 | The app can pass Apple App Store review without persistent background location | MEDIUM | Apple allows "in-use" location | Competitors use background location for tracking | Submit test build to Apple review | Unvalidated |
| 10 | True Marketplace pricing survives UK employment tribunal | CRITICAL | No court has tested this exact model | Uber v Aslam set broad precedent | Legal opinion from employment barrister | Unvalidated |
| 11 | Sender NPS will exceed 30 | MEDIUM | P2P delivery is novel and exciting | Delays and mismatches could frustrate | Measure NPS after first 50 drops | Unvalidated |
| 12 | Couriers can batch 2+ drops per trip | HIGH | Dense urban areas have overlapping routes | Timing alignment is statistically unlikely at low volume | Simulate with synthetic order data | Unvalidated |
| 13 | Onfido KYC completes in <5 minutes | LOW | Onfido advertises 95% auto-approval | Budget Android cameras may fail liveness checks | Test with 20 different phone models | Unvalidated |
| 14 | Stripe aggregated billing reduces fees by >50% | MEDIUM | Math confirms (1 charge vs 10 charges) | Stripe may flag unusual billing patterns | Test with Stripe sandbox | Unvalidated |
| 15 | Viral coefficient >1.0 is achievable via referrals | HIGH | Double-sided incentives work (Uber, Revolut) | Logistics is less viral than fintech | Measure referral rate during beta | Unvalidated |
| 16 | Senders will use tamper-evident bags without complaint | MEDIUM | Amazon uses sealed packaging universally | Extra step in the shipping process adds friction | Observe sender behavior during concierge MVP | Unvalidated |
| 17 | The carbon savings narrative drives adoption | LOW | ESG is trending among Gen Z | Price and speed matter more than sustainability | A/B test marketing with/without green messaging | Unvalidated |
| 18 | B2B field sales can onboard 15 merchants in 90 days | MEDIUM | 1 merchant per week is conservative | Decision-makers are hard to reach | Track conversion funnel during pilot | Unvalidated |
| 19 | Above-ground handshakes are acceptable to users | LOW | Meeting outside is natural | Rain/cold weather may deter | Monitor cancellation rates by weather | Unvalidated |
| 20 | The platform can operate without goods-in-transit insurance | HIGH | We are a software intermediary, not a carrier | Regulators or users may demand it | Legal review + user survey | Unvalidated |

---

# Lean Experiment Backlog

| # | Hypothesis | Experiment | Success Metric | Timeline | Cost | Priority |
|---|---|---|---|---|---|---|
| 1 | Students will sign up as couriers | Post flyers at UCL + Instagram ad | 50 signups in 2 weeks | Week 1-2 | £200 | P0 |
| 2 | Senders will pay £5 for same-day local delivery | Landing page with Stripe checkout | 20 pre-orders in 2 weeks | Week 1-2 | £100 | P0 |
| 3 | Couriers accept £50 staking requirement | Ask first 20 courier signups to Venmo £50 | >50% acceptance rate | Week 3 | £0 | P0 |
| 4 | QR handshake is usable by non-tech users | Paper prototype test with 10 users | >80% complete scan without help | Week 3-4 | £0 | P0 |
| 5 | Pharmacies will pay £49/mo for delivery SaaS | Cold-call 15 pharmacies near UCL | 3+ express strong interest | Week 3-4 | £0 | P1 |
| 6 | Route density exists in Bloomsbury | Map 100 student commute routes via survey | >30% route overlap within 1-mile | Week 2-3 | £50 | P0 |
| 7 | Sender repeat rate >40% | Track repeat usage during concierge MVP | >40% use service twice in 4 weeks | Week 5-8 | £0 | P1 |
| 8 | Carbon messaging increases conversion | A/B test landing page (green vs neutral) | >15% conversion lift | Week 2-4 | £100 | P2 |
| 9 | Referral viral coefficient >0.5 | Launch double-sided referral in beta | Each user refers >0.5 new users | Week 6-8 | £300 | P2 |
| 10 | Courier earnings >£10/hr are achievable | Track earnings/hour during concierge MVP | Average >£10/hr with 2+ drops/hr | Week 5-8 | £0 | P1 |
| 11 | Aggregated billing is accepted | Survey 30 senders on billing preference | >60% prefer weekly over per-trip | Week 4 | £0 | P2 |
| 12 | Package loss rate <5% with staking | Track all drops during concierge MVP | <5% loss/theft | Week 5-8 | £0 | P0 |
| 13 | Merchants prefer API integration over manual dispatch | Interview 5 tech-savvy merchants | >3 want API/POS integration | Week 6-8 | £0 | P2 |
| 14 | Above-ground meeting points are acceptable | Ask 20 users about preferred handover location | >75% accept station exit meeting | Week 4 | £0 | P2 |
| 15 | App Store approves without background location | Submit minimal test build | Approval received | Week 8 | £99 | P1 |

---

# Success Metrics & North Star

## North Star Metric
**Successful Drops Per Day** — This single metric captures supply-side health (courier availability), demand-side health (sender volume), and platform reliability (completion rate) simultaneously.

## Pirate Metrics (AARRR)

| Stage | Metric | Month 1 | Month 3 | Month 6 | Month 12 |
|---|---|---|---|---|---|
| **Acquisition** | App Downloads | 200 | 1,000 | 5,000 | 25,000 |
| **Activation** | First Drop Completed (% of downloads) | 15% | 20% | 25% | 30% |
| **Retention** | Monthly Active Users (senders) | 30 | 150 | 750 | 3,750 |
| **Revenue** | Monthly Revenue | £180 | £2,700 | £27,000 | £202,500 |
| **Referral** | Viral Coefficient | 0.2 | 0.5 | 0.8 | 1.2 |

## Key Performance Indicators

| KPI | Target | Measurement |
|---|---|---|
| Drops/Day | 10 → 200 → 500 (M1/M6/M12) | Backend analytics |
| Courier Retention (30-day) | >60% | Cohort analysis |
| Sender Repeat Rate | >40% | Cohort analysis |
| Average Delivery Time | <45 minutes | GPS timestamp delta |
| Package Loss Rate | <2% | Incident reports |
| NPS (Sender) | >40 | In-app survey |
| NPS (Courier) | >30 | In-app survey |
| CAC (Sender) | <£8 | Marketing spend / new senders |
| LTV (Sender) | >£40 | Revenue per user over lifetime |
| LTV:CAC Ratio | >5:1 | Calculated |
