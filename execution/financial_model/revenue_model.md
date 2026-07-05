# Revenue Model — Local-Logistics Protocol

> Last updated: July 2026 | Version 2.0

---

## Executive Summary

Local-Logistics Protocol generates revenue through two complementary streams designed to compound: a **transactional platform fee** on every delivery and a **recurring B2B SaaS subscription** for merchant dashboard access. This dual-stream architecture creates revenue resilience — the transactional stream scales with volume while the SaaS stream provides predictable baseline revenue for financial planning.

---

## Revenue Stream 1: Platform Transaction Fee (15%)

### Mechanism

Couriers set their own delivery rates via the True Marketplace pricing engine. The platform charges a **15% fee on the courier-set rate**, deducted at settlement. This fee funds matching infrastructure, TOTP handshake verification, escrow management, and dispute resolution.

### Pricing Dynamics

| Variable | Value | Notes |
|---|---|---|
| Average courier-set rate | £4.00 | Based on London gig-economy benchmarks for <2km drops |
| Platform fee percentage | 15% | Competitive with Uber Eats (30%), Deliveroo (25-35%) |
| **Platform revenue per drop** | **£0.60** | £4.00 × 15% |
| Average drops per active courier/day | 3.5 | Conservative; Deliveroo riders average 2-4/hr |
| Sender-paid delivery cost | £4.00 | Courier sets rate; sender pays full amount |
| Courier net payout per drop | £3.40 | £4.00 – £0.60 platform fee |

### Why 15% Is Defensible

- **Uber Eats / Deliveroo** charge merchants 25-35% — our 15% is on the courier rate only, not the item value
- **Couriers retain 85%** — significantly better than gig-economy norms (65-75%)
- **True Marketplace compliance** — couriers set rates, we take a fixed commission percentage
- At scale, the 15% fee covers: payment processing (2.5%), insurance reserve (1.5%), infrastructure (3%), margin (8%)

---

## Revenue Stream 2: B2B SaaS Subscription (£49/month)

### Mechanism

Merchants (pharmacies, hardware stores, print shops, dry cleaners) subscribe to access the **Merchant Dashboard** — a SaaS tool providing:

- Real-time delivery tracking and chain-of-custody audit trail
- Batch dispatch queue (upload CSV → auto-match couriers)
- Customer notification engine (SMS/email updates branded to merchant)
- Monthly analytics: delivery times, courier ratings, cost-per-drop
- API access for POS/inventory integration
- Priority matching (merchant jobs surface first in courier feed)
- Aggregated monthly invoicing (no per-drop card processing)

### Pricing Justification

| Benchmark | Monthly Cost | Notes |
|---|---|---|
| Shopify POS | £69/mo | E-commerce SaaS comparison |
| Square for Retail | £60/mo | Retail management SaaS |
| Stuart (B2B delivery) | Variable per-drop | No SaaS layer, pure transactional |
| **Local-Logistics B2B** | **£49/mo** | Undercuts SaaS benchmarks + includes delivery infrastructure |

### Subscription Tiers (Post-MVP)

| Tier | Price | Drops Included | Additional Drop Fee | Target |
|---|---|---|---|---|
| Starter | £49/mo | Up to 100 drops/mo | £0.10 per extra drop | Independent shops |
| Growth | £149/mo | Up to 500 drops/mo | £0.08 per extra drop | Multi-location merchants |
| Enterprise | £499/mo | Unlimited drops | Included | Pharmacy chains, universities |

> **MVP launches with Starter tier only.** Growth and Enterprise tiers are Year 2 features.

---

## Combined Revenue Model — Monthly Projections

### Key Assumptions

| Assumption | Value | Basis |
|---|---|---|
| Launch month | Month 1 (Q1 Year 1) | UCL/Bloomsbury wedge |
| Starting active couriers | 30 | Anchor Courier programme |
| Courier growth rate | 25% MoM (M1-6), 15% MoM (M7-12) | Network effects in dense wedge |
| Starting B2B merchants | 3 | Pre-signed LOIs |
| Merchant growth rate | 2-3 new merchants/month | Field sales team |
| Average drops per courier/day | 2.0 (M1-3), 3.0 (M4-6), 3.5 (M7-12) | Ramp as demand increases |
| Courier active days per month | 15 | Part-time gig workers |
| Monthly courier churn | 12% | Industry average for gig platforms |
| Monthly merchant churn | 5% | B2B SaaS benchmark |
| Platform fee | 15% on £4.00 avg rate = £0.60/drop | — |
| B2B subscription | £49/month | Starter tier |

### Year 1 — Monthly Revenue Projection

