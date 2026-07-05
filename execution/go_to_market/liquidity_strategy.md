# Marketplace Liquidity Strategy — Local-Logistics Protocol

## The Liquidity Problem

Local-Logistics is a **hyperlocal two-sided marketplace** connecting senders (demand) and couriers (supply). The fundamental challenge: senders won't use a platform with no couriers, and couriers won't join a platform with no deliveries.

This is the **chicken-and-egg problem**, and it kills more marketplaces than any competitor ever will.

Our solution: **concentrated geographic density + supply-first bootstrapping + structured liquidity thresholds.**

---

## 1. Defining Liquidity

### 1.1 What Is Marketplace Liquidity?

Liquidity = the probability that a user's intent is fulfilled within an acceptable time frame.

| User | Intent | Liquidity = Fulfilled When |
|------|--------|---------------------------|
| Sender | "I want to send a package" | A courier accepts within 5 minutes |
| Courier | "I want to earn money" | A drop is available within 10 minutes of going online |
| Merchant | "I want to dispatch an order" | A courier arrives within 8 minutes of tapping "dispatch" |

### 1.2 Liquidity Metrics

| Metric | Definition | Target | Minimum Viable |
|--------|-----------|--------|----------------|
| **Time-to-Match** | Seconds from sender request to courier acceptance | < 120 sec | < 300 sec |
| **Courier Utilisation** | % of online time spent on active drops | 40–60% | ≥ 25% |
| **Request Fill Rate** | % of sender requests that get matched to a courier | ≥ 95% | ≥ 80% |
| **Courier Idle Time** | Minutes between drops for an online courier | < 15 min | < 25 min |
| **Sender Wait Time** | Minutes from request to courier at door (pickup) | < 8 min | < 15 min |

### 1.3 The Liquidity Death Spiral

```
Low courier supply
    │
    ▼
Long wait times for senders ──→ Senders churn
    │
    ▼
Fewer drops available ──→ Couriers earn less
    │
    ▼
Couriers churn ──→ Even lower supply
    │
    ▼
Even longer wait times ──→ More sender churn
    │
    ▼
💀 MARKETPLACE DEATH
```

**Our entire launch strategy is designed to prevent this spiral from ever starting.**

---

## 2. Concentration Strategy

### 2.1 The 1-Mile Radius Thesis

Most failed hyperlocal marketplaces (Homejoy, Washio, SpoonRocket) launched across entire cities simultaneously. This creates the illusion of coverage with no actual density.

**Our approach: compress all supply and demand into a 1-mile radius until it's bursting with activity, then expand.**

| Metric | City-Wide Launch (10-mile radius) | Concentrated Launch (1-mile radius) |
|--------|-----------------------------------|-------------------------------------|
| Area covered | 314 mi² | 3.14 mi² |
| Density factor | 1x | **100x** |
| Couriers needed for 5-min pickup | 500+ | 8–12 |
| Senders needed for courier utilisation | 5,000+ | 50–100 |
| Marketing efficiency | Scattered, low impression density | Hyper-targeted, high impression density |
| Brand awareness | Diluted | "Everyone in Bloomsbury knows us" |

### 2.2 Why UCL / Bloomsbury

| Factor | Score | Reasoning |
|--------|-------|-----------|
| Population density | ⭐⭐⭐⭐⭐ | 43,000 students + 15,000 local residents in 1 mi² |
| Package demand | ⭐⭐⭐⭐ | Students send documents, keys, forgotten items constantly |
| Merchant density | ⭐⭐⭐⭐ | 23 pharmacies, 8 print shops, 15+ independent shops |
| Courier supply | ⭐⭐⭐⭐⭐ | Massive student population seeking flexible work |
| Walkability | ⭐⭐⭐⭐⭐ | Flat terrain, pedestrian-friendly, cycle infrastructure |
| Competitor presence | ⭐⭐⭐ | No direct competitor doing TOTP-secured hyperlocal |
| Expansion adjacency | ⭐⭐⭐⭐ | King's Cross, Islington, Camden all border the zone |

### 2.3 Density Thresholds

| Metric | Minimum Viable Density | Target Density | Current London Avg (Deliveroo) |
|--------|----------------------|---------------|------------------------------|
| Couriers per mi² | 5 (during peak) | 15 | ~8 |
| Active senders per mi² | 30 | 100+ | ~50 |
| Merchants per mi² | 3 | 10 | ~12 |
| Drops per mi² per day | 10 | 50 | ~30 |

