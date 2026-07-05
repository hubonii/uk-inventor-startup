# Flywheel Strategy: The Local-Logistics Growth Engine

## The Core Flywheel

Every great platform business is powered by a flywheel — a self-reinforcing loop where each revolution makes the next one faster. Our flywheel has six stages:

```
    ┌─────────────────┐
    │  MORE MERCHANTS  │
    │  (Supply of jobs) │
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │   MORE DROPS     │
    │  (Volume)        │
    └────────┬────────┘
             │
             ▼
    ┌─────────────────────┐
    │  MORE COURIER        │
    │  EARNINGS            │
    │  (Attractiveness)    │
    └────────┬────────────┘
             │
             ▼
    ┌─────────────────┐
    │  MORE COURIERS   │
    │  (Supply of labor)│
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │ FASTER DELIVERY  │
    │ (Service quality) │
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │  MORE MERCHANTS  │ ◄── Cycle repeats, each revolution faster
    └─────────────────┘
```

**The virtuous cycle:** More merchants create more delivery jobs → more jobs mean higher total courier earnings → higher earnings attract more couriers → more couriers mean faster delivery assignment → faster delivery improves merchant experience → more merchants join.

---

## Stage-by-Stage Analysis

### Stage 1: More Merchants → More Drops

**Mechanism:** Each new merchant adds 15–40 deliveries/month to the platform. Merchant density in the wedge creates courier utilization — a courier can pick up from Merchant A, deliver, then immediately accept a job from nearby Merchant B.

**Key metric:** Merchant density per square kilometer

| Merchants in Wedge | Deliveries/Day | Courier Utilization |
|-------------------|---------------|-------------------|
| 10 | 5-13 | Low (couriers idle 70% of time) |
| 30 | 15-40 | Moderate (couriers idle 40% of time) |
| 50 | 25-65 | Good (couriers idle 20% of time) |
| 100 | 50-130 | High (couriers can chain deliveries) |
| 200+ | 100-260+ | Excellent (continuous delivery flow) |

**Friction point:** Low merchant density means couriers walk empty between jobs. Below 20 merchants, courier earnings are too low to sustain supply.

**Grease:** Guarantee minimum earnings for early couriers (first 50 couriers get £5 minimum per delivery, subsidized by platform). Cost: ~£2,000/month during seed phase.

---

### Stage 2: More Drops → More Courier Earnings

**Mechanism:** Higher delivery volume means couriers complete more deliveries per hour. A courier doing 2 deliveries/hour earns £7.60 (at £3.80/delivery). A courier doing 3 deliveries/hour (possible with merchant density) earns £11.40.

**Key metric:** Deliveries per courier per hour

```
COURIER EARNINGS MODEL:

Scenario A: Low density (10 merchants)
├── Walk time between jobs: 15 min avg
├── Deliveries per hour: 1.5
├── Hourly earnings: £5.70
└── Below London Living Wage (£13.15) → couriers leave

Scenario B: Medium density (50 merchants)
├── Walk time between jobs: 8 min avg
├── Deliveries per hour: 2.5
├── Hourly earnings: £9.50
└── Approaching Living Wage → couriers stay

Scenario C: High density (100+ merchants)
├── Walk time between jobs: 4 min avg
├── Deliveries per hour: 3.5
├── Hourly earnings: £13.30
└── Exceeds Living Wage → couriers actively recruited by word-of-mouth
```

**Friction point:** At low density, courier earnings are below Living Wage. Couriers rational to leave for Deliveroo/UberEats where demand is higher.

**Grease:** Focus on high-frequency merchants first (pharmacies doing 3-5 deliveries/day, print shops doing 2-4). Even 10 high-frequency merchants create enough volume for reasonable courier earnings.

---

### Stage 3: More Courier Earnings → More Couriers

**Mechanism:** Word-of-mouth among students: "I'm making £12/hour walking packages around Bloomsbury, no interview needed, just deposit £50." University WhatsApp groups and societies spread the word.

**Key metric:** Courier recruitment rate (new couriers per week)

| Average Courier Earnings | Recruitment Channel | New Couriers/Week |
|-------------------------|--------------------|--------------------|
| £5-7/hour | None (below threshold) | 0-1 |
| £8-10/hour | Passive word-of-mouth | 2-4 |
| £11-13/hour | Active word-of-mouth + referrals | 5-10 |
| £14+/hour | Viral growth + social media posts | 10-20+ |