| Month | Active Couriers | Drops/Day | Monthly Drops | Platform Fee Rev | B2B Merchants | SaaS Rev | **Total Revenue** |
|---|---|---|---|---|---|---|---|
| M1 | 30 | 60 | 900 | £540 | 3 | £147 | **£687** |
| M2 | 35 | 70 | 1,050 | £630 | 5 | £245 | **£875** |
| M3 | 42 | 84 | 1,260 | £756 | 7 | £343 | **£1,099** |
| M4 | 50 | 150 | 2,250 | £1,350 | 9 | £441 | **£1,791** |
| M5 | 60 | 180 | 2,700 | £1,620 | 11 | £539 | **£2,159** |
| M6 | 72 | 216 | 3,240 | £1,944 | 14 | £686 | **£2,630** |
| M7 | 82 | 287 | 4,305 | £2,583 | 16 | £784 | **£3,367** |
| M8 | 93 | 326 | 4,884 | £2,930 | 18 | £882 | **£3,812** |
| M9 | 105 | 368 | 5,513 | £3,308 | 20 | £980 | **£4,288** |
| M10 | 118 | 413 | 6,195 | £3,717 | 22 | £1,078 | **£4,795** |
| M11 | 132 | 462 | 6,930 | £4,158 | 24 | £1,176 | **£5,334** |
| M12 | 148 | 518 | 7,770 | £4,662 | 26 | £1,274 | **£5,936** |
| **Year 1 Total** | — | — | **46,997** | **£28,198** | — | — | **£36,773** |

### Year 2 — Quarterly Revenue Projection

Assumptions: Expand to 3 London wedges (King's Cross, Shoreditch). Introduce Growth tier. Courier base reaches 500+.

| Quarter | Active Couriers | Monthly Drops | Platform Fee Rev/Qtr | B2B Merchants | SaaS Rev/Qtr | **Quarterly Revenue** |
|---|---|---|---|---|---|---|
| Q1 Y2 | 200 | 10,500 | £18,900 | 35 | £5,145 | **£24,045** |
| Q2 Y2 | 320 | 16,800 | £30,240 | 50 | £8,575 | **£38,815** |
| Q3 Y2 | 450 | 23,625 | £42,525 | 70 | £13,230 | **£55,755** |
| Q4 Y2 | 600 | 31,500 | £56,700 | 95 | £19,355 | **£76,055** |
| **Year 2 Total** | — | **82,425** | **£148,365** | — | **£46,305** | **£194,670** |

> Note: SaaS Rev/Qtr includes a blended average as some merchants upgrade to Growth tier (£149/mo).

### Year 3 — Quarterly Revenue Projection

Assumptions: Operating in 6 London zones + 2 secondary cities (Manchester, Bristol). Enterprise tier live. Series A capital deployed.

| Quarter | Active Couriers | Monthly Drops | Platform Fee Rev/Qtr | B2B Merchants | SaaS Rev/Qtr | **Quarterly Revenue** |
|---|---|---|---|---|---|---|
| Q1 Y3 | 1,200 | 63,000 | £113,400 | 150 | £39,600 | **£153,000** |
| Q2 Y3 | 1,800 | 94,500 | £170,100 | 220 | £60,720 | **£230,820** |
| Q3 Y3 | 2,500 | 131,250 | £236,250 | 300 | £87,000 | **£323,250** |
| Q4 Y3 | 3,200 | 168,000 | £302,400 | 400 | £122,400 | **£424,800** |
| **Year 3 Total** | — | **456,750** | **£822,150** | — | **£309,720** | **£1,131,870** |

---

## Revenue Mix Evolution

| Period | Platform Fee % | SaaS % | Total Revenue |
|---|---|---|---|
| Year 1 | 77% | 23% | £36,773 |
| Year 2 | 76% | 24% | £194,670 |
| Year 3 | 73% | 27% | £1,131,870 |

> **Strategic Target:** SaaS revenue grows as a share over time, improving revenue quality and predictability. Target 35% SaaS by Year 5.

---

## Revenue Risk Factors

| Risk | Impact | Mitigation |
|---|---|---|
| Courier rates race to bottom | Platform fee per drop decreases | Set minimum rate floor (£2.50/drop) |
| Merchant churn above 5%/mo | SaaS base erodes | 3-month onboarding support; annual discount (£470/yr = 2 months free) |
| Seasonality (summer dips) | 20-30% volume drop Jul-Aug | University wedge strategy — pivot to tourist/resident demand |
| Regulatory fee cap | Forced to reduce 15% | Already lowest in market; can absorb down to 10% and remain viable |
| Competitor price war | Pressure on both streams | Differentiate on chain-of-custody trust, not price |

---

## Key Metrics to Track

| Metric | Target (M6) | Target (M12) | Target (Y2) |
|---|---|---|---|
| Monthly Recurring Revenue (MRR) | £686 | £1,274 | £6,452 |
| Gross Transaction Volume (GTV) | £12,960 | £31,080 | £168,000 |
| Platform Take Rate | 15% | 15% | 15% |
| Revenue per Active Courier | £36.50/mo | £40.10/mo | £48.00/mo |
| Merchant ARPU | £49/mo | £49/mo | £68/mo (blended) |
| Net Revenue Retention (NRR) | — | 110% | 125% |

---

*This model is updated quarterly. All projections assume the UCL/Bloomsbury wedge launch and are subject to revision based on actual launch data.*