**In a 1-mile radius (3.14 mi²), we need just 15 peak couriers to achieve minimum viable density. That's achievable in Week 1.**

---

## 3. Supply-First vs Demand-First Analysis

### 3.1 The Debate

| Approach | Description | Pros | Cons |
|----------|-------------|------|------|
| **Supply-first** | Recruit couriers before senders | Ensures instant pickup when demand arrives; no wait times | Couriers churn if no drops; expensive guarantees |
| **Demand-first** | Build sender waitlist before recruiting couriers | Ensures couriers have work immediately; no idle time | Senders experience long waits at launch; bad first impression |
| **Hybrid** | Build both simultaneously with timing controls | Balances both sides; can adjust ratios | Complex to execute; requires real-time monitoring |

### 3.2 Our Decision: Supply-First with Demand Staging

**We choose supply-first** for three reasons:

1. **First impressions are permanent:** A sender who requests a delivery and waits 30 minutes will never come back. A courier who waits 30 minutes for a drop will be frustrated but will try again if guaranteed earnings are in place.

2. **Supply is easier to subsidise:** Guaranteed earnings (£10–12/hr) during idle periods is a known, budgetable cost. Subsidising demand (free deliveries) is open-ended and doesn't guarantee retention.

3. **Supply creates demand signals:** Couriers walking around with branded bags, sharing earnings on social media, and telling friends creates organic demand. Senders sitting at home do not create supply.

### 3.3 Supply-First Execution Plan

```
Week -4:  Recruit & KYC 30 couriers
              │ (0 demand — just building the pool)
              │
Week -2:  Activate 10 couriers on "standby" shifts
              │ (£10/hr guarantee; they walk around the zone, familiarise)
              │
Week 0:   Launch demand (50 beta senders)
              │ Couriers already positioned → instant 5-min pickup
              │ Sender first experience = magical
              │
Week 1-2: Add 10 more couriers
              │ Demand growing → courier utilisation improving
              │ Guarantee cost declining as organic drops increase
              │
Week 3-4: Guarantee cost → £0 as supply/demand balance
              │ Couriers earning organically from drops alone
              │ Flywheel spinning: more drops → more couriers → faster pickups → more senders
```

### 3.4 Supply/Demand Ratio Targets

| Week | Active Couriers | Active Senders | Supply:Demand Ratio | Courier Util. | Guarantee Cost |
|------|----------------|---------------|--------------------|----|-------|
| 0 | 10 | 10 | 1.0 | 15% | £400/wk |
| 1 | 15 | 20 | 0.75 | 25% | £350/wk |
| 2 | 18 | 35 | 0.51 | 35% | £250/wk |
| 3 | 22 | 50 | 0.44 | 45% | £150/wk |
| 4 | 25 | 65 | 0.38 | 55% | £50/wk |
| 6 | 30 | 100 | 0.30 | 60% | £0 |
| 8 | 40 | 150 | 0.27 | 65% | £0 |

**Ideal steady-state ratio: 0.25–0.35 (1 courier per 3–4 senders)**

---

## 4. Chicken-and-Egg Solution

### 4.1 Strategic Framework

We solve the chicken-and-egg problem through **four simultaneous tactics:**