**The £10/hour threshold:** Our research suggests £10/hour is the minimum for sustained courier recruitment among university students. Below this, they prefer bar work, tutoring, or other gig platforms. Above this, walking packages is genuinely attractive.

**Friction point:** The £50 staking requirement deters some potential couriers, especially cash-constrained students.

**Grease:**
1. **Earn-your-stake program:** Allow new couriers to start with a £10 deposit, earn the remaining £40 from their first 10 deliveries (platform holds back £4/delivery until stake is fully funded).
2. **Referral bonus:** Existing courier gets £10 credit when their referral completes 25 deliveries.
3. **University society partnerships:** Partner with entrepreneurship, sports, and social societies — offer "delivery challenges" with prizes.

---

### Stage 4: More Couriers → Faster Delivery

**Mechanism:** More couriers in the wedge means shorter distance between available courier and pickup merchant. Courier assignment time drops exponentially with courier density.

**Key metric:** Average time from dispatch to courier assignment

```
COURIER DENSITY VS. ASSIGNMENT TIME:

Couriers Active in Wedge    Avg Distance to Merchant    Assignment Time
         5                        800m                    12-18 min
        10                        500m                     8-12 min
        20                        300m                     5-8 min
        40                        200m                     3-5 min
        80                        100m                     1-3 min
       160+                        50m                     <1 min

Formula (approximation):
Assignment Time ≈ (Wedge Area / Active Couriers) × Walking Speed Factor

For 2.5 km² wedge at 5 km/h walking speed:
Assignment Time ≈ (2,500,000 m² / N couriers)^0.5 / 83 m/min
```

**Friction point:** During off-peak hours (early morning, late evening), active courier count drops below threshold. Assignment times spike.

**Grease:**
1. **Time-of-day incentives:** Couriers earn 20% bonus during off-peak hours (7-9am, 7-9pm).
2. **Predictive positioning:** Notify couriers of upcoming dispatches before merchants actually click "dispatch" — based on historical patterns.
3. **Merchant scheduling:** Allow merchants to schedule deliveries for high-supply periods rather than dispatching during low-supply periods.

---

### Stage 5: Faster Delivery → More Merchants

**Mechanism:** When merchants experience consistently fast delivery (sub-10-minute assignment, sub-30-minute total), they increase usage, upgrade to premium tiers, and recommend the platform to neighboring merchants.

**Key metric:** Merchant retention rate and same-store delivery growth

| Assignment Time | Merchant Satisfaction | Monthly Retention | Growth Rate (Delivery/Month) |
|----------------|----------------------|-------------------|-------------------------------|
| >15 min | Low (frustrated) | 60% | -10% (decreasing usage) |
| 10-15 min | Moderate | 80% | 0% (stable) |
| 5-10 min | Good | 90% | +10% (increasing usage) |
| <5 min | Excellent | 95%+ | +20% (rapid growth + referrals) |

**Friction point:** A single bad experience (30+ minute assignment) can undo 20 good experiences. Reliability > average speed.

**Grease:**
1. **SLA guarantee:** If assignment takes >15 minutes, delivery fee is refunded to merchant.
2. **Real-time supply visibility:** Dashboard shows merchants how many couriers are available before they dispatch — merchants can time their dispatches for high-supply periods.
3. **Merchant success manager** (first 50 merchants only): Proactive outreach after bad experiences. Manual intervention to prevent churn.

---

## The Anti-Flywheel: Death Spiral to Avoid

The flywheel works in reverse too — and it's faster downward than upward:

```
DEATH SPIRAL:

Merchants leave → Fewer drops → Lower courier earnings →
Couriers leave → Slower delivery → More merchants leave
```

**Critical mass threshold:** If we drop below 20 merchants AND 30 active couriers simultaneously, the death spiral activates. Below this threshold, the platform is worse than alternatives on every dimension.

**Prevention strategy:**
- Never expand to a new wedge until the current wedge is above critical mass
- Maintain a "merchant floor" — subsidize delivery fees before letting the last 20 merchants churn
- Track the flywheel health score (see below) weekly and intervene immediately if declining

---

## Flywheel Velocity Targets

### Quarterly Targets (Month 1-18)