```
┌─────────────────────────────────────────────────────────────────┐
│                    CHICKEN-AND-EGG SOLUTION                     │
│                                                                 │
│  ┌─────────────┐  ┌─────────────┐  ┌───────────┐  ┌──────────┐ │
│  │ 1. SEED     │  │ 2. ANCHOR   │  │ 3. FAKE   │  │ 4. CROSS │ │
│  │ SUPPLY      │  │ TENANTS     │  │ DEMAND    │  │ NETWORK  │ │
│  │             │  │             │  │           │  │          │ │
│  │ Pre-recruit │  │ Merchants   │  │ Internal  │  │ Sender's │ │
│  │ couriers    │  │ provide     │  │ test      │  │ recipient│ │
│  │ with        │  │ baseline    │  │ drops to  │  │ becomes  │ │
│  │ guaranteed  │  │ recurring   │  │ bootstrap │  │ a sender │ │
│  │ earnings    │  │ drops       │  │ activity  │  │          │ │
│  └─────────────┘  └─────────────┘  └───────────┘  └──────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

### 4.2 Tactic 1: Seed Supply

**What:** Pre-recruit 30 couriers before any demand exists. Pay guaranteed minimum (£10–12/hr) during standby shifts.

**Cost:** £2,400 total over 4 weeks (declining as organic drops increase)

**Why it works:** When the first sender requests a delivery, there's already a courier 3 minutes away. The sender's first experience is magic — not frustration.

### 4.3 Tactic 2: Anchor Tenants (Merchants)

**What:** Onboard 5–10 merchants who provide **baseline recurring demand** regardless of individual sender activity.

| Merchant Type | Expected Weekly Dispatches | Revenue per Dispatch |
|--------------|--------------------------|---------------------|
| Pharmacy (prescriptions) | 15–25 | £4.50 avg |
| Print shop (documents) | 8–12 | £3.50 avg |
| Convenience store | 5–8 | £3.00 avg |
| **Total baseline (5 merchants)** | **40–60 drops/week** | — |

**Why it works:** Merchants provide predictable, recurring demand that keeps couriers fed even on slow sender days. A pharmacy dispatching 4 prescriptions/day creates enough work for 1 courier for 2 hours.

**Key insight:** Merchants are the **single most important liquidity lever.** Each merchant generates steady demand without marketing spend. Acquiring 10 merchants is equivalent to acquiring 50+ individual senders in terms of drop volume.

### 4.4 Tactic 3: Manufactured Demand

**What:** In the first 2 weeks, the founding team creates real drops to simulate demand and train couriers.

| Activity | Frequency | Purpose |
|----------|-----------|---------|
| Founder sends packages to friends/family in zone | 3–5/day | Real drops for couriers to practice |
| Team members send items between themselves | 2–3/day | Test edge cases, timing |
| "Mystery shopper" drops | 1–2/day | Quality check on courier experience |

**Cost:** ~£200/week (delivery fees paid by company)

**Why it works:** Couriers get real practice and real earnings. The platform shows activity even before organic demand materialises. This is not "fake" — these are real packages, real deliveries, real payments.

**Exit:** Phase out by Week 3 as organic demand exceeds manufactured demand.

### 4.5 Tactic 4: Cross-Network Effects

**What:** Every delivery creates a new potential user (the recipient). Design the product so recipients naturally become senders.

- Recipient receives tracking SMS → sees product in action → prompted to download
- Recipient rates delivery → prompted to "send something yourself"
- Recipient tells friends about the experience → organic word-of-mouth

**This is the only tactic that scales infinitely at zero marginal cost.** See [Viral Loops](viral_loops.md) for detailed analysis.

---

## 5. Liquidity Flywheel

### 5.1 The Virtuous Cycle

```
More Couriers  ──→  Faster Pickup Times  ──→  Better Sender Experience
     ↑                                              │
     │                                              ▼
Higher Courier     ←──  More Drops/Hour  ←──  More Senders
  Earnings                                    More Merchants
     │                                              │
     ▼                                              │
More Courier       ──→  Lower CAC         ←────────┘
  Retention             (viral growth)
```

### 5.2 Flywheel Stages

| Stage | State | Action | Duration |
|-------|-------|--------|----------|
| **1. Cold Start** | No liquidity; everything manual | Seed supply, anchor tenants, manufactured demand | Weeks -4 to 2 |
| **2. Spark** | First organic drops; supply/demand finding balance | Monitor ratios; adjust guarantees; push merchant volume | Weeks 3–6 |
| **3. Ignition** | Self-sustaining at low volume; guarantees → £0 | Shift to growth; add marketing channels; referral launch | Weeks 7–12 |
| **4. Flywheel** | Supply creates demand creates supply; K approaching 1.0 | Expand zone; reduce CAC; optimise matching | Weeks 13–24 |
| **5. Orbit** | Self-sustaining growth; unit economics strong | Geographic expansion; new verticals; fundraise | Month 7+ |

### 5.3 Leading Indicators of Liquidity Health

| Indicator | Healthy | Warning | Critical |
|-----------|---------|---------|----------|
| Time-to-match | < 2 min | 2–5 min | > 5 min |
| Request fill rate | > 95% | 85–95% | < 85% |
| Courier utilisation | 40–65% | 25–40% | < 25% |
| Courier idle time | < 12 min | 12–20 min | > 20 min |
| Sender repeat rate (week-over-week) | > 30% | 20–30% | < 20% |
| Daily drop volume growth | > 5% week-over-week | 0–5% | Negative |

---

## 6. Liquidity Levers

### 6.1 Emergency Supply Interventions

If demand exceeds supply (sender wait > 10 minutes):

| Lever | Speed | Cost | Duration |
|-------|-------|------|----------|
| Push notification to offline couriers: "High demand right now — earn £5+ this hour" | Immediate | £0 | Real-time |
| Surge pricing: +30% delivery fee (courier earns more) | Immediate | £0 (market-priced) | Until supply normalises |
| Activate standby couriers on guaranteed earnings | 15 min | £10/hr per courier | 2-hour blocks |
| Emergency courier recruitment blast (WhatsApp groups) | 24 hrs | £0 | One-time |

### 6.2 Emergency Demand Interventions

If supply exceeds demand (courier utilisation < 20%):

| Lever | Speed | Cost | Duration |
|-------|-------|------|----------|
| "Flash sale": £1 deliveries for next 2 hours | Immediate | ~£3/drop subsidy | 2 hours |
| Push notification to inactive senders: "A courier is 2 min away — send something now!" | Immediate | £0 | Real-time |
| Merchant activation call: "It's a quiet day — can you dispatch any pending orders?" | 30 min | £0 | Same day |
| Reduce sender fees by 20% for 24 hours | 1 hour | ~£1/drop | 24 hours |

### 6.3 Structural Interventions

| Intervention | Description | Timeline |
|-------------|-------------|----------|
| Expand operating hours | Add early morning (7–9 AM) and late evening (9–11 PM) | Month 2 |
| Add scheduled deliveries | Senders book future time slots; spreads demand | Month 2 |
| Batch matching | Group nearby drops for single courier route | Month 3 |
| Predictive positioning | ML model positions couriers in high-demand zones before requests | Month 6 |
| Subscription model | Senders pre-commit to X drops/month → predictable demand | Month 4 |

---

## 7. Geographic Expansion Protocol

### 7.1 Expansion Readiness Criteria

Before expanding to an adjacent zone, the **origin zone must achieve:**

| Criterion | Threshold |
|-----------|-----------|
| Request fill rate | ≥ 95% sustained for 4 weeks |
| Time-to-match | < 2 min average for 4 weeks |
| Courier utilisation | 50–65% (not over-supplied) |
| Weekly drop volume | ≥ 200 drops/week |
| Positive unit economics | ≥ £0.50 margin/drop for 4 weeks |
| Waitlist in adjacent zone | ≥ 200 signups |

### 7.2 Expansion Sequence

| Order | Zone | Adjacency | Population Density | Merchant Density | Priority |
|-------|------|-----------|-------------------|-----------------|----------|
| 1 | UCL / Bloomsbury (ORIGIN) | — | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | CURRENT |
| 2 | King's Cross / Islington South | North border | ⭐⭐⭐⭐ | ⭐⭐⭐ | HIGH |
| 3 | Holborn / Covent Garden | South border | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | HIGH |
| 4 | Fitzrovia / Marylebone | West border | ⭐⭐⭐ | ⭐⭐⭐ | MEDIUM |
| 5 | Clerkenwell / Farringdon | East border | ⭐⭐⭐ | ⭐⭐⭐ | MEDIUM |

### 7.3 Expansion Model

Each new zone follows the same playbook:
1. **Waitlist** (4 weeks before): Collect signups from adjacent zone
2. **Seed supply** (2 weeks before): Recruit 15 couriers in new zone
3. **Anchor tenants** (1 week before): Onboard 3–5 merchants
4. **Launch** (Day 1): Open zone to senders; overlap with origin zone (couriers can serve both)
5. **Stabilise** (Weeks 1–4): Monitor liquidity metrics; adjust supply/demand levers

**Key advantage of adjacent expansion:** Courier pools overlap. A courier near the zone boundary can serve both zones, providing instant liquidity in the new zone without requiring a full new supply base.

---

## 8. Liquidity Benchmarks from Comparable Marketplaces

| Company | Stage | Liquidity Metric | Value at Product-Market Fit |
|---------|-------|------------------|-----------------------------|
| Uber | Early London | Time-to-pickup | < 5 min |
| Deliveroo | Early London | Time-to-delivery | < 30 min |
| Instacart | Early SF | Order fill rate | > 90% |
| TaskRabbit | Early SF | Task match rate | > 80% |
| **LocalLogistics** | **Target** | **Time-to-match** | **< 2 min** |
| **LocalLogistics** | **Target** | **Pickup arrival** | **< 8 min** |
| **LocalLogistics** | **Target** | **Fill rate** | **> 95%** |

**Our advantage over Uber/Deliveroo at launch:** We're 100x more geographically concentrated. Uber launched across all of London; we're launching in 3 mi². Our density-to-volume ratio will be dramatically higher from Day 1.