| Quarter | Merchants | Active Couriers | Monthly Deliveries | Courier Earnings/hr | Assignment Time | Flywheel Status |
|---------|-----------|----------------|-------------------|--------------------|-----------------|-----------------| 
| **Q1** (M1-3) | 10→30 | 15→50 | 150→1,000 | £5→8 | 20→12 min | **Pushing** (manual effort) |
| **Q2** (M4-6) | 30→60 | 50→100 | 1,000→3,000 | £8→10 | 12→8 min | **Rolling** (early momentum) |
| **Q3** (M7-9) | 60→100 | 100→200 | 3,000→6,000 | £10→12 | 8→5 min | **Accelerating** (self-sustaining) |
| **Q4** (M10-12) | 100→150 | 200→350 | 6,000→10,000 | £12→14 | 5→3 min | **Spinning** (growth exceeds capacity to onboard) |
| **Q5** (M13-15) | 150→200 | 350→500 | 10,000→15,000 | £14→15 | 3→2 min | **Humming** (stable velocity) |
| **Q6** (M16-18) | 200+ (expand to 2nd wedge) | 500+ | 15,000+ | £15+ | <2 min | **Replicating** (copy to new wedge) |

### Flywheel Health Score

Track weekly, score 1-10:

```
FLYWHEEL HEALTH SCORE = Average of:

1. Merchant Growth Rate   (target: +10%/month = 10, 0% = 5, negative = 1)
2. Courier Growth Rate    (target: +15%/month = 10, 0% = 5, negative = 1)
3. Courier Utilization    (target: >80% = 10, 50% = 5, <30% = 1)
4. Assignment Time        (target: <5 min = 10, 10 min = 5, >15 min = 1)
5. Merchant Retention     (target: >95% = 10, 85% = 5, <75% = 1)
6. Courier Retention      (target: >80% = 10, 60% = 5, <40% = 1)
7. Delivery Success Rate  (target: >98% = 10, 95% = 5, <90% = 1)

SCORE INTERPRETATION:
8-10: Flywheel is humming — maintain and prepare to scale
6-7:  Flywheel is rolling — keep pushing, monitor friction points
4-5:  Flywheel is stuck — identify and address specific friction
1-3:  Flywheel is dying — emergency intervention required
```

---

## Friction Points & Greasing Strategies

### Summary Table

| Flywheel Stage | Friction Point | Severity | Greasing Strategy | Cost | When to Deploy |
|---------------|---------------|----------|------------------|------|----------------|
| Merchants → Drops | Low merchant density | Critical | Target high-frequency merchants first | £0 | Day 1 |
| Drops → Earnings | Low utilization between jobs | High | Guarantee minimum earnings (£5/delivery) | £2K/mo | Month 1-3 |
| Earnings → Couriers | £50 stake barrier | Medium | Earn-your-stake program | £1K/mo | Month 1-6 |
| Earnings → Couriers | Below Living Wage earnings | High | Focus on density before coverage | £0 | Month 1-6 |
| Couriers → Speed | Off-peak courier shortages | Medium | Time-of-day bonuses (20%) | £500/mo | Month 3-6 |
| Speed → Merchants | Inconsistent assignment times | High | SLA guarantee + refund policy | £300/mo | Month 2+ |
| Speed → Merchants | Single bad experience churn | Critical | Proactive merchant outreach | £0 | Always |

### Total Greasing Budget

| Period | Monthly Budget | Primary Friction | Approach |
|--------|---------------|-----------------|----------|
| Month 1-3 | £3,000/mo | Cold start (both sides) | Subsidize courier earnings + manual merchant outreach |
| Month 4-6 | £2,000/mo | Courier supply | Referral bonuses + society partnerships |
| Month 7-9 | £1,000/mo | Off-peak coverage | Time-of-day incentives |
| Month 10-12 | £500/mo | Maintenance only | System is self-sustaining |
| Month 13+ | £0/mo | None | Flywheel spins on its own |

**Total flywheel investment: ~£20,000** to reach self-sustaining velocity. Compare to Uber's $3.8B in pre-profitability subsidies.

---

## Flywheel Metrics Dashboard

### Real-Time Tracking (Build into Operations Dashboard)

```
┌─────────────────────────────────────────────────────────────┐
│                    FLYWHEEL DASHBOARD                        │
│                                                             │
│  ┌────────────┐  ┌────────────┐  ┌────────────┐            │
│  │ MERCHANTS  │  │  COURIERS  │  │   DROPS    │            │
│  │    47      │  │    82      │  │  1,247/mo  │            │
│  │  +12% ▲   │  │  +18% ▲   │  │  +22% ▲    │            │
│  └────────────┘  └────────────┘  └────────────┘            │
│                                                             │
│  ┌────────────┐  ┌────────────┐  ┌────────────┐            │
│  │ EARNINGS   │  │ ASSIGN TIME│  │ RETENTION  │            │
│  │ £11.20/hr  │  │  6.3 min   │  │   92%      │            │
│  │  +8% ▲    │  │  -15% ▼   │  │  +3% ▲     │            │
│  └────────────┘  └────────────┘  └────────────┘            │
│                                                             │
│  FLYWHEEL HEALTH SCORE: ███████░░░ 7.2/10 — Rolling        │
│                                                             │
│  ⚠ Friction Alert: Off-peak assignment time >15 min        │
│    Recommended: Activate time-of-day bonus for 7-9am       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Second Flywheel: The Data Flywheel

Running in parallel with the marketplace flywheel, our data flywheel creates a compounding intelligence advantage:

```
More Deliveries → More Data → Better Matching Algorithm →
Faster Assignment → Higher Courier Earnings → More Couriers →
More Deliveries → Even More Data → Even Better Matching...
```

### Data Flywheel Milestones

| Deliveries | Data Milestone | Algorithm Capability |
|-----------|---------------|---------------------|
| 1,000 | Basic patterns | "Merchant X is busiest 12-2pm" |
| 5,000 | Route intelligence | "Route A is 3 min faster than Route B at 5pm" |
| 20,000 | Predictive dispatch | "Merchant X will likely dispatch in 15 min — pre-position courier" |
| 50,000 | Dynamic pricing insights | "Courier demand exceeds supply at 1pm — suggest merchants schedule for 3pm" |
| 100,000 | Full optimization | Automated courier positioning, predictive demand, dynamic routing |

---

## Third Flywheel: The Trust Flywheel

A separate flywheel operates on the trust dimension:

```
Successful Deliveries → Higher Courier Reputation →
Access to Higher-Value Jobs → Higher Earnings →
More Committed Couriers → Even More Successful Deliveries →
Even Higher Reputation → Platform-Wide Trust Increases →
More Merchants Trust Platform → More High-Value Jobs Available...
```

This flywheel creates a **rising floor of platform quality** — the average courier reputation score increases over time as low-quality couriers are slashed out and high-quality couriers accumulate reputation.

---

## Flywheel Replication Protocol

When the first wedge achieves "Humming" status (Health Score >8 for 4 consecutive weeks), we replicate:

```
WEDGE REPLICATION CHECKLIST:

□ Source wedge Health Score >8 for 4+ weeks
□ New wedge selected (next university zone)
□ 5 "seed merchants" identified in new wedge
□ 10 "seed couriers" recruited from new wedge
□ Referral pipeline: existing couriers invited to recruit in new wedge
□ Same greasing playbook deployed (earn-your-stake, minimum earnings)
□ Independent Health Score tracking for new wedge
□ No resources diverted from source wedge during new wedge setup

TARGET: New wedge reaches "Rolling" (Score 6+) within 8 weeks
        using playbook refined from first wedge
```

### Replication Velocity

| Wedge # | Time to Rolling | Time to Humming | Cumulative Wedges |
|---------|----------------|----------------|-------------------|
| 1 (UCL/Bloomsbury) | 6 months | 12 months | 1 |
| 2 (King's/Strand) | 4 months | 8 months | 2 |
| 3 (Imperial/Kensington) | 3 months | 6 months | 3 |
| 4-5 (LSE/City, SOAS/Euston) | 2 months each | 5 months each | 5 |
| 6-10 (Non-London universities) | 3 months each | 8 months each | 10 |

**Learning curve:** Each new wedge launches faster because the playbook is refined, the brand has recognition, and existing couriers can seed new wedges through personal networks.

---

*Flywheel concept: Jim Collins, Good to Great (2001); Amazon flywheel (Jeff Bezos, 2001)*
*Last updated: July 2026*
